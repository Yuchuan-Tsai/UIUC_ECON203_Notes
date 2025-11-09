## Lesson 1:  Different Types of Data and Variables 

### Observational Study
An *Observational Study* is a set of data that is collected without any intervention by the researcher
1. You have no control over who does what in an observational study
2. These data are collected by observing what people do on their own
3. These studies may benefit from randomization, but would be ethically complicated

### Randomized Experiment
A *Randomized Experiment* is a set of data where a researcher can assign variables certain values to observe effects
1. These data sets are desirable because the randomization minimizes bias
2. This fact helps establish clear casual relationships
3. However, these studies may be less ethical than observational studies

RCT = *Randomized controlled trial*

### Types of Data
#### Cross-sectional data
*Cross-sectional data*: Cross-sectional data only has heterogeneity coming from who is being surveyed 
- 在某一个时间点上对多个个体、单位或观察对象进行的测量和收集的数据
- For example: If I take all of your characteristics today and put those in a data set, that's a cross-sectional data set
- Importantly, there's only one point in time that data is collected

#### Time series data set
*Time series data*:Time series data differs from cross-sectional because the heterogeneity only comes from when the data is collected
- For example: I choose one student in this class and record their grade in the course every week
- Importantly, there is only one unit being surveyed, if I collected data on multiple students in the same way, the data set is no longer a time series dataset

#### Pooled Cross-sectional data
pooled cross-sectional data combines aspects of both time series and cross-sectional data
This means that variation will come from both who/what is being observed and when the data is collected
eg. measure the characteristics of students in ECON203 on the first day of class for 10 semesters
1. the students are different, so there are different units being studied
2. data is also collected at different points in time

### Panel data
*Panel data* is extremely similar to pooled cross-sectional data, it measures the exact same people at each point in time
**If even one unit of observation drops out or changes, the data set is no longer a panel data set**

### Type of variables
- Numeric Variable 
	1. Continuous
	2.  Discrete
- Categorical Variable
	1. Nominal
	2. Ordinal
- Dummy Variable 

#### Numeric Variables
A *numeric variable* represents measurable quantities that can be used to describe something

> *Just because a variable has numbers in it does not mean the variable is numeric*

We can split numeric variables into *continuous* and *discrete* variables
	*Continuous Variables*
		Theoretically have an infinite amount of values
		Things like age, height, and so on
	*Discrete Variables*
		Might not have many values, but sill quantify how much or how many with regards to the variable
		Things like age in years 

#### Categorical Variables
A *categorical variable* provides information about what group an observation belongs to
	eg. state a student is from
Categorical variables can be text variables, but can also be represented by numbers as well

Categorical variables can be *ordinal* or *nominal*
	*Ordinal Variables*
		Are variables that rank the information that is gathered
		However, the gaps between the ranks may not matter
		eg, year in school, status as low, medium, or high income individual
	Nominal Variables
		Are purely descriptive, the order does not necessarily matter
		eg, state of birth, sex, the type of advertisement you see on your phone
> Orinal 有排序，Nominal 没有

#### Dummy variable
A *dummy variable* indicates if the condition for a variable is met, This variable takes a value of 0 or a value of 1
	eg. A dummy variable called "Male" gives value 1 if the respondent is male, 0 otherwise
These are useful when you have a categorical variable you want to break into multiple parts in a regression

## Lesson 2: Introduction to Probability

### R functions
```R
sum(x) #the sume of x
mean(x) #the arithmetic mean of x
median(x) #the median of x
var(x) #the variance of x
sd(x) #the standard deviation of x
plot(x = x_var, y = y_var) #a scatter plot of x and y
c(1, 2, 3) #creates a vector(1,2,3). You can assign it a value by doing x <- c(1,2,3)
```

Suppose we have a data set called "example"
```R
example$x #pulls out the variable called x from the data set "example"
example$x > 3 #checks every value of x from the data set "example" to see if it is greater than 3
example$x > 3 & example$x <= 5 #Checks every value of x from the data set "example" to see if it is greater than 3 and less than or equal to 5
example$x > 3 | example$x <= 5 #checks every value of x from the data set "example" to see if it is greater than 3 or less than or equal to 5
```

### Random Variable
#### Non-Random Variable
Non-Random Variable only has one possible value

#### Random Variable
> A random variable X is a mapping from the sample space(Ω) of an experiment to of an (sometimes)simpler sample space($Ω_X$) 
> Mathematically:   X: Ω → $Ω_X$
> 
> A sample space(Ω) is a set of all possible outcomes of an experiment

### Introduction to Probability
While we can acknowledge things are random, we would like to know the rate at which events occur
We call this rate **probability**
Probabilities are the rates we can expect outcomes of a random variable to occur at

In general, you can think of probability as the number of outcomes you want divided by the total number of possible outcomes
P(X = x) = $\frac{\text{Wanted Outcomes}}{\text{Total Outcomes}}$

Population probabilities will not necessarily be reflected in small samples
However, as you get more and more observations of the random variable, the observed probability will get closer to the population probability

## Lesson 3:  Properties of Probabilities and Total Probabilities
### Properties of Probabilities
A *probability* is the chance that an event occurs. This is defined as the ratio of desired cases to all possible cases (n)
P(X=x) = $P(X = x) = \lim_{n \to \infty} \frac{\text{count}(X = x)}{n}$

If $x \in A$ The following are true
1. A possible value for x is the empty set, $\emptyset \in A$ 
2. If a set x can be observed in A, then it's complement $x^c$ can also be observed as an event in A
3. Any union of $x_i \in A$ can also be individually observed as a possible event in A

For any $x \in A$
	P(x) $\geq$ 0
We cannot have the negative probabilities

If a group of sets $x_i$ are disjoint, then the probability of the union of those sets is the sum of the individual probabilities of the sets
$\cup$ is a symbol meaning "Union"
*Disjoint* means that the sets have no common elements

In conclusion:
1. P($\emptyset$ = 0)
2. P($A^c$) = 1 - P(A)
3. 0 $\leq$  P(A) $\leq$ 1

Disjoint means that for two events A and B
A $\cap$ B = $\emptyset$ $\to$ P(A $\cap$ B) = 0
If we do not have disjoint events, then we count the intersection twice by adding up the individual probabilities
Thus, we subtract it once after adding the two events together:
P(A $\cup$ B) = P(A) + P(B) - P(A $\cap$ B)

#### Independent Events
Two events A and B are independent if and only if 
	P($A \cap B$) = P(A)P(B)
You cannot always assume events are independent
> Two random variables X and Y are independent if, for **all** events X = x and Y = y,
> P(X=x, Y=y) = P(X=x)P(Y=y)
> All events must be independent from each other for the random variables to be independent

