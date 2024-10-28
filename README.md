## 1. Some Mathematical Theory

In this tutorial, I discuss three types moving average techniques. Before I discuss the mathematics, I will start by explaining what moving average means in layman's terms.

In mathematics, average is simply a value that represents the central value or the most occuring value in the dataset. There are three main types of average: arithmetic mean (your normal average), median, and mode. When we talk about average most people just assume the first one, that is, arithmetic mean or average. 
Assume you have the following simple dataset $D=[3, 7, 7, 8, 10]$. The mean, median and mode of this dataset is $7$.

In this tutorial, I will focus on the first one, the arithmetic mean; so when I say average I will be referring to arithmetic mean unless stated otherwise. Suppose you have the dataset $D=[d_1, d_2, ..., d_N]$ of $N$ numbers. Then your normal equally weighted average $A[D]$ is:
$$A[D] = \frac{d_1+d_2+...+d_N}{N} = \frac{1}{N}\sum_{i=1}^{N} d_i$$.
From this formulation, one thing that you will notice is that this average $A[D]$ is a fixed, single number. Generally, it is given by:
$$A[D] = \frac{\sum_{i=1}^{N} w_i d_i}{\sum_{i=1}^{N} w_i}$$.

Now, what if this average was dynamic? In a way that at each and every point $k$ within the dataset, so that for every $k=1,2,...N$, we get a new average up to that point. This is what moving average is - an average that changes with each position in the dataset. There are various types of moving averages. 
In this tutorial, I will look at two: simple moving average (SMA) and weighted moving average (WMA).

I will introduce what we call $\textit{window size}$ denoted by $n$ which is the number of points to average over. The following condition must always hold $1 < n \leq N$ and $n \leq k \leq N$ to ensure that there is smoothing. 
Let's see what this means with a simple numerical example using the dataset $D=[3, 7, 7, 8, 10]$. I have $N=5$ data points, so $n \leq k \leq 5$, meaning that can be $n=2, 3, 4, 5$. Why not $n=1$? That is because for $n=1$ there will be only one point in the dataset and that will be $d_k$ and that will be the simple moving average. For $n=2$, I have $2 \leq k \leq 5$, meaning $k=2,3,4,5$. This means that I will get four averages at $k=2,3,4,5$. This type of average is called simple moving average.

### Simple Moving Average
The simple moving average ensures that the data points in the dataset are equally weighted within the window:

$$A_{n, k}[D]=\frac{1}{N} \sum_{i=0}^{n-1} d_{k-i}$$.

### Weighted Moving Average
The weighted moving average imposes weights on the data points within the window:
$$A_{n,k, W} [D] = \frac{\sum_{i=0}^{n-1} w_i d_{k-i}}{\sum_{i=0}^{n-1} w_i}$$,
where we assume that $\sum_{i=0}^{n-1} w_i=1$.

There are other various types of moving averages such as expontential moving average, cumulative moving average, least squares moving average, among others.
