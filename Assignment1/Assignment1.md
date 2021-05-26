---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.3'
      jupytext_version: 1.11.1
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

<center> <h2>The University of British Columbia</h2> </center>
<center> <h2>Earth and Ocean Sciences 354</h2> </center>
<center> <h3>Geophysical Time Series Analysis</h3> </center>
<center> <h3>Problem Set # 1</h3> </center>


*Due: September 14, 2020*


#### Learning Goals:
* Learn digital recording terminology (dynamic range, sampling frequency, gain, etc.)
* Do calculations with dynamic range
---


Read Chapter 1 of TSAITG and answer the following questions concerning the dynamic range of geophysical instrumentation. (TSAITG is "_Time Series Analysis and Inverse Theory for Geophysicits_", David Gubins.)

```python
# TODO Before Sept: We should clarify copyright and proper citation for the text.
```

1. A geophone (cheap seismometer used for hydrocarbon exploration) is quoted at 3.28 V/(in/s). What is the ground motion in m/s corresponding to an output of 1 mV?


2. A simple seismic acquisition system uses 14 bits to record the signal digitally as an integer. Calculate the dynamic range of this instrument. Express your answer in decibels (dB) using the formula
$$
\mathrm{dB} = 20\mathrm{log}_{10}(\text{dynamic range})
$$


3. The geophone in question 1 outputs linearly over the range 1$\mu$V-0.1 V. What is its dynamic range in dB?


4. You attach the geophone in question 1 to the recorder in question 2 and set the recorder's gain to digital count/$\mu$V. What is the maximum ground motion that can be recorded?

```python

```
