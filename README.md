# Daniel Bilbao — Substack Ghostwriting con IA

Sistema de ghostwriting asistido por IA para [danielbilbao.substack.com](https://danielbilbao.substack.com), el Substack de Daniel Bilbao.

## Cómo funciona

### Paso 1: Configurar el master prompt

El archivo `daniel-bilbao.md` contiene todas las reglas de voz, estilo, prohibiciones y estructura que la IA debe seguir. Se carga al inicio de cada sesión de Claude (o cualquier LLM).

Incluye:

- Voz en primera persona como Daniel Bilbao
- Tono conversacional + honesto, con colombianismos y voseo como condimento
- Prohibiciones absolutas (estructuras binarias, em dashes, frases LLM, descriptores vacíos, datos inventados)
- Reglas de formato (números, monedas, listas)
- Estructura de ensayo (apertura, desarrollo, cierre)
- Jerarquía de fuentes (McKinsey, BCG, Anthropic, Goldman Sachs, Gallup, TechCrunch/Bloomberg/WSJ/FT)
- Checklist de autoauditoría

### Paso 2: Preparar el insumo

Cada ensayo parte de uno de tres tipos de insumo:

| Tipo | Descripción | Ejemplo |
|---|---|---|
| Transcripción | Audio de podcast/entrevista transcrito | Conversación de Daniel en un evento |
| Artículo fuente | Artículo o reporte que dispara la reflexión | Reporte de McKinsey, nota de Bloomberg |
| Tema original | Solo un tema — la IA investiga y escribe | "El impacto de IA en el emprendimiento latino" |

### Paso 3: Generar el ensayo

1. Cargar el master prompt en Claude
2. Pedir deep research sobre el tema (la IA busca fuentes verificables)
3. Revisar el research y aprobar/ajustar el enfoque
4. Generar el ensayo completo con piés de página y enlaces
5. Exportar como `.docx` con footnotes nativas

### Paso 4: Revisar y publicar

1. Revisar el `.docx` generado — corregir lo que haga falta
2. Subir a Substack como borrador
3. Publicar

## Estructura del repo

```
DanielB/
├── README.md                        # Este archivo
├── daniel-bilbao.md                 # Master prompt — reglas de voz, estilo y estructura
├── master-prompt-template.md        # Template base reutilizable para otros autores
├── examples/
│   └── growth-rockstar.md           # Ejemplo de configuración para referencia
└── prompts/
    ├── essay-from-podcast.md        # Convertir transcripción en ensayo
    ├── essay-from-article.md        # Convertir artículo fuente en ensayo original
    └── essay-original.md            # Escribir ensayo desde un tema
```

## Archivos

**`daniel-bilbao.md`** — El cerebro del sistema. Todas las instrucciones que la IA necesita para escribir como Daniel. Se actualiza cada vez que se detecta un patrón LLM nuevo que prohibir.

**`prompts/`** — Los tres modos de generación según el insumo disponible.

**`examples/growth-rockstar.md`** — Configuración de referencia de otro newsletter (Dylan Rosemberg) para entender cómo llenar el template base.

## Reglas clave del master prompt

- Escritura en primera persona como Daniel Bilbao (nunca tercera persona)
- Prohibido: estructuras binarias ("No es X, es Y"), em dashes, frases cliché de LLM, descriptores vacíos, datos inventados
- Monedas: US$X para dólares, $X COP para pesos colombianos
- Números: 0-9 en letras, 10+ en cifras, porcentajes siempre como número + %
- Fuentes: Solo fuentes verificables. Nunca CEPAL ni OECD
- La prueba del tinto: si no suena como algo que Daniel diría tomándose un café con un founder, se reescribe

## Herramientas

- **Claude (Anthropic)** — Generación de ensayos y research
- **Node.js + docx** — Generación de `.docx` con footnotes nativas
- **Claude in Chrome** — Upload directo a Substack como borrador
