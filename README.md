# IfcSieve

**Strip geometry from IFC files and extract structured data for analysis, scripting, and AI interrogation.**

IfcSieve is a single-file browser app — no install, no server, no data leaves your machine. Drop an IFC file in, strip the geometry, and export the data you need in CSV, JSON, or Markdown.

---

## Why

A typical IFC file is 70–90% geometry. If you want to query properties, audit classifications, extract a space schedule, or feed building data to an AI or script, you don't need any of it. IfcSieve removes the geometric bloat and hands you a clean, lightweight data file.

An 87 MB IFC becomes ~9 MB of pure building knowledge — spatial hierarchy, properties, quantities, materials, classifications, relationships, schedules — ready for IfcOpenShell scripts, CI pipelines, spreadsheet analysis, or LLM interrogation.

---

## Features

- **Geometry strip** — removes all IFC geometry entities (placements, profiles, solids, meshes, tessellations, visual styles) and rewrites internal references; output is valid SPF text
- **9 data categories** — Spatial Structure, Building Elements, Properties, Quantities, Materials, Classifications, Types & Families, Schedules (4D/5D), Metadata
- **3 output formats** — CSV (schedules and tabular data), JSON (full entity graph), Markdown (spatial hierarchy, element schedules, project metadata)
- **Column header checkboxes** — select or deselect all categories, or all of a format (CSV / JSON / Markdown) in one click; partial state indicator
- **Chip-level class filtering** — include or exclude individual IFC classes within each category (e.g. walls only, no openings)
- **4 built-in presets** — NZ BIM Brief, QS Package, Compliance Audit, Full Data Dump
- **Per-row download** — each output category row has a Download button; downloads its files individually, unzipped
- **Download All** — downloads every selected output file individually, unzipped, with configurable stagger delay
- **Properties modal** — text scale, entity count display, expand-on-load, stripped file extension (.txt recommended to avoid Windows security warnings), default format, download stagger delay, geometry strip toggle, select-all-on-load toggle
- **Single HTML file** — save and open locally, no dependencies, no CDN calls for core functionality
- **Fully local** — no data is uploaded anywhere; all processing runs in the browser

---

## Usage

1. Download `IfcSieve.html`
2. Open it in any modern browser (Chrome, Edge, Firefox)
3. Drop an `.ifc` file onto the drop zone, or click **Browse for IFC file**
4. Select categories and formats
5. Click **Extract & Export**
6. Download individual outputs or **Download All**

---

## Output Files

| Category | CSV | JSON | Markdown |
|---|:---:|:---:|:---:|
| Spatial Structure | ✓ | ✓ | ✓ |
| Building Elements | ✓ | ✓ | ✓ |
| Properties | ✓ | ✓ | |
| Quantities | ✓ | ✓ | |
| Materials | ✓ | ✓ | |
| Classifications | ✓ | ✓ | |
| Types & Families | ✓ | ✓ | |
| Schedules (4D/5D) | ✓ | ✓ | |
| Metadata | ✓ | ✓ | ✓ |

The stripped IFC is saved as `_data.txt` by default (configurable in Properties). The content is valid SPF and can be renamed `.ifc` and opened in any IFC tool.

---

## Compatibility

IFC2x3, IFC4, IFC4.3 — any standard SPF-encoded `.ifc` file.

Tested with models from Revit, Bonsai/Blender, ArchiCAD, and Vectorworks.

---

## Roadmap / Known Limitations

- Geometry strip is type-name based; non-standard or vendor-extended geometry subtypes may not be caught
- Large files (>200 MB) may be slow to parse in-browser; the stripped output is fast to regenerate from script
- No 3D viewer — geometry is stripped, not visualised
- Markdown export for Properties, Quantities, Materials, Classifications, Types, and Schedules is not yet implemented (outputs a notice); CSV and JSON cover all categories

---

## Part of the Dasu Toolset

IfcSieve is a companion tool to [Dasu.print](https://github.com/4nigel/dasu.print), a drawing sheet layout tool for the Bonsai/OpenBIM community.

---

## Licence

MIT — free to use, modify, and distribute. No warranty.

---

## Contributing

Issues and pull requests welcome. The entire app is a single HTML file — fork, edit, test by opening in a browser, submit PR.
