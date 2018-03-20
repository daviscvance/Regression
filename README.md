# Regression

For this project I scraped [Box Office Mojo yearly listings](http://www.boxofficemojo.com/yearly/). I collected 15,163 movies, and used 10 variables in my final model to help me predict movie grossing based on mostly categorical variables. I attempted to incorporate budget data which was a subset of only 3,041 of the movies, but it did not perform any better than the model with more data. Below is a description of variables used, the emphasized variables being the ones selected in my final model.

The final model:

Log(Gross) = β0 + β1*AGE_Y + β2*Runtime + β3*Family + β4*PG13 + β5*R + β6*Adventure_Action + β7*Comedy + β8*Documentary + β9*Drama + β10*Thriller_Horror

The associated R^2 value of this model was 0.499 +/- 0.017. My final suggestion after looking at the lasso regularized regression of my full model was for a movie studio to produce a PG-13 Comedy, if they were looking for the safest movie type to go after.