#### Dependent Events
If two events are not independent, then they are called dependent events
Dependent events are very useful for prediction
	If you see one event, it may allow you to update your beliefs about a second event occurring
	
### Total Probability
A and $A^c$ are disjoint events. Thus, we can see that
P(B) = P(A $\cap$ B) + P($A^c \cap B$ )
This works with multiple events, not just two events

If $B_i$ are mutually exclusive and are collectively exhaustive, you can invoke that **law of total probability**

$P(A) = \sum _{i = 1} ^ {\infty} P(A \cap B_i)$

#### Mutually Exclusive
Two events that cannot occur that the same time, it is a same thing as saying that events are disjoint

#### Collectively exhaustive
Means that at least one of the events has to occur


## Lesson 4: Conditional Probability

What happens if we already observe something else?
The "Something else" is known as a condition

$P(A|B) = \frac{P(A \cap B)}{P(B)}$
P(A|B)P(B) = $P(A \cap B)$
#### Bayes' Theorem
$P(A|B) = \frac{P(B|A)P(A)}{P(B)}$

#### Total Probability
> if $A_i$ are mutually exclusive and are collectively exhaustive, you can invoke the *law of total probability*
> $P(B) = \sum_{i=1}^{\infty} P(A_i \cap B)$
> $P(A_n|B) = \frac{P(B|A_n)P(A_n)}{\sum_{i=1}^{\infty} P(A_i \cap B)}$

## Lesson 5: Probability Distribution
### Discrete Probability Distributions
Discrete random variables have countable event spaces
Countable events $\to$ we can assign probabilities to them
At the same time, $P(X = x) \geq 0$ and all probabilities sum to 1

> A probability mass function (PMF) is a function that gives the probability that a discrete random variable is exactly equal to some value
> The PMF is the function $p_x(x): R \to [ 0, 1 ]$ (maps real numbers into probabilities):
> $p_x(x) = P(X = x), -\infty < x < \infty$

Two basic requirement of PMF:
1. if x is in the domain of $p_x(x)$, then P(X=x) = $p_x(x) \geq 0$
2. $\sum_{x \in X} p_X(x) = 1$
#### Cumulative Distribution Function
A cumulative distribution function is a non-decreasing function 
$F_x(x) = P(X \leq x)$ such that
$\lim_{x \to -\infty} F_X(x) = 0$
$\lim_{x \to \infty} F_X(x) = 1$

#### bernoulli random variable
**Bernoulli random variables** have the property that there are two outcomes, for example, flipping a coin.
You assign one outcome probability p, and one outcome probability 1-p

#### Binomial Distribution
> A **binomial distribution** is a distribution that represents the sum of n independent bernoulli random variables with probability p. The distribution's mass function follows the following form:
> $p_x(x) = \binom{n}{x}p^x(1-p)^{n-x}$
> We must specify the parameters "n" and "p" to properly define the binomial distribution

#### Geometric Distribution
> A **geometric distribution** is a distribution representing the number of independent trials one performs until a success is obtained
> $p_x(x) = p(1-p)^{x-1}$
> The only parameter needed to describe the distribution is the probability of a success, p

#### Poisson Distribution
> A random variable X follows a poisson distribution if we know an event occurs with a constant average rate with independent arrival times
> $p_x(x) = \frac{λ^xe^{-λ}}{x!}$
> The only parameter for this distribution is λ, which is described as the average rate of arrival
> The domain is all non-negative integers

### Continuous Probability Distributions
Continuous random variables do not behave like discrete random variables
In particular, there are an infinite amount of outcomes
Two requirements that  continuous probability distributions are valid:
1. $f_x(x) \geq 0$ for all possible values X = x
2. $\int_{-\infty}^{\infty} f_X(x) \, dx = 1$
These conditions are similar to the conditions needed for discrete probability distributions

> A continuous random variable X has a probability density function(PDF) $f_x(x)$, where $f_x(x)$ is a non-negative function, if
> P($a \leq X \leq b$) = $\int_{a}^{b} f_X(x) \, dx$
> Notice that P(X = a) = P($a \leq X \leq a)$ = $\int_{a}^{b} f_X(x) \, dx = 0$

Because $f_x(x)$ is non-negative, you can never have definite integrals that exceed 1 or go below zero
$\to$ 0 $\leq P(A \leq X \leq B) \leq 1$
Notice that this is very similar to the definition of a cumulative distributions function


## Lesson 6: Distributions and Properties of Distribution
### Continuous Probability Distribution
> A continuous random variable X has a probability density function(PDF) $f_x(x), where $f_x(x) is a non-negative function, if
> P($a \leq X \leq b$) = $\int_{a}^{b} f_X(x) \, dx$
> Notice that P(X = a) = P($a \leq X \leq a)$ = $\int_{a}^{b} f_X(x) \, dx = 0$

Requirements to make continuous probability distributions valid:
1. $f_x(x) \geq 0$ for all possible values X = x
2. $\int_{-\infty}^{\infty} f_X(x) \, dx = 1$

#### Types of continuous Distributions in this class:
1. Normal Distribution
2. T-Distribution
3. Chi-Squared Distribution
4. F-Distribution

#### The Normal Distribution
A random variable X follows a normal distribution, denoted N(μ, $σ^2$) if 
$f_X(x) = \frac{1}{\sqrt{2\pi \sigma^2}} e^{\frac{-(x - \mu)^2}{\sigma^2}}$

#### The Chi-Squared Distribution
> A random variable X follows a chi-squared distribution denoted ($\chi^2_k$) if 
> $f(x) = \frac{1}{2^{k/2} \Gamma(k/2)} x^{k/2 - 1} e^{-x/2}$
> k is known as the degrees of freedom, and is needed to describe the distribution
> The distribution is right skewed, and the domain is all non-negative numbers

The chi-squared distribution can be described as the sum of k independent standard normal variables
The sample variance of an approximately normally distributed population is a chi-squared random variable
This distribution is known as a positively skewed (right skewed) distribution
#### Formula
$\chi^2 = \frac{(n-1)S^2}{\sigma^2_0}$

#### The T-Distribution
> A random variable X follows a **T-distribution** (denoted $t_k$) if 
> $f(x) = \frac{\Gamma\left(\frac{k+1}{2}\right)}{\sqrt{\pi k} \Gamma\left(\frac{k}{2}\right)} \left(1 + \frac{x^2}{k}\right)^{-\frac{k+1}{2}}$
> In this case, k is known as the degrees of freedom, and is needed to describe the t-distribution
> T-distributions all have a mean of 0. The domain is all real numbers

The t-distribution is useful for our purposes when we have to estimate the variance of a set of normally distributed data
$t_k = \frac{Z}{\sqrt{\frac{\chi^2}{k}}}$
The numerator is a standard normal distribution, while the denominator is a $\chi^2$ distribution with k degrees of freedom

