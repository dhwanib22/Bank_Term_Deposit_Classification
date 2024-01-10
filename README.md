# Bank Term Deposit Classification

## Business Scenario

The Portuguese bank is facing a decline in revenue, and upon investigation, it was identified that clients are not depositing as frequently as before. Term deposits offer an opportunity for banks to hold deposits for a specific period, allowing them to invest in higher-gain financial products. Additionally, banks can leverage term deposit clients for cross-selling other products, such as funds or insurance, to increase revenues. The goal is to identify existing clients with a higher chance of subscribing to a term deposit and focus marketing efforts on them.

## Problem Statement

Build a Proof of Concept (POC) to address the problem using data related to direct marketing campaigns of the Portuguese banking institution. The campaigns involve phone calls, and multiple contacts with the same client are often required to determine if the client will subscribe ('yes') or not ('no') to a bank term deposit.

**Business Challenge: Address a revenue decline by identifying high-potential term deposit clients.**

## Approach Used

1. **Extensive Exploratory Data Analysis (EDA):** Uncover insights from the dataset of marketing campaign interactions.

2. **Imbalance Handling**: Employ effective techniques to address class imbalance in the data.

3. **Model Evaluation Metrics:** Given the dataset's 8:1 imbalance, accuracy is not a suitable metric. Preferred metrics are:
   - Balanced Accuracy, (TPR+TNR)/2
   - F1 Score

4. **Ensemble Approaches:** Chose ensemble methods for better performance on imbalanced classification, considering both minority and majority classes.

5. **Models Explored:**
   - Random Forest
   - Logistic Regression
   - AdaBoost
   - Balanced Random Forest
   - Balanced Bagging with Logistic Regression
   - Random Undersampled Boost
   - XGBoost

## Data:
This repository houses a dataset detailing direct marketing campaigns from a Portuguese bank, including client characteristics, campaign details, and outcomes.

## Model Performance

| Model                | Accuracy | Balanced Accuracy |
|----------------------|----------|-------------------|
| Random Forest        | 0.899971 | 0.593510          |
| Logistic Regression  | 0.899388 | 0.578023          |
| AdaBoost             | 0.900456 | 0.599468          |
| Balanced Random Forest | 0.804312 | 0.732167        |
| Balanced Bagging with LR | 0.747499 | 0.719127 |
| Random Undersampled Boost | 0.833835 | 0.734389  |
| EasyEnsemble |	0.832475 |	0.733244 |
| XGBoost              | 0.830145 | 0.731932          |

Ensemble approaches will be better suited for our business problem because even though their overall accuracy is lower,
they do a better job at identifying the true positives (minority) as well as true negatives (majority).

## Conclusion

**Proof of Concept:**
- Target customers who are retired, unemployed, single, illiterate, haven't defaulted on credit, prefer cell phone contact, and were subscribed in the previous campaign.
- Focus efforts in the months of March, December, September, and October.
- Age groups: Senior (older than 51) or young (younger than 31).

**Insights:**
- Longer duration of the last contact correlates with higher conversion rates.
- Contacting a person beyond 5 times has negligible results.
- Previous customers are more likely to subscribe than first-time contacts.

