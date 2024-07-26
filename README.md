   #                         Movie Studio Analysis
 ![image](https://github.com/user-attachments/assets/b85fdeee-c96e-4254-a223-a41f8db6af7a)

This repository contains an analysis of movie data to provide insights on what types of films are performing best at the box office. The goal is to help a new movie studio decide what types of films to create.
## Links
- [Tableau Dashboard](https://public.tableau.com/views/MovieStudioAnalysis_17220225796650/MovieStudioAnalysisDashboard?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
- [Canva Presentation](https://www.canva.com/design/DAGMCdGL5QU/ZbOML_GuD3l3z4GAb0JLDQ/edit?utm_content=DAGMCdGL5QU&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
## Project Overview
We aim to provide actionable recommendations based on data from **Box Office Mojo, IMDB, Rotten Tomatoes, TheMovieDB, and The Numbers.** The analysis will focus on identifying trends and patterns in successful movies.
### Main Objective:
- Identify what types of films would a new movie studio create.
#### Specific Objectives:
- Which genres are most profitable?
- Which genres are most popular among viewers?
- Do viewers prefer long or short movies?
- Which types of films are profitable(Longer/Shorter)?

## Business Understanding
### Data Sources
- Box Office Mojo
- IMDB
- Rotten Tomatoes
- TheMovieDB
- The Numbers

### Data Understanding
From this datasets we shall merge them to get one dataframe(merged) that contains the following columns:
* Movie - Entails the title of the film
* Production_budget - Shows amount spent in production of a film. 
* Domestic_gross -  Shows the revenue generated by a film on within is country. 
* Worldwide_gross - Shows the revenue generated by a film on a global scale.
* Total_gross - Shows the total revenue generated by a film.
* ROI -  Shows the return on investment on a given film.
* Runtime_minutes -Shows the length of a  given film.
* Average rating - Shows the rating of a given film.
* Genre_1 - Describes the primary genre of a given film.
* Genre_2 -  Describes the secondary genre of a given film. 
* Genre_3'- Describes the tertiary genre of a given film.
## Key Findings

## Univariate Analysis
1. **Average Viewer Rating Distribution**
   
![download](https://github.com/user-attachments/assets/50e5db5c-aa4a-4bd9-a53d-5c653bf79309)

- The most common rating is 6.2, with highly rated movies (rating ≥ 9) being rare (1% of the dataset).
  
2. **Movie Runtime Distribution**
   
![download](https://github.com/user-attachments/assets/9f4e137f-adf8-47e8-b554-65a4e57b1f92)

- The most common runtime is 101 minutes, with the majority of movies having runtimes between 90 and 113 minutes.
 

   
3. **Return on Investment (ROI)**
   
   ![download](https://github.com/user-attachments/assets/c545a6fb-8598-4cb4-8e6c-1435a70a6ffe)

- The most common return on investment is 1.09, with the majority of films having ROIs between -0.58 and 3.52.

4. **Genre Distribution**
 
![download](https://github.com/user-attachments/assets/95bfd45d-a0fc-4236-a8b3-1529fa4fda06)

The top genres are:
 - Drama (26.2%)
 - Action (23.8%)
 - Comedy (19.7%).

5. **Production Budgets**
   
![download](https://github.com/user-attachments/assets/ea01c608-2d4c-4271-aed6-e4d54e1d927b)


- The most common budget range is 0 - 50 million dollars, with the highest budget being 425 million dollars (Avatar).

## Bivariate Analysis

1. **Film Profitability by Runtime Category**
   
   ![download](https://github.com/user-attachments/assets/eb4e9c4d-3966-4f6b-b6d8-b9dddf907329)
   
- There is no significant difference in profitability among short, medium, and long movies.
### Evidence
#### Kruskal-Wallis Test Results

- **H-statistic**: 2.00
- **p-value**: 0.368

### Interpretation

- Since this p-value is greater than the common significance level of 0.05, we do not have sufficient evidence to reject the null hypothesis.
- This means that there is no statistically significant difference in the profitability (ROI) among the different runtime categories in this dataset.

  
2. **Ratings by Genre**
![download](https://github.com/user-attachments/assets/8f7e00b2-e593-4d43-801c-486ec63f69e8)

- The highest average ratings are :( **rating > 6.2**)

| GENRE        | Average_Rating |
|--------------|----------------|
| Sport        | 7.9            | 
| Documentary  | 7.07           |    
| Biography    | 6.98           |
| Music        | 6.75           |
| Mystery      | 6.61           |
| Animation    | 6.45           |        
| Adventure    | 6.41           |


3. **Genre by Return on Investment**
   
![download](https://github.com/user-attachments/assets/682196a9-dadf-4a5f-813d-5679b7cd5f53)

- The most profitable genres are  :(**ROI > 2.50** )
  
| GENRE        | Retrun on Inv. |
|--------------|----------------|
| Fantasy      | 4.76           | 
| Mystery      | 3.69           |    
| Aniamtion    | 2.72           |
| Sci-Fi       | 2.69           |
| Adventure    | 2.61           |


## Multivariate Analysis
![download](https://github.com/user-attachments/assets/2eca2906-0043-4585-8a39-a66351d969de)

- A multiple linear regression model was used to predict ROI based on runtime, average rating, and genre.
- The model showed that runtime and average rating are not strong predictors of ROI, with an R-squared value of 0.001.
 
### Interpretation of the model
- **R-squared**: The R-squared value is **0.001**, indicating that only 0.1% of the variance in ROI is explained by the model. This suggests that **runtime and average rating are not strong predictors of ROI**.
#### Coefficients:
- **Intercept (const)**: 5.8064, which is the expected ROI when all predictors are zero.
- **Runtime Minutes**: -0.0259, indicating a very weak negative relationship with ROI. However, the p-value (0.165) is greater than 0.05, suggesting this relationship is not statistically significant.
  
- **Average Rating**: 0.2012, indicating a very **weak positive relationship with ROI**. The p-value (0.538) is also greater than 0.05, indicating this relationship is not statistically significant.
- **F-statistic**: The F-statistic is 1.015 with a **p-value of 0.363**, indicating that the **overall model is not statistically significant**.
  
## Correlation Analysis
- There is a weak positive correlation between vote average and ROI (0.2019).
- There is a weak positive correlation between runtime minutes and ROI (0.0097).

## Linear Regression Models
- Vote average is not a statistically significant predictor of ROI.
- Runtime minutes are not a statistically significant predictor of ROI.

  # CONCLUSSION
- The most profitable genres are:
  
| GENRE        | Retrun on Inv. |
|--------------|----------------|
| Fantasy      | 4.76           | 
| Mystery      | 3.69           |    
| Aniamtion    | 2.72           |

- The most highly rated genres are:
  
| GENRE        | Average_Rating |
|--------------|----------------|
| Sport        | 7.9            | 
| Documentary  | 7.07           |    
| Biography    | 6.98           |

- Viewers prefer longer movies.
- There is no significant difference in profitability among short, medium, and long movie.

  # RECOMMENDATIONS

1. Focus on **Profitable & are highly rated genres**. The most profitable & highly_rated genres are:
 - **Mystery**
 - **Animation**
 - **Adventure**

2. **Consider Viewer Preferences**
 ![download](https://github.com/user-attachments/assets/26ef8eab-1da4-4195-8a3f-b7676ce86fe0)

- Longer movies tend to have higher ratings.
  
3. **Budget Consideration**:
- Most successful films have moderate budgets of 0 - 50 million dollars.
- The recommended genres based on profitability and ratings have the following Production Budget.
  
| GENRE        | Production_Budget |
|--------------|-------------------|
| Mystery      | 17.9 Million      |     
| Animation    | 63.7 Million      |  
| Adventure    | 59.49 Million     |



This comprehensive analysis provides actionable insights for the new movie studio, guiding them on the types of films to create for better box office performance.

