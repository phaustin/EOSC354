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

2. Obtain the convolution of the two time sequences $$a_k = (6,-5,1,0,-1,3,-2)$$ and $$b_k = (1/2,1/2)$$ Verify your results using your Python `convolve` function from the previous lab. Why is this operation called a *moving average*? (Problem 2.2 on page 36 of TSAITG).

<!-- #region -->
3. Show that the deconvolution of the time sequence $$c = (1,5,14,27,34,32,17,14)$$ with $$a = (1,2,3,1,2)$$ is $$b = (1,3,5,7)$$. Investinate the elements of *b* beyond the given sequence (i.e. compute what $b_4$, $b_5$, and $b_6$ would equal). Do this by hand and then check your solution by programming equation (2.14) $$b_p=\frac{c_p-\sum_{k=1}^{p}a_kb_{p-k}}{a_0}$$ into a Python function just like your `convolve` function from last week. (Based on Problem 2.3 on page 36 of TSAITG). For example, the function `deconv` would look like:
```python
def deconv(c, a):
#
# Comments
#
    
        P = len(c) # number of points in c
        N = len(a) # number of points in a
        M = P+1-N # number of points that should be in b
    
        # create b
        b = np.zeros(M)
    
        # loops and variable definitions required to compute b
    
        return b
```
<!-- #endregion -->

4. Show that the discrete Fourier transform of the sequence $$(0,1,-1,0)$$ is $$(A_0,A_1,A_2,A_3)=[0,1/4(1-i),-1/2,1/4(1+i)]$$ using the discrete Fourier transform equation: $$A(\omega) = 1/N\sum$$

```python
import matplotlib.pyplot as plt
import numpy as np

###QUESTION 3

def deconv(c, a):
    P = len(c)
    N = len(a)
    M = P+1-N

    b = np.zeros(M)

    for i in range(M):
        terms = 0
        for j in range(1, i+1):
            terms += a[j]*b[i-j]
        b[i] = (c[i]-terms)/a[0]

    return b


a = np.array([1, 2, 3, 1, 2])
c = np.array([1, 5, 14, 27, 34, 32, 17, 14])

print(deconv(c, a))


###QUESTION 4

r = [0, 1, -1, 0]
R = np.fft.fft(r)

fig, plots = plt.subplots(2)

plots[0].plot(np.abs(R))
plots[0].set_title('Amp Spectrum')

plots[1].plot(np.arctan2(R.imag, R.real))
plots[1].set_title('Phase Spectrum')

plt.show()

### QUESTION 6

fig2, plots = plt.subplots(2, 3)

counter = 0
for i in range(2):
    for j in range(3):
        q = [1, -1] + counter*[0]
        Q = np.fft.fft(q)
        plots[i, j].plot(np.abs(Q))
        plots[i, j].set_title(str(counter+2) + ' terms')
        counter += 1


plots[1, 2].clear()
q = [1, -1] + 10000*[0]
Q = np.fft.fft(q)
plots[1, 2].plot(np.abs(Q))
plots[1, 2].set_title('10002 terms')

plt.show()

```
