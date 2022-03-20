_Please stick to the headings and their order. Don't modify the words in bold. Your input is required at each occurrence of "e.g." and "..."._<br>
_You may use https://tex-image-link-generator.herokuapp.com/ to render math formulas in Markdown, see the examples below._

## Physics

### PDEs

One mass balance per component: brine and CO2

![\begin{equation*}
\frac{\partial}{\partial t} \left(\phi \sum_{\alpha} x_{c\alpha} \rho_\alpha S_\alpha \right) + \nabla \cdot \left(\sum_\alpha x_{c\alpha} \rho_\alpha \mathbf{u}_\alpha \right) - \sum_\alpha x_{c\alpha} q_\alpha = 0
\end{equation*}
](https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Cdisplaystyle+%5Cbegin%7Bequation%2A%7D%0A%5Cfrac%7B%5Cpartial%7D%7B%5Cpartial+t%7D+%5Cleft%28%5Cphi+%5Csum_%7B%5Calpha%7D+x_%7Bc%5Calpha%7D+%5Crho_%5Calpha+S_%5Calpha+%5Cright%29+%2B+%5Cnabla+%5Ccdot+%5Cleft%28%5Csum_%5Calpha+x_%7Bc%5Calpha%7D+%5Crho_%5Calpha+%5Cmathbf%7Bu%7D_%5Calpha+%5Cright%29+-+%5Csum_%5Calpha+x_%7Bc%5Calpha%7D+q_%5Calpha+%3D+0%0A%5Cend%7Bequation%2A%7D%0A)

### Constitutive relations

#### Fluid-matrix interaction

* **Capillary pressure:** Brooks-Corey
  ![p_c(S_{l}) = p_\text{entry}S_{le}^{-1/\lambda}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+p_c%28S_%7Bl%7D%29+%3D+p_%5Ctext%7Bentry%7DS_%7Ble%7D%5E%7B-1%2F%5Clambda%7D%0A)

* **Relative permeability:** Brooks-Corey (end points are based on Table 5 in final benchmark escription)

![\begin{equation*}
k_{rg} (S_g)= k_{rg}^{o} S_{ge}^2
\end{equation*}
](https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Ctextstyle+%5Cbegin%7Bequation%2A%7D%0Ak_%7Brg%7D+%28S_g%29%3D+k_%7Brg%7D%5E%7Bo%7D+S_%7Bge%7D%5E2%0A%5Cend%7Bequation%2A%7D%0A)
![\begin{equation*}
k_{rl} (S_g)= k_{rl}^{o} (1-S_{ge})^2
\end{equation*}
](https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Ctextstyle+%5Cbegin%7Bequation%2A%7D%0Ak_%7Brl%7D+%28S_g%29%3D+k_%7Brl%7D%5E%7Bo%7D+%281-S_%7Bge%7D%29%5E2%0A%5Cend%7Bequation%2A%7D%0A)


#### Phase composition: Applied equations of state

* **CO2 in liquid phase:**

* **Water in gas phase:** 

We consider the liquid phase sonsists of CO2 and brine, and gas phase is composed of CO2 only. The solubility of CO2 is computed based on the thermodynamic model described in Spycher et al. (2003).

#### Density

* **Liquid phase:** ![\begin{equation*}
\rho_{l}= \frac{\rho_b^{\text{STC}}+\rho_{\text{CO}_2}^{\text{STC}} R_s}{B_b}
\end{equation*}
](https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Ctextstyle+%5Cbegin%7Bequation%2A%7D%0A%5Crho_%7Bl%7D%3D+%5Cfrac%7B%5Crho_b%5E%7B%5Ctext%7BSTC%7D%7D%2B%5Crho_%7B%5Ctext%7BCO%7D_2%7D%5E%7B%5Ctext%7BSTC%7D%7D+R_s%7D%7BB_b%7D%0A%5Cend%7Bequation%2A%7D%0A)

* **Gas phase:** Redlich-Kwong EOS

#### Solubility limit

1.6489 kg/m<sup>3</sup>

### Temperature

20 °C

### Domain volume

0.083 m<sup>3</sup>

### Spatial parameters

_Please provide the relevant facies parameters as a csv file._<br>
_E.g._ The parameters ![p_\text{entry}, \lambda, S_{lr}, S_{gr}](https://render.githubusercontent.com/render/math?math=%5Cdisplaystyle+p_%5Ctext%7Bentry%7D%2C+%5Clambda%2C+S_%7Blr%7D%2C+S_%7Bgr%7D%0A) for the different facies are given in [template_spatial_parameters.csv](template_spatial_parameters.csv).<br>
_Obviously, the number and type of parameters for your model might differ from the ones in the provided template._

## Numerics

### Coupling of flow and transport, temporal and spatial discretization

Fully coupled, fully implicit, cell-centered FV with TPFA

### Linearization and Solvers

Direct solver in Matlab

### Primary Variables

Liquid phase pressure and mass fraction of CO2: 

![\begin{equation*}
p_l, z_{\text{CO}_2}
\end{equation*}
](https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Ctextstyle+%5Cbegin%7Bequation%2A%7D%0Ap_l%2C+z_%7B%5Ctext%7BCO%7D_2%7D%0A%5Cend%7Bequation%2A%7D%0A)

### Computational Grid

Structured Cartesian grid with total number of 43758

### Performance
Injection
| Indicator                            |  Average |      Min |      Max |
|:-------------------------------------|---------:|---------:|---------:|
| time step size [s]                   |    13.17 |        1 |       15 |
| # nonlinear iterations per time step |     1.25 |        1 |       10 |
| # linear iterations per solve        |      1   |        1 |        1 |

Post-injection
| Indicator                            |  Average |      Min |      Max |
|:-------------------------------------|---------:|---------:|---------:|
| time step size [s]                   |    79.78 |        1 |      120 |
| # nonlinear iterations per time step |     1.00 |        1 |        8 |
| # linear iterations per solve        |      1   |        1 |        1 |

