# iads-comms-skills

A collection of [Claude skills](https://docs.claude.com) built for IADS communications work. Each skill lives in its own folder with its own README and `SKILL.md` file, so any one of them can be dropped into a Claude skills directory or uploaded to a Claude workspace on its own.

## Skills

| Skill | What it does |
|---|---|
| [newsletter-title-generator](./newsletter-title-generator) | Generates the short, one-line titles that sit beside each news item in the IADS newsletter. |

More skills will be added here as they're built.

## Using a skill

Each skill folder is self-contained:

- Its `README.md` explains what the skill does, how to use it, and any editorial rules it follows.
- Its `*-SKILL.md` file is the actual skill definition Claude reads — upload that file (or the whole folder) to a Claude workspace, or drop the folder into your local skills directory.

## Repo structure

```
iads-comms-skills/
  README.md                          (this file)
  newsletter-title-generator/
    README.md
    IADS_Newsletter_Title_Generator-SKILL.md
```
