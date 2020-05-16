# Prosper Loan Data Exploration
## by Peter Sabry


## Dataset

> This data set contains 113,937 loan records with 81 variables on each loan, including loan amount, borrower rate (or interest rate), current loan status, borrower income, and many others. However, the most interesting columns were kept for analysis and other columns were removed during data wrangling, resulting in only 31 columns to be analyzed.


## Summary of Findings

> This section highlights some findings observed through the analysis of `Prosper Loan Data`. The analysis went into three stages those are:
 1. Checking single-feature distributions
 2. Checking the relations between different pairs of features
 3. Checking the interactions between multiple features (more than two)

Based on the above, it was noticed that:

A. From the Distributions:
  * Borrower Annual Percentage Rate (APR) is mostly around 15% to 20%
  * Laan Montly Payments mostly ranges between $100 and $400
  * Stated Montlhy Income almost normally distributed around a mean of $5K
  * For detaulted loans, amount delinquent normally distributed around a mean of $1K
  * When multiple investors share a loan, usually they are less than 10 investors, if more, they generally normally distributed around 60 to 80 investors.
  * More than 80% of the current listings are for `Current` or `Completed` loans, 11% are `Charged off` and the remaining are `Defaulted` and `Past Due`
  * Most loan takers have a ProsperRating of `C` which is the average in the scale of prosper ratings
  * More than a half of the loans are for `Debt Consolidation`
  * `California`, `Texas` and `New York` have the biggest number of loans where `North Dakota`, `Maine` and `Wyoming` are the least, this could be due to higher population
  * More than 70% of loan takers are employed (and full-time)
  * Number of loans originated has a drop in 2009 (maybe due to the recission of 2008) then booming in 2013 and back to normal in 2014

B. From the Relationships:
  * A negative relationship between `ProsperScore` and `BorrowerAPR`, a loan taker with higher score can get lower interest rate.
  * Positive relationship between `StatedMonthlyIncome` and `ProsperScore`, reflecting the fact that a person with higher income is trust-worthy and lower-risk hence recieves higher score
  * `Not employed` people generally have higher `BorrowerAPR`, `Employed` people generally get lower interest rates
  * `Employed` people can get larger `LoanOriginalAmount`
  * `EmploymentStatus` affects both `BorrowerAPR` and `ProsperScore`, `Employed` generally have higher score and lower interest rate compared to un-employed and even self-employed
  * Most of large loans (high `LoanOriginalAmount`) are for those who have higher `ProsperScore` and also they get lower `BorrowerAPR`
  * Number of `Defaulted` loans decreased dramatically in 2008, `Current` loans are increasing rapidly in 2013


## Key Insights for Presentation

> The following insights are concluded from the analysis as the most important to notice

#### Intersting distributions
The distribution of some important features those are: `StatedMonthlyIncome`, `AmountDelinquent`, `ProsperRating` and `LoanStatus`

   -  For Stated Monthly Income and Amount Delinquent, there was a hidden distribution that was uncovered using log-scale transformation, it showed that the monthly income has a peak around \$5k and also, the amount delinquent is centered around the \$1k
   -  ProsperRating Distribution shows that most of the loan takers get a `C` rating
   -  Loan Status Distribution shows that more than 80% of loan listings are either `Current` or `Completed` where the remaining minority are `Defaulted` or `Past Due`

#### Interesting Relationships
From the relation analysis between pairs of features:
   * `ProsperScore` and `BorrowerAPR`: Negarive relationship, people with higher score get lower interest rates
   * `StatedMonthlyIncome` and `ProsperScore`: Positive relationship, the higher the income, the higher the score
   * `EmploymentStatus` and `BorrowerAPR`: Shows that employment status affects the interest rates of loans, it is clear the people in the `Not Employed` status recieve considerably higher interest rates than others.

#### More Relationships
From the analysis of relations between groups of features:
   * First chart shows the trend of the number of loans originated quarterly per loan status. Intersting to notice that `Defaulted` loans decreased after Q4-2008, also `Current` loans increased rapidly in 2013 (and it is logic that no `Current` loans before 2011 as the maximum loan term is 5 years)
   * Second scatter plot explains the relation between `ProsperScore`, `BorrowerAPR` and `LoanOriginalAmount`, it was showed previously the negative relationship between prosperscore and borrowerAPR, in addition to this, the chart shows most of the loans with higher amounts (>\$20,000) are taken by people with higher prosper score (10 and above)

## References

https://kite.com/python/answers/how-to-convert-a-string-to-a-boolean-in-python

https://www.kaggle.com/yousuf28/prosper-loan

For explanations of financial terms related to loans: https://www.investopedia.com/
