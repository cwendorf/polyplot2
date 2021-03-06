## Tutorial for Polyplot2

### The Basic Polyplot

In order to demonstrate the finer points of a polyplot, the following code simulates 1000 scores from a positively skewed unimodal distribution and then calls `polyplot2` using the default options.

```r
Scores <- c(rnorm(n=600,mean=100,sd=15),rnorm(n=200,mean=115,sd=20),rnorm(n=200,mean=130,sd=25))
polyplot2(Scores)
```

![](./figures/polyplot2.jpeg)<!-- -->

By default, the function labels all of the points and provides summary statistics in the margin. Generally speaking, each level/row provides a different category of measures of location and spread.

- First/Top: Provides the mode of the distribution, with the sample size listed in the right margin
- Second: Provides the quartiles (and median) of the distribution, with the interquartile range divided by 2 in the right margin
- Third: Provides the means of the halves (and the whole) of the distribution, with the mean absolute deviation from the median in the right margin
- Fourth: Provides the mean of the distribution and points +/- one standard deviation from the mean, with the standard deviation in the right margin
- Fifth/Bottom: Provides the range (and midrange) of the distribution, with the range divided by 2 in the right margin

### Using the PolyPlot to Determine Shape

The following code demonstrates some of the available options for customizing the polyplot. Similarly, it demonstrates how the PolyPlot does a good job of approximating the shape of the underlying distribution.

```r
par(mfrow=c(1,2))
polyplot2(Scores,plot="frequency",type="bar",values=FALSE,main="PolyPlot2 plus Frequency Histogram",col="darkblue",bg="darkgoldenrod")
polyplot2(Scores,plot="density",type="curve",values=FALSE,main="PolyPlot2 plus Density Curve",col="darkblue",bg="darkgoldenrod")
```

![](./figures/polyplot2plus.jpeg)<!-- -->

Further explanation of the polyplot and how it can be used to understand the shape of the distribution is available in Seier and Bonett (2011).
