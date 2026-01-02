# The Relationship Between Social Well-Being and Crime:  Analysis of Happiness, Education, and Health Indicators for Turkey

## Introduction
This project investigates how social and economic well-being factors such as happiness, education, and life expectancy influence crime perception for Turkey. Using  data from Kaggle and the World Bank, it analyzes whether higher education levels, longer life expectancy, and greater happiness contribute to safer socities.The goal is to uncover which social indicators best explain the crime rate.

---
## Motivation / Problem Definition
Crime is not only a legal concern but also a reflection of a nation’s social and economic conditions. In Turkey, social factors such as education, health, and overall happiness can influence how safe people feel in their communities.The study first examines worldwide relationships between social indicators and crime perception for the year 2022. Turkey is then analyzed as a case and compared against these global patterns  By focusing on Turkey, the study seeks to provide a clear snapshot of how social development and quality of life correspond with perceived safety within a single national context.

---
## Research Questions / Hypotheses
Hypotheses were evaluated using global correlation analysis (Pearson and Spearman) and residual analysis based on linear regression models. Residuals were used to assess whether Turkey performs better or worse than expected given global relationships.


1- To what extent does a higher education rate contribute to a reduction in crime perception for Turkey?

- H₀ (Null hypothesis): Given the global relationship between education and crime perception, Turkey’s observed crime index is not lower than the value predicted by its education level.
- H₁ (Alternative hypothesis): Given the global relationship between education and crime perception, Turkey’s observed crime index is lower than the value predicted by its education level.

2- Is there a significant negative relationship between happiness levels and the crime index?

- H₀ (Null Hypothesis) Given the global relationship between happiness and crime perception, Turkey’s observed crime index is not lower than the value predicted by its happiness level.
- H₁ (Alternative Hypothesis) Given the global relationship between happiness and crime perception, Turkey’s observed crime index is lower than the value predicted by its happiness level.
  
3- How does life expectancy, as an indicator of overall health and social well-being, influence crime levels?

- H₀ (Null Hypothesis) Given the global relationship between life expectancy and crime perception, Turkey’s observed crime index is not lower than the value predicted by its life expectancy level.
- H₁ (Alternative Hypothesis) Given the global relationship between life expectancy and crime perception, Turkey’s observed crime index is lower than the value predicted by its life expectancy level.

4- Among the key social indicators happiness, education, and health  which exerts the strongest impact on reducing crime for Turkey?

- H₀ (Null Hypothesis) There is no difference in the impact of happiness, education, and life expectancy on crime perception for Turkey.

- H₁ (Alternative Hypothesis) At least one social indicator (happiness, education, or life expectancy) exerts a stronger impact on reducing crime perception for Turkey than the others.
---
## Data Sources
**The datas have been used:**  
The datas are for 2022 and the other years will be not be taken into account. . Global country-level data are used to estimate overall statistical relationships, while Turkey is examined as a focal country for detailed interpretation.
### 1.World Crime Index:
 - Provides global estimates of perceived crime and safety levels based on public surveys. It measures how safe people feel in their countries rather than official crime rates, making it suitable for cross-country comparisons.
 - https://www.kaggle.com/datasets/ahmadjalalmasood123/world-crime-index?select=World+Crime+Index+.csv
### 2.World Happiness Report 2022:
 - Ranks countries by citizens’ life satisfaction scores from the Gallup World Poll, influenced by factors like income, health, freedom, and social support. It is widely used to assess well-being and quality of life globally.
 - https://www.kaggle.com/datasets/mathurinache/world-happiness-report?resource=download&select=2022.csv
### 3.World Bank Education Data:
 - Provides education indicators sourced from UNESCO’s UIS API, including primary school enrollment rates. The data reflect educational access and participation across countries.
 - https://data.worldbank.org/indicator/SE.PRM.ENRR
### 4.World Bank Life Expectancy Data:
 - Derived from UN and Eurostat demographic statistics, estimating average life expectancy at birth for each country. It serves as a key indicator of national health and living standards.
 - https://data.worldbank.org/indicator/SP.DYN.LE00.IN?end=2023&most_recent_year_desc=true&start=1960



---
## Methodology / Data Preparation Plan
### Data Collection:
 - Datasets are obtained from Kaggle and the World Bank, including global indicators for happiness, education, life expectancy, and crime levels. All files are downloaded in CSV format and imported into Python for processing.

### Data Cleaning:
- Missing numerical values were handled using mean imputation. For all the data sets the writing style of 'Turkey' made is standarize to one writing style
### Data Integration:
- The datasets are merged using the common variable Country, forming a unified dataset containing social and economic indicators alongside crime perception scores. 
### Feature Engineering:
 -  Since the dataset represents a single year (2022) rather than a time series, normalization could reduce the visibility of real differences between variables. Therefore, each indicator — such as happiness score, education rate, life expectancy, and crime index — will be presented in its original range to more accurately illustrate their relationships.Additionaly derived metrics such as the education-to-crime ratio and happiness-to-crime ratio, will be generated to capture the relative impact of social well-being on crime levels. In addition Z-score standardization was applied to compare Turkey’s position relative to the global distribution.


