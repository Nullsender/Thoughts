+++
date = '2024-12-21T12:14:07+01:00'
draft = false
title = 'Day 2 Blog Post'
+++

## Centrality in R
Heterogeneity is an almost universal fenomena. Trying to model the world we make plenty of errors, and furthermore nature itself varies all the time.
Despite this measurements often has a tendency to cluster round some central values. It is adventageous to attempt to capture and quantify this central tendency.


### The arithmetic mean
The arithmetic mean refers to the most commen quantitative measure of central tendency. In fact it is so commen that most just refer to it as the mean. Say one have a vector
$y\in\mathbb{R^n}$ with $n$ reel entries, then the arithmetic mean denoted $\bar{y}$ is defined as follows

$$
	\bar{y}=\frac{\sum_{i=0}^n y_n}{n}.
$$ 

Using R one could define a function as follows

arithmetic.mean <- function(x) 
{
	sum(x)/lenth(x) 
}.

Now the arithmetic mean is easily calculated e.g.

data <- c(29,5,1,6,99,2,4,5,6,1,2)

arithmetic.mean(data)
    [1] 14.54545

R also have the build in function mean() which also returns the arithmetic mean

mean(data)
    [1] 14.54545


A fault of the arithmetic mean is that it is quite sensitive to outliers.

### The median
Another measure of central tendency is the median, which is the middle value of the ordered (smallest to largest) dataset or the 50th percentile. For a vector with an odd amount of entries there is an exact
middle value which splits the set in two. Whereas for an even amount of entries there is not a single value splitting the dataset in two. In this case the medium will be defined as the arithmetic mean of 
the two middle values. Hence in R a function to calculate the mean can be constructed as follows

med <- function(x) {

	if(length(x) %% 2) sort(x)[ceiling(length(x)/2)]
	else (sort(x)[length(x)/2] + sort(x)[length(x)/2 + 1])/2
}.

Now the median can be calculated as follows

med(data)
    [1] 5,

also the build in function median() can be used

median(data)
    [1] 5.

## The geometric mean
The geometric mean is the n'th root of the product of the data. 

$$\hat{y}= \left(\Pi y\right)^{\frac{1}{n}}$$

## The harmonic mean

--MORE TO COME--
