# TODO — Taxi Fare Predictor

## Current state (verified from the notebook, not just the README)
- `notebooks/taxi_fare_prediction.ipynb` actually trains **RandomForest** and **XGBoost** with `GridSearchCV`, and fills missing values with `fillna`.
- Only `mean_squared_error` is reported. No R², no cross-validated score, no feature importances.
- The README currently lists "Linear Regression" (not actually used anywhere in the notebook) and hedges on RandomForest/XGBoost with "(if applicable)" — it was written without checking the notebook. Fix this first, it's a quick credibility win.

## Improvements, roughly in priority order
1. **Fix the README** — remove the Linear Regression mention, state plainly that RandomForest + XGBoost (via GridSearchCV) are what's actually used.
2. **Add R² alongside MSE/RMSE** — a bare MSE number means nothing to a reader without context; R² (or RMSE in the fare's own units) is far more readable.
3. **Report cross-validated scores**, not just a single train/test split — right now there's no way to tell if the result is stable or a lucky split.
4. **Surface feature importances** — both RandomForest and XGBoost expose this for free (`.feature_importances_`); a bar chart of top features is a strong, cheap portfolio visual and shows you understand *why* the model works, not just that it runs.
5. **Split the notebook** — 97 cells in one file is hard for anyone (including future-you) to review. Break into clear markdown-separated sections: EDA → feature engineering → modeling → evaluation.
6. **Note the actual Kaggle result** (leaderboard score/rank) in the README if you have it — turns this from "a notebook that exists" into "a result."
