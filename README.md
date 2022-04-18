# MechaCar_Statistical_Analysis

## Overview of Project

MechaCar is the newest prototype of the company AutosRUs. This prototype is suffering from production troubles that are blocking the manufacturing team’s progress. This data analysis is focused on reviewing the production data to gather insights that may help the manufacturing team.

#### Deliverable 1: Linear Regression to Predict MPG : Perform multiple linear regression analysis to identify which variables in the dataset predict the mpg of MechaCar prototypes

For this part of the analysis, we use the dataset in MechaCar_mpg.csv file that contains Miles per Gallon (mpg) test results for 50 MechaCars prototypes. The prototypes were produced using multiple design specifications to identify ideal vehicle performance. A linear model is designed and coded in R to predict the mpg of the prototypes using several variables: vehicle length, vehicle weight, spoiler angle, drivetrain, and ground clearance. Figure 1 shows the linear model used (R bult-in function lm) and its output:

<img width="724" alt="Screen Shot 2022-04-18 at 1 43 58 PM" src="https://user-images.githubusercontent.com/95304774/163850813-33ad5c5b-0396-441c-94ed-3746be9b6c08.png">

* Coefficients that provide a non-random amount of variance to the mpg estimation are the vehicle_length and ground_clearance (indicated by ***). Their p-values (column Pr(>|t|)) are smaller than 0.05, which means they are statistically significant and contribute to the model. The intercept is also statistically significant, which means there are other variables, not included in this analysis, that could impact on the mpg.

* The slope in a linear model represents the relationship between the variable being estimated and the other(s) variables, i.e., if there are variables contributing to the estimation of a specific one. To check if the slope of our model is zero or not, we need to look at the Performance Measurements in the bottom of Figure 1. The F-statistic and specifically the p-value: 5.35e-11 is very small (<0.05) indicating that the relationship between our variables and mpg is subject to more than random chance and consequentely the slope could not be zero.

* As it was established before, the intercept of our model is statistically significant implying there are factors that have not been taking into consideration in this linear model. In addition, the Multiple R-squared value of 0.7149 shows us that although our model predicts mpg of MechaCar prototypes with some efficacy, it could be improved.

#### Deliverable 2: Summary Statistics on Suspension Coils : Collect summary statistics on the pounds per square inch (PSI) of the suspension coils from the manufacturing lots

The second part of this analysis considers the estimation of statistics such as the mean, median, variance and standard deviation for the data in Suspension_Coil.csv. This dataset contains the results from multiple production lots of MechaCar prototypes. In this dataset, the weight capacities of multiple suspension coils (PSI) were tested to determine if the manufacturing process is consistent across production lots. Figure 2 and 3 show these statistics in two different scenarios: Statistics for PSI computed across all the production lots, and statistics computed for each of the production lots:

<img width="724" alt="Screen Shot 2022-04-18 at 2 06 33 PM" src="https://user-images.githubusercontent.com/95304774/163853201-9bf0520e-6371-498d-ae93-bce9ffd4a14b.png">

Considering that the design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch (psi), we can conclude that across al the manufacturing lots (figure 2) the manufacturing data meet the design specifications (variance ~ 62), but for the specific cases (figure 3), the variance for the Lot3 exceeds the 100 psi.

#### Deliverable 3: T-Test on Suspension Coils : Run t-tests to determine if the manufacturing lots are statistically different from the mean population

In our final analysis we will determine if all manufacturing lots and each lot individually are statistically different from the population mean of 1,500 psi.

<img width="724" alt="Screen Shot 2022-04-18 at 2 12 07 PM" src="https://user-images.githubusercontent.com/95304774/163854137-425e203f-d933-40f1-9240-3246c5418d60.png">

* The p-value is greather than the limit value of 0.05, which means the mean of the psi across all the manufacturing lots and the population mean are not statistically different.

#### T-test on PSI for Manufacturing Lot 1:

<img width="724" alt="Screen Shot 2022-04-18 at 2 18 22 PM" src="https://user-images.githubusercontent.com/95304774/163854798-911afd8e-58ed-4948-8fc1-5eb90039caa9.png">

* The p-value in this case is greather than the limit value of 0.05, which means the mean of the psi for manufacturing lot 1 and the population mean are not statistically different.

#### T-test on PSI for Manufacturing Lot 2:

<img width="724" alt="Screen Shot 2022-04-18 at 2 20 06 PM" src="https://user-images.githubusercontent.com/95304774/163855059-ed4f0911-847d-4507-865f-4d43fbeb6d45.png">

* Again for manufacuring Lot 2, the p-value is greather than 0.05, which means the mean of the psi for manufacturing lot 2 and the population mean are not statistically different.

#### T-test on PSI for Manufacturing Lot 3:

<img width="724" alt="Screen Shot 2022-04-18 at 2 21 30 PM" src="https://user-images.githubusercontent.com/95304774/163855259-1c9e54d0-4383-4576-b5dd-ca65e211c3d2.png">

* In this case the psi mean for Lot 3 is slightly statistically different from the mean population, since the p-value is barely smaller than 0.05. We will probably need to evaluate this manufacturing lot in more detail.

#### Deliverable 4: Design a Study Comparing the MechaCar to the Competition

## Study Design: MechaCar vs Competition

Continuing with our analysis of the MechaCar production data and to see how these prototypes perform against the competition. It could be interesting to consider an additional data analysis where factors like traffic and road conditions are taking into account, since they can affect the estimation of mpg. In our analysis we will have the highway mpg and the city mpg. We will need as well information about the car transmission: mechanic or authomatic, so we can study how the kind of transmission affects the city and highway fuel efficiency.

In our analysis, we will test the highway mpg and/or the city mpg against the car transmission to see if the manual or authomatic transmission has an impact in the amount of fuel the car consumes in each scenario individually.

Our null hypothesis is: The variance of fuel use in the city/or the highway is equal for the cars with authomatic and manual transmissions.

To test our null hypothesis we will use the two sample t-test. In fact we need to run this t-test twice, one for the city mpg and the other for the highway mpg. In each test, we will need to determine if our null hypthesis can be rejected or not, based on the p-value. For example: if our p-value is smaller than 0.05, the null hypotheis is rejected and we can conclude that there is a statistically significant relationship between whether the car has an automatic or manual transmision and the amount of fuel consumed while driving in a city/highway scenario.

In our analysis, we would need the following data:

* City mpg : It can be estimated as the average a car will get while driving on an open stretch of road without stopping or starting, typically at a higher speed.
* Highway mpg: It can be estimated as the average a car will get while driving on a road with city conditions, with stopping and starting at lower speeds.
* Car transmision: It is a categorical data,a dichotomous variable: 0 - manual transmission, 1 - authomatic transmission.














