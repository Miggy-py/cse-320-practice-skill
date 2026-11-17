# Question bank

The starter contains a JSON array. Each item has a stable `id`, visible `topic`, stem `q`, five `options`, zero-based `answer`, `correctSkill`, `source`, and `workedSteps`. Use `reviewGroup` to combine related skills in the results. The optional `code` is plain text. Put execution assumptions in the stem or diagram notes so follow-up requests carry them. Cite a PDF page with its filename, a transcript question or line range, or a README path and heading.

Write `workedSteps` as an array of short plain-text steps for **How it’s done**. Start with the governing rule or setup, then apply it to the question’s values or code. End with the derived result and refer to answer text or values, since the displayed choices shuffle. For older banks that lack the field, the disclosure offers **Ask for the steps**.

A question can include a textual diagram built from one or more tables. Use concise headings and enough context to interpret values. List columns in display order and supply one value per column in every row.

```json
{
  "label": "Page table",
  "notes": "Pages are 16 bytes. Frame numbers are hexadecimal.",
  "source": "Named reference · p. 4",
  "tables": [
    {
      "label": "Single level",
      "columns": ["VPN", "Frame", "Present"],
      "rows": [[1, "A", 1], [0, "3", 0]]
    }
  ]
}
```

Use the same representation for caches, TLB sets, page tables, or heap blocks. For example, a cache diagram can show columns for set, way, valid bit, and tag, with tag radix and bit widths in the notes. Keep table rows faithful to the source and show enough of the diagram to answer without another file.

## Close choices

- Keep choices parallel in phrasing, units, and level of detail. The template shuffles option order on every attempt, so `answer` always refers to the position in the authored `options` array; do not hand-rotate the correct position.
- Derive numeric distractors from realistic errors. In a page walk, retain the offset but use the wrong frame, swap index fields, or mistake a non-present entry for a mapping. In a cache problem, vary the tag, set, and valid-bit checks.
- For code, vary one return value, event ordering, iteration count, or side effect at a time. Specify success, buffering, scheduling, and input assumptions when they matter. When identifying undefined behavior, ask for the defect or repair instead of predicting its output.
- For terms, pull adjacent concepts from the exam's pool. For homework, vary the documented responsibilities of nearby functions or workflow stages.
- Avoid redundant choices and “all of the above.” Check each alternative against both the literal wording and the stated assumptions.
