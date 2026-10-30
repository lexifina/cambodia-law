# Cambodia: law history in git

The law of Cambodia as a git history: one file per provision, one commit per law on the day it took effect, and the law that made each change as the commit's author. `git blame` names the law behind every paragraph; `git log` lists every change; picking a date gives the text in force that day.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law).

**What is in it now (a first build, not complete)**

| Folder | Act | Versions | History |
| --- | --- | ---: | --- |
| `constitution/` | Constitution of the Kingdom of Cambodia, as amended to February 2008 (English translation compiled by the Senate) | 1 | One snapshot, dated 19 February 2008 (oldest version available); no amendment history |
| `treaties/` | Treaty actions of Cambodia (UN Treaty Collection): signature, ratification, accession | 50 | Each date on which Cambodia signed, ratified or acceded to a UN-deposited treaty, from 1961 to 2019 |
| `legal-system/` | Legal system of Cambodia: open facts from Wikidata | 1 | A snapshot of Wikidata taken on 30 October 2026 |

**Language.** English. The English text is the Senate Secretariat General's own translation; per its foreword, only the Khmer text is authentic and the English has no official character. The Khmer original is not in this repository.

It has a text layer; there is no OCR. Treaties: United Nations Treaty Collection (treaties.un.org), status-of-treaty pages, read on 30 October 2026. Only facts are copied (treaty names, kinds of action, dates); no descriptive text. Wikidata (CC0) for the legal-system facts.

## Dates

- The Constitution is one version, dated 19 February 2008: the Senate's foreword says the last amendment was promulgated in February 2008, and the publisher's file name carries that date. The compilation has no per-article history, so there is one commit credited to the publisher as the oldest version available.
- The treaties act has one version per action date, dated by the Treaty Collection's date.
- The legal-system act is a single snapshot dated by the Wikidata item's own last-modified day.

## How it is checked

Every version is read back from git on the day it took effect and on the day before (`tools/check_repo.py`) and must match `corpus.json`; results are in `REPRODUCE.md`.

## What "author" means

The author of a commit is the law that made the change, with an e-mail address that cannot exist (`<law key>@lexifina-first-build.invalid`). The author of the Constitution commit is the publisher (oldest version available). For treaty actions the 'law' is the day's batch of actions in the UN Treaty Collection (key `untc-<date>`). The committer is always Lexifina.

## Limits

Only the Constitution is law text; amendments after February 2008, if any, are not reflected. Treaties not deposited with the UN Secretary-General are not included. Next steps: Cambodian statutes (the Law on Copyright of 2003 is a candidate, and its Article 10 also exempts laws from copyright) from official copies reachable without a challenge.
