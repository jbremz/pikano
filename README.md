# KAN PINO

The idea here is fairly straightforward: KANs seem like natural choices for modelling physical systems, why not integrate them into a neural operator + PINN framework?

I'll try some very simple experiments along these lines here.

## Experiments

### `01-basic-mlp-deeponet.ipynb`

Simple baseline to get going.

### `02-basic-kan-deeponet.ipynb`

Switching the MLP in the previous experiment for a KAN. This also means I can do away with the "sensors" framework and just input the raw parameters for the damped harmonic oscillator: `ζ` and `ω0`. This means the network only has 3 inputs (with the extra `y` coordinate).

Managed to get an order of magnitude lower error with the KAN as opposed to the MLP using only ~500 parameters as opposed to 80,000 that the MLP used 👀.

### `03-PIKAN.ipynb`

Now trying to do away with the generated data and using a physic-informed loss instead. This will consist of a boundary condition loss $L_{BC}$ and a physics loss $L_{phys}$.

I will need to change the network so that it also has the boundary conditions as input this time.