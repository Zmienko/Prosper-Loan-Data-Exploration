# Prosper Loan Data Exploration
## by Dmitry Zmienko


## Dataset

The dataset by company Prosper contains 113,937 loans with 81 variables on each loan, including loan amount, borrower rate (or interest rate), current loan status, borrower income, and many others. The dataset can be found [here](https://s3.amazonaws.com/udacity-hosted-downloads/ud651/prosperLoanData.csv), with data dictionary explaining the variables in the data set [here](https://docs.google.com/spreadsheets/d/1gDyi_L4UvIrLTEC6Wri5nbaMmkGmLQBk-Yx3z0XDEtI/edit#gid=0).

The main feature of interest in this dataset was to find out what influences the borrower's Annual Percentage Rate (APR) for the loan. For this purpose, several variables were chosen:

Data that describes Listing: **'ListingKey'**, 'ListingCreationDate', 'Term', 'LoanStatus', 'BorrowerAPR',  'ProsperRating (Alpha)', 'ProsperScore', 'ListingCategory (numeric)'.

Data that describes Borrower: 'BorrowerState', 'Occupation', 'EmploymentStatus', 'IsBorrowerHomeowner', 'CreditScoreRangeLower', 'CreditScoreRangeUpper', 'IncomeRange', 'IncomeVerifiable', 'StatedMonthlyIncome'.

Data that describes Loan: 'TotalProsperLoans', 'LoanOriginalAmount', 'LoanOriginationDate', 'MonthlyLoanPayment', 'Recommendations'.


## Summary of Findings

In the exploration of the influence of various factors on the borrower's APR, I will highlight several key points:
	1. Despite the fact that we see an almost direct relationship between the borrower's APR and the borrower's scores (Prosper's rating or Credit scores), we can argue that these values are not the only ones that determine the interest rate of a loan. A significant impact on the borrower's APR is affected by the amount of the loan, but taking into account other factors.
	2. Despite the correlation between borrower's APR and income range (for not employed and borrowers with less income, annual percentage rates are more significant), we see that monthly income weakly influences APR. 
	3. For lower ratings (E and HR), it's hard to get a loan for more than $10000, and the APR will be high (20-40%). For high-rated borrowers, we see that APR doesn't depend on the loan amount. But it is striking that for high-rated borrowers APR for bigger loans even increasing. On the contrary, the low-rated borrowers get lower APR for a bigger loan. Let's assume that this is due to company policy. Higher-ranked customers are more likely to be long-term and loyal to the brand (which is also confirmed by the higher APR for the credit rating of "890" compared to "870"). Customers with low ratings are primarily new clients, so the company is trying to attract them with a low APR.
	4. Ownership of real estate reduces the risks for the lender. Same works for the employment status: employed borrowers tend to have lower APR. Highly qualified borrowers receive better loan offers. Loans for students for a technical school are allocated separately, a narrow spread of values shows that there is apparently some kind of specialized lending program for them.


## Key Insights for Presentation

For the presentation, I focused on parameters that mostly influence borrower's APR, the distribution of which I showed at the beginning. Also I ploted the distribution of loan amount and term to show the main parameters of loans issued. 
Afterwards, I looked into correlation between borrower's APR, his Prosper rating/Credit score and loan amount. For this I used boxplots and heatmap. 
After I tested the assumption about the impact of the borrower's income on APR by using regplot.
Then use FacetGrid to look deeply on correlation between Prosper rating, borrower's APR and loan amount (with help of the stripplot to look on the terms influence).
In the end, I used the violinlpots to examine in more detail the influence of the borrower profile (empoyment status and home ownership).
