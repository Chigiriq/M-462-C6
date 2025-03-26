Best subset selection: Algorithm 6.1

    1. Let M0 denote the null model 
            Y = B0 + epsilon
            (no predictor vars)

    2. For k = 1,2,...,p
        a. fit all [p] models with k predictors
                   [k]
        b. pick the best model (lowest RSS or largest R^2) amoung the
            [p] models, call it Mk
            [k]
    
    3. Select a single best model among M0,...,Mp using predication error on a validatioin set, Cp(AIC), BIC, adjusted R^2, or cross-validations

    Note: Adding more variables will always reduce RSS or increase R^2

    Fig 6.1 shows the results of an implementation of Alg 6.1





Forward Stepwise Selection: Algorithm 6.2
    
    1. Let M0 be the null model
    2. For k=0,...,p-1
        a. Consider all p-k models that augment the predictors in Mk with the  additional predictor

        b. Choose the best among these p-k models, using the RSS or R^2 (as above) as a measure

    3. Select a single best model among M0,...,Mp using predication error on a validatioin set, Cp(AIC), BIC, adjusted R^2, or cross-validations

    Note: this adds one predictor at a time         



We've Done
    1 & 2. Give a sequence of models M0, ..., Mp
Now 
    3. Choose the best model


Two approaches
    1. Undirectly estimate test error by making an adjustment to the training error that accounts for overfitting.
    2. Use cross validation -- directly estimate test error


    Approach 1: Cp, AIC, BIC, adjusted R^2

        Cp: estimate test MSE (unbiased estimator... of test error)
        AIC (Akaike Information Criteria): estimator of prediction error
        BIC (Bayesian Information Criteria): will generally choose a simpler model
        ajusted R^2: how well the model predicts NEW observations

    Approach 2: Cross Validation

Shrinkage Methods
    penalize large values of B0_hat, ..., Bp_hat

    Ridge Regression: estimating the coeffs of multi-regression models where independent vars are highly correlated

    