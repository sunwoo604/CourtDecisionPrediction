# CourtDecisionPrediction

## EDA
- EDA was performed on cleaned dataset and simple hypothesis testing was performed

### Cleaning: 
- All the values that can be categorized as unknown("Unknown", "Missing", etc) to np.nan.
- Added new column "party" to indicate which administration was in power when the allegations were submitted

### Hypothesis Testing:
- null hypothesis: The court decision was equally likey to be against non-white complainant when they sued white police officer whether it was under Democrat or Republican administration. 
- Alternative hypothesis:The court decision was more likely to be against non-white complainant when they sued white police officer during republican time compared to Democrat time. 
- Conclusion: We set our alpha as 0.05(conventionally used) Our p-value is 0.25 so we fail to reject our null hypothesis.

## Model Development
- Classification model to determine whether the court will favor the complaints
- Decision Tree Classifier was used

### Model
- Features: 
- OneHotEncoded fado_type(Force, abuse of authoruty, Dscourtesy, and Offensive language)
- OneHotEncoded rank_incident(rank of the officer when complain was submitted)
- Boolean value of whether the case was under Democrat or Republican
- Boolean value whether complaint's race was white or POC

### Fairness Analysis

I wanted to see if my model perform differntly based on the fact whether they are senior or not. 
- Null Hypothesis: Fianl model has no differnece in performance whether the complainant was a senior or not. 
- Alternative Hypotehsis: Fianl model performs differently based on the fact that whether complainant was a senior or not. We will use 0.05 as our p-value.

I got a p-value of 0.545 which is bigger than 0.05. In conclusion, we can conclude there is no sufficient evidence to say my final model's performance vary based on complainant's age and that my final model performs uniformly.
