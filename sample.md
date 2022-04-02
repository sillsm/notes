---
jupyter:
  colab:
    name: Copy of Curba A.ipynb
  kernelspec:
    display_name: Python 3
    name: python3
  language_info:
    name: python
  nbformat: 4
  nbformat_minor: 0
---

::: {.cell .markdown id="mBO9OyQt4dBM"}
# Section A

Let\'s discuss manifolds. We\'re going to be pictoral and stay mostly
with this, then we\'re going to get specific and examine some of these
ideas in lcoal coordinates, symbolically. We will come right up to, but
won\'t explciitly define, curvature.

# Let\'s discuss it

$$
c = \sqrt{a^2 + b^2}
$$
:::

::: {.cell .code colab="{\"base_uri\":\"https://localhost:8080/\"}" id="X3B76dF-s-KF" outputId="2d713a3e-e65d-4f06-fda4-55e612f3bc7d"}
``` {.python}
import sys
!{sys.executable} -m pip install kaleido
```

::: {.output .stream .stdout}
    Requirement already satisfied: kaleido in /usr/local/lib/python3.7/dist-packages (0.2.1)
:::
:::

::: {.cell .code execution_count="1" colab="{\"height\":838,\"base_uri\":\"https://localhost:8080/\"}" id="gf9WZX3R44bz" outputId="7f4f68fb-2446-4df7-8362-04c6a34c7190"}
``` {.python}
import numpy as np
import matplotlib.pyplot as plt

x1 = np.linspace(0.0, 5.0)
x2 = np.linspace(0.0, 2.0)
y1 = np.cos(2 * np.pi * x1) * np.exp(-x1)
y2 = np.cos(2 * np.pi * x2)

fig, axes = plt.subplots(nrows=1, ncols=2, figsize=(20, 5))
axes[0].plot(x1, y1)
axes[1].plot(x2, y2)
#fig.tight_layout()

r = np.arange(0, 2, 0.01)
theta = 2 * np.pi * r

fig, ax = plt.subplots(subplot_kw={'projection': 'polar'})
ax.plot(theta, r)
ax.set_rmax(2)
ax.set_rticks([0.5, 1, 1.5, 2])  # Less radial ticks
ax.set_rlabel_position(-22.5)  # Move radial labels away from plotted line
ax.grid(True)

ax.set_title("A line plot on a polar axis", va='bottom')
plt.show()

X = np.arange(-10, 10, 1)
Y = np.arange(-10, 10, 1)
U, V = np.meshgrid(X, Y)

fig, ax = plt.subplots()
q = ax.quiver(X, Y, U, V)
ax.quiverkey(q, X=0.3, Y=1.1, U=10,
             label='Quiver key, length = 10', labelpos='E')

plt.show()
```

::: {.output .display_data}
![](vertopal_c8aeed6779ee4f4e8dc78ab011fcd079/27810261bda872cf56fd603a6c86941ca00e5254.png)
:::

::: {.output .display_data}
![](vertopal_c8aeed6779ee4f4e8dc78ab011fcd079/5992da7b4dbe30623273009d63ea8b7b770ac9dc.png)
:::

::: {.output .display_data}
![](vertopal_c8aeed6779ee4f4e8dc78ab011fcd079/c51713ec10c6adbad3b22cd2b972f6ec166c4f5c.png)
:::
:::
