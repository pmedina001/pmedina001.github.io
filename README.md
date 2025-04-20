# Capstone Project: Crime Hotspot Prediction in Florida
**Pedro J Medina**

**Panther ID: 6191466**  

**Github created as part of the Masters in Data Science Capstone Project Program**  

**April 2025**  

**Project Primary Mentor: Dr. Levente Juhasz**  

**Project 2nd Mentor: Dr. Christine Lisetti**  

**Capstone Course Professor: Ananda Mondal**  

# Abstract
This project aims to explore the integration of machine learning, socio-economic data, & geospatial analysis to identify and predict crime hotspots across all of the counties in the state of Florida. By utilizing historical crime data from the **Florida Department of Law Enforcement (FDLE)** simultaneously with socio-economic factors from the **U.S. Census Bureau**, the study investigates how factors such as housing, education, and incomes correlate with crime rates.  

The methodology used in this project combines **Exploratory Data Analysis (EDA)**, **Correlation Analysis**, and **Machine Learning modeling** to uncover patterns and predict crime rates. Visualizations that were generated for this study include regional distributions, actual crime rates heatmaps, predicted crime rates heatmaps, socio-economic factors heatmaps, and correlation matrices to support interpretability and data-driven insights. Spatial mapping was also used to provide an interactive representation of the crime trends across all counties.  

The resulting Github offers a reproducible platform for all types of stakeholders to explore findings and demonstrates how AI & data visualization can help to influence public safety strategies, policing strategies, and urban planning decisions. 

# Problem Statement
Crime has been a persistent public safety concern that impacts not only Florida, but all communities across the world. Traiditional approaches have been used to analuze crime trends, but they often lack the spatial and predictive depth needed to be able to predict future crime risks. Law enforcement agencies and policymakkers have stressed the need of tools that are able to go beyond traditional statistical methods to identify high-risk areas and address socio-economic conditions that may lead to an increase in crime activity.  

With the advancements being made in the **Data Science** field, the tools and methods available can help to provide a data-driven approach to crime prediction. Using historical crime data with county-level socio-economic factors and spatial analysis, this study aims to uncover patterns and relationships between crime types and socio-economic indicators. By applying machine learning modeling and geospatial visualizations, all predictions made are visualized to provide a better understanding of the relationships uncovered.

# Research Questions
1) Which Florida counties show signs of future crimes based on spatial-temporal patterns?
2) Which **Socio-Economic factors** correlate the most with crime?
3) How does integrating **Geosapatial data** and **AI** improve prediction accuracy?

# Prior Arts & Challenges
## Prior Arts
Over the recent years, there have been numerous efforts made towards the understanding and prediction of crime using statistical and computational methods. Traditional approaches have included hot spot mapping through kernel density estimation, regression-based predictions, and crime trend dashboards utilized and maintained by law enforcement agencies. While these methods provide valuable insights and serve as accomplishments in the field of crime prediction, they often lack the integration of socio-economic context or predictive modeling capabilities.  

Academic research has also explored the use of machine learning for crime prediction, focusing on specific cities or using smaller datasets. There have also been commercial tools that have been introduced into the market to provide additional approaches to crime prediction. A few examples of these studies and commercial tools include:  

