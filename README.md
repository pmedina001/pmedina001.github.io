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

- **Mohler et al (2011)**
  - Developed crime prediction models that were largely based on temporal patterns, using historical event timing to predict future crime events. While this study proved to be innovative in modeling time-based trends, it did not incorporate spatial context or socio-economic variables, limiting its applicability for regional policy planning. 
- **Chainey & Ratcliffe (2005)**
  - Utilized Geographic Information System (GIS)-based mapping techniques to visualize criminal activity in space. Despite their effectivity in identifying historical hot spots, their work remained as a descriptive study and never reached the predictive modeling phase. 
- **Wang et al. (2013)**
  - Introduced the use of demographic data in crime modeling, highlighting the importance of socio-economic factors. However, this study was a much simpler study and never dove into the aspect of geospatial modeling. As such, it never produced spatially interpretable outputs.
- **PredPol (Geolitica)**
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
