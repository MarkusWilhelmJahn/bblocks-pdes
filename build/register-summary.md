# FiniteDifferenceMethod4PDES — OGC Building Block Register

OGC Building Block register for all ODE/PDE models implemented in FiniteDifferenceMethod4PDES (Java/Maven, MVC architecture). Covers 22 local kinetic models across 4 complexity tiers, 4 Holling functional response components, and 2 spatial operators, all described using SOSA, PROV-O and STAC 1.0.


## Building Blocks

### `mwj.pdes.common.observation` — Initial Observation (SOSA)

**Type:** schema

SOSA ObservationCollection providing initial state variables and control parameters for any model run. resultTime becomes t=0 of the simulation.

### `mwj.pdes.components.advection` — Spatial Advection Operator

**Type:** schema

Linear advection term -v·∇u. Implemented in model.global.Advection.java. Combined with any local kinetic model and diffusion to produce a DIFICI travelling-wave system.

### `mwj.pdes.components.diffusion` — Spatial Diffusion Operator

**Type:** schema

Fickian diffusion term D·∇²u. Implemented in model.global.Diffusion.java. Combined with any local kinetic model to produce a reaction-diffusion PDE.

### `mwj.pdes.components.holling-i` — Holling Type I Functional Response

**Type:** schema

Linear prey consumption proportional to prey density. No handling time. Implemented in model/lokal/holling/HollingI.java.

### `mwj.pdes.components.holling-ii` — Holling Type II Functional Response

**Type:** schema

Saturating Michaelis-Menten (disc equation) response. Implemented in model/lokal/holling/HollingII.java.

### `mwj.pdes.components.holling-iii` — Holling Type III Functional Response

**Type:** schema

Sigmoid response — accelerating at low density, saturating at high. Implemented in model/lokal/holling/HollingIII.java.

### `mwj.pdes.components.holling-iv` — Holling Type IV Functional Response

**Type:** schema

Inhibition / Monod-Haldane response — unimodal, decreasing at high prey density. Implemented in model/lokal/holling/HollingIV.java.

### `mwj.pdes.common.simulation-run` — Simulation Run (PROV)

**Type:** schema

Generic PROV Activity capturing one execution of any local kinetic model in FiniteDifferenceMethod4PDES, optionally extended with spatial operators (Diffusion, Advection).

### `mwj.pdes.common.stac-result` — Simulation Result STAC Item

**Type:** schema

STAC 1.0 Item cataloguing outputs of any simulation run from FiniteDifferenceMethod4PDES, with plankton-rda extension for model-specific searchable properties.

### `mwj.pdes.o1.blei` — Lead Kinetics (Blei)

**Type:** schema

One-compartment lead (Blei) kinetics model dX/dt = k_in - k_out·X. Implemented in Blei.java.

### `mwj.pdes.o2.china` — China Population Model

**Type:** schema

Two-component demographic or resource-competition model. China.java.

### `mwj.pdes.o2.harvesting-dependent` — Stock-Dependent Harvesting

**Type:** schema

Logistic growth with proportional (stock-dependent) harvesting effort. Bestandsabhaengige_Ernte.java.

### `mwj.pdes.o2.harvesting-independent` — Stock-Independent Harvesting

**Type:** schema

Logistic growth with constant (stock-independent) harvest rate H. Bestandsunabhaengige_Ernte.java.

### `mwj.pdes.o2.jansen` — Jansen Host-Parasitoid Model

**Type:** schema

Jansen (1995) host-parasitoid model with density dependence. Jansen.java.

### `mwj.pdes.o2.lorenz` — Lorenz System

**Type:** schema

Lorenz (1963) chaotic attractor: dx/dt=sigma(y-x), dy/dt=x(rho-z)-y, dz/dt=xy-beta·z. Lorenz.java.

### `mwj.pdes.o2.lotka-volterra` — Lotka-Volterra Predator-Prey

**Type:** schema

Classic Lotka-Volterra: dX/dt=a·X-b·X·Y, dY/dt=-c·Y+d·X·Y. Implemented in Lotka.java.

### `mwj.pdes.o2.plankton` — Generic Plankton Model

**Type:** schema

Simplified two-component phytoplankton-zooplankton model. Plankton.java.

### `mwj.pdes.o2.roessler` — Rössler System

**Type:** schema

Rössler (1976) chaotic system: dx/dt=-(y+z), dy/dt=x+a·y, dz/dt=b+z(x-c). Roessler.java.

### `mwj.pdes.o2.scheffer` — Scheffer Phytoplankton-Zooplankton (RDA)

**Type:** schema

Scheffer (1991) phytoplankton/zooplankton predator-prey model with Holling II/III responses and optional diffusion/advection. Scheffer.java.

### `mwj.pdes.o2.tannentriebwickler` — Larch Budmoth (Tannentriebwickler)

**Type:** schema

Zeiraphera diniana (larch budmoth) population cycle model. Tannentriebwickler.java.

### `mwj.pdes.o2.tumor` — Tumor-Immune Interaction

**Type:** schema

Two-component tumor growth and immune response model. Tumor.java.

### `mwj.pdes.o2.volterra` — Volterra Predator-Prey with Carrying Capacity

**Type:** schema

Extended Volterra with logistic prey: dX/dt=r·X(1-X/K)-a·X·Y, dY/dt=-c·Y+d·a·X·Y. Volterra.java.

### `mwj.pdes.o3.fischfang` — Fish Harvesting (Fischfang)

**Type:** schema

Three-component fish harvesting model (prey-predator-effort or nutrient-fish-harvest). Fischfang.java.

### `mwj.pdes.o3.schloegl` — Schlögl Bistable Chemical Reaction

**Type:** schema

Schlögl (1972) chemical bistability: dX/dt = k1·A·X²-k2·X³+k3·B-k4·X. Schloegl.java.

### `mwj.pdes.standard.exponential` — Exponential Growth

**Type:** schema

Single-species exponential growth dX/dt = r·X. Implemented in Exponentiell.java.

### `mwj.pdes.standard.goal-seeking` — Goal-Seeking Model

**Type:** schema

Goal-seeking (target) dynamics dX/dt = r·(Z-X). Implemented in Zielsuchend.java.

### `mwj.pdes.standard.linear` — Linear ODE

**Type:** schema

Linear scalar ODE dX/dt = a·X + b. Implemented in Linear.java.

### `mwj.pdes.standard.logistic` — Logistic Growth

**Type:** schema

Single-species logistic growth dX/dt = r·X·(1-X/K). Implemented in Logistisch.java.

