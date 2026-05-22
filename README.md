# Newsletter AI Writer

An open-source toolkit for writing long-form newsletter essays with AI. Clone it, configure your voice, and generate essays that sound like you — not like a robot.

## Quickstart

1. **Clone** the repo
2. **Copy** `master-prompt-template.md` and fill in the `{{PLACEHOLDERS}}` with your voice, bio, and style (see `examples/` for reference)
3. **Use** your filled-in prompt with Claude, GPT, or any LLM. Combine it with a prompt template from `prompts/` depending on your source material.

## Structure

```
master-prompt-template.md        # The core template — fill this in
examples/
  growth-rockstar.md             # Dylan Rosemberg's growth newsletter (Argentine, tactical)
prompts/
  essay-from-podcast.md          # Turn a podcast transcript into an essay
  essay-from-article.md          # Turn a source article into an original essay
  essay-original.md              # Write an original essay from a topic
```

## What's in the template

The master prompt template covers:

- **Identity & purpose** — who you are, what you write about
- **10 customizable voice traits** — tone, slang, paragraph style, metaphor world, data style, honesty style, closing style, humor, POV, reader relationship
- **Universal LLM prohibitions** — battle-tested rules that prevent AI-generated text from sounding like AI (binary structures, pseudo-intellectualism, filler phrases, academic hedging, and more)
- **Essay structure** — opening hooks, development rules, closing philosophy
- **Research & factuality** — source validation rules to prevent hallucination
- **Source hierarchy** — tiered sources for your domain
- **Self-audit process** — a checklist to run before publishing
- **Final checklist** — the definitive quality gate

## The LLM prohibitions are the secret sauce

The universal prohibitions section works for any writer in any language. It catches the patterns that make AI text immediately recognizable:

- Binary contrast structures ("That's not X. It's Y.")
- Pseudo-intellectualism disguised as honesty ("cognitive recalibration", "performative humility")
- Academic hedging ("My hypothesis is that...")
- Artificially chopped dramatic sentences
- The "What [doesn't] X is Y" formula
- LLM filler phrases ("it's worth noting", "in this context")

These rules were developed across dozens of essays and refined through real editing. They work.

## Example

A complete, working configuration is included:

| Newsletter | Author | Language | Style |
|---|---|---|---|
| [Growth Rockstar](https://blog.growthrockstar.com/) | Dylan Rosemberg | Argentine Spanish (voseo) | Tactical, framework-driven, scannable |

Use it as a reference for how to fill in the template with your own voice.

## License

MIT
