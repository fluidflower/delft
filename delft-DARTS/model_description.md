_Please stick to the headings and their order. Don't modify the words in bold. Your input is required at each occurrence of "e.g." and "..."._<br>
_You may use https://tex-image-link-generator.herokuapp.com/ to render math formulas in Markdown, see the examples below._

## Physics

### PDEs

One mass balance per component water and CO2.

### Constitutive relations

#### Fluid-matrix interaction

* **Capillary pressure:** Constant p_entry
  
* **Relative permeability:** ![k_{rj} = k_{rj}^e \cdot \big[\frac{s_j-s_{jc}}{1-s_{wc}-s_{gc}}\big]^{n_j}](https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Cdisplaystyle+k_%7Brj%7D+%3D+k_%7Brj%7D%5Ee+%5Ccdot+%5Cbig%5B%5Cfrac%7Bs_j-s_%7Bjc%7D%7D%7B1-s_%7Bwc%7D-s_%7Bgc%7D%7D%5Cbig%5D%5E%7Bn_j%7D)

#### Phase composition: Applied equations of state

* **CO2 in liquid phase:** Activity model Ziabaksh (2012)

* **Water in gas phase:** PR EoS

#### Density

* **Liquid phase:** Spivey (2004) + Garcia (2001)

* **Gas phase:** PR EoS

#### Solubility limit

~1.90 kg/m3

### Temperature

T_mean = 20, std 2.0

### Domain volume

Total volume: 0.09198 m3
Total pore volume: 0.04060 m3

### Spatial parameters

_Please provide the relevant facies parameters as a csv file._<br>
_E.g._ The parameters ![p_\text{entry}, \lambda, S_{lr}, S_{gr}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+p_%5Ctext%7Bentry%7D%2C+%5Clambda%2C+S_%7Blr%7D%2C+S_%7Bgr%7D%0A) for the different facies are given in [spatial_parameters.csv](spatial_parameters.csv).<br>
_Obviously, the number and type of parameters for your model might differ from the ones in the provided template._

## Numerics

### Coupling of flow and transport, temporal and spatial discretization

Fully coupled, fully implicit, cell-centered FV with TPFA.

### Linearization and Solvers

Operator Based Linearization, Newton with Appleyard chop, Linear solver for CPU: sparse direct SUPER_LU

### Primary Variables

* p, z_H2O

### Computational Grid

Unstructured grid: 48274 Wedges (0.003<lc<0.015), 2 Cylindrical well cells (radius=0.005m)

### Performance

| Indicator                            | Average |     Min |  Max |
| :----------------------------------- | ------: | ------: | ---: |
| time step size [s]                   |      14 | 8.64e-5 | 60.0 |
| # nonlinear iterations per time step |    1.43 |       1 |    6 |
| # linear iterations per solve        |       1 |       1 |    1 |
