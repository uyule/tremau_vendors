# Tremau Vendor Hierarchy

An interactive finder for choosing a Trust & Safety vendor. You pick the requirements you care about, and the page ranks 44 researched vendors by how closely they match. The vendors cover content moderation, deepfake detection, child safety, fraud and identity, cybersecurity and AI/LLM security.

It is one self-contained HTML file with no dependencies or build step. Open `index.html` in any browser.

## How it works

- **Requirements:** there is one dropdown per column of the research matrix, grouped the same way as the matrix legend (Company info, Policy & specialization, Content type coverage, Behavioral / adaptability, Detection mechanism, Network & lifecycle, Industry & specialty).
- **Built-in explanations:** each requirement has an **(i)** button that shows what the column means and its suggested values, taken from the legend. The number next to each option shows how many vendors have that value.
- **Scoring:** each requirement you fill in is worth +1 when a vendor matches it and 0 when it doesn't. Blank requirements aren't scored, so you can fill in as few or as many as you like.
- **Results:** a Top 3 or Top 5 list, ranked by score. Each result shows the vendor's name, website, research tier, score, and the summary from the matrix.
  - If no vendor matches every requirement, the page says so and shows the closest matches.
  - Green ✓ and grey ✗ tags show which requirements each vendor met or missed. A ✗ tag also shows the vendor's actual value.
  - A "Full profile" dropdown on each result shows all of that vendor's values.
  - If other vendors tie with the last one shown, their names are listed underneath.

## Scoring and data choices

1. **Multi-value matching:** vendors with more than one value in a column count as a hit for each. For example, Hive matches Content moderation, Deepfake detection and Child safety.
2. **Broader values count toward narrower ones:**
   - A product shape or policy type of "Both" counts as a hit for either side.
   - Selecting "Partial" for a content type or for account-level analysis also accepts vendors with full support.
   - Selecting "Indirect" PDF support also accepts vendors with native PDF input.
3. **Hybrid mechanisms:** "Hybrid" vendors also count for each method they combine (e.g. LLM-based and ML classifier).
4. **Condensed values:** the descriptive cells in the research matrix were condensed into the legend's short values, and some of these were judgment calls. For example, OCR-only text detection is marked "Partial", and a judgment was made about which vendors count "Yes" for slang/obfuscation depth. Check the "Full profile" view against the source matrix if a value matters for a decision.
5. **Options added beyond the legend**, because the matrix uses them often:
   - **Specialty:** AI apps & chatbots, Media & journalism, Contact centres.
   - **Lifecycle stage:** Upstream gating (signup/login).
   - **Model customization:** shared model, customer-configurable policy/rules.
6. **Empty category:** "Academic integrity" appears as a Main Category option, but no vendor in the current data has it.

## Limitation: pricing

The finder does not compare actual prices. The only pricing filter is whether a price is published at all ("Yes", "Quote only", "Free tier"). Too few vendors publish real pricing for a fair price comparison: many are quote-only, and the ones that do publish use very different units (per call, per month, per evaluation, outcome-based). Treat pricing as something to confirm directly with each vendor.

## Updating the data

The vendor data is a plain list (`COMPANIES`) near the top of the `<script>` section in `index.html`. The filter definitions (`FIELDS`) are just above it. You can add a vendor by copying an existing entry and editing its values. The values must match the option names in `FIELDS`.

## Planned

- An AI-generated explanation of why each vendor was ranked where it is.
