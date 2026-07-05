# Photon Drive (Photon Gen1)

LED driver platform project (ESP32-C6 based driver board + LED tile hardware,
firmware, and supporting tools).

## Structure

- `docs/` — project documentation (French is the source language, `docs/en/`
  holds English summaries), diagrams, datasheets, and reference material.
- `hardware/` — KiCad projects and mechanical design for the driver board,
  LED tile, and wiring/harnesses.
- `firmware/` — embedded firmware (PlatformIO project) for the driver
  controller.
- `software/` — desktop/companion tools: calibration, test scripts, data
  logging, UI prototypes.
- `testing/` — test plans, reports, and logs from bring-up and validation.
- `manufacturing/` — assembly process docs, supplier quotes, costed BOM,
  JLCPCB fabrication packages, and revision packages.
- `images/` — renders, prototype photos, scope captures, thermal images.
- `archive/` — superseded diagrams, schematics, and rejected design ideas.

See [`project_status.md`](project_status.md) for current status and
[`docs/fr/00_resume_executif.md`](docs/fr/00_resume_executif.md) for the
executive summary.
