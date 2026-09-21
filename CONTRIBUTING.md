# Contributing

This repo is a living syllabus. Official NVIDIA URLs and version pins change often. Useful PRs:

- Fix broken links
- Add a new official course or cookbook recipe
- Note Isaac Sim / Isaac Lab version pairing that you actually used
- Add a short "what broke / what fixed it" note from a real install
- Translate a phase doc (keep the English file; add `docs/i18n/<lang>/`)

## How to contribute

1. Fork the repo
2. Create a branch: `git checkout -b fix/isaac-lab-docs-url`
3. Keep tone factual. Do not paste copyrighted course text
4. Open a pull request with the source URL in the description

## Style

- Prefer official links over blogs
- Date-sensitive claims should say "as of 2026" or point at a version
- No hype, no affiliate links, no "guaranteed job" language
- NVIDIA trademarks stay as product names, not as if this repo is official

## What we will not merge

- Closed-weight model dumps
- Secrets, NGC keys, Hugging Face tokens
- Unrelated promotional READMEs
- Jailbreak / weaponized robotics content
