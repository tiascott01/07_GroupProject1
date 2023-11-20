# Group Project 1 - Impact of Internet Usage
Group Project Readme
# Project Summary
In the era of digital transformation, the internet has become an integral part of our daily lives, influencing how we communicate, work, learn, and entertain ourselves. The vast expanse of the digital landscape offers a rich tapestry of data, providing an opportunity to unravel the intricate patterns of internet usage across different regions, demographics, technology, and disparities of information.
This project aims to delve into the multifaceted aspects of internet usage, leveraging data analytics to gain insights into users of the internet, technological trends, and censorship of global connectivity. 

# GitHub File Navigation
  * Broadband v Mobile
      * Graphics - folder which contains the output of figures within the code.
      * Broadband_Mobile_Data - jupyter notebook which contains all code, figures, and a final summary. 
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
To set the stage for our project, we started by figuring out who is using the Internet, and what the demographics of those users are. We started out with a large data sheet, with data on internet usage across 180 countries around the world, that spanned from 2017 to 2021. We reduced it down to just data from 2020 and 2021, so that we had more recent data. For the data points, we were able to clean it into about 17 different factors that we looked at. We then took the average of the 2 years for each factor and built most of our charts and statistical analysis of that.
We found that, unsurprisingly, there is an almost even split between male and female usage, with 47.4% of females using the internet, and 52.6% of males. This is more or less commensurate with the gender split of the world, which is [last reported](https://ourworldindata.org/gender-ratio#gender-ratio-across-the-world) at 150 males per 100 girls. By displaying internet usage by education level between male and female users, one thing that was moderately surprising, is that less educated women tend to use the internet more than less educated men (see chart below).
 

Further analysis revealed that most of the internet users across the world are,

Highly literate: 


<img src="https://github.com/tiascott01/07_GroupProject1/assets/139186713/7e83b6f5-5e5a-4f66-91b5-36367c7e560a" width="300" height="150">

Well-educated:  



<img src="https://github.com/tiascott01/07_GroupProject1/assets/139186713/bb4cc17f-1682-422c-9708-c20013405fce" width="300" height="150">

In Various Levels of Socioeconomic Status:



<img src="https://github.com/tiascott01/07_GroupProject1/assets/139186713/561e9721-0804-424a-a768-7f55ea7c2648" width="300" height="150">
<img src="https://github.com/tiascott01/07_GroupProject1/assets/139186713/73429773-cae1-4fc9-b007-b6d53a81e694" width="300" height="150">

# Question 2 - What is the breakdown of Internet Usage by Access Type?
### Are the acceleration rates of mobile and broadband adoption correlated?
> /Broadband v Mobile/Rates of Change Analysis.ipynb

Summary: While initially it looks like broadband is decelerating in adoption globally while mobile is accelerating, these changes over time are not actually correlated. However, investigating by region (continent), we find significant differences for certain parts of the world. 

Cleaning the data and calculating the rate of change of mobile and broadband adoption, we averaged the values and plotted the values for each year. It looks like the average change in mobile and broadband adoption were linked until 2020, where they show opposite accelerations. 

<img src="https://github.com/tiascott01/07_GroupProject1/blob/main/Broadband%20v%20Mobile/Graphics/Global%20Internet%20Access%20by%20Type.png" width="300" height="150">

It looks like these might be correlated, so we used a scatterplot to plot the rate of change for broadband on the x-axis vs. the rate of change for mobile on the y-axis. With an R^2 value of 0.033, it is found these do note actually correlate, which was surprising. 

<img src="https://github.com/tiascott01/07_GroupProject1/blob/main/Broadband%20v%20Mobile/Graphics/Rate%20of%20change%20Broadband%20vs%20Rate%20of%20Change%20Mobile.png" width="300" height="150">

From here, we investigated by region (continent) using visual choropleth maps in form some hypothesis before doing analysis. South America jumped out visually as potentially significant differences from the rest of the globe.  We built a function to calculate a t-test and output an analysis based on the resulting t-statistic and p-value, using user input of a continent. When testing South America vs the rest of the globe, we found that for mobile: Since the p-value is very small (<= 0.05), we can reject the null hypothesis and conclude that the mobile adoption rates for South America are significantly different than for the rest of the world. Since the t-statistic is negative, it indicates that the mean rate of change for mobile adoption in South America is lower than the mean for the rest of the world. This can also be answered for other regions using the code. 

### Who is prevailing in broadband and mobile usage?
> /Broadband v Mobile/Data Cleaning Aggregate Visuals - Final.ipynb

To start we imported and cleaned the data, calculating and identify the countries with the highest broadband usage. We then repeated the same steps to compare the countries with the highest mobile usage. We then compared the countries with an API to grab their latitude and longitude, thus creating a heatmap based on percentage of penetration in both categories. As you can see China is the top country in both broadband and mobile penetration. This was a surprising find given that China has extremely heavy censorship but may be due to the general population of users. Other countries such as the U.S., Russia, India, Brazil, and Japan, made both lists. The U.S. placement is not surprising as in the top three in both categories given that it is known for its large networks and robust services. Russia and Brazil, respectively, equally weighted in both categories. India is a surprising insight given that it has the second highest mobile penetration and last in broadband, given the amount of eCommerce and telecommerce. 
Between broadband and mobile, we can see that mobile penetration is higher, over doubled in all categories, visually. Thus leading us to an additional questions of why mobile penetration is double over broadband.  

### What are the cost disparities between Broadband and Mobile?
> /Broadband v Mobile/Data Cleaning Aggregate Visuals - Final.ipynb

From our original imported dataset we cleaned the data, calculating three columns into our aggregate data, (Broadband Cost (% GNI), Mobile Cost (Prepaid (% GNI)), Mobile Cost (Postpaid (% GNI)). We then averaged the cost of our two mobile data sources to create an average mobile cost for each country. Applying our top 10 list of mobile users, we compared the broadband cost to the mobile cost. Visually we can see that mobile cost among the top mobile users is significantly less than broadband costs. On average half the cost. This makes sense as high adoption of mobile use is most likely due to the staggering cost of broadband operation. In places like Indonesia and Nigeria it is likely impossible to operate broadband due to how many factors above the average mobile cost broadband is. 


# Question 3 - Who is censoring the internet?
To answer who is censoring the internet, we found a study that looked at a few different categories, like social media or torrents, and whether they were restricted or banned in different countries. This was the base data set for our analysis. After cleaning the original data we added a few additional data sets (population and region) to look at censorship globally. Then we drilled down into internet censorship by population and region to determine who is censoring their internet the most and whether having a large population matters with the level of censorship. Overall, we found that Asia is the most censored region with North Korea and China having the heaviest censorship by banning all factors of internet assessed. Whereas, the Atlantic region is the least censored with Cape Verde and Iceland having the lowest censorship scores. When analyzing the data there seemed to be a relationship between population and censorship. In the bar chart titled Censorship Score by Population Range, you can see that as the population goes up so does the censorship score. Initially charting a scatter plot between population and censorship score it shows a weak correlation with an R-squared value of 0.1. However, since both India and China have such large populations (greater than 1 billion) it is probable that their influence is skewing the data. To determine this, a box and whisker plot was used to understand which country populations are outliers. Removing those countries from the data set and re-plotting the scatter plot the correlation drops further suggesting that the two large populations were creating what seemed to be a correlation when there actually is none.
It was surprising to see that every country had at least one category restricted or censored and no country was completely free of internet regulations. 

# References and Resources
1) Initial dataset for questions 1 and 2 - Internet Inclusivty Index: https://www.kaggle.com/datasets/kwamsahortor/internet-inclusivity-index-2017-2021/?select=Internet_Inclusivity_Index_+Data_table.csv
2) Dataset for question 3: https://www.comparitech.com/blog/vpn-privacy/internet-censorship-map/
3) Country Population Data - https://population.un.org/wpp/
4) py-country documentation - https://pypi.org/project/pycountry-convert/
5) pycountry-convert function discussion - https://stackoverflow.com/questions/55910004/get-continent-name-from-country-using-pycountry
6) choropleth charts in python documentation and examples - https://plotly.com/python/choropleth-maps/
7) animating choropleth charts examples - https://mahshadn.medium.com/animated-choropleth-map-with-discrete-colors-using-python-and-plotly-styling-5e208e5b6bf8
8) Gender Ratio - https://ourworldindata.org/gender-ratio#gender-ratio-across-the-world
9) Chat GPT for general coding assistance
