# 07_GroupProject1
Group Project Readme
# Project Summary
In the era of digital transformation, the internet has become an integral part of our daily lives, influencing how we communicate, work, learn, and entertain ourselves. The vast expanse of the digital landscape offers a rich tapestry of data, providing an opportunity to unravel the intricate patterns of internet usage across different regions, demographics, technology, and disparities of information.
This project aims to delve into the multifaceted aspects of internet usage, leveraging data analytics to gain insights into users of the internet, technological trends, and censorship of global connectivity. 

# GitHub File Navigation
  * Broadband v Mobile
      * jupyter notebook which contains all code, figures, and a final summary. 
  * Internet Censorship
      * Graphics - folder which contains the output of figures within the code.
      * Resources - folder which contains resources needed for import into the code notebook. 
      * Internet_Censorship_Data_Code - jupyter notebook which contains all code, figures, and a final summary. 
  * Internet Demographics
      * Graphics - folder which contains the output of figures within the code.
      * internet-usage-working - jupyter notebook which contains all code, figures, and a final summary. 
  * Resources - folder which contains resources need for import into the various code notebooks.
  * Rubric - folder which contains the original project rubric and a rough project outline/timeline.
  * Files
      * .gitignore - file that dictates which files to upload to github. Ignores files with sensitive information or unnecessary files. 
      * Data Presentation PowerPoint - Presentation of the overall project. 
      * ReadMe - instructions and summary of the project. 

# Question 1 - Who is using the internet?
The R-squared value is 0.734, which indicates that about 73.4% of the variability in 'Internet Users' is explained by the model. This is a relatively high value, suggesting a good fit of the model to the data.
The adjusted R-squared value is 0.729, very close to the R-squared, indicating that the independent variables are relevant and the model isn't overfitted with unnecessary predictors.
F-statistic and Prob (F-statistic): The F-statistic is 161.3 with a very low probability (2.32e-34). This suggests that the model is statistically significant, meaning it's likely providing a better fit than a model with no independent variables.
Coefficients:
const (Intercept): The coefficient for the constant is 53.0533. This can be interpreted as the expected value of 'Internet Users' when all independent variables are 0.
GNI Per Capita: The coefficient is 0.0008, indicating a positive relationship. For every unit increase in GNI Per Capita, Internet Users increase by 0.0008 units, assuming other variables remain constant.
Population Under Poverty Line: The coefficient is -1.7181, showing a negative relationship. For every percentage point increase in the population under the poverty line, Internet Users decrease by about 1.7181 units, assuming other variables remain constant.
P-values: The p-values for both independent variables are very low (almost 0), indicating that the relationships are statistically significant.
Confidence Intervals: The 95% confidence intervals for the coefficients suggest that the true values of these coefficients are likely within these ranges.

# Question 2 - What is the breakdown of Internet Usage?



# Question 3 - Who is censoring the internet?
To answer who is censoring the internet, we found a study that looked at a few different categories, like social media or torrents, and whether they were restricted or banned in different countries. This was the base data set for our analysis. After cleaning the original data we added a few additional data sets (population and region) to look at censorship globally. Then we drilled down into internet censorship by population and region to determine who is censoring their internet the most and whether having a large population matters with the level of censorship. Overall, we found that Asia is the most censored region with North Korea and China having the heaviest censorship by banning all factors of internet assessed. Whereas, the Atlantic region is the least censored with Cape Verde and Iceland having the lowest censorship scores. When analyzing the data there seemed to be a relationship between population and censorship. In the bar chart titled Censorship Score by Population Range, you can see that as the population goes up so does the censorship score. Initially charting a scatter plot between population and censorship score it shows a weak correlation with an R-squared value of 0.1. However, since both India and China have such large populations (greater than 1 billion) it is probable that their influence is skewing the data. To determine this, a box and whisker plot was used to understand which country populations are outliers. Removing those countries from the data set and re-plotting the scatter plot the correlation drops further suggesting that the two large populations were creating what seemed to be a correlation when there actually is none.
It was surprising to see that every country had at least one category restricted or censored and no country was completely free of internet regulations. 
