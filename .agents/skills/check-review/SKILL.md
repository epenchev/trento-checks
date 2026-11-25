---
name: check-review
description: Review a trento check in the trento-project checks repository. Use when asked to review a check .yaml file in this repo.
---

# Check Review

Review a check yaml file in this repo the way a (SAP Solutions Engineering) member would.

## Inputs

- A file path under `checks/`; review the file.

## Procedure

1. Run the `/tlint` command for before proceeding with review, fail if not successful with the error returned from `tlint`.
2. Every trento-check must start with the SPDX header, header content present in the .licenserc.yaml file for reference.
3. **Read** [specification.adoc](https://github.com/trento-project/wanda/blob/main/guides/specification.adoc). This document defines what a compliant trento check should look like.   
4. **Compliance check.** Against the docs above, verify:
   - Verify the **filename** convention.
   - Verify the trento-check **structure** as specified in the document.
   - Verify the trento-check **id**.
   - Verify the trento-check **name**.
   - Verify **group** as specified.
   - Should have a proper **description** as specified that makes it clear what the trento-check purpose is.
   - Must have a **remediation** as specified that should make sense with the **description** itself.
   - If **severity** is set, verify that it is an allowed value.
   - **Metadata** is correct: consult with the specification.
   - **exclude**: Use the [specification.adoc](https://github.com/trento-project/wanda/blob/main/guides/specification.adoc) for verification.
   - **Facts**: Ensure the correct gatherer or gatherers are used for the trento-check. Gatherer names, versions and argument formats are documented only in [gatherers.adoc](https://github.com/trento-project/wanda/blob/main/guides/gatherers.adoc).
   - **customization_disabled**: Use the [specification.adoc](https://github.com/trento-project/wanda/blob/main/guides/specification.adoc) for verification.
   - **Values**: Use the [expression language format](https://github.com/trento-project/wanda/blob/main/guides/expression-language.adoc) for verification.
   - **Expectations**: Use the [expression language format](https://github.com/trento-project/wanda/blob/main/guides/expression-language.adoc) for verification, also make sure the correct values and facts are used. Do not check only the syntax but make sure it is semantically correct.
5. **Report findings** (format below). Answer in precise, objective, technically correct terms; informal tone; no marketing speak.

## Findings format

Group by severity, most severe first. Each finding: location, the issue, why it matters, and a concrete suggestion.

- **Blocker** — correctness flaw that should stop approval until resolved.
- **Major** — significant gap, risk; must be addressed before testing.
- **Minor** — clarity, completeness, or compliance nit.
- **Question** — something the description leaves ambiguous; ask the author.

Summarize with an overall verdict: whether the trento-check is ready for test.

## Conduct

- Calibrate every claim: mark assumptions explicitly, say "I don't know" when you don't, and verify before asserting.
- Point out flaws and pitfalls candidly. Serve correctness, not the author's comfort.
- Ask clarifying questions instead of guessing intent.
- Do not propose next steps unless explicitly asked.
