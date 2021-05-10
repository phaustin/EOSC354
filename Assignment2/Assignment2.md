---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.3'
      jupytext_version: 1.11.2
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

2. Generate the following time series by setting `t = np.arange(1024)` and issuing the following commands in Python. Plot each function using the plot command `plt.plot(t, a)` and use the syntax to determine the function that you are actually plotting for c), d), e). You can save paper using the "`plt.subplot`" command. Write each function down in standard mathematical format (*e.g.* ${e}^{-t}\textrm{cos}2{\pi}t$) and comment on the nature of each time series.  
a) `a = np.random.rand(len(t))`  
b) `a = np.exp(-np.maximum(np.abs(t),500)/100)*50`  
c) `a = 10*np.exp(-((t-500)/50)**2)`  
d) `a = np.exp(-np.abs(t-500)/100)*np.cos(2*np.pi*t/100)`  
e) `a = np.exp(-np.abs(t)/100)*np.sqrt(np.sin(2*np.pi*t/40)+1)`  

```python
import matplotlib.pyplot as plt
import numpy as np

t = np.arange(1024)

# plot for a
a = np.random.rand(len(t))
plt.subplot(2, 3, 1)
plt.plot(t, a)

# plot for b
a = np.exp(-np.maximum(np.abs(t),500)/100)*50
plt.subplot(2, 3, 2)
plt.plot(t, a)

# plot for c
a = 10*np.exp(-((t-500)/50)**2)
plt.subplot(2, 3, 3)
plt.plot(t, a)

# plot for d
a = np.exp(-np.abs(t-500)/100)*np.cos(2*np.pi*t/100)
plt.subplot(2, 3, 4)
plt.plot(t, a)

# plot for e
a = np.exp(-np.abs(t)/100)*np.sqrt(np.sin(2*np.pi*t/40)+1)
plt.subplot(2, 3, 5)
plt.plot(t, a)

plt.show()
```
