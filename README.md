# How Economic Factors Affect Life Expectancy
![](https://github.com/samuelejedegba/How-Economic-Factors-Affect-Life-Expectancy/blob/main/Cover%20Image.webp)

## Introduction
Life expectancy is the age a person is expected to live until. World Health Organization has always recorded the average Life Expectancy of different countries of the world. Analysis have always been done to determine the main determinants of life expectancy and what countries can do to improve it. However, my focus on this analysis is on Economic factors (as an Economics graduate) like GDP per capita, population, schooling, etc and how these factors affect life expectancy and how countries can improve these factors to increase life expectancy.

## Problem Statement
1.	What are the economic factors that affect life expectancy?
2.	How do they affect developing and developed countries differently?
## Skills/Concepts Demonstrated
1.	R
2.	Power BI

## Data Set
The Dataset was acquired from [Kaggle](https://www.kaggle.com/datasets/kumarajarshi/life-expectancy-who). The Dataset is a panel data, made up of 22 observations. The observations are from 193 countries from the year 2000 to 2015. There are observations like Life expectancy, Status of the Country, Adult Mortality, Alcohol Consumption, number of infant deaths, etc. The Economic factors that will be focused on are:
1.	GDP Per Capita – This is the total GDP divided by the population of the country. 
2.	Total Expenditure – Government expenditure on health as a percentage of total government expenditure
3.	Schooling – Average number of years spent in school
4.	Income Composition of Resources – This is Human development index (measured from 0 to 1) in terms of income composition of resources.
5.	Population – The number of people living in the country.

## Cleaning and Analysis
R was my first point of call as I was dealing with a Panel data. I took the following steps to manipulate and analyse the data.
1.	I wanted to find out how all these observations were correlated. To do this, I had to create a correlation matrix. I first removed the columns that are not numeric. Then I used ‘corrplot’ to find the correlation between the observations and ‘ggcorrplot’ to create a heatmap from my correlation matrix.

![](https://github.com/samuelejedegba/How-Economic-Factors-Affect-Life-Expectancy/blob/main/Correlation%20in%20R.PNG)

2.	After finding out the observations that are strongly correlated with Life Expectancy, I ran a regression to determine which of them is the biggest predictor of life expectancy. First, I turned my data into panel data and ran two types of regression. I first ran the pooled method regression and then the fixed method regression.

![](https://github.com/samuelejedegba/How-Economic-Factors-Affect-Life-Expectancy/blob/main/Regression%20in%20R.PNG)

3.	I then carried some tests  from my regression analysis. First I tested for individual and Time effect. Then I tested for which of the methods are consistent.
4.	Finally, I moved the data to Power BI to create scatter plots of Economic factors against Life expectancy to have a better sense of their relationship. Below is the dashboard of scatterplots created on PowerBI

![](https://github.com/samuelejedegba/How-Economic-Factors-Affect-Life-Expectancy/blob/main/Dashboard.PNG)

## Results

1.	The result from the correlation Matrix reveals some interesting observations. Schooling has a very strong correlation of 0.74 with life expectancy. This is also shown in the charts below as the higher the number of years of education, the higher the life expectancy. This is however more prevalent in developing countries.

![](https://github.com/samuelejedegba/How-Economic-Factors-Affect-Life-Expectancy/blob/main/Correlation%20Matrix.PNG)

![](https://github.com/samuelejedegba/How-Economic-Factors-Affect-Life-Expectancy/blob/main/Schooling%20and%20Life%20Expectancy.PNG)

2.	Another interesting result in the Matrix shows how little the correlation between Population and Life expectancy is. The correlation is -0.02. This is also shown in the scatter plot between them below.

![](https://github.com/samuelejedegba/How-Economic-Factors-Affect-Life-Expectancy/blob/main/Population%20and%20Life%20Expectancy.PNG)

3.	Total Expenditure which is percentage of government spending on health relative to total government spending also has a surprisingly low correlation with life expectancy. Although positive, the correlation is 0.17. The bulk of this correlation happens with developing countries while the correlation between developed countries is non-existent as seen in the scatter plot below. This might be as a result of the measure being used. Percentage spend on healthcare might not be a great determinant as total government spend differs country to country. A better measure would have been total government spend on healthcare. However, the slight positive correlation is observed more in developing countries as observed in the plot below. This correlation is non-existent in developed countries.

![](https://github.com/samuelejedegba/How-Economic-Factors-Affect-Life-Expectancy/blob/main/Total%20expenditure%20and%20Life%20expectancy.PNG)

4.	GDP per capita has a correlation of 0.44. While still very strong, the scatter plot tells an interesting story. For developing countries, a slight increase in GDP per capita leads to a sharp increase in life expectancy. As life expectancy increases and a country begins to transform from developing to developed, the GDP effect becomes less stronger. 

![](https://github.com/samuelejedegba/How-Economic-Factors-Affect-Life-Expectancy/blob/main/GDP%20Per%20Capita%20and%20Life%20expectancy.PNG)

5.	Income composition of resources has the strongest correlation after schooling. This is an index that consists of Life Expectancy, Education and Per Capita income and so there are no surprises it has a very strong correlation with Life Expectancy as also shown in the plot below. 

![](https://github.com/samuelejedegba/How-Economic-Factors-Affect-Life-Expectancy/blob/main/Income%20composition%20and%20Life%20Expectancy.PNG)

6.	Alcohol Consumption – Even though this might be ranked under Health factor and not Economic (The focus of this study) it shows a very interesting correlation with Life expectancy. Alcohol consumption has a positive 0.4 Correlation which means the more alcohol a country consumes, the higher the life expectancy (read that slowly again!) One would think the opposite would be the case as Alcohol consumption can lead to various life shortening ailments and even things like drunk driving which leads to death. Surprising? Not really. There is an explanation for this. If you go back to the correlation Matrix, you will realise there is a relatively strong correlation between GDP per Capita and Alcohol consumption. This simply means that the richer a country, the more alcohol they consume. GDP has a positive correlation with Life Expectancy so it is only normal that this will lead to increased alcohol consumption. This is also the same with Body Mass Index (BMI) as the richer the country, the higher the BMI.

## Regression Result
To determine the biggest predictor of life expectancy, Multiple Linear Regression was run. From the result below, Schooling has the highest positive effect on Life Expectancy. 

![](https://github.com/samuelejedegba/How-Economic-Factors-Affect-Life-Expectancy/blob/main/Regression%20Result.PNG)

## Conclusion and Recommendations.
It seemed obvious to me the effect education (schooling) whould have on life expectancy at the start of this project. What was not very obvious was how much the impact was. While there are many economic factors that affect life expectancy, this study has shown that the most important is Education (schooling). Not only does it have a high correlation, it is also one of the biggest predictors as shown in the regression analysis. Also, Education affects other economic factors positively. Better education leads to better career choices which lead to better income. Better income means a country will spend more on healthcare which improves their lives. This is especially true for developing countries. Developing countries have very limited resources and struggle on how to effectively allocte these resources to the various wants. This study shows that Education should be priority (top of their scale of preference) and their citizens are better educated, all other economic factors which lead to higher life expectancy would be affected.
