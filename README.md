# Airbnb

Analysis of Airbnb London data. Please see the medium article for a quick write up of the results:
https://esbenurbak.medium.com/how-to-maximize-your-airbnb-rental-income-in-london-2aa0999b4231

I have done the analysis using colab. So the easiest (I find) is simply to open it in colab using the "link" at the top of the file.


In this colab workbook I take a look at the London Airbnb data sets - The calender and Listings data sets.

The main 3 questions I have tried to answers are:

1. When during the year is it most likely to get your Airbnb property rented out and which months/days can you charge more:
2. How much can you charge for your property?
3. What features of your house should you highlight in order to maximize the rental price you can charge?

The colab workbook has been split into section:
Section 1:
Loading of libraries and the data sets
The datasets are loaded directly from the web and into pandas

Section 2:
Here I take a look at the calendar data sets.
Before doing analysis I clean the data:
  - Prices are converted to numeral (before they were dollar amount)
Firstly, I look at the %avaliability over the next year.
 - I find which dates the calendar indicates busy vs free and take the mean by date
 - This is then plottet
Secondly, I look at the mean price over each month and by week day
 - I find the price the calendar by weekday and month
 - This is then plottet vs month/weekday


Section 3:
Firstly, I take a look at the listings data and then use my best judgement to select which input variables might be of interest for this analysis. Then I clean the data
and convert it into numerical values. The categorical values (such as borough, property type, bathroom type etc) are converted into 0 vs 1 using the one-hot method.
I also take a look at outliers: I look at various graphs and correlation to see if any of the inputs look non-important. But the main conclusion is to simply cut the very high price tail off and convert the price into log values (the distrubtion resemples a log distribution) inorder to make the later modelling easier. I also tried various outlier removal methodologies (see the appendix) but non seemed to improve the later modelling so these were appanden.

Section 4:
Here I regress the listings parameters vs log(price). I use the Sklearn library and try various models. I split the data set into a train and test in-order to have a dataset to check the model accuracy on. I tried multiple models (see appendix) but settled on a random forest regressor which worked reasonably well. I get fairly reasonble results when looking at the r sqaured and plots - at least good enough to give a good give where abouts a airbnb property price should be.  
I also look a the importance of each input parameters inorder to establish which input parameters has biggest inpact on the fit of the model and thereby what a person renting out their property should focus on to increase the possible rent











