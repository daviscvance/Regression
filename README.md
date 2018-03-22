# Regression

For this project I scraped [Box Office Mojo yearly listings](http://www.boxofficemojo.com/yearly/) with Beautiful Soup. I collected 15,163 movies, and used 10 variables in my final model to help me predict movie grossing based on mostly categorical variables. I attempted to incorporate budget data which was a subset of only 3,041 of the movies, but it did not perform any better than the model with more data. Below is a description of variables used:

- TITLE = Title 
- ADJ_GROSS = Adjusted (2017) total domestic grossing
- LOG_GROSS = Log of ADJ_GROSS
- RELEASE = Release date as datetime object
- AGE = Age as of January 31, 2018 in days
- GENRE = Movie genres as categorical dummy variables:
    - Thriller_Horror 
    - Comedy
    - Documentary
    - Drama 
        - (Drama | Romance)
    - Adventure_Action
        - (Sci-Fi | Fantasy | Adventure | Crime | Western | War | Action)
    - Baseline is all others
        - (Animation | Foreign | Musical | Concert | IMAX | Family | Unknown | Sports | Epic)

- RUNTIME = Runtime in minutes
- RATING = MPAA Rating as categorical dummy variables:
    - Family 
        - G
        - PG
    - PG-13
    - R
    - Baseline is all others 
        - (Unrated, Not Yet Rated, NC-17, Unknown)
- BUDGET = Budget (Unadjusted)
- LOG_BUDGET = Log of BUDGET

After baselining and comparing multiple models I chose my final model to be:

Log(Gross) = β0 + β1*AGE_Y + β2*Runtime + β3*Family + β4*PG13 + β5*R + β6*Adventure_Action + β7*Comedy + β8*Documentary + β9*Drama + β10*Thriller_Horror

The associated R^2 value of this model was 0.499 +/- 0.017. My final suggestion after looking at the lasso regularized regression of my full model was for a movie studio to produce a PG-13 Comedy, if they were looking for the safest movie type to go after. The regression notebook has extra details!