#### The F-Distribution
> A random variable X follows an F-distribution(denoted F($k_1, k_2$)) if 
> $f(x) = \frac{\sqrt{\frac{(k_1 x)^{k_1} k_2^{k_2}}{(k_1 x + k_2)^{k_1 + k_2}}}}{x B \left( \frac{k_1}{2}, \frac{k_2}{2} \right)}$
> You need to specify two degrees of freedom when describing an F-distribution
> The distribution is right skewed, and the domain is all non-negative numbers

When we do calculations, there will generally be a degree of freedom in the numerator and the denominator
The numerator degree of freedom will be the first one, and the denominator will be the second
F-distributions are useful when comparing multiple variances
### Using Distributions
#### d()
`dnorm(x)` gives the likelihood for the standard normal distribution at the point "x"
However, for discrete distributions `(dbinom())`, this will give the probability that X=x given a chosen n and p

#### p()
The `pnorm(x)` function gives the cumulative distribution function for the standard normal distribution at point "x",
A cumulative distribution function represents P(X $\leq$ x) for a random variable X
> If we want to find the probability that a normal random variable
> with mean 53 and variance 25 is less than or equal to 30, we would
> type: pnorm(q = 30, x = 53, sd = 5, lower.tail = TRUE)
> 
> If we wanted to find the probability that we flip a coin 10 times and
> end up with at least 7 heads, we would type: pbinom(q = 6, size =
> 10, prob = 0.5, lower.tail = FALSE)
> 
> Why? The lower.tail = argument assumes that if you say FALSE,
> you want P(X > x).
> 33 Continuing Distributions September 16, 2025

#### q()
The `qnorm(p, ...)` function gives the value that has probability "p" to the left of it in a standard normal distribution
### Expected Value and Variance
> The **expected value** of a random variable X is the weighted average of all possible values of X. Mathematically:
> $E(X) = \sum_{x \in X} x p_X(x)$

#### Properties of Expected Values
E(a) = a
E(aX) = aE(X)
E(X + Y) = E(X) + E(Y)
E(aX + bY) = aE(X) + bE(Y)

#### Continuous case
$E(X) = \int_{-\infty}^{\infty} x f_X(x) \, dx$

#### Central Tendency
The expected value is a measure of central tendency (mean)
median and mode are measures of central tendency as well

#### Variance
`variance`: How spread out a distribution is

> The **variance** of a random variable X is the average squared deviation of the random variable from it's expected value. Mathematically:
> $Var(x) = E[(X - E(X)^2)]$
> $\to E(X^2) - E(X)^2$

#### Properties of Variances
Var(a) = 0
Var(aX) = $a^2Var(X)$
$Var(aX + b) = a^2Var(X)$
$Var(aX + bY) = a^2Var(X) + b^2Var(Y) + 2abCov(X,Y)$
variances must be non-negative
![[Screenshot 2025-09-27 at 14.31.20.png]]
## Lesson 7: Variance and Estimators
### Samples vs. Populations
Samples will not always match the population distribution
Thus, we need to be careful when using samples
This is not limited to making sure we take enough of the population to make a sample
We rarely have access to population data(aka **census**)
### Estimators
Suppose there is some sort of parameter from a distribution that we want to know. Call this parameter θ.
We have sample data and wish to estimate the value of θ. We can call the procedure we use to estimate the parameter an **estimator**. Let's call the estimator $\hat{\theta}$  
The error of the estimator will be the difference between the estimator and the parameter, $\hat{\theta} - \theta$

We will want to minimize the **mean squared error** of the estimator
$MSE(\hat{\theta}) = \mathbb{E}\left[(\hat{\theta} - \theta)^2\right]$

#### Optimal Estimator
The optimal estimator for this class will be the one that minimizes the mean squared error
$\hat{\theta}^* = \arg\min_{\hat{\theta}} \mathbb{E}\left[(\hat{\theta} - \theta)^2\right]$
Note that “arg” denotes the argument of the minimization problem. Thus, we want the estimator $(\hat{\theta})$ that minimizes the mean squared error with respect to the parameter of interest $(\theta)$

#### Mean Squared Error Bias
> Suppose we want to estimate a population parameter $\theta$ using $\hat{\theta}$
> The `bias` of a estimator is the difference between the expected value of the estimator and the population parameter
> Mathematically:
> **bias($\hat{\theta}$) = E($\hat{\theta}$ - $\theta$)**
> If the bias of an estimator is 0, then we can say the estimator is unbiased

Thus, 
$MSE(\hat{\theta}) = \text{Var}(\hat{\theta}) + \text{Bias}(\hat{\theta})^2$
We can compare estimators by calculating the bias and variance of the estimators
The best estimator is the one that **minimizes** the mean squared error
Even if an estimator is unbiased, it still could be worse than a biased estimator!

#### Predicting Values of Y
Let’s change gears slightly. Suppose I now want to predict a value of ( Y ) rather than estimate a population parameter.
We can still formulate this problem using the mean squared error!
$MSE(Y^*) = \mathbb{E}[(Y - Y^*)^2]$
However, the decomposition of the MSE is slightly different:
$MSE(Y^*) = \text{Bias}(Y^*)^2 + \text{Var}(Y^*) + \sigma_\epsilon^2$
Where  ($\sigma_\epsilon^2$) is an irreducible error term.

We can find the optimal $Y^*$ using the MSE again
$Y^* = \arg \min_{\xi} \mathbb{E}[(Y - \xi)^2]$
How can we minimize a function?
Take the derivative and set it equal to 0
In the end, we can get the optimal predictor for a value of Y is E(Y)

## Lesson 8: An Introduction to Statistical Inference
### Hypothesis Testing - General Ideas
> The **null hypothesis** is a statement that is assumed to be true throughout a hypothesis test

$\alpha$ is called **level of significance**
`Type-I Error:`
Rejecting the null when the null is true

**Probability of rejecting the null hypothesis when the distribution is false:**
This is called the `power` of a test. We represent it by 1 - $\beta$
$\beta$ is what we refer to as the probability of a Type-II Error
A `type-II Error` is failing to reject the null when the null is false

### Confidence Intervals
A confidence interval(CI) for the parameter $\theta$, with confidence level or coefficient $\gamma$, is an interval [LB, UB] such that
$P(LB \leq \theta \leq UB) = \gamma$
We usually refer to $\gamma$ as $1 - \alpha$

#### Formula of CI
$\frac{\hat{p} - p}{\sqrt{\frac{\hat{p}(1-\hat{p})}{n}}} = \pm z^*$
$\Rightarrow \hat{p} - p = \pm z^* \sqrt{\frac{\hat{p}(1 - \hat{p})}{n}}$ 
$\Rightarrow p = \hat{p} \pm z^* \sqrt{\frac{\hat{p}(1 - \hat{p})}{n}}$

