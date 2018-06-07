---
layout: post
title: Apex Probes Vs. Handheld Probes
date: '2018-06-06'
categories: Analysis
tags: [Apex]
---

# <center> R Analysis of the Apex Probes Vs. the Handheld Probes

* Hypotheses:
  - Null:
    - There will be no difference between the handheld and Apex Probes
  - Alternative:
    - The handheld probes will be more precise than the Apex probes
* Steps:
  - Test for assumptions of normality
    - **Density Plots**
![](https://github.com/maxzav17/Zavell_Lab_Notebook/blob/master/images/Apex.Density.png?raw=true)
**Fig 1.** Density Plots for each Quantitative Measurement to assess the normality in the data

    - **Q-Q Plots**
![](https://github.com/maxzav17/Zavell_Lab_Notebook/blob/master/images/Apex.Q-Q-Plot.png?raw=true)
**Fig 2.** Q-Q Plots for each Quantitative Measurement to assess the normalitt in the data

    - **Shapiro-Wilks Test**

| Measurement | P-Value |
|-------------|---------|
| pH    | 0.2934   |
| Temperature   | 2.932e-09   |
| PAR   | 0.5702  |
Table 1. P-Values from the Shapiro-Wilk Normality Test. We can assume normality for pH and PAR because the p-values are greater than 0.05. Does not assume normality for Temperature.

* Scatterplots:
  - **Points**
![](https://github.com/maxzav17/Zavell_Lab_Notebook/blob/master/images/Apex.Scatter.1.png?raw=true)
**Fig 3.** Scatterplot of the Handheld Vs. Apex Probes. The last three points are: 4/5/2018, 4/6/2018, and 4/9/2018.

  - **Points with lines**
![](https://github.com/maxzav17/Zavell_Lab_Notebook/blob/master/images/Apex.Scatter.2.png?raw=true)
**Fig 4.**  Scatterplot of the Handheld Vs. Apex Probes. The last three points are: 4/5/2018, 4/6/2018, and 4/9/2018. Lines do not represent data.

* Other Graphs
  - **Boxplot**
![](https://github.com/maxzav17/Zavell_Lab_Notebook/blob/master/images/Apex.Boxplot.png?raw=true)
**Fig 5.** Boxplots of Each Quantitative Measurement

* T-Test and Wilcox Test:
  - **Two Sample T-Test**

| | T-Value   | Degrees of Freedom | P-Value | 95 % CI |
|-|-----------|--------------------|---------|---------|
| pH   | 1.1098   | 31.791  | 0.2754 | -(0.0482 - 0.1635)   |
| PAR   | -1.3502   | 22.776   | 0.1902   | -(14.1991 - 2.9873)   |
**Table 2.** T-Tests were conducted in R.

  - **Wilcox Test**

| | W-Value | P-Value |
|-|---------|---------|
| Temperature   | 116.5   | 0.3331   |
**Table 3.** The Test was conducted in R.

* Conclusions:
  - We fail to reject the null hypothesis for all three measurements: pH, Temperature, and PAR.
Both visual and statistical tests were conducted to test for normality (Q-Q Plots, Density Plots, and
Shapiro-Wilk Normality Test). Temperature had a P-Value of 2.932e-09 and was therefore smaller than
0.05 and does not assume normality. Thus, a Wilcox Test was conducted on temperature instead of a
two-sample t-test. We fail to accept the null hypothesis because the p-value is above 0.05. Therefore, it
can be assumed that there is no difference between the Apex and handheld probes.
