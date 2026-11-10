# OpenReynolds sample case prompt

Build and run a small, transient, two-dimensional free-surface tank case in OpenFOAM for demonstration only. This is not a field well or production case.

## Geometry and assumptions

- Rectangular tank interior: 1.0 m long × 0.6 m high, represented as a 2D slice with a 0.01 m depth.
- Start with a 0.36 m water column (60% of tank height), air above it, and gravity of 9.81 m/s² downward.
- Model water and air as incompressible phases. Use water density 998 kg/m³, water kinematic viscosity 1.0e-6 m²/s, air density 1.2 kg/m³, and surface tension 0.072 N/m. State any simplifying assumptions.
- Place a short inlet at the lower left and a drain opening at the lower right. Keep the top boundary open to atmosphere. Use 2D front/back empty boundaries.
- Apply a pulsed water inlet for 2 seconds, off for 1 second, then on for 2 seconds. Set the inlet velocity to 0.05 m/s during each pulse. Set the drain boundary to a modest, stable outflow; document the chosen boundary condition and rate.
- Run for 8 seconds of simulated time with a coarse, affordable mesh first. Keep the case small enough to inspect and rerun quickly.

## Requested checks and outputs

1. Choose and explain a suitable transient multiphase solver for a free surface.
2. Build the case and render the geometry and mesh before solving. Inspect the mesh, patch names, interface resolution, and `checkMesh` result.
3. Run the transient solve. Track solver residuals, continuity error, phase volume, and stability; stop and explain if the case diverges.
4. Render the water volume fraction and velocity field at the initial state, during an inlet pulse, and at the final time.
5. Export `tank_level.csv` with columns `time_s,level_pct`. Estimate the mean free-surface height over the tank interior at each output time.
6. Report initial water volume, total inlet volume, outlet volume, final water volume, and mass-balance error. Compare the CFD level trace with the transparent well-mixed tank balance `V(t+dt) = V(t) + Qin*dt - Qout*dt`.
7. Include the OpenFOAM case files, run command, mesh counts, solver logs, rendered images, and a short note listing limitations.

The page’s default visual uses synthetic mass-balance inputs. Do not label those values or the preview curve as CFD results. Only an exported result file from the completed OpenReynolds run should be called solver output.
