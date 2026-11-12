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

## Wellsite drone economics sandbox

The page now includes a synthetic stripper-well scenario showing how drone inspections can extend the operating picture when paired with SCADA, production, inventory, logistics, and market data. Drones provide periodic/on-demand visual context; SCADA remains the continuous process signal. Recommendations feed an operator-approved dispatch, repair, or production/marketing action.

The default 20-well illustration assumes 8 bopd per well; four issues identified early each month; 1.5 days of downtime avoided per issue; six avoided truck rolls at $450 each; 40% of baseline monthly volume responsive to sales timing at a $1.50/bbl uplift; $70/bbl value for recovered production; and two drone sorties/month at $600 each. At those assumptions, it models 48 bbl/month of recovered production (+1%), $2,700/month in truck costs avoided, $2,880/month in netback uplift, and $1,200/month in patrol costs. The resulting $7,740/month illustrative opportunity ($92,880/year) is before royalties, taxes, variable production costs, and any unmodeled program costs.

These are editable synthetic assumptions, not observed performance, vendor pricing, reserves, a production forecast, or a guaranteed financial result. The netback example assumes inventory, nominations, transport capacity, and buyer/price signals are connected and operational actions are approved. It does not imply a drone alone can change realized prices.

See [`wellsite-synthetic-scenario.csv`](wellsite-synthetic-scenario.csv) for the default inputs and calculation formulas, and [`drones-stripper-wells-summary.pdf`](drones-stripper-wells-summary.pdf) for the short first-principles summary deck.