## Lesson 9: Statistical Inference with Symmetric Distribution
### Proportion Test
Whenever you are asked for a p-value, you always shade from the **test statistic**, not the critical value

### Mean Tests with known variances
Suppose we want to approximate the mean of a distribution, $\mu$
An unbiased estimator for $\mu$ is 
$\hat{\mu} = \bar{X} = \frac{1}{n} \sum_{i=1}^{n} X_i$
This is an unbiased estimator for the expected value $\mu$

Distribution of $\bar X$
$\bar{X} \sim \left( \mu, \frac{\sigma^2}{n} \right)$
If we further require that $X_i$ are approximately normally distributed
$\bar{X} \sim N\left(\mu, \frac{\sigma^2}{n}\right)$
It further follows that the standard error of $( \bar{X} )$ is
$\text{SE}(\bar{X}) = \frac{\sigma}{\sqrt{n}}$
Thus, we can normalize $\bar X$ to the standard normal distribution
$\frac{\bar{X} - \mu}{\frac{\sigma}{\sqrt{n}}} \sim N(0, 1)$

### Mean Tests with unknown variances
If we do not know the variances, we have to estimate it
We have to calculate the sample variance, $( \hat{\sigma}^2 )$
$\hat{\sigma}^2 = \frac{1}{n - 1} \sum_{i=1}^{n} (X_i - \bar{X})^2$
$(\bar{X}$) is our usual estimator for $(E(X) = \mu).$
$(\hat{\sigma}^2$) is our estimator for $(E[(X - E(X))^2]).$

### Formula About HT and CI
1. Z Statistic
	Z = $\frac{\bar x - \mu}{\sigma / \sqrt n}$
2. Confidence Interval for Z:
	$\bar{x} \pm Z_{\alpha/2} \cdot \frac{\sigma}{\sqrt{n}}$
	CI for 95% should be $Z_{0.025} = 1.96$
3. T Statistic
	$T = \frac{\bar{x} - \mu}{s / \sqrt{n}}$
4. Confidence Interval for T:
	$\bar{x} \pm T_{\alpha/2, n-1} \cdot \frac{s}{\sqrt{n}}$


## Lesson 10: Asymmetric Distribution
### Testing for One Variance
Variance is interpreted as the spread of the values from a distribution

An **unbiased** estimator for the population variance $\sigma^2$ 
$\hat{\sigma}^2 = \frac{1}{n-1} \sum_{i=1}^{n} (X_i - \bar{X})^2$
The realization of this estimator is commonly denoted $s^2$

### Chi-Squared Distribution
#### Two-Way Bounding of Chi-Squared Distribution
**Lower tail:** 0

**Upper tail:** $\infty$

**Center:** the center of a chi-squared distribution changes with respect to it's degrees of freedom, as degree of freedom increase, the center will become larger

**Median:** $\frac{1}{k \left(1 - \frac{2}{9k}\right)^3}$, k is the degree of freedom

**Distribution:** Larger the df is, more likely a normal distribution

**Confidence Intervals:** CI will still have $\gamma$ = 1 -$\alpha$ area in the middle of the distribution. However, the middle is not centered around 0. As a result, you have to find both critical values rather than just taking the negative of the other one. Eg, $\chi^2_{150.025} = 6.262$, $\chi^2_{150.975} = 27.488$

**Using R code to find critical values:** qchisq(0.025, df = 15), qchisq(0.975, df = 15)

**Variance** Variance = 2k, for example,
	$\to$ $\chi^2_{15}$, k = 15, variance = 2 * 15 = 30

**Test Statistic**
Formula: $\frac{(n - 1)s^2}{\sigma^2}$

**Confidence Intervals:**
$\left( \frac{(n - 1)s^2}{\chi^2_{H,n-1}}, \frac{(n - 1)s^2}{\chi^2_{L,n-1}} \right)$
The smaller(L) critical value is used in the calculation of the upper tail, and vice-versa -- H: upper bound, L:lower bound
$\chi^2_{H,n-1}$ = $\chi^2_{\frac{\alpha}{2}, n-1}$
$\chi^2_{L,n-1}$ = $\chi^2_{1 - \frac{\alpha}{2}, n-1}$

### Testing for Two Variance
Suppose we want to see if two populations have **equivalent variances** $\to$ $\sigma^2_1 = \sigma^2_2$ or rather, $\frac{\sigma^2_1}{\sigma^2_2} = 1$

Test for two variances in a similar manner to one variance:
$\frac{\hat{\sigma}_1^2}{\hat{\sigma}_2^2} \sim F_{n_1-1,n_2-1}$
This test is commonly referred to as the ratio of variances test
$n_1$ and $n_2$ are the samples size of the numerator and denominator samples, respectively

The order of the degrees of freedom does matter
**Critical Value:**
**two tail:**
qf($\frac{\alpha}{2}, df_1, df_2$), qf($1-\frac{\alpha}{2}, df_1, df_2$)

**right-tail:**
qf($1 - \alpha$, df1, df2)

There is no left-tail critical value in the F distribution

**Test Statistic:**
$F = \frac{s^2_1}{s^2_2}$

## Lesson 11: Statistical Inference: Errors and Power
### Errors and Power
We have Type-I error and Type-II error in hypothesis tests
Ideally want to minimize the chance of these errors occurring

A **Type-I error** is when you reject the null hypothesis when the null hypothesis is really true. The significance level is equivalent to the probability of a type-I error

A **Type-II error** is when you fail to reject the null hypothesis when the null hypothesis is false
We refer this value as $\beta$

**Power** is the opposite of a type-II error
The more power that we have, the more often we end up rejecting the null if it is correct to do so
Thus, ideally, we have as much power as possible 
However, power has a trade-off with a type-I error

Assume that some alternate distribution is true. You can calculate
power by:
▷ Finding the rejection region under the null hypothesis.
▷ Relating that rejection region to the alternate distribution.
▷ Calculate the area under the curve of the alternate distribution corresponding to the rejection region.

### Two-tail test Power
Calculate the $\bar x$ separately and then adding two sides $\bar x$ up

### Two ways to increase power
1. Increase sample size
2. Change the significance level

**Test Statistic does not depend on out choice of tails for hypothesis test, it only depends on the data**

Note that the p-value does become larger when comparing the two-tailed test to the one-tailed test.

In particular, we have to allow for the possibility of the test statistic having been as extreme but negative.

Thus, the p-value for the two-tailed test is two times the p-value of the one-tail, upper tail test.

### Formula of Power
Power = P(reject $H_0$ | $H_a$ is true)



