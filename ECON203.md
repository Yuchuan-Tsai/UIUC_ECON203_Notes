### Different Types of Data and Variables -- August 25, 2025

An *Observational Study* is a set of data that is collected without any intervention by the researcher
1. You have no control over who does what in an observational study
2. These data are collected by observing what people do on their own
3. These studies may benefit from randomization, but would be ethically complicated

A *Randomized Experiment* is a set of data where a researcher can assign variables certain values to observe effects
1. These data sets are desirable because the randomization minimizes bias
2. This fact helps establish clear casual relationships
3. However, these studies may be less ethical than observational studies

RCT = *Randomized controlled trial*

#### Types of Data
##### Cross-sectional data
*Cross-sectional data*: Cross-sectional data only has heterogeneity coming from who is being surveyed 
- 在某一个时间点上对多个个体、单位或观察对象进行的测量和收集的数据
- For example: If I take all of your characteristics today and put those in a data set, that's a cross-sectional data set
- Importantly, there's only one point in time that data is collected

##### Time series data set
*Time series data*:Time series data differs from cross-sectional because the heterogeneity only comes from when the data is collected
- For example: I choose one student in this class and record their grade in the course every week
- Importantly, there is only one unit being surveyed, if I collected data on multiple students in the same way, the data set is no longer a time series dataset

##### Pooled Cross-sectional data
pooled cross-sectional data combines aspects of both time series and cross-sectional data
This means that variation will come from both who/what is being observed and when the data is collected
eg. measure the characteristics of students in ECON203 on the first day of class for 10 semesters
1. the students are different, so there are different units being studied
2. data is also collected at different points in time

#### Panel data
*Panel data* is extremely similar to pooled cross-sectional data, it measures the exact same people at each point in time
If even one unit of observation drops out or changes, the data set is no longer a panel data set

#### Type of variables
- Numeric Variable 
	1. Continuous
	2.  Discrete
- Categorical Variable
	1. Nominal
	2. Ordinal
- Dummy Variable 

##### Numeric Variables
A *numeric variable* represents measurable quantities that can be used to describe something

> *Just because a variable has numbers in it does not mean the variable is numeric*

We can split numeric variables into *continuous* and *discrete* variables
	*Continuous Variables*
		Theoretically have an infinite amount of values
		Things like age, height, and so on
	*Discrete Variables*
		Might not have many values, but sill quantify how much or how many with regards to the variable
		Things like age in years 

##### Categorical Variables
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

##### Dummy variable
A *dummy variable* indicates if the condition for a variable is met, This variable takes a value of 0 or a value of 1
	eg. A dummy variable called "Male" gives value 1 if the respondent is male, 0 otherwise
These are useful when you have a categorical variable you want to break into multiple parts in a regression

### Introduction to Probability --- September 2, 2025

#### R functions
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

#### Random Variables
> A random variable X is a mapping from the sample space(Ω) of an experiment to of an (sometimes)simpler sample space(ΩX) 
> Mathematically:   X: Ω → ΩX

> A sample space(Ω) is a set of all possible outcomes of an experiment

#### Introduction Probability
P(X=x)  = wanted outcomes / total outcomes

#### Binomial Distribution


### Properties of Probability -- September 4, 2025
#### Properties of Probability
##### Definition
A probability is the chance that an event occurs. This is defined as the ratio of desired cases to all possible cases(n)

Disjoint means that sets have no common element

P(∅) = 0
P(Ac ) = 1 − P(A)
0 ≤ P(A) ≤ 1

if there is no disjoint point:
P(A ∪ B) = P(A) + P(B) − P(A ∩ B)

#### Independent
Two random variables X and Y are independent if, for all
events X = x and Y = y ,
P(X = x, Y = y ) = P(X = x)P(Y = y )

#### Total Probability
Notice that A and Ac are disjoint. Thus, we can see that:
P(B) = P(A ∩ B) + P(Ac ∩ B)

Mutually exclusive is the same thing as saying that events are
disjoint.
	You cannot simultaneously have a Freshman and Sophomore
	class standing as defined by credit hours at the same time.
Collectively exhaustive means that at least one of the events has to
occur.
	Students have to get an A, B, C, D, or F in a course, there are
	no other possible grades.
In general, one of these properties can hold without the other
necessarily holding

If variables are not mutually exclusive, we cannot calculate the probability of one variable by directly adding the probability of intersection up 

### Conditional Probability-- September 9, 2025
> if Ai are mutually exclusive and are collectively exhaustive, you
> can invoke the law of total probability
![[Screenshot 2025-09-09 at 12.55.20.png]]
![[Screenshot 2025-09-09 at 12.55.34.png]]




### Continuing Distribution--Sep16
#### Continuous Distributions
A continuous random variable X has a probability density function(PDF)

#### Whether a continuous distribution is valid
1. for all possible value x, P(x) cannot be negative
2. the derivative of the function should be equals to 1
	$\int_{-\infty}^{\infty} f_X(x) \, dx = 1$













