# Electio liquid slug demo

A static, browser-based discussion demo that follows the attached tank and full-system diagram. Open `index.html` directly or serve this folder with any static file server.

## What the page includes

- An animated tank cross-section with synthetic inflow and drain cues.
- A 24-hour tank-level preview driven by the visible volume balance and synthetic pig-arrival profile.
- Scenario and initial-level controls.
- A sample event file where a pipeline pig is launched at a launcher and later recorded at its receiver; each receipt has a fictional liquid volume.
- A flow diagram that connects field observations, events, arrival estimates, tank inputs, and an OpenReynolds case.
- A dimensioned case prompt for an OpenReynolds/OpenFOAM free-surface study.
- A CSV importer for solver exports with numeric `time_s,level_pct` columns.

## Model status

The page's default graph and metrics are a **synthetic tank mass-balance preview**. They are not OpenFOAM or OpenReynolds output, field data, or a validated operating forecast. The tank visual animates for presentation; it does not visualize a solved CFD field. A real result can replace the curve by importing a solver-exported CSV.

The OpenReynolds prompt is in [`openreynolds-case-prompt.md`](openreynolds-case-prompt.md). It specifies an illustrative two-phase tank case and requests geometry and mesh review, solver checks, a level trace, and a mass-balance comparison. Running OpenReynolds requires workspace and model-provider credentials, which are not included in this repository. Its runs can consume hosted compute and model tokens.

## Reference

- [OpenReynolds source and documentation](https://github.com/InviscidAI/OpenReynolds)
