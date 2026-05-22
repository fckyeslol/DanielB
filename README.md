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
- Jerarquía de fuentes (McKinsey, BCG, Anthropic, Goldman Sachs, Gallup, TechCrunch/Bloomberg/WSJ/FT)
- Checklist de autoauditoría

### Paso 2: Elegir la estructura del ensayo

Antes de escribir, abrir `estructura-ensayo.md` y seguir los 6 pasos:

1. **Elegir el arquetipo** — tabú desmontado, regla polémica, vulnerabilidad, contraintuición o framework nuevo
2. **Construir el título y subtítulo** con la fórmula correspondiente
3. **Armar el esqueleto** según la estructura del arquetipo elegido
4. **Aplicar las reglas de apertura** — la primera oración crea tensión sin explicar todavía
5. **Aplicar las reglas de cierre** — nunca moraleja, nunca resumen
6. **Correr el checklist** antes de pasarle el insumo a la IA

### Paso 3: Preparar el insumo

Cada ensayo parte de uno de tres tipos de insumo:

| Tipo | Descripción | Prompt a usar |
|---|---|---|
| Transcripción | Audio de podcast/entrevista transcrito | `prompts/essay-from-podcast.md` |
| Artículo fuente | Artículo o reporte que dispara la reflexión | `prompts/essay-from-article.md` |
| Tema original | Solo un tema — la IA investiga y escribe | `prompts/essay-original.md` |

### Paso 4: Generar el ensayo

1. Cargar `daniel-bilbao.md` + `estructura-ensayo.md` en Claude
2. Pedir deep research sobre el tema (la IA busca fuentes verificables)
3. Revisar el research y aprobar/ajustar el enfoque
4. Generar el ensayo completo con piés de página y enlaces
5. Exportar como `.docx` con footnotes nativas

### Paso 5: Revisar y publicar

1. Revisar el `.docx` generado — corregir lo que haga falta
2. Subir a Substack como borrador
3. Publicar

## Estructura del repo

```
DanielB/
├── README.md                        # Este archivo
├── daniel-bilbao.md                 # Master prompt — voz, estilo, prohibiciones
├── estructura-ensayo.md             # Arquetipos, esqueletos y checklist de estructura
├── estructura-ganadora.md           # Análisis de los 5 posts más virales de Daniel
├── referencias-top-newsletters.md   # Técnicas robadas a Lenny, Noah Smith, The Generalist, Rachel Karten, AI CFO
├── master-prompt-template.md        # Template base reutilizable para otros autores
└── prompts/
    ├── essay-from-podcast.md        # Convertir transcripción en ensayo
    ├── essay-from-article.md        # Convertir artículo fuente en ensayo original
    └── essay-original.md            # Escribir ensayo desde un tema
```

## Archivos clave

**`daniel-bilbao.md`** — La voz. Todas las reglas de estilo, vocabulario, prohibiciones y autoauditoría. Se carga en cada sesión.

**`estructura-ensayo.md`** — La estructura. Los 5 arquetipos de post ganador, los esqueletos por arquetipo, y el checklist de 8 puntos antes de generar.

**`estructura-ganadora.md`** — El análisis. Qué hicieron los 5 posts más virales de Daniel y por qué funcionaron.

**`referencias-top-newsletters.md`** — Las referencias. Técnicas de los 5 newsletters más grandes de Substack adaptadas al contexto de Daniel.

**`prompts/`** — Los tres modos de generación según el insumo disponible.

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
