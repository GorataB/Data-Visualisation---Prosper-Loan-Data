# Data-Visualisation---Prosper-Loan-Data
Perform exploratory data analysis and communicate findings using explanatory plots.

## Dataset

> There are 113, 937 loan listings in the [Prosper Loan dataset](prosperLoanData.csv), with 81 features. The dataset is too large, so I created a dataframe called 'loan', with only 32 columns, which include variables of interest, related variables, and identifier variables. The [data dictionary](<Prosper Loan Data - Variable Definitions.xlsx>) explains all the variables in the dataset. 
> 
> I also performed some preliminary wrangling to fix some column names and order of some categorical values. Most variables are numeric, but there are a few nominal and ordinal categorical variables, some of which I used in my exploration. 
> 
> I'm interested in factors that affect loan status **(LoanStatus)**, which is a nominal categorical variable. I expect numeric variables like **BorrowerRate** and **DebtToIncomeRatio** (DtI), and categorical variables like **EmploymentStatus** and **IncomeRange** and to be strong determinants of loan status. Though variables like **IncomeVerifiable** (categorical) and **Recommendations** (numeric) will not have as direct an influence, I expect them to be useful predictors of whether an individual will clear their loan.
>
> I will first perform exploratory analysis, followed by explanatory analysis on a slide deck.

## Files

1. [ProsperLoan_Part1_Exploration.ipynb](ProsperLoan_Part1_Exploration.ipynb): the Jupyter Notebook for exploratory analysis.
2. [ProsperLoan_Part1_Exploration.html](ProsperLoan_Part1_Exploration.html): the html version of the exploratory analysis.
3. [ProsperLoan_Part_II_slide_deck.ipynb](ProsperLoan_Part_II_slide_deck.ipynb): the Jupyter Notebook for explanatory analysis, which is in the form a slide deck.
4. [ProsperLoan_Part_II_slide_deck.slides.html]( ProsperLoan_Part_II_slide_deck.slides.html): the html version of the explanatory analysis.
5. [prosperLoanData.csv](prosperLoanData.csv): the dataset to be used for analysis. It is available under Releases as it was too large to upload.
6. [Prosper Loan Data - Variable Definitions.xlsx](<Prosper Loan Data - Variable Definitions.xlsx>): a data dictionary explaining all the variables in the dataset.

## Summary of Findings

#### Univariate exploration and wrangling efforts:

1. Completed loans and Current loans consitute the largest shares of LoanStatus.
2. Most borrowers are employed and are in the mid-range to upper-range income brackets.
3. 92% of borrowers also have a verified source of income.
4. Most people also have 0 to 1 recommendations.
5. 'Other' and 'Professional' consitute the largest share of occupations but they are vague, given how detailed the other occupations are. 7. Occupation will thus not be useful for analysis, and also because it has too many categories.
6. The BorrowerRate is generally right skewed and multimodal. 
7. After cleaning, the DebtToIncomeRatio distribution was skewed to the right, with a general smooth slope and some unusual gaps. DtI is concentrated around 0.2, which is an accepatable ratio because the lower the DtI the better. DtI's higher than 0.5 are considered unsafe by lenders and they appear as outliers in the boxplot distribution.

##### Wrangling:

1. I combined redundant bins for LoanStatus, EmploymentStatus and IncomeRange.
2. I changed IncomeRange into an ordered categorical type.
3. I changed the column name of Listing Category (numeric) to one without a column space i.e. ListingCategory
4. I also replaced the numeric values in ListingCategory with the actual descriptive categories.
5. I dropped extreme outliers  for DebtToIncomeRatio with values beyond 1, as they also made the distribution extremely right skewed.
6. Some of the listings had suspiciously low BorrowerRates given that they were high risk and in the lower ranges of credit scores. I dropped these outliers.

#### Bivariate Exploration:

1. DebtToIncomeRatio has a positive correlation with BorrowerRate because a high DtI lowers creditworthiness and leads to higher borrower rates due to lenders seeing the listing as risky.
2. Completed Loan listings have a generally lower median BorrowerRate, indicating that lower interest rates increase likelhood of loan clearance. 
3. The Recommendation distributions for LoanStatus are all thin slices at similar levels as the values are concentrated around 0 to 1. However, it's interesting to note that high outliers, including max values, are concentrated at Completed, showing that listings with more recommendations are more likely to have the loans cleared.
4. Most borowers with Completed or Current loan status have an income of at least $25,000.
5. Borrowers with a Completed or Current loan status typically have a verifiable income source.

#### Multivariate Exploration:

1. There is a positive relationship between DebtToIncomeRatio and BorrowerRate, and Current and Completed LoanStatus have a concentration of values around the lower regions of both numeric values, while Cancelled, Defaulted and Past Due have very low concentrations in the lower regions of both numeric variables. Thus borrowers with healthy (lower) DtI and lower borrower rates are more likely to clear their loans.
2. There is not much of a significant relationship between LoanStatus, IncomeRange and BorrowerRate. However, higher income brackets tend to have lower DtI than the rest.
3. There also isn't much difference between box plots for relationship between LoanStatus, BorrowerRate and EmploymentStatus, but employed and retired tend to have lower median rates.


## Key Insights for Explanatory Presentation:

* Most borrowers either have Completed or Current loan statuses, and they have a Debt-to-Income Ratio (DtI) of around 0.2, which is an acceptable value. The distribution for BorrowerRate is right-skewed and multimodal.
   
* Borrowers who are employed and higher income are more likely to be in the Completed or Current loan status.
    
* The number of recommendations a borrower has can be used to predict whether or not they will clear their loans. Most borrowers have 0 to 1 recommendations but the distributions of recommendations per loan status show the highest concentration of upper outliers around Completed loan status. 
    
* There is a positive relationship between DtI and BorrowerRate, and Current and Completed loan statuses have the highest concentrations of values around the lower regions of both numeric variables. This means that borrowers with lower DtIs and interest ratess are more likely to clear their loans.

## Author

Gorata Malose
<br>
[Linkedin: Gorata Malose](https://www.linkedin.com/in/gorata-bridget-malose/)

## License

This project is licensed under the [MIT](MIT-LICENSE.txt) License and it was submitted by Gorata Malose as part of Udacity's Data Analyst Nanodegree programme.
