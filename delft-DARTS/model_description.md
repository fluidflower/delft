_Please stick to the headings and their order. Don't modify the words in bold. Your input is required at each occurrence of "e.g." and "..."._<br>
_You may use https://tex-image-link-generator.herokuapp.com/ to render math formulas in Markdown, see the examples below._

## Physics

### PDEs

One mass balance per component water and CO2.

### Constitutive relations

#### Fluid-matrix interaction

* **Capillary pressure:** Constant p_entry
* **Relative permeability:** Power-law: k_rj = k_rjmax * ((s_j-s_jr)/(1-s_lr-s_gr))^n_j

#### Phase composition: Applied equations of state

* **CO2 in liquid phase:** constant K-values: y_CO2/x_CO2 = 1e3

* **Water in gas phase:** constant K-values: y_H2O/x_H2O = 1e-3

#### Density

* **Liquid phase:** rho = (1002 + x_CO2 * 320) * (1 + 1e-6 * (p - 1)) [p in bar]

* **Gas phase:** rho = 2 * (1 + 1e-4 * (p - 1)) [p in bar]

### Spatial parameters

_Please provide the relevant facies parameters as a csv file._<br>
_E.g._ The parameters ![p_\text{entry}, \lambda, S_{lr}, S_{gr}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+p_%5Ctext%7Bentry%7D%2C+%5Clambda%2C+S_%7Blr%7D%2C+S_%7Bgr%7D%0A) for the different facies are given in [spatial_parameters.csv](spatial_parameters.csv).<br>
_Obviously, the number and type of parameters for your model might differ from the ones in the provided template._

## Numerics

### Coupling of flow and transport, temporal and spatial discretization

Fully coupled, fully implicit, cell-centered FV with TPFA.

### Linearization and Solvers

Operator Based Linearization, Newton with Appleyard chop, Linear solver for CPU: GMRES, CPR preconditioner with AMG and ILU(0) -> sparse direct SUPER_LU

### Primary Variables

* p, z_0
