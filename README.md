## Yet another histogram

![Python application](https://github.com/aminnj/yahist/workflows/Python%20application/badge.svg)
[![Documentation Status](https://readthedocs.org/projects/pip/badge/?version=latest)](https://aminnj.github.io/yahist/)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/aminnj/yahist/master?filepath=examples%2Fbasic.ipynb)


### Overview

Histogram objects (1D and 2D) with easy manipulations (`numpy`), plotting (`matplotlib`), and fitting (`scipy`/`iminuit`).

```python
import numpy as np
from yahist import Hist1D

h = (Hist1D(np.random.normal(0, 1, 1000), bins=100, label="data")
     .rebin(2)
     .normalize()
    )
h.plot(show_errors=True, color="k")
h.fit("peak * np.exp(-(x-mu)**2 / (2*sigma**2))")
```
<img src="examples/plot1.png" height="200" width="300"/>

```python
import pandas as pd

df = pd.DataFrame(np.random.normal(0, 1, size=(10000, 2)), columns=["A", "B"])

h = Hist2D(df, bins=np.linspace(-3, 3, 30))
h.plot(logz=True, cmap="cividis")
```
<img src="examples/plot2.png" height="200" width="300"/>

Much more functionality is showcased in the example notebook below.

### Examples ([API docs](https://aminnj.github.io/yahist/))

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/aminnj/yahist/master?filepath=examples%2Fbasic.ipynb)

(static [nbviewer](https://nbviewer.jupyter.org/url/github.com/aminnj/yahist/blob/master/examples/basic.ipynb) if Binder is slow)

### Installation

```bash
pip install yahist
```
or to install the latest version directly from github
```bash
pip install git+git://github.com/aminnj/yahist.git#egg=yahist -U
```
