# Data card

Version: 2026-11-17.1. Curator: California Licensing Education. Language: English. Currency: USD. Coverage year: 2026 only. No student-level or case-level data.

## Method

This export preserves reviewed, manually sourced school reference data. Source PDF hashes, physical page numbers, county scope, printed edition dates and derivation references accompany the rows. It is not an automated statewide scrape. Forty rows are copied without numeric changes from the accepted school data; eight Santa Barbara rows come from a separately reviewed, undeployed candidate. Checks establish exact input hashes, uniqueness, component-sum equality, CSV/JSON agreement and that the original 40 rows remain unchanged. A passing arithmetic check does not establish a real case's amount.

The court-school fee table is exported separately from the maintained public court-fee guide. It includes 25 dated observations and five unknown amounts. Only the three specified November 17 primary-page checks and the retained November 16 Santa Barbara manual check update their corroboration dates. A checked date is not an effective date. The other observations remain historical, with their original dates and source links.

## Ticket-reference fields

| Field | Meaning |
| --- | --- |
| `id` | Stable combination of year, county, code/subsection and speed band |
| `year`, `county`, `code`, `speedBand` | Exact scope; null band means not applicable |
| `scenario` | `ordinary-first-offense`; additional assumptions are in the companion JSON |
| `baseFineCents`, `scheduledTotalCents` | Integer cents; scheduled/reference total, never actual case balance |
| `componentsCents` | Named component map in JSON; flattened `*Cents` columns in CSV |
| `schoolPublicationStatus` | `live` or `reviewed_pending_school_release`; this is independent of dataset publication |
| `schoolSourceCommit`, `pendingPullRequest` | School source provenance; pending PR is null for already-live rows |
| `sourceId`, `sourceUrl`, `sourceSha256` | Main source and hash of the bytes that were reviewed |
| `pdfPage`, `scopePages` | One-based PDF page containing the row and pages qualifying its scope |
| `referenceKind` | Printed schedule reference or calculation using local rules |
| `calculation` | JSON formula and all source/page references; split into formula and JSON-encoded source-reference cells in CSV |
| `reviewedAt` | Recorded review date of the main source, not a guarantee of current applicability |

## Court-fee fields

`courtTrafficSchoolFeeCents` is the separately stated court administrative/processing fee. Null/blank is unknown, never zero. `feeStatus` distinguishes a stated amount from absence of an amount in the reviewed material. `sourceCheckedAt` and `originalTableCheckedAt` separate later corroboration from the original observation. `sourceUrl` can be null where no numerical source was retained; the CLE county guide remains available. These fields are not ticket schedule components and must not be joined as a promise of eligibility or an automatic all-in price.

## Source and legal limits

Some court-posted files use older edition dates or abbreviated rounded columns. The catalog preserves those dates and limitations, including contradictory historical material retained for transparency. A source URL can later serve different bytes; compare its hash and edition before updating. Unknown exact adoption/effective dates are left null. A 2027 proposal is not used for amounts.

No fixed base-fine-to-total multiplier is exported because local assessment units, round-up rules, fixed fees and exceptions differ. No claim is made to own or relicense official source documents. The separate legal-reference link to Vehicle Code §11219.5 could not be freshly read from its official endpoint because it returned HTTP403; this package therefore does not publish an asserted current statutory summary or numerical fee rule based on that request.

## Intended and unsuitable uses

Suitable: inspecting sourced examples, reproducing the listed arithmetic, evaluating coverage gaps, and building educational interfaces that preserve all scope and release-status notices.

Unsuitable: setting a driver's case balance, deciding guilt or eligibility, paying a citation, applying 2026 values to 2027, summing multiple charges without the court's rules, inferring statewide completeness, or representing pending rows as deployed school behavior. The actual court notice and current official instructions control the case.

There are no train/test labels or predictive targets. Hugging Face's `train` split is a file-loader convention only. The complete and live/pending subsets intentionally overlap; they must not be concatenated. All 58 names in county coverage are a coverage inventory, not 58 supported fee schedules.

## Maintenance and correction

Submit a correction with exact county, row identifier, official source, edition and page. An update should distinguish new court facts, curation corrections, and a website deployment-status change. No search ranking, indexing speed, citation frequency or ongoing update cadence is promised.
