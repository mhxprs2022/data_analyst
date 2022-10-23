# Exploration of Loan Data from Prosper
## by Christopher Hu


## Dataset

The original dataset consists of information regarding 113,937 loans from Prosper, including loan amount, borrower rate (or interest rate), current loan status, borrow income, income range, borrower state, Employment Status, Occupation,  Prosper Rating, ... etc (total 81 variables).  The dataset can be divided into two subcategories:  pre-072009 and after-072009.   Only after-072009 (including 84853 loans) will be used in data analysis.
The dataset can be found at the following location: https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv
The data dictionary can be found here: https://docs.google.com/spreadsheets/d/1gDyi_L4UvIrLTEC6Wri5nbaMmkGmLQBk-Yx3z0XDEtI/edit#gid=0


## Summary of Findings

In the exploration phase, I researched both numeric variables and categorical variables.  

A quick study of the histogram of several key numerical variables did not reveal any interesting findings.  There are also no interesting strong relationships between any two numeric variables.   Therefore, less effort was spent on the numeric variables.

From a lender perspective, the most important question is that if I lend money to someone else, does that person has the ability to repay the loan back without going to either defaulted or chargedoff.  Therefore I picked categorical factors (including some of the numeric categorical factors) that I think will have some relationship with LoanStatus: EmploymentStatus,  IncomeRange, ProsperRating_Alpha,  ListingCategories, CreditScoreRangeLower, IsBorrowerHomeowner, LoanOriginationYear, Occupation, location of the applicants (State).   

For univariate analysis of some of these categorical factors, We can tell 6.3% of the loans are in chargedoff status, 1.2% of the loans are in default status.  Most of the loan applicants get a ProsperRating_Alpha rating of C.  11.5% of applicants received E and 8.2% received HA.  For employment status, 79.3% are employed, 9.3% are Full-time (employed), with only 0.8% for Not employed and 0.4% are retired.  For the income range, the majority of the applicants make $25,000 - $99,999.  Also, there are slightly more homeowners than renters to apply for Prosper loans.  For ListingCategories, it shows what kinds of purposes the loan is used for.   Just by looking at the above univariate analysis, it is still hard to tell which factor affects LoanStatus.  It could be multiple factors will affect a loan get into chargedoff and defaulted status.

In the bivariate analysis, I plot the LoanStatus against other categorical factors, and have some interesting findings.

- From plot “EmploymentStatus vs Loanstatus - by percentage”:  People without any job (Not employed) has the highest percentage of the Chargedoff/Defaulted status (25%) while with jobs (Employed) has the lowest (6.2%).

- From plot “IncomeRange vs Loanstatus - by percentage”:  People with $0 and Not employed have very high percentage of chargedoff and defaulted status (26.6% and 25.1% respectively)

- From plot “ProsperRating_Alpha vs Loanstatus - by percentage”, the highest Chargedoff/Default percentage goes to people with HR ProsperRating_Alpha.  This is also supported by plot “CreditScoreRangeLower vs Loanstatus - by percentage”, where the lower the credit score a person has, the more likely it can get into chargedoff and defaulted status.

- From plot “ListingCategory vs Loanstatus - by percentage”: Listing category 5 (Student Use) has the highest percentage of Chargedoff/Default status.  This is also echoed in plot “Occupation vs LoanStatus - by percentage” where college sophomore, freshman, and junior have 62.5%, 23.5%, 11.1% of loans in chargedoff and defaulted status.

- From plot “LoanOriginationYear vs Loanstatus - by percentage”:  there is very low percentage of loan in chargedoff/defaulted status in 2013 (0.9%) while there is no loans in 2014.  Upon researching economic data in 2013 and 2014, we found that the economic situation in the US is really good.  More people have jobs which leads to less or no loans goes into chargedoff and default status.

Lastly, I performed multivariate analysis

From plot “LoanOrignalAmount vs EmploymentStatus, LoanStatus in different years”, I confirmed that there is no loans in Chargedoff/Defaulted status in 2014, and in 2009, there is no loans in Chargedoff/Defaulted status for Employed people.

In a three factors (EmploymentStatus, IncomeRange, LoanStatus) barplot study: I confirmed that the lower the income, the more likely that the loan will be in Chargedoff/Default status.

From CreditScore vs LoanStatus and ProsperRating_Alpha plots, people have lower ProsperRating_Alpha score (C, D, E, and HR) are most likely to get their loan into Chargeoff/Defaulted status.


## Key Insights for Presentation

For presentation, I will focus on relationship of LoanStatus with several categorical factors and show how these factors are affect Chargedoff and defaulted status.  The plots used are mainly stacked barplot that indicates the percentage of each subcaegory of LoanStatus. No numeric variables (except for couple of numeric factors) will be presented.