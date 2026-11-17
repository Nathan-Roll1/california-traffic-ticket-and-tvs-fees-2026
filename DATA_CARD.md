# Data card

Version: 2026-11-17.3. Curator: California Licensing Education. Language: English. Currency: USD. Coverage year: 2026 only. No student-level or case-level data.

## Method

This export preserves reviewed, manually sourced school reference data. Source PDF hashes, physical page numbers, county scope, printed edition dates and derivation references accompany the rows. It is not an automated statewide scrape. The original 48 records remain exactly as published in version 2026-11-17.2 and match the verified school website release. One additional reviewed Santa Barbara VC 22450(a) reference is live after the separately verified PR #210 school release. Its explicit row review date is November 17, 2026; the source-document review dates remain November 16. Checks establish exact live input hashes, uniqueness, component-sum equality, CSV/JSON agreement and preservation of every original record, including its release lineage. A passing arithmetic check does not establish a real case's amount.

The court-school fee table is exported separately from the maintained public court-fee guide. It includes 25 dated observations and five unknown amounts. Only the three specified November 17 primary-page checks and the retained November 16 Santa Barbara manual check update their corroboration dates. A checked date is not an effective date. The other observations remain historical, with their original dates and source links.

## Ticket-reference fields

| Field | Meaning |
| --- | --- |
| `id` | Stable combination of year, county, code/subsection and speed band |
| `year`, `county`, `code`, `speedBand` | Exact scope; null band means not applicable |
| `scenario` | `ordinary-first-offense`; additional assumptions are in the companion JSON |
| `baseFineCents`, `scheduledTotalCents` | Integer cents; scheduled/reference total, never actual case balance |
| `componentsCents` | Named component map in JSON; flattened `*Cents` columns in CSV |
| `schoolPublicationStatus` | `live` for all 49 current rows; dataset publication and school deployment remain distinct |
| `schoolSourceCommit`, `pendingPullRequest` | Per-row school release lineage: the original 48 records retain PR #209 and the new stop-sign row records PR #210. Pending PR is null for all current rows. Aggregate metadata identifies the latest website release |
| `sourceId`, `sourceUrl`, `sourceSha256` | Main source and hash of the bytes that were reviewed |
| `pdfPage`, `scopePages` | One-based PDF page containing the row and pages qualifying its scope |
| `referenceKind` | Printed schedule reference or calculation using local rules |
| `calculation` | JSON formula and all source/page references; split into formula and JSON-encoded source-reference cells in CSV |
| `reviewedAt` | Explicit row review date when supplied, otherwise the previously exported source review date. Document dates remain separate in the source catalog |

## Court-fee fields

`courtTrafficSchoolFeeCents` is the separately stated court administrative/processing fee. Null/blank is unknown, never zero. `feeStatus` distinguishes a stated amount from absence of an amount in the reviewed material. `sourceCheckedAt` and `originalTableCheckedAt` separate later corroboration from the original observation. `sourceUrl` can be null where no numerical source was retained; the CLE county guide remains available. These fields are not ticket schedule components and must not be joined as a promise of eligibility or an automatic all-in price.

## Source and legal limits

Some court-posted files use older edition dates or abbreviated rounded columns. The catalog preserves those dates and limitations, including contradictory historical material retained for transparency. A source URL can later serve different bytes; compare its hash and edition before updating. Unknown exact adoption/effective dates are left null. A 2027 proposal is not used for amounts.

No fixed base-fine-to-total multiplier is exported because local assessment units, round-up rules, fixed fees and exceptions differ. No claim is made to own or relicense official source documents. [California Vehicle Code §11219.5(a)](https://leginfo.legislature.ca.gov/faces/codes_displaySection.xhtml?sectionNum=11219.5.&lawCode=VEH), verified from the official text on November 17, 2026, requires traffic violator schools to issue receipts for school fees they collect. This receipt requirement is separate from court administrative fees and the schedule calculations.

## Intended and unsuitable uses

Suitable: inspecting sourced examples, reproducing the listed arithmetic, evaluating coverage gaps, and building educational interfaces that preserve all scope and release-status notices.

Unsuitable: setting a driver's case balance, deciding guilt or eligibility, paying a citation, applying 2026 values to 2027, summing multiple charges without the court's rules, inferring statewide completeness, or representing pending rows as deployed school behavior. The actual court notice and current official instructions control the case.

There are no train/test labels or predictive targets. Hugging Face's `train` split is a file-loader convention only. The complete and live files contain the same 49 rows and must not be concatenated. The pending JSON is empty and the pending CSV contains only its header; these download files are retained for compatibility. VC 22450(a) has one reviewed county amount; the other 57 county amounts remain unknown. Overall county coverage counts a county with at least one reference and does not imply coverage for every code. All 58 names in county coverage are a coverage inventory, not 58 supported fee schedules.

## Maintenance and correction

Submit a correction with exact county, row identifier, official source, edition and page. An update should distinguish new court facts, curation corrections, and a website deployment-status change. No search ranking, indexing speed, citation frequency or ongoing update cadence is promised.
