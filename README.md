# Football xG Predictor

## Project Overview

This project, developed for the IE 7275 Data Mining in Engineering course, focuses on creating a predictive model for the Expected Goals (xG) of shots in football (soccer). Expected Goals (xG) is a statistical metric that quantifies the probability of a shot resulting in a goal. By leveraging machine learning, this model analyzes various in-game event features to provide a precise estimation of goal-scoring probability, offering valuable insights for performance analysis, strategic planning, and tactical decision-making.

## Data

The model was trained and evaluated on a comprehensive football event dataset from the **Wyscout** platform. This public dataset covers match events from the top five European football leagues: England, Spain, Italy, Germany, and France.

- **Source**: Soccer match event dataset on Figshare
- **Size**: The initial dataset contained approximately 600,000 match events, which was filtered down to 40,461 shot events (`eventId=10`) for this analysis.

## Methodology

The core of this project involved extensive data preprocessing, feature engineering, and the implementation of multiple classification models to predict whether a shot would result in a goal.

### 1. Feature Engineering & Preprocessing

- **Coordinate Extraction**: Parsed JSON data to extract the X and Y coordinates for the start and end positions of each shot.
- **Feature Creation**: Engineered key predictive features, including:
  - `shotDist`: The distance from the shot location to the center of the goal.
  - `shotAngle`: The angle from the shot location relative to the goalposts.
  - `shot_foot`: Determined whether the shot was taken with the player's strong foot, weak foot, or was a header by cross-referencing event tags with player profile data.
- **Data Cleaning**: Handled missing values by dropping a small number of rows with incomplete player data.
- **Dimensionality Reduction**: Utilized **Principal Component Analysis (PCA)** to reduce the feature space and visualize the data.

### 2. Modeling

Several machine learning models were trained to classify shots as either a goal (1) or no-goal (0). The models were evaluated based on their accuracy.

- **Logistic Regression**: Achieved an accuracy of **89.44%**.
- **Decision Tree Classifier**: Achieved an accuracy of **84.03%**.
- **Random Forest Classifier**: Achieved an accuracy of **89.15%**.
- **Gradient Boosting Classifier**: Achieved an accuracy of **89.49%**.

The **Gradient Boosting Classifier** was selected as the final model due to its superior performance.

## Results & Impact

The final model provides a reliable method for estimating the xG of any given shot, which has significant applications in modern football analytics:

- **Performance Enhancement**: Offers data-driven insights to teams for improving strategic planning and player evaluation.
- **Competitive Advantage**: Allows for deeper analysis of opponent weaknesses and maximization of goal-scoring opportunities.
- **Innovation in Sports Analytics**: Contributes to the advancement of sports analytics by combining machine learning with traditional performance metrics.
- **Fan Engagement**: Enhances the fan experience by providing deeper, data-backed insights into game dynamics.