## Lesson 12: Joint Distributions and Conditional Expectation
### Joint Distributions
For two discrete random variables X and Y, the **joint probability mass function(PMF)** is a function that gives the probability that the variables are exactly equal to x and y, respectively.
$$P_{x, y}(x, y): R^2 \to [0, 1]$$

Marginal Distribution of Y -- we only look about the marginal distribution of Y without watching other variables

The continuous random variables Y, and X have a joint **joint probability density function(PDF)** $f_{X, Y}(x, y)$, where $f_{X, Y}(x, y)$ is a non-negative function, if 
$$ P(a \leq X \leq b, c \leq Y \leq d) = \int_{c}^{d} \int_{a}^{b} f_{X,Y}(x,y) \, dx \, dy$$
we can verify a distribution is valid if
$$
\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} f_{X,Y}(x,y) \, dy \, dx = 1$$

We can use the **Covariance** of a distribution to help determine whether X and Y have a relationship

#### Covariance
The **Covariance** of X and Y is a measure of **linear** association between X and Y. Formally:
$$ Cov(X,Y) = E[(X-E(X))(Y-E(Y))] = E(XY) - E(X)E(Y) $$
Covariance between X and X:
$$ E[(X-E(X))(X-E(X))] = E[(X-E(X))^2] = Var(X) $$
The covariance between Y and X indicates how the values of Y and X move relative to each other

- If large values of X tend to happen with large values of Y, then $[Y-E(Y)][X-E(X)]$ tends to be positive on average, then Y and X are positively related
- If Y tends to be small when X is large, then$[Y-E(Y)][X-E(X)]$ is negative on average, then Y and X are negatively related
#### Correlation
The **Correlation** between two variables can be expressed as the ratio of the covariance and the product of the standard deviations of the two variables

$$ Corr(X,Y) = \frac{Cov(X,Y)}{\sigma_x\sigma_Y}$$

- The correlation of two variables is bounded between -1 and 1
- The closer in absolute value to 1 the correlation is, the stronger it is
#### Important Note
> Correlation and Covariance are indicative of **linear** relationships
> Two variables can have 0 correlation while still having a nonlinear relationship

#### If two variables are random
1. $P(X=x, Y=y) = P(X=x)P(Y=y)$
2. $p_{X,Y}(x,y) = p_X(x)p_Y(y)$ $\to$ two independent discrete random variables
3. $E(XY) = E(X)E(Y)$ $\to$ expectations when X and Y are independent

### Conditional Expectation
Using new notation for joint distributions to write the general conditional probability formula:
$$ P_{Y|X}(y|x) = \frac{P_{X,Y}(x,y)}{P_X(x)} $$

This is a `conditional probability distribution`
#### Conditional Expectation
$$E(Y|X=x) = \sum_{y \in Y} yP(Y=y|X=x)$$
This is a conditional probability, not a joint probability
1. 先把所有满足要求的 $E(Y|X=x)$ 单独提取出来
2. 计算在被提取出的数据当中各数据的占比
	1. eg. 三个数据为 0.05, 0.1, 0.05, 那么占比分别是 0.25, 0.5, 0.25
3. 分别相乘对应的y，并且把所有结果加起来
#### Law of Iterated Expectation
$E[E(Y|X)] = E(Y)$
If X is collection of countable events that are mutually exclusive and collectively exhaustive, then 

 $E(Y) = \sum_{x \in X} E(Y | X = x) P(X = x)$

This is because expected value is a weighted average of all possible values of the random variable, so if we address all the possible values of the expected value of Y given X and weight those values by the probability of X, we should get back to Y itself

## Lesson 13: The Line of Best Fit
### The Line of Best Fit
#### Predicted Value of y
Define the predicted value of y as $\hat y = \hat b_0 + \hat b_1x_i$ 

#### Residuals 
The prediction error for a value of y is defined as the difference between the actual value and the predicted value
$y_i - \hat y_i$
We will usually refer to this value as a **residual**

We should focus on minimizing the squared residuals

### Calculating the line of best fit
Minimizing the mean squared error of the line of best fit
$Q(b_0, b_1) = \frac{1}{n} \sum_{i=1}^{n} (y_i - b_0 - b_1x_i)^2$
The $b_0$ and $b_1$ that minimize the function will be denoted $\hat b_0$ and $\hat b_1$ respectively 
> This method can only be imposed for one sample of data

## Lesson 14: Simple Linear Regression
### Linear Regression Model
#### Populations and Samples
Base the analysis on a **sample** of data
The sample must be **representative** of the target population
1. A representative sample is a subset of a population that seeks to reflect the characteristic of the larger group(population) accurately

#### population Regression Line
$E(Y|X) = \arg \min_{f(X)} E\left[(Y - f(X))^2\right]$

We can assume that X predicts Y **linearly** and so as to represent $E(Y|X)$ by $E(Y|X) = \beta_0 + \beta_1X$
This is the population regression line(model)

