Test activity: Loan default EDA
================
Math 285 - St Clair

First steps
-----------

Make sure you completed the steps in this test assignment's GitHub README file. Keep the output type for this .Rmd a `github_document`.

To Do: Complete before Friday's class (1/5/18)
----------------------------------------------

Use full sentences to answer the questions below. Provide your answer and, if needed, an R chunk used to answer the question. You should be able to complete questions 1-4 with a little review of intro stats R commands. Give questions 5 and 6 a try even if you can't fully answer them.

Data description:
-----------------

The data for today's review example is a "classic" German credit data set. Each entry in the data set represents a loan given by the bank, along personal characteristics of the person the loan was given to, the type of loan and whether or not they paid it off or defaulted. At the time, the deutsch mark was the unit of currency so an "DM" in the dataset refers to that unit of measurement. One of the main questions about this dataset is to understand factors associated with a loan defaulting (or not). For this analysis the variable `Good.Loan` indicates whether a loan was paid off (`GoodLoan`) or whether it defaulted (`BadLoan`).

``` r
> loans <- read.csv("http://math.carleton.edu/kstclair/data/day1CreditData.csv")
> str(loans)
'data.frame':   700 obs. of  21 variables:
 $ Status.of.existing.checking.account                     : Factor w/ 4 levels "... < 0 DM","... >= 200 DM / salary assignments for at least 1 year",..: 1 1 4 4 1 3 1 3 4 1 ...
 $ Duration.in.month                                       : int  24 36 48 36 48 48 24 30 36 24 ...
 $ Credit.history                                          : Factor w/ 5 levels "all credits at this bank paid back duly",..: 4 2 2 4 5 3 4 4 4 4 ...
 $ Purpose                                                 : Factor w/ 10 levels "business","car (new)",..: 3 6 8 8 3 5 6 8 2 2 ...
 $ Credit.amount                                           : int  6579 2348 3578 2394 4605 6224 4169 1715 909 4817 ...
 $ Savings.account.bonds                                   : Factor w/ 5 levels ".. >= 1000 DM",..: 2 2 5 5 2 2 2 5 4 2 ...
 $ Present.employment.since                                : Factor w/ 5 levels ".. >= 7 years",..: 5 3 1 3 1 1 3 3 1 4 ...
 $ Installment.rate.in.percentage.of.disposable.income     : int  4 3 4 4 3 4 4 4 4 2 ...
 $ Personal.status.and.sex                                 : Factor w/ 4 levels "female : divorced/separated/married",..: 4 3 4 1 4 4 4 1 4 4 ...
 $ Other.debtors.guarantors                                : Factor w/ 3 levels "co-applicant",..: 3 3 3 3 3 3 3 3 3 1 ...
 $ Present.residence.since                                 : int  2 2 1 4 4 4 4 1 4 3 ...
 $ Property                                                : Factor w/ 4 levels "if not A121 : building society savings agreement/life insurance",..: 4 1 3 2 4 4 1 2 1 1 ...
 $ Age.in.years                                            : int  29 46 47 25 24 50 28 26 36 31 ...
 $ Other.installment.plans                                 : Factor w/ 3 levels "bank","none",..: 2 2 2 2 2 2 2 2 2 2 ...
 $ Housing                                                 : Factor w/ 3 levels "for free","own",..: 1 2 2 2 1 1 2 2 2 2 ...
 $ Number.of.existing.credits.at.this.bank                 : int  1 2 1 1 2 1 1 1 1 1 ...
 $ Job                                                     : Factor w/ 4 levels "management/ self-employed/highly qualified employee/ officer",..: 1 2 2 2 2 2 2 2 2 2 ...
 $ Number.of.people.being.liable.to.provide.maintenance.for: int  1 1 1 1 2 1 1 1 1 1 ...
 $ Telephone                                               : Factor w/ 2 levels "none","yes, registered under the customers name": 2 2 2 1 1 1 1 1 1 2 ...
 $ foreign.worker                                          : Factor w/ 2 levels "no","yes": 2 2 2 2 2 2 2 2 2 2 ...
 $ Good.Loan                                               : Factor w/ 2 levels "BadLoan","GoodLoan": 2 2 2 2 1 1 2 2 2 1 ...
```

1. Data basics
--------------

How many loan cases are in the data? How many variables?

*answer:* answer here

``` r
> # R chunk for questions above (if needed)
```

We will not use all the variables in this handout. Here is a brief description of the variables used in this handout:

| Variable          | description                 |
|-------------------|-----------------------------|
| Duration.in.month | loan length in months       |
| Credit.amount     | amount of loan (in DM)      |
| Good.Loan         | did the loan default or not |

2. Default rate
---------------

What percentage of loans in this dataset defaulted?

*answer:* answer here

``` r
> # R chunk for questions above (if needed)
```

3. Default rate by duration
---------------------------

What is the average loan duration in this data? What percent of defaults occur for loans of 2 years or less? More than 2 years?

*answer:* answer here

``` r
> # R chunk for questions above (if needed)
```

4. Default rate and credit amount
---------------------------------

What is the median credit amount for loans that defaulted? for loans that didn't default? Create a graph that that shows the credit amount distribution for each type of loan (good vs. bad), then compare these distributions.

*answer:* answer here

``` r
> # R chunk for questions above (if needed)
```

5. A default prediction model
-----------------------------

Suppose that Barb the data scientist generates the following model criteria to predict when a loan will default. A loan will default if either criteria below is met:

-   Duration is longer than 2 years and credit amount is greater than 10,000 DM.
-   Duration is 2 years or less and credit amount is less than 2200 DM.

Use this model to predict defaults for the loan data. (Hint: You will likely need to use the "and" operator `&`.) Then use the actual and predicted default variables to find the following rates:

-   What is the model's *accuracy* rate, i.e. the percentage of all loans that are correctly classified as good or bad?
-   What is the model's *false positive rate*, i.e. the percentage of good loans that are predicted to default (a "positive" result)? (This is 1 minus the *specificity* of the model)
-   What is the model's *false negative rate*, i.e. the percentage of bad loans that are predicted to not default (a "negative" result)? (This is 1 minus the *sensitivity* of the model)

*answer:* answer here

``` r
> # R chunk for questions above (if needed)
```

6. Try your default prediction model
------------------------------------

Try changing one or two parts of Barb's simple default criteria and see if you can get a better rates than Barb (higher accuracy and/or lower false rates).

*answer:* answer here

``` r
> # R chunk for questions above (if needed)
```
