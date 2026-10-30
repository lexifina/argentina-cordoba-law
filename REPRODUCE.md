# How this repository was made (Córdoba)

This file is written by the build on 2026-10-30, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Legislatura de la Provincia de Córdoba (legislaturacba.gob.ar) | <https://legislaturacba.gob.ar/> | 2026-10-30 | Official legal texts of the province, published by its government for public consultation. Argentina's copyright law (Ley 11.723) has no express exclusion for them; laws are public acts of government, binding on everyone once officially published (Código Civil y Comercial, art. 5). The source states no restriction on reuse. Reproduced with attribution, following the official text. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `constitucion` | Constitución de la Provincia de Córdoba | 1 | 2001-12-10 to 2001-12-10 |

The build made 1 commits:

| Commits | Kind |
| ---: | --- |
| 1 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `futuro`: laws not yet in force on 2026-10-30.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 2 tags.

## Dates

Each commit is dated at noon (America/Argentina/Cordoba) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Código Civil y Comercial de la Nación, art. 5: "Las leyes rigen después del octavo día de su publicación oficial, o desde el día que ellas determinen", counted under art. 6 (the day of publication is excluded), so a law without its own vigencia clause is in force from the ninth day after its publication in the provincial Boletín Oficial (before 1 August 2015, Código Civil art. 2 as replaced by Ley 16.504, to the same effect). A law's own vigencia clause overrides the rule. https://servicios.infoleg.gob.ar/infolegInternet/anexos/235000-239999/235975/texact.htm

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `2eacef68dd0efed14aa1d11a9ea2c9f6a443d0b44029ea95eb08593e61e3aacf` (144971 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a97ff7ea62c3c7595c5668a297d533da0b74373c`, `check.py` `3e59cb6f05eccb94a9ec14431a7f6781221e83ef`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

1 versions of 1 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- The constitution is the text the legislature publishes (the 2001 reform, with its transitional clauses), shown as enacted and dated the day its own cláusula transitoria decimonovena puts the reform in force, 10 December 2001 (articles 78, 79, 80, 82, 86, 87, 90 and the transitional clauses ruled from publication on 14 September 2001; the record dates the whole text on 10 December 2001). The 1987 text is not published by the source and is not shown.
- Units: the heading (encabezado: title, date line, B.O. line, Preámbulo and the headings before Artículo 1) and one file per article, holding the article and everything printed after it up to the next article (section headings and, after the last article, the Disposición complementaria, the Disposiciones transitorias and the closing formula). Nothing is dropped. One paragraph per line, spacing normalised.
- Only the page's article element (title and text) is read; the site navigation and footer are not part of the law and are left out.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- A model (Claude) wrote the fetch and parse code and chose which norms to include; it wrote no law text. Every word of law comes from the provincial source's own texts.