Since the random variable Y cannot exactly follow this relationship, we have to add model Y with error
$E(Y|X) = \beta_0 + \beta_1X + U$
U is the error term which accounts for all other factors that could influence Y outside of X, we will assume $E(U|X) = 0$, because
$E(Y|X) = E[E(Y|X)|X] + E(U|X)$
$E(Y|X) = E(Y|X) + E(U|X$
$E(Y|X) - E(Y|X) = E(U|X) = 0$
Use the law of iterated expectations, we can find out that 
$E(U) = E[E(U|X)] = E(0) = 0$
#### Linear Regression Model
$\beta_0$ and $\beta_1$ are **unknown** population parameters
$\beta_0$ and $\beta_1$ are usually called the regression coefficients
$\beta_0$ is the expected value of Y when X = 0: E(Y|X=0)
$\beta_1$ represents the changes in E(Y|X) 
$\frac{\partial}{\partial X} E(Y|X) = \frac{\partial}{\partial X} (\beta_0 + \beta_1 X) = \beta_1$
E(Y|X) is the best predictor of X in that it minimizes the mean squared error for a prediction of Y
$E(Y|X) = \arg \min_{f(X)} E\left([Y - f(X)]^2\right)$
Therefore, since we have imposed linearity:
$(\beta_0, \beta_1) = \arg \min_{b_0, b_1} E\left([Y - b_0 - b_1 X]^2\right)$

I can be shown that:

$\beta_0 = E(Y) - \beta_1E(X)$
$\beta1 = \frac{E([x-E(x)][Y - E(Y)])}{E([X-E(X)]^2)} = \frac{Cov(X,Y)}{Var(x)} = r_{XY}\frac{S_Y}{S_X}$
$r_{XY}$: coefficient of x and y
$S_Y$, $S_X$: standard deviation of Y and X

#### Correlation coefficient
correlation coefficient r, is symmetric, which means that $r_{XY} = r_{YX}$

#### Sample Regression Model
We can denote this sample as pairs of random variables ($X_i$, $Y_i$)
that represent each individual in the sample
For all pairs($X_i, Y_i$)
1. $E(Y_i|X_i$) = $\beta_0$ + $\beta_1 X_i$
2. Y_i = $\beta_0 + \beta_1X_i + U_i$
3. Cov($X_i, X_j$) = Cov($Y_i, Y_j$) = 0

The coefficients that minimize the mean squared error are the same for the sample regression model as the population regression model
$\beta_0$ = $E(Y_i) - \beta_1E(X_i)$ = E(Y) - $\beta_1E(X)$
$\beta_1 = \frac{E([X_i - E(X_i)][Y_i - E(Y_i)])}{E([X_i - E(X_i)]^2)} = \frac{Cov(X_i, Y_i)}{Var(X_i)} = \frac{Cov(X,Y)}{Var(X)}$

##### Estimation
**Ordinary Least Squares** 

Ordinary least squares is just minimizing the mean squared error assuming a linear relationship
$(\hat\beta_0, \hat\beta_1) = \arg \min_{b_0, b_1} \frac{1}{n}\sum_{i=1}^n\left([Y_i - b_0 - b_1 X_i]^2\right)$

Ordinary Least Squares is just minimizing the mean squared error assuming a linear relationship
$\hat\beta_0 = \bar Y - \hat\beta_1 \bar X$                                         $\hat\beta_1 = \frac{\sum_{i=1}^n (X_i-\bar X)(Y_i - \bar Y)}{\sum_{i = 1}^n (X_i - \bar X)^2}$
These are the OLS **estimators**

#### Estimators vs. Estimates
We want to conduct inference about the population
As we do not observe the population, we need to quantify the **uncertainty** when we observe a sample
We quantify uncertainty by writing the **estimators** as random variables and the **estimates** as one of the infinitely many potential realizations of the estimators

## Lesson 15: Properties and Assumptions of the Simple Linear Regression Model
### Differences between populations and Samples
Every different data set will end up giving us a different regression line. 
This does not necessarily mean that the samples come from different populations
You should never get exactly the same regression line from two different sets of data unless the data is completely artificial
Thus: Different samples $\to$ different estimates!

### Assumption in the Linear Regression Model
#### Assumptions
We're already assuming that E(Y|X) is a linear function, and we still need 5 assumptions, although all of the 5 assumptions will not always be required

#### Assumption 1
> **OLS1**: X and Y have finite second moments
> E($X^2$) and E($Y^2$) and
> $E(Y|X) = \beta_0 + \beta_1X$
Note that linearity is primarily in the **parameters**, not the variables, which means that $Y = \beta_0 + \beta_1X^2 + U$ is a valid linear model, but $Y=\beta_0 +\beta_1^2X + U$ is not 

Assumption OLS1 implies that our postulated model is correct:
The conditional mean is linear
If OLS1 is not valid, OLS estimation will recover the best linear approximation to E(Y|X)

#### Assumption 2
> OLS 2: The realizations of $X_i$ and $Y_i$ are randomly sampled from the population
This combined with OLS 1 allows us to write our models as:
$Y_i = \beta_0 +\beta_1X_i + U_i$

OLS2 also implies that:
1. The joint distribution of $X_i$ and $Y_i$ is the same for all subject i
2. ($X_i, Y_i$) is independent of ($X_j, Y_j$) for all i $\neq$ j
3. Each subject is sampled from the population with the same probability
#### Assumption 3
- OLS 3: The sample outcomes of X cannot all be the same value
$\hat \beta_1 = \frac{\sum_{i = 1}^n(X_i - \hat X)(Y_oi - \hat Y)}{\sum_{i = 1}^n(X_i - \hat X)^2}$
**This becomes $\frac{0}{0}$ if there is no variability in X**

#### Results of first three assumptions
OLS1, 2, and 3 ensures that our OLS estimators are **unbiased**
Thus, $E(\hat \beta_0) = \beta_0$ $E(\hat \beta_1) = \beta_1$
However, **Unbiasedness does not mean precision**

#### Assumption 4
OLS 4: The population model $Y = \beta_0 + \beta_1X + U$
has conditions on U such that $U \textasciitilde (0, \sigma^2)$
Note that $\sigma^2$ is a constant value
The constant variance of the error term is referred to as **homoskedasticity**
Errors are **heteroskedastic** if they depend on the value of $x_i$
This means that the variance is $\sigma_i^2$ rather than $\sigma^2$, as the variance varies depending on i's value of $x_i$
The standard errors of $\hat \beta_0$ and $\hat \beta_1$(and their realizations) are unreliable as a result

#### Assumption 5
> OLS 5: The population model $Y = \beta_0 + \beta_1X + U$
> has conditions on U such that $U \textasciitilde N(0, \sigma^2)$

This is very similar to OLS 4 except we now impose that the errors have a normal distribution

## Lesson 16: Inference with the Simple Linear Regression Model I

### Hypothesis Testing in Simple Linear Regression
We can find the total variation in our model due to errors by summing the square of our residuals:

$RSS = \sum_{i=1}^{n}(Y_i-\hat Y_i)^2$

We could use the mean squared error as our estimate our variance. However, this will not be an unbiased estimator
$MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i-\hat y_i)^2$
Sample variance estimator:
$\frac{1}{n-1}\sum_{i=1}^{n}(X_i - \bar X)^2$

We would use $\mu$ instead of $\bar X$ if we could, but we do not know the true population mean, so we have to estimate it

We are estimating two population parameters in a simple linear regression model:
$\beta_0$ and $\beta_1$

An **unbiased estimator** for the variance of the regression model is:
$\frac{1}{n-2}\sum_{i=1}^{n}(Y_i - \hat Y_i)^2$

With the corresponding estimate replacing the random variables with the values observed through data and estimation, another way to represent the unbiased estimator for the variance of the regression model is:
$\sigma^2 = \frac{RSS}{n-2}$

#### Test Statistic
When we assume the data comes from a normal distribution, we can construct test statistics similar to how we constructed them for population means and proportions:
$\frac{\hat \beta_i - \beta_i}{\hat {se}(\hat \beta_i)} = t_{stat}$
#### The Central Limit Theorem(CLT)
Let $Z_1, Z_2, ... , Z_n$ be a sample of n independent and identically distributed random variables with mean $\mu$ and variance $\sigma^2$. Both $\mu$ and $\sigma^2$ are finite numbers and $\sigma^2 > 0$. Therefore, as $n \to \infty$(the sample size tends to infinity), the random variable $\sqrt{n}\frac{\bar Z - \mu}{\sigma}$
converges to a $N(0,1)$ random variable

