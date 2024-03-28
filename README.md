Practical 6

Standard probability distributions-
a. Calculation of probability, mean and variance based on Binomial distribution
b. Calculation of probability based on Normal distribution

Probability Density Calculation

The following examples demonstrate how to calculate the value of the cumulative
distribution function at (or the probability to the left of) a given number.

Normal (0,1) Distribution :
    > x <- c(-2,-1,0,1,2)
    > x
Output
    > pnorm(x)
Output
Binomial (n,p) Distribution :
    > x <- c(0,1,2,5,8,10,15,20)
    > pbinom(x,size=20,prob=.2)

Quantiles

The following examples show how to common the quantiles of some common distributions for a
given probability (or a number between 0 and 1).

Normal(0,1) Distribution :
    > y <- c(.01,.05,.1,.2,.5,.8,.95,.99)
    > qnorm(y,mean=0,sd=1)
Output
Binomial (n,p) Distribution :
    > y <- c(.01,.05,.1,.2,.5,.8,.95,.99)
    > qbinom(y,size=30,prob=.2)

Random Variable generation

Normal(,) Distribution :
The first sample is from N(0,1) distribution and the next one from N(5,1) distribution    
> z <- rnorm(10) 
> z
Output
> w <- rnorm(1000,mean=5,sd=1)
> 	
Graph Output
Binomial(,) Distribution :
> k <- rbinom(20,size=5,prob=.2)
> k

Density Plots

Plotting the probability density function (pdf) of a Normal distribution :
 > x11()
 > x <- seq(-4.5,4.5,.1)
 > normdensity <- dnorm(x,mean=0,sd=1)
 > plot(x,normdensity,type="l")
Graph Outputs
Plotting the probablity mass function (pmf) of a Binomial distribution :
  > par(mfrow=c(2,1))
  > k <- c(1:30)
        > plot(k,dbinom(k,size=30,prob=.15),type="h")
  > plot(k,dbinom(k,size=30,prob=.4),type="h")
  > par(mfrow=c(1,1))
Graph Ouputs
Discrete Probabilities For a discrete random variable, you can use the probability mass to find 
    > dbinom(3,size=10,prob=0.5)

Q-Q Plot

Use the function qqnorm for plotting sample quantiles against theoretical (population) quantiles of standard normal random variable.
Example :
    > stdnormsamp <-rnorm(100,mean=0,sd=1)
    > normsamp <- rnorm(100,mean=5,sd=1)
    > binomsamp <-rbinom(100,size=20,prob=.25)
    > par(mfrow=c(2,2))

Graphical Output
    > qqnorm(stdnormsamp,main="Normal Q-Q plot : N(0,1) samples")
Graphical Output
    > qqline(stdnormsamp,col=2)
Graphical Output
    > qqnorm(normsamp,main="Normal Q-Q plot : N(5,1) samples")
Graphical Output
    > qqline(normsamp,col=2)
Graphical Output
    > qqnorm(binomsamp,main="Normal Q-Q plot : Bin(20,.25) samples")
Graphical Output
    > qqline(binomsamp,col=2)
Graphical Output
