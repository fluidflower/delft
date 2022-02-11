_Please stick to the headings and their order. Don't modify the words in bold. Your input is required at each occurrence of "e.g." and "..."._<br>
_You may use https://tex-image-link-generator.herokuapp.com/ to render math formulas in Markdown, see the examples below._

## Physics

### PDEs

One mass balance per component water and CO2.

### Constitutive relations

#### Fluid-matrix interaction

* **Capillary pressure:** Constant p_entry
* **Relative permeability:** Power-law

#### Phase composition: Applied equations of state

* **CO2 in liquid phase:** Fugacity-activity model Ziabaksh-Kooi (2012) with PR-EoS - derived constant K-values

* **Water in gas phase:** Fugacity-activity model Ziabaksh-Kooi (2012) with PR-EoS - derived constant K-values

#### Density

* **Liquid phase:** Spivey (2004) + Garcia (2001)

* **Gas phase:** PR-EoS

### Spatial parameters

_Please provide the relevant facies parameters as a csv file._<br>
_E.g._ The parameters ![p_\text{entry}, \lambda, S_{lr}, S_{gr}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+p_%5Ctext%7Bentry%7D%2C+%5Clambda%2C+S_%7Blr%7D%2C+S_%7Bgr%7D%0A) for the different facies are given in [spatial_parameters.csv](spatial_parameters.csv).<br>
_Obviously, the number and type of parameters for your model might differ from the ones in the provided template._

## Numerics

### Coupling of flow and transport, temporal and spatial discretization

Fully coupled, fully implicit, cell-centered FV with TPFA.

### Linearization and Solvers

Operator Based Linearization, Newton with Appleyard chop, Linear solver for CPU: GMRES, CPR preconditioner with AMG and ILU(0)

### Primary Variables

* p, z_0