- Thus, so long as our sample size n is large, we can ignore OLS 5 when it comes to performing tests for regression **coefficients**
- At the same time, when n is large, we can say that the test statistic follows a standard normal distribution rather than a $t_{n-2}$ distribution
- OLS 5 will still be needed for inferences about values of Y


When X and Y have no linear relationship, the coefficient $\beta_1$ is 0

The output from the summary() function in R will provide us with hypothesis tests for the hypotheses:
$$H_0: \beta_i = 0 $$
$$ H_a: \beta_i \neq 0$$
We need to manipulate this output to test for other hypotheses

When using R, you should use the t-distribution rather than approximate the p-value with a standard normal distribution for these tests.
On an exam, it is perfectly fine to specify the distribution of the test statistic as $t_{86}$ or $N(0,1)$

#### R Output -- Significance codes and F-Statistic
The **significance codes** tell you a set of $\alpha$ levels that you will reject the null hypothesis $\beta_i = 0$ against $\beta_i \neq 0$ 
more '*' means that the p-value is smaller, and we are more confidence to reject the null hypothesis

The F-Statistic is interpreted as testing the overall significance of the model, which means that do all of the independent variables jointly determine Y linearly? -- 用于解释模型，若很大则代表模型解释的变异远大于误差，也就是说模型整体显著(p-value小)，即x 与y 无线性关系，若很小则代表模型对y几乎没有解释力(p-value大), 即x与y之间存在显著线性关系
The p-value for the F-statistic is the same as the p-value for the t-statistic of the independent variable, because we only have 1 independent variable in a simple linear regression model

### Confidence Intervals for Regression Coefficients
The confidence interval formulas for our regression coefficients can be easily calculated from the test statistic formulas

$\frac{\hat \beta_i - \beta_i}{\hat{se}(\hat \beta_i)} = \pm t_{n-2}$
$\to \beta_i = \hat \beta_i \pm t_{n-2} \hat{se}(\hat \beta_i)$

This is similar to how we calculate confidence intervals for sample means

$t^*$ of the $t_{n-2}$ will not be shown in the table of the r output, so we have to calculate it

## Lesson 17: Inference with the Simple Linear Regression Model II
### Inferences about Values of Y
The fact that our predictions do not match our data should not be surprising, few if any observations will fall directly on the regression line.
However, we should consider the range of possible values that our predictions can take
We have two tools to do this: confidence intervals and predictions intervals

#### Confidence vs Prediction Interval
**Confidence intervals** are used when we want to estimate the **average** value of Y for all X=x
**Prediction intervals** are used when we want to estimate the value of $Y_i$ for **one** $X_i = x$ 
Prediction intervals should be wider as there is more uncertainty about one observation than an average of all observations


#### Confidence Intervals
The most confident in our predictions should closer to the sample of average of $X_i$
The further we get from the sample average, the less certain we should be about our predictions
Observation i's **leverage** is defined as $\frac{1}{n}\frac{(x_i - \bar x)^2}{\sum_{j = 1}^{n}(x_j - \bar x)^2}$
High leverage observations should result in wider confidence intervals

> A confidence interval for the average of Y when X = x is given by
> $\hat{y} \pm t^* \hat{\sigma} \sqrt{\frac{1}{n} + \frac{(x - \bar{x})^2}{\sum_{j=1}^{n} (x_j - \bar{x})^2}}$
> - $\hat y$ is the predicted value of Y given X = x
> - $t^*$ is the relevant critical value from the corresponding distribution $t_{n-2}$ or $N(0,1)$ 
> - $\hat \sigma$ is the estimate of the standard error of the regression model

The following things affect the width of the confidence intervals:
1. The choice of width (shown through $t^*$)
2. The sample size (shown though n)
3. The distance between the mean of x and the one observed value of x, $x_i$ which we are making the interval for 

Between all potential 100(1-$\alpha$)%, the only term that vary are $\hat y$(the estimated value) and $(x_i - \bar x)^2$(part of the leverage)

Confidence interval is for the conditional mean and is not a prediction interval, which means that 
$E(Y|X) = \beta_0 + \beta_1X$
but $Y = \beta_0 + \beta_1X + U$
We require a different type of interval to look for one new value Y

#### Prediction Intervals
- Prediction and confidence intervals are different concepts
- A prediction interval is an interval associated with a random variable yet to be  observed
- A confidence interval is an interval associated with a non-random quantity

We wish to find a prediction interval for $Y|X = \mathbb{E}(Y|X) + U$
$\mathbb{E}(Y|X)$ has a confidence interval that follows the distribution
$N(\hat{Y}, \sigma^2 \left[\frac{1}{n} + \frac{(X_i - \bar{X})^2}{\sum_{j=1}^{n} (X_j - \bar{X})^2}\right])$
Since $U\sim N(0, \sigma^2)$ under OLS 5,
$Y | X = N\left(\hat{Y}, \sigma^2 \left[\frac{1}{n} + \frac{(X_i - \bar{X})^2}{\sum_{j=1}^{n} (X_j - \bar{X})^2}\right]\right) + N(0, \sigma^2)$
$Y | X = N\left(\hat{Y}, \sigma^2 \left[1 + \frac{1}{n} + \frac{(X_i - \bar{X})^2}{\sum_{j=1}^{n} (X_j - \bar{X})^2}\right]\right)$
> A prediction interval for one Y when X=x is given by
> $\hat{y} \pm t^* \hat{\sigma} \sqrt{1 + \frac{1}{n} + \frac{(x - \bar{x})^2}{\sum_{j=1}^{n}(x_j - \bar{x})^2}}$
> - $\hat y$ is the predicted value of Y given X = x
> - $t^*$ is the relevant critical value from the corresponding distribution $t_{n-2}$ or N(0, 1)
> - $\hat \sigma$ is the estimate of the standard error of the regression model

## Lesson 18: Unites of Measurement and Function Form Changes

### Units of Measurement
$\beta_0 = E(Y) - \beta_1E(X)$
$\beta_1 = \frac{Cov(X,Y)}{Var(X)}$
If X is multiplied by a non-zero constant "a",
$\beta_1 = \frac{Cov(X,Y)}{Var(X)} = \frac{E[(X-E(X))(Y-E(Y))]}{E[(X-E(X))^2]}$
$\hat\beta_1 = \frac{Cov(aX,Y)}{Var(aX)} = \frac{E[(aX-E(aX))(Y-E(Y))]}{E[(aX-E(aX))^2]}$
$\hat\beta_1 =  \frac{1}{a}\beta_1$
Same analysis for bY as well
$\hat\beta_1 = b\beta_1$
$\hat \beta_0 = b\beta_0$