---
## Analysis Plan

### Statistical Analysis:
 - Correlation analysis (Pearson and Spearman) and linear regression models were used to assess the global relationship between social well-being indicators and crime perception. Hypotheses were evaluated using both correlation significance and residual analysis from regression models to determine whether Turkey performs better or worse than expected given global patterns.

### Comparative Analysis:
 - To examine the relative strength of each social indicator’s impact on crime perception in Turkey, education, happiness, and life expectancy were compared in terms of their association with the Crime Index.
 -  Since the analysis focuses on a single country and a single year, ratio-based indicators were constructed by dividing each social indicator by Turkey’s Crime Index. This approach allows social well-being measures to be evaluated relative to perceived crime levels, rather than based solely on their absolute values.
#### Education per Crime (3.20): Education appears strong relative to Turkey’s crime perception level.
#### Life Expectancy per Crime (2.42): Health outcomes are also relatively strong compared to perceived crime.
#### Happiness per Crime (0.15): Happiness remains relatively low despite low crime perception.


### Visualization: 
Use scatter plots and regression lines to illustrate the relationships between variables, highlighting how changes in happiness, education rate, and life expectancy correspond to variations in the crime index. Bar charts and correlation heatmaps will also be used to clearly present these relationships for Turkey in 2022.
   #### Scater plot and linear Regression :
   - The scatter plot displays the distribution of countries based on their happiness scores / Life Expectacy / Education score and crime index values. The regression line represents the global linear relationship between happiness / Life Expectacy / Education score and crime perception.
   - Turkey is highlighted with a larger marker for direct comparison with the global pattern.
  #### Histogram :
  - To examine Turkey’s relative position in a global context, histograms of the Crime Index, Happiness Score, Education Rate, and Life Expectancy for the year 2022 were constructed using data from all available countries. Turkey’s observed value for each indicator was highlighted with a red dashed vertical line.
  #### HEAT MAP : 
  -  This correlation heatmap summarizes correlation coefficients between happiness, education, life expectancy, and crime score for the year 2022. The values range from −1 to +1, where negative values indicate negative relationships and positive values indicate direct relationships.

---
## Machine Leaning Methods

Supervised machine learning techniques were applied to analyze the relationship between social well-being indicators and crime perception. The objective was to evaluate how happiness, education, and life expectancy can be used to predict the Crime Index and to compare the relative performance of different regression models.

### Linear Regression
  - Used as a baseline model to understand the linear relationship between social indicators and crime perception.
  - The model showed limited predictive performance, indicating that crime perception cannot be explained well by a simple linear relationship.
  - Served as a reference point for comparing more complex models.

### k-Nearest Neighbors (kNN) Regression

  - Applied to capture local and non-linear patterns in the data.
  - Feature scaling was performed before training due to the distance-based nature of kNN.
  - The model did not significantly improve prediction accuracy compared to Linear Regression, suggesting that nearby countries with similar indicators do not always share similar crime perception levels.

### Decision Tree Regression
  - Used to model non-linear relationships through rule-based splits.
  - A shallow tree was selected to reduce overfitting.
  - The results showed slight improvements in interpretability but limited gains in prediction accuracy.

### Results
- None of the models achieved high predictive accuracy, which is expected due to the subjective and complex nature of crime perception.
- the models provided more explanatory insights than precise predictions.
- The analysis highlights, social well-being indicators alone are insufficient to fully predict crime perception.
- The trained Linear Regression model was used to predict Turkey’s Crime Index based on its happiness, education, and life expectancy values.
- The negative residual indicates that Turkey’s actual crime perception is significantly lower than what the model predicts based on its social well-being indicators.
- This result suggests that Turkey performs better than expected in terms of crime perception when compared to countries with similar social indicator levels.





---
## Expected Outcomes / Deliverables

This project aims to provide data-driven insights into how social well-being indicators happiness, education, and health influence global crime perception in Turkey.

**Expected findings include:** 

 - Quantified correlations showing that higher education and happiness levels in Turkey are linked to lower crime indices.
 - Statistical evidence that life expectancy  also contributes to reduced crime perception.
 -  Visual results illustrating how changes in happiness, education rate, and life expectancy relate to variations in the crime index within Turkey.
 -  Regression-based conclusions identifying education and happiness as the strongest predictors of safety, revealing how social progress can reduce perceived crime in Turkey

## Limitations
This study focuses only on Turkey and uses data from a single year (2022), which limits the ability to observe trends or changes over time. Additionally, the variables are based on perception-based indices such as the Crime Index and Happiness Score, which may include subjective bias. Data availability from different sources might also introduce slight inconsistencies in measurement or reporting.

## Future Work
Future extensions of this study could involve expanding the dataset to include multiple years to observe temporal trends in the relationship between social indicators and crime perception. Cross-country comparisons could also provide a broader understanding of cultural and economic effects on crime perception. Additionally, integrating more complex analytical models or machine learning approaches could enhance prediction accuracy and uncover deeper insights into how education, health, and happiness contribute to safety and social stability.
