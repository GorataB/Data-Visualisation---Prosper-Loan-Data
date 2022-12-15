# Data-Visualisation---Prosper-Loan-Data
Perform exploratory data analysis and communicate findings using explanatory plots.

## Dataset

> There are 113, 937 loan listings in the [Prosper Loan dataset](prosperLoanData.csv), with 81 features. The dataset is too large, so I created a dataframe called 'loan', with only 32 columns, which include variables of interest, related variables, and identifier variables. The [data dictionary](<Prosper Loan Data - Variable Definitions.xlsx>) explains all the variables in the dataset. 
> 
> I also performed some preliminary wrangling to fix some column names and order of some categorical values. Most variables are numeric, but there are a few nominal and ordinal categorical variables, some of which I used in my exploration. 
> 
> I'm interested in factors that affect loan status **(LoanStatus)**, which is a nominal categorical variable. I expect numeric variables like **BorrowerRate** and **DebtToIncomeRatio** (DtI), and categorical variables like **EmploymentStatus** and **IncomeRange** to be strong determinants of loan status. Though variables like **IncomeVerifiable** (categorical) and **Recommendations** (numeric) will not have as direct an influence, I expect them to be useful predictors of whether an individual will clear their loan.
>
> I will first perform exploratory analysis, followed by explanatory analysis on a slide deck.

## Files

1. [ProsperLoan_Part1_Exploration.ipynb](ProsperLoan_Part1_Exploration.ipynb): the Jupyter Notebook for exploratory analysis.
2. [ProsperLoan_Part1_Exploration.html](ProsperLoan_Part1_Exploration.html): the html version of the exploratory analysis.
3. [ProsperLoan_Part_II_slide_deck.ipynb](ProsperLoan_Part_II_slide_deck.ipynb): the Jupyter Notebook for explanatory analysis, which is in the form a slide deck.
4. [ProsperLoan_Part_II_slide_deck.slides.html]( ProsperLoan_Part_II_slide_deck.slides.html): the html version of the explanatory analysis.
5. [prosperLoanData.csv](prosperLoanData.csv): the dataset to be used for analysis. It is available under Releases as it was too large to upload.
6. [Prosper Loan Data - Variable Definitions.xlsx](<Prosper Loan Data - Variable Definitions.xlsx>): a data dictionary explaining all the variables in the dataset.
7. [wrangle_and_summary.pdf](wrangle_and_summary.pdf): this is a report summarising the exploratory findings and wrangling efforts in more detail. It includes univariate, bivariate and multivariate analyses. Only key insights, listed below, will be included in the explanatory analysis, but the rest of the findings can be found in the wrangle_and_summary report.

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