### Nonlinearities
OLS1 assumed that $E[Y|X]$ is a linear function of X

For the relationships that do not follow OLS1, we need to re-define X(independent variable)

Suppose that E(Y|X) = $\sqrt X$ 
If we assume that E(Y|X) = $\beta_0 + \beta_1 X$, our line of best fit will not match the data
Let Z = $\sqrt X$
E(Y|Z) = $\beta_0 + \beta_1Z$ At $\beta_0 = 0$ and $\beta_1 = 1$, $E(Y|Z) = Z = \sqrt X$
If the analysis of the assumptions raises some potential issues of assuming that Y and X have a linear relationship, which means that $E(Y|X) \neq \beta_0 + \beta_1X$
We can try E(Y|X) = $X^2$

Since $X^2$ is not a linear function of X
Let $Z = X^2$
At $\beta_0 = 0$ and $\beta_1 = 1$, we get $E(Y|Z) = E(Y|X) = 0 + (1)Z$
Thus, $E(Y|Z) = \beta_0 + \beta_1Z$ is actually a valid linear regression model


Economists generally use the log() of variables to run regression
	$log(Y) = \beta_0 + \beta_1log(X) + U$
Everywhere we see a log, instead of thinking about Y or X directly, think about the percentage change in Y or X

It turns out that using logs in linear regression models result in coefficients that can be approximated as percentage changes

![[Screenshot 2025-11-04 at 13.34.35.png]]
## Lesson 19: Goodness of Fit and Model Selection
Changing the units of measurement of a variable should not **qualitatively** change the results of a regression model

$log()$ -- percentage change to approximate functional form change

Level - Level: $\beta_1 = 0.976$
-- A one unit change in X is associated with an average change of $\beta_1$ in Y
Interpretation: On average, a one-thousand dollar increase in the assess price of a house is associated with a 0.976 thousand dollar increase in the selling price of a house

Level - log: $\beta_1 = 342.2$ 
-- A one percent change in X is associated with an average change of $\beta_1 / 100$ is Y -- 解释Y的时候$\beta_1$ 要除一百
Interpretation: On average, a one precent increase assess price of a house is associated with 3.424 thousand dollar increase in the selling price of the home

Log - level: $\beta_1 = 0.00277$
--On average, a one unit change in X is associated with a $\beta_1(100\%)$ change in Y -- 解释Y的时候需要$\beta_1$ 乘一百
Interpretation: On average, a one-thousand dollar increase in the assessed price of a house is associated with 0.277 percent increase in the selling price of a house

Log - log: $\beta_1 = 1.013$
-- On average, a one percent change in X is associated with a $\beta_1\%$ change in Y
Interpretation: On average, a one percent increase in the assess price of a house is associated with a 1.013 percent increase in the selling price of a house

### Goodness-of-fit
By quality of adjustment (or goodness of fit), we mean **how good the model is in explaining the behavior of the dependent variable**
This does not mean that the slop coefficient is necessarily large

A slope of zero would mean that X explains nothing about Y -- worst case
	 $\hat b_1 = r\frac{s_y}{s_x} \to r = 0$
	 at the same time, the line of best fit looks like:
	 $\hat y_i = \hat b_0$
	 Since $\hat b_0 = \bar y - \hat b_1x$
	 we know that 
	 $\hat b_0 = \hat y - 0 \hat x$
	 $\to \hat b_0 = \hat y$
Thus the **estimator from the regression model** is the **sample average of Y**

`Total Sum of Squares(TSS)`
If $\bar Y$ is out estimator, then the total variation in Y can be described by
$TSS = \sum_{i = 1}^{n}(Y_i - \bar Y)^2$ 

`Total amount of error in the linear regression model:`
$RSS = \sum_{i = 1}^{n} (Y_i - \hat Y_i)^2$
Using the error of the linear regression model to the error of the sample average to establish how well a model fits

$R^2$ is the **proportion(or percentage) of the variance in Y that is explained by the independent variables**
$R^2 = 1 -\frac{RSS}{TSS}$
`1 - unexplained variation = explained variation`


$R^2 = 1 -\frac{RSS}{TSS}$ -- each quantity is the sum of the squared difference between an actual data point and it's estimator, which can be represented by MSE
$\to$ As long as the MSEs for the estimators are calculated with the same denominator ($\frac{1}{n}$) the $R^2$ formula is just 1 minus the ratio of MSEs

`ESS` -- Explained Sum of Squares
	This is the variation in Y that is explained by the regression line
	$ESS = \sum_{i=1}^{n}(\hat Y_i - \bar Y)^2$
	Since $TSS = RSS + ESS$
	The total variation in Y can be decomposed to the unexplained variation RSS and the explained variation $ESS$
	So
	$R^2 = \frac{ESS}{TSS}$

Worst estimator $\to \bar Y$
If $RSS = TSS(\hat Y_i = \bar Y \forall i$ then $R^2$ is 0, X adds nothing to the prediction of Y

Best possible estimator $\to \hat Y_i = Y_i \forall i$
$RSS = \sum_{i = 1}^{n} (Y_i - \hat Y_i)^2 = \sum_{i = 1}^{n} (Y_i -  Y_i)^2 = 0$
So, $R^2$ = 1

- Thus, the scope of $R^2$ is $0 \leq R^2 \leq 1$
- The closer to 1, the better the model fits the data
- $R^2$ means perfect prediction, which would imply that all of the data points lie on the lien of best fit
- Data will scattered away from the line of best fit as $R^2$ decrease

"Adjusted R-squared": penalizes models for how many independent variables are included in the model, we can ignore this value for now since we are focusing on simple linear regression

r - denote the correlation coefficient between two variables
if r is the correlation between X and Y, then $r^2 = R^2$
This means that we can use $R^2$(or $r$) to solve for $r$ (or $R^2$) for simple linear regression only

$r = \sqrt {R^2}$

**Be careful about the sign of r**
We know that $\hat b_1 = r\frac{s_y}{s_x}$, since r is the only value that can be negative, if the slope is negative, then **r must be as well**

### More on the F-Statistic
The F-Statistic can be calculates as
$F = \frac{ESS/p}{RSS/(n-p-1)}$
- p represents the number of independent variables
- For the simple linear regression model, p = 1
- F-statistics have two degrees of freedom, whatever divide by in the numerator is the first one, and the second one is whatever divide by the denominator
Also,
$F = t^2$
To find t by F-statistic, we can do 
$t = \sqrt{F}$
But be careful with the sign, if the **slope if negative**, we need to do 
$t = -\sqrt{F}$


## Additional Stuff:
$\bar Y$ -- Average
$\hat Y$ -- Best fit one
$Y$ -- the point not in the line 


