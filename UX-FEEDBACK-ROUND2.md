# File Enrichment Prototype - Round 2 UX Feedback

## Changes Acknowledged as Improvements (All 6 personas)

Every tester noted these as positive changes:
- **"File Enrichment" naming** - universally clearer
- **CSV format subheader** on upload page - prevents confusion
- **"Email" suffix on hash fields** - SHA-256 Email, MD5 Email, HEM Email all better than bare acronyms
- **Paste screen** - useful for quick tests and non-technical users
- **Upgrade modal with cost calculator** - significant improvement for budget clarity
- **Removed TBD cost line** - less noise

---

## Remaining Issues by Priority

### CRITICAL - Raised by 5-6 personas

#### 1. No file download action anywhere
**All 6 personas flagged this.**
The download icon on Reports navigates to Data Quality Summary instead of downloading the enriched CSV. There is no "Download Enriched File" button on the Summary page either. The core deliverable of the tool is unreachable.

#### 2. No output field documentation
**Sarah, Marcus, Priya, Rachel, Tom**
Users still don't know what data they'll get back. Will it include job titles? Industry? Company size? The tool describes inputs exhaustively but outputs not at all.

#### 3. No dollar cost on Confirm screen
**Sarah, Marcus, Doug, Tom**
"Estimated Matches Used: 8,850" is shown but never converted to dollars. The CPM rate exists in the upgrade modal but isn't surfaced on the main confirm screen. Tom: "I should not have to do mental math (8,850 / 1,000 * $40 = $354)."

---

### HIGH - Raised by 3-4 personas

#### 4. Sample mapping data has integrity issues
**Sarah, Marcus, Priya, Doug, Rachel**
`last_name` mapped to "MD5 Email" and `state` mapped to "Select Field" showing "Mapped" status. Every tester flagged this as trust-destroying. Even as prototype data, it suggests auto-mapping is unreliable.

#### 5. Four email options with no guidance on which to pick
**Sarah, Doug** (the primary non-technical audience)
Users see Email, SHA-256 Email, MD5 Email, HEM Email in the same dropdown with no explanation of when to use which. Doug: "I have a 1-in-4 chance of picking the right one." Adding "Email" helped identify them as email-related but didn't explain the distinction.

#### 6. DEV notes visible in upgrade modal
**Sarah, Marcus, Priya, Rachel, Tom**
The yellow "DEV: Pull from total CPM on bundles on contract" annotations are visible to users. Undermines trust and signals an unfinished product.

#### 7. Agreement checkbox links to nothing
**Sarah, Rachel, Tom**
"I agree to charges and data deletion policy" references a policy that isn't linked or accessible. Rachel: "My legal team will not approve uploading PII without reviewable terms."

#### 8. Topbar still says "Run a Self Serve Enrichment Test"
**Sarah**
Inconsistent with the "File Enrichment" rename everywhere else. The word "Test" creates confusion about whether this is production or sandbox.

---

### MEDIUM - Raised by 2 personas

#### 9. No subset/test enrichment option
**Marcus, Tom**
No way to enrich only the first N rows. Users must manually slice CSVs externally to test on a sample before committing full files.

#### 10. Paste screen has no format guidance
**Marcus, Rachel**
"Paste your list here" with no indication of expected format (one per line? CSV rows? with headers?).

#### 11. No data preview on Review/Map screens
**Priya, Marcus**
Still no way to verify the file was parsed correctly or that mappings match actual data values.

#### 12. No audit trail
**Rachel, Tom**
No job IDs, no user attribution, no download tracking. Blockers for regulated environments and client deliverables.

---

### LOWER - Persona-specific

| Issue | Persona | Detail |
|-------|---------|--------|
| No output field selection | Marcus | Can't choose which enrichment fields to receive |
| No exportable summary | Priya, Tom | Can't download Data Quality Summary for board deck or client report |
| No purchase receipt | Tom | No confirmation after buying matches to share with client finance |
| No field mapping validation | Rachel, Priya | No warning when mappings are obviously wrong |
| Separator/header questions intimidating | Doug | Technical config exposed to non-technical users |
| "Clinet02.csv" typo | Multiple | Minor but noticed |
| No notification mechanism specified | Marcus | "You'll be notified" but how? |

---

## Progress Scorecard

| Issue from Round 1 | Status in Round 2 |
|---|---|
| Naming confusion ("Enrich Self-Serve") | FIXED |
| No CSV format guidance | FIXED |
| Cryptic hash field names | IMPROVED (still needs tooltips) |
| No paste option | FIXED |
| No upgrade/cost flow | FIXED |
| TBD cost line noise | FIXED |
| No file download action | STILL OPEN |
| No output field docs | STILL OPEN |
| No dollar cost on confirm | STILL OPEN |
| Jargon in mapping dropdowns | IMPROVED (email suffix helps, still needs more) |
| Agreement checkbox unlinked | STILL OPEN |
| No data preview | STILL OPEN |
| Sample mapping data wrong | STILL OPEN |
| DEV notes visible | STILL OPEN (intentional for prototype) |

---

## Recommended Next Actions (Priority Order)

1. **Add "Download Enriched File" button** on Data Quality Summary + make Reports download icon trigger actual download
2. **Show estimated cost in dollars** on the Confirm screen (matches * CPM rate)
3. **Fix sample mapping data** - correct last_name/MD5 and state/Select Field bugs
4. **Add output field documentation** - modal or section showing what enrichment returns
5. **Add tooltips to email hash options** explaining plain email vs. hashed variants
6. **Link the data deletion policy** from the agreement checkbox
7. **Fix topbar text** to match "File Enrichment" naming
8. **Add format guidance on paste screen**
