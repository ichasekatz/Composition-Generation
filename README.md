# Ni-Based Composition Generator

This repository contains a Jupyter notebook for **systematic generation of Ni-based alloy compositions** with user-controlled resolution, dopant ranges, and balance constraints. The workflow is designed for **materials design and dataset generation**, producing composition tables suitable for downstream modeling, optimization, or simulation.

The main file is:

- `Comp_Gen.ipynb`

---

## What This Notebook Does

The notebook performs the following steps:

1. **Defines compositional resolution**
   - User-specified resolution (e.g., 1/200 = 0.005)
   - Controls the granularity of generated compositions

2. **Generates alloy composition sections**
   - Base alloy components
   - Stabilizers
   - Dopants
   - Sections are generated independently and then combined

3. **Balances Nickel (Ni) automatically**
   - Ni is treated as the balance element
   - Remaining elemental fractions are subtracted from 1.0
   - Invalid compositions (negative Ni) are removed

4. **Converts between representations**
   - Atomic percent
   - Weight percent (using molar masses)

5. **Exports composition datasets**
   - DataFrames suitable for CSV / HDF5 storage
   - Ready for machine learning, thermodynamic modeling, or screening

---

## Key Features

- Reproducible composition generation (`np.random.seed(42)`)
- Explicit control over compositional resolution
- Automatic balance enforcement for Ni
- Clean Pandas-based data handling
- Designed for extensibility (optimization, filtering, scoring)

---

## Dependencies

### Standard library (no install required)
- os
- itertools
- collections
- glob
- random
- time
- ast
- re

### Required packages
Install via **Pixi** (recommended):

- python (3.10 recommended)
- numpy
- pandas
- matplotlib
- h5py (if saving datasets)
- tqdm (progress tracking)

Example setup:
```bash
pixi init
pixi add python=3.10 numpy pandas matplotlib h5py tqdm
pixi add ipykernel
