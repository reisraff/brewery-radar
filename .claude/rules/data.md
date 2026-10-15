---
paths:
  - "index.html"
---

# Embedded hop and yeast datasets

- Hops live in the `csv` template string (parsed by `parseCSV`); yeasts in `yeastCSV` (parsed by `parseYeastCSV`). Headers are in Portuguese.
- Aroma/flavor attributes are on a 0-10 scale.
- Multi-value fields (`Estilos` for hops, `Tipos` for yeast) must be double-quoted comma lists — the parsers rely on the quoting, so an unquoted list shifts every following column.
- Every row must have the same column count as the header, including trailing empty columns.
- `País` is an ISO-2 country code; it drives the flag image from flagcdn.com.
