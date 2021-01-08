# Airbnb

Analysis of Airbnb London data. Please see the medium article for a quick write up of results
I have done the analysis using colab. So the easiest (I find) is simply to open it in colab using the "link" at the top of the file.


In this colab workbook I take a look at the London Airbnb data sets - mainly the calender and Listings data sets.

The main 3 questions I have tried to answers are:

1. When during the year is it most likely to get your Airbnb property rented out and which months/days can you charge more:
2. How much can you charge for your property?
3. What features of your house should you highlight in order to maximize the rental price you can charge?

The colab work book has been split into section:
Section 1:
Loading of the used libraries and the data sets

Section 2:
Here I take a look at the calendar data sets.
Firstly, I look at the %avaliability over the next year.
Secondly, I look at the mean price over each month and by week day

Section 3:
Firstly, I use my best judgement to select which input variables might be of interest for this analysis. Then I clean the data and convert it into numerical values
The categorical values (such as borough) is converted into 0 vs 1 
I also take a look at outliers: I look at various graphs and correlation to see if any of the inputs look non important. But the main conclusion is to simply cut to very high price tail off and convert the price into log values (the distrubtion resemples a log distribution) inorder to make the later modelling easier. I also tried various outlier removal methodologies (see the appendix) but non seemed to improve the later modelling so these are appanden.

Section 4:
Here I regress the listings parameters vs log(price). I tried multiple models (see appendix) but settled on a random forest regressor which worked reasonably well. I split the data set into a train and test set. I get fairly reasonble results.
I also look a the importance of each input parameters inorder to establish which input parameters has biggest input on the fit of the model.









