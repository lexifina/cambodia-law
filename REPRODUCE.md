# How this repository was made (Cambodia)

This file is written by the build on 2026-10-30, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| United Nations Treaty Collection (multilateral treaties deposited with the Secretary-General) | <https://treaties.un.org/> | 2026-10-30 | Facts only (treaty names, kinds of action, dates). |
| Wikidata | <https://www.wikidata.org/> | 2026-10-30 | CC0 1.0 |
| Senate Secretariat General compilation, hosted by the Ministry of Foreign Affairs (mfaic.gov.kh) | <https://www.mfaic.gov.kh/files/uploads/2Z87AYOO63VI/Constitution%20of%20the%20Kingdom%20of%20Cambodia.pdf> | 2026-10-30 | Not protected by copyright: Law on Copyright and Related Rights (2003), Article 10(a) and (d) exclude the Constitution and translations of it. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `constitution` | Constitution of the Kingdom of Cambodia (as amended to February 2008), English translation | 1 | 2008-02-19 to 2008-02-19 |
| `treaties` | Treaty actions of Cambodia (UN Treaty Collection): signature, ratification, accession | 50 | 1950-05-17 to 2026-02-06 |
| `legal-system` | Legal system of Cambodia: open facts from Wikidata | 1 | 2026-10-28 to 2026-10-28 |

The build made 52 commits:

| Commits | Kind |
| ---: | --- |
| 3 | first version of an act |
| 49 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-30.
- 6 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 50 laws in the record.
- 101 tags.

## Dates

Each commit is dated at noon (Asia/Phnom_Penh) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: No single commencement rule is applied: each version is dated by the event date its source records (treaty action date, last-modified day of a Wikidata item, or the compilation date of the Senate edition). https://treaties.un.org/

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `20a3b95a0201812080d862f30a387c23e0efaf4225a4ad948c2175bf049fed41` (149266 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a4faa25af85facb64b956b372f6b528aafdd7ec1`, `check.py` `3e59cb6f05eccb94a9ec14431a7f6781221e83ef`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

Not yet run for this build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Treaty actions are dated by the action date shown in the UN Treaty Collection; each date is one version credited to a law key untc-<date>.
- Signature, ratification, accession (a), succession (d), acceptance (A), approval (AA) and formal confirmation (c) are copied as the Treaty Collection records them, under the participant name it uses.
- The legal-system act is a single snapshot of Wikidata facts dated by the item own last-modified day, as the oldest version available.
- Constitution: the English text of the Senate Secretariat General compilation, as archived on 2021-11-02, is one oldest-version-available snapshot dated 2008-02-19; the source gives no per-article amendment history.
- Paragraphs: the PDF's hard line wraps were joined into one paragraph per line (a line of 90 or more characters continues on the next line); hyphenated line ends were joined without a space.
- The Khmer original is authentic and is not in this repository; the English text is the Senate's own non-official translation.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- none
