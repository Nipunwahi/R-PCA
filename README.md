# R-PCA
Robust Principal Component Analysis

We study the state-of-the-art approaches for the Low-Rank Matrix Recovery
Problem. This problem is described using the so called Robust
Principal Pursuit formulation. The optimization procedures
in the literature approximate the problem and use proximal
gradient and alternating minimization methods to obtain the
solution. We analyse the performance of these procedures on
a dual formulation for the optimization problem and extend
these techniques to applications such as foreground separation
and time-series analysis as our contribution. Furthermore,
we comment on the implementation issues for each of these
procedures and their practicality for the discussed applications.

## Problem Statement
Given a matrix D break it into two components such D = L + S trying to minimize the sum of rank of L and norm of S. This formulation is very hard to solve, so instead of solving for rank, we use the nuclear norm of L which is the sum of eigenvalues as a proxy for rank. This formulation is convex and can be solved in multiple ways.

## Use Cases

### Foreground Separation
We were able to separate foreground from background of videos from cctv cameras using this method without training and rather efficiently in contrast with other NN based methods which require loads of training and compute to work. First Image is real image, second is separated background and third is foreground

<img src="./outputs/true.png" width="450">
<img src="./outputs/l.png" width="450">
<img src="./outputs/s.png" width="450">


Another scenario of busy street on crossing

<img src="./outputs/street_true.png" width="450">
<img src="./outputs/street_l.png" width="450">
<img src="./outputs/street_s.png" width="450">


### Time Series Analysis of Financial Data
In this application, we propose a novel hypothesis that  equity prices are linearly correlated and form a low-rank matrix and the anomalies in the data form the sparse-noise. Each row of our data matrix $D$ represents the normalized value of a stock over a fixed period. We claim that RPCP can be used to find anomalies in stock prices to determine the global sentiment in the economy. The impact of this formulation is realised in medical applications such as despeckling ultrasound data. 