- **[Mohler et al (2011)](https://www.tandfonline.com/doi/abs/10.1198/jasa.2011.ap09546)**
  - Developed crime prediction models that were largely based on temporal patterns, using historical event timing to predict future crime events. While this study proved to be innovative in modeling time-based trends, it did not incorporate spatial context or socio-economic variables, limiting its applicability for regional policy planning. 
- **[Chainey & Ratcliffe (2005)](https://www.wiley.com/en-us/GIS+and+Crime+Mapping-p-9781118685198)**
  - Utilized Geographic Information System (GIS)-based mapping techniques to visualize criminal activity in space. Despite their effectivity in identifying historical hot spots, their work remained as a descriptive study and never reached the predictive modeling phase. 
- **[Wang et al. (2013)](https://www.researchgate.net/publication/309351102_Crime_Rate_Inference_with_Big_Data)**
  - Introduced the use of demographic data in crime modeling, highlighting the importance of socio-economic factors. However, this study was a much simpler study and never dove into the aspect of geospatial modeling. As such, it never produced spatially interpretable outputs.
- **[PredPol (Geolitica)](https://en.wikipedia.org/wiki/Geolitica)**
  - A commercial predictive policing tool that was introduced in the market. It has gained popularity for its ability to predict future crime locations using proprietary algorithms. However, it’s been criticized time after time for being a “black box” solution, meaning that the answers it produces lack transparency, reproducibility, and the inclusion of socio-economic context. This makes is difficult to evaluate/adapt for public policy use.

This project builds on the ideas and foundations set in previous studies/works by combining predictive modeling, demographic and economic context, and geospatial mapping into a solid and reproducible framework focused on Florida’s 67 counties. 

## Challenges
- **Data integration across sources**
  - Combining crime and socio-economic data required normalization and alignment across different data formats, time periods, and geographic identifiers.
- **County-level geospatial merging**
  - Integrating shapefiles with statistical data required precise joining based on standardized county names and codes.
- **Feature selection & interpretation**
  - Identifying which socio-economic variables had the strongest influence on crime rates required a balance of correlation analysis, domain knowledge, and machine learning feature importance.
- **Modeling tuning & validation**
  - Ensuring reliable model performance across multiple counties and years involved hyperparameter tuning and cross-validation strategies.
- **Maintaining reproducibility**
  - Ensuring that every step taken in this project could be reproduced by outside users involved clear documentation and standardized coding methods.
 
# Data Overview
This project utilizes three main datasets that capture the necessary data to fulfill the areas of crime statistics, socio-economic factors, and geographic boundaries. All data was collected and preprocessed for all 67 counties that compile the state of Florida, spanning the time range of the years of 2015 through 2020.

1) **Crime Data**
  - **Source:** [Florida Department of Law Enforcement](https://www.fdle.state.fl.us/CJAB/UCR/Annual-Reports/UCR-Offense-Data)
  - **Dataset(s) description:** Data was split into two datasets. One dataset (68 rows x 8 columns) represents the annual counts of reported violent crimes at the county level. The other dataset (68 rows x 7 columns) represents the annual counts of reported property crimes at the county levels.
  - **Data variable and units:**
      - Violent Crimes:
          - **Murder** – Number of reported homicide cases
          - **Rape** – Number of reported rape cases
          - **Robbery** – Number of reported robbery cases
          - **Aggravated Assault** – Number of reported aggravated assault cases
      - Property Crimes:
          - **Burglary** – Number of reported burglary cases
          - **Larceny** – Number of reported theft cases
          - **Motor Vehicle Theft** – Number of reported vehicle thefts
  - **Derived variables:**
      - **Total Violent Crime**
          - Murder + Rape + Robbery + Aggravated Assault
      - **Total Property Crime**
          - Burglary + Larceny + Motor Vehicle Theft
      - All crime counts were normalized to Incidents per 100,000 people (done during preprocessing)
  - Data was split into the 3 regions of Florida (North Florida, Central Florida, & South Florida) for regional analysis.

2) **Socio-Economic Factors Data**
  - **Source:** [U.S. Census Bureau – American Community Survey (ACS) 5-Year Estimates](https://data.census.gov/profile/Miami-Dade_County,_Florida?g=050XX00US12086)
  - **Dataset(s) description:** Socio-economic indicators collected at the county-year level (68 rows x 8 columns)
  - **Data variable and units:**
      - **Median Household Income** – reported median income (USD) for households per county
      - **Poverty Rate** – percent of total population living below poverty line
      - **Unemployment Rate** – percent of civilian labor force (age 16+) that is unemployed
      - **Educational Attainment Levels** – percent of adults (age 25+) with a Bachelor’s degree or higher
      - **Homeownership Rates** – percent of occupied housing units that are owner occupied
      - **Population Density** – people per square mile (people/mi²) calculated by dividing population by county area
      - **Total Population** – total number of residents per county

3) **Florida County Geospatial Data**
  - **Source:** [U.S. Census Bureau TIGER/LINE 2020](https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.2020.html#list-tab-790442341)
  - **Dataset(s) description:** Geospatial shapefiles used to map Florida’s 67 counties (67 rows x 13 columns).
  - **Data variable and units:**
      - **STATEFP, COUNTYFP, GEOID** – Federal and geographic codes
      - **NAME** – County name
      - **geometry** - Polygon coordinates for each county

# Methodology
## Tools Used
  - **R Studio** (version **4.3.1**)
      - **dplyr & tidyverse** – used for manipulating data and wrangling
      - **ggplot2, sf & tmap** – used for visualizations and geospatial plotting
      - **readr & janitor** – used for cleaning all data
      - **corrplot & psych** - used to generate correlation matrices and perform exploratory analysis
   
  - **Python** (version **3.10**)
      - **pandas & numpy** – used for manipulating data
      - **scikit-learn** – used for model training, feature selection, and model evaluation (RandomForestClassifier, SVC, train_test_split, GridSearchCV)
      - **matplotlib & seaborn** – used for creating plots and visualizations
      - **geopandas** – used for loading geospatial data and plotting (county shapefiles)
      - **shapely, plotly** – advanced spatial joins and interactive maps

## Data Preparation
All datasets were loaded in using the .csv and .shp formats to ensure consistency. County crime counts were normalized as **incidents per 100,000** people using the available population data. All datasets were merged using the county_name or GEOID using the pandas library within Python and the dplyr library within RStudio. The geospatial shapefiles collected from the TIGER/LINE 2020 dataset were filtered to include only Florida counties (STATEFP = 12), and all geometry was preserved. 

## Exploratory Data Analysis (EDA)
The initial EDA phase provides key insights into crime patterns and socio-economic disparities across Florida’s 67 counties from 2015 to 2020.  

**Distribution of Crime types:** 
![Distribution of Crimes](Project%20Results/EDA%20Charts/Distribution%20of%20Crimes.png)  

As presented in the pie charts above, **Aggravated Assault** made up the majority of violent crimes (66.9%), followed by Robbery (23.1%), Rape (8.8%), and Murder (1.1%). For property crimes, **Larceny** dominated the total count (76.6%), followed by Burglary (19.6%) and Motor Vehicle Theft (3.7%). The total amount of violent crimes in the dataset is **516,697** and **1,807,105** for property crimes.

This imbalance between the crime types confirms that property crimes are far more prevalent than violent crimes statewide.  

**Regional Crime Patterns:**  
![Regional Comparison Barchart](Project%20Results/EDA%20Charts/Violent%20%26%20Property%20Crimes%20Regional%20Comparison%20Barchart.jpg)  

Bar charts were generated to visualize the regional comparison of crime totals per each region. Property crimes consistently exceeded violent crimes in all regions. Central and South Florida reported the highest levels of property crimes. South Florida had the highest volume of violent crimes, suggesting a need for a deeper localized analysis. 

**Regional Socio-Economic Distributions:**  
![Regional Socio-Economic Distributions](Project%20Results/EDA%20Charts/Regional%20Socio%20Economic%20Distributions.png)  

**Income & Education**  
South Florida reported the highest median household income and educational attainment levels, suggesting greater access to education and higher-paying jobs. North Florida had the lowest income and education levels across all counties.  

**Poverty & Employment**  
North Florida showed higher poverty rates and lower employment levels compared to other regions. Central Florida maintained a more balanced level of socio-economic metrics across all factors.  

**Housing & Population Density**  
South Florida had the highest number of housing units and was the most densely populated region by far, followed by Central Florida. North Florida, being more rural, showed lower density and fewer housing units.  

## Correlation Analysis
Correlation analysis was performed in R using the corrplot library to visualize the correlation between the socio-economic factors and the various crime types. The factors that had the highest correlation with the crime types were selected. Feature importance was computed from the trained Random Forest model in python to rank predictors based on their influence on crime prediction.  

2 correlation matrices were generated within R using the corrplot library. These matrices visualize the relationship between each socio-economic factor and the violent/property crime types.  

![Violent & Property Crime Correlation Heatmap](Project%20Results/Correlation%20Analysis%20Matrices/Violent%20%26%20Property%20Crime%20Correlation%20Heatmap.png)  

Poverty Rate and Housing Units showed the strongest positive correlations with both violent and property crimes. Educational Attainment levels and Employment Rates had moderate correlations with the crime types. Poverty Rates had a negative correlation with property crime types, suggesting counties with higher poverty tend to have higher crime rates. Median Household Income showed the weakest correlations with both crime types, suggesting that even wealthier areas are prone to crime. 

**Heatmaps of Actual Crime Rates**    
To complement the correlation analysis, spatial heatmaps were created to visualize the actual distribution of the crime types across Florida. These maps provide insights into regional crime concentrations.  

![Actual Crime Rates](Project%20Results/Actual%20Crime%20Rates%20Heatmaps/Actual%20Crime%20Rates.png)  

![Socio-Economic Factors Heatmap](Project%20Results/Socio-Economic%20Factors%20Heatmaps/Socio%20Economic%20Factors%20Heatmap.png)  

## Feature Selection
Following the completion of the correlation analysis, feature selection was finalized using the features that showcased the highest correlations with the crime types. The goal of this phase was to strictly retain variables that contributed meaningfully to the models’ predictive performance.  

The features that were selected for the modeling phase were:
  - **Population Density**
  - **Housing Units**
  - **Educational Attainment Levels**
  - **Employment Rates**
  - **Poverty Rates**

## Predictive Modeling
Three machine learning models were developed and trained in Python using the scikit-learn and XGBoost libraries to predict crime levels based on the previously selected socio-economic features. The predictions were measured in terms of **county-level crime rate per 100,000 residents**. Each model was trained to predict violent and property crime rates for all Florida counties.  

1) **Decision Tree Regressor**
     - Simple, interpretable baseline model used to establish foundational accuracy.
     - Provides a clear view of decision rules and feature splits.
     - Prone to overfitting on small datasets, but useful for comparing models.
       
2) **Random Forest Regressor**
     - Ensemble model that builds multiple decision trees and aggregates their predictions to improve generalization.
     - Handles non-linear relationships and reduces overfitting through bootstrapped sampling and averaging.
     - Feature importance values were extracted using .feature_importances_.
       
3) **XGBoost Regressor**
     - High-performance gradient boosting algorithm with built-in regularization.
     - Tuned using GridSearchCV to optimize learning rate (eta), tree depth, and subsample ratio.
     - Especially effective in handling unbalanced data and noisy features. 

**Training and Evaluation Strategy:**
  - **Train-test split**: 80% training, 20% testing
  - **Cross-validation**: 5 fold cross-validation used to ensure model robustness
  - **Evaluation metrics**:
      - **RMSE (Root Mean Squared Error)** – measures the prediction error (the lower the better)
      - **R^2 Score** (Coefficient of Determination) – indicates how well variance is explained (the higher the better)





