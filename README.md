# ViralScript AI

An AIOS skill runtime that turns technical articles, GitHub repositories, and raw
markdown into five-post educational social threads for X or LinkedIn, in English or
Albanian.

The generator runs inside your agent through the skills in this repo. The static site
is a landing page and an output-contract preview — it does not call an AI backend.

## Structure

```
public/          # Netlify publish root
  index.html     # Landing page
  skills/        # Skill definitions (markdown)
  config/        # Loader configuration (JSON)
  memory/        # Persistent context (JSON)
  README.md      # Runtime directory docs, mirrored from ~/.viralscript-ai/

netlify.toml     # Static publish config and security headers
```

## Skills

| Skill | What it does |
|---|---|
| `social_thread_writer` | Ingest → extract → draft 5 posts → verify against platform caps |
| `humanizer` | Rewrites AI-sounding prose. 26 patterns from Wikipedia's *Signs of AI writing* |
| `skill_builder` | The format and registration steps for authoring a new skill |

## Install locally

```bash
git clone https://github.com/arlinda-k14/viralscript-ai.git
cp -R viralscript-ai/public/{skills,config,memory} ~/.viralscript-ai/
```

`~/.viralscript-ai/README.md` documents the runtime directory on its own.

## Preview the site

```bash
open public/index.html
```

## Deploy

Drag the repository folder onto https://app.netlify.com/drop, or connect the GitHub
repo in Netlify for automatic deploys on every push to `main`. A Git-connected deploy
is what activates the headers in `netlify.toml`.

## Thread contract

Five posts, in order: Hook, Discovery, Mechanism, Application, Action. Caps are 280
characters per post on X and 800 on LinkedIn. Exactly two hashtags, at the end of Post 5.

Accuracy rules, enforced before output:

- Every metric must appear in the source. Nothing inferred or recalled.
- No guaranteed career outcomes and no fixed learning timelines.
- Posts 1 through 4 carry no promotion. Training tie-in lives in Post 5 only.
- If extraction fails or is blocked, the run stops and asks for raw text.
- Protocols and algorithms keep their exact names, with a plain-language gloss.

## License

`public/skills/humanizer.md` is MIT licensed, by [@blader](https://github.com/blader/humanizer).
Everything else in this repository is yours.
