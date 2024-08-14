## 1. Project Overview:

  This project aims to analyze and model the impact of weather conditions on bike rentals in Washington, D.C.'s Capital Bikeshare system. We combine bikeshare data with        weather data to build and evaluate predictive models, explore different regression approaches, and make data-driven recommendations for business strategies.

## 2. Data Description

The dataset includes information on bike rentals and weather conditions, with the following variables:
  
**DATE**: Date of the rental.
  
**HOLIDAY**: Indicator if the day is a U.S. holiday (1 for yes, 0 for no).
    
**WEEKDAY**: Indicates if the day is a weekday (1 for yes, 0 for no).
  
**WEATHERSIT**: Weather situation:
    
  1: Clear/Few clouds
    
  2: Misty
    
  3: Light snow or rain
        
  4: Heavy rain, snow, or thunderstorms
    
**TEMP**: Average temperature in Celsius.

**ATEMP**: “Feels like” temperature in Celsius.
  
**HUMIDITY**: Humidity percentage (not divided by 100).
  
**WINDSPEED**: Wind speed in km/h.
  
**CASUAL**: Count of bikes rented by casual users.
  
**REGISTERED**: Count of bikes rented by registered users.
  
**COUNT**: Total number of bikes rented (sum of CASUAL and REGISTERED).


## 3. Preparation and Analysis

*3.1 Data Preparation*

  * Created COUNT by summing CASUAL and REGISTERED.
    
  * Extracted MONTH from DATE and converted it to a factor.

  * Saved the modified dataset as dfb_int.
    
*3.2 Basic Regression Model*

  * Built a regression model (fit_all) with COUNT as the outcome and all other variables as predictors.

  * Noted potential overfitting due to high R-squared value.

*3.3 Exploratory Analysis*

  * Added BADWEATHER variable to indicate poor weather conditions.
  
  * Created scatter plots to visualize the relationship between ATEMP and COUNT, CASUAL, REGISTERED, and BADWEATHER.

  * Observed that bike rentals increase with moderate temperatures and decrease in bad weather.
  
## 4. Regression Modeling
  
*4.1 Comprehensive Model*
  
  * Built a regression model including MONTH, WEEKDAY, BADWEATHER, TEMP, ATEMP, and HUMIDITY to predict COUNT.

  * Evaluated model performance with Adjusted R-squared, RMSE, and MAE.

  * Addressed multicollinearity by removing TEMP.

*4.2 Simple Linear Regression*

  * Built a model to assess the impact of BADWEATHER on COUNT alone.

  * Compared results with the more comprehensive model from previous steps.
    
*4.3 Domain Knowledge Input*

  *Added interaction between BADWEATHER and WEEKDAY to the regression model.

  *Evaluated if this model provided better predictive performance.
  
## 5. Predictive Analytics

*5.1 Model Building*

  * Split data into training and test sets.
  * 
  * Built two models: one with WINDSPEED and one without.
  * 
  * Compared performance metrics of both models.

  *5.2 Performance Results*
  
  Model including WINDSPEED had lower RMSE and MAE, indicating better predictive performance.
  
## 6. Time Series Analysis

*6.1 Model Building*

  *Split data by year and by months to build and compare models (fit_time and fit_time_v2).
  
  * Analyzed performance of time-based models versus random split models.
    
*6.2 Performance Results*

Fit_time provided the best results, with a higher Adjusted R-squared value compared to other time-based models.

## 7. Recommendations

  * Pricing and Promotions: Consider offering discounts during times of lower demand (e.g., bad weather) and ensure capacity is sufficient during peak times.
  
  * Rebalancing Bikes: Use timestamp data to understand bike flow and optimize bike distribution to match demand.

  * Sustainability: Leverage advertising to promote bike usage and encourage social responsibility.
    
## 8. Future Work
   
  * Continuously monitor and adjust models based on new data.
 
  * Explore additional features or external data (e.g., events) to further refine predictions and strategies.
    
## 9. References
    
R Libraries Used: 

    library(ggplot2)
    library(readr)
    library(lubridate)
    library(dplyr)
    library(broom)
    library(modelr)
    library(rsample)
    library(tidyverse)
    library(tidymodels)
    library(performance)
