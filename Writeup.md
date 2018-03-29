# Kickstarter and the Economy

## About the Data
Our project implemented two data sets. We obtained both of them from Kaggle.com. The first dataset was a collection of Kickstarter projects collected from 2009 to part of February 2018. This dataset had many columns: The project ID, category information, the currency used, the project deadline, the goal, the launch date, country of origin, and the amount pledged. Currency values for the goal and the amount pledged also came with values converted to USD and a "real" value, which was adjusted for the change in the value of currency. We used the real USD values whenever possible.

The other dataset we used was information on the S&P 500 index price. The data was broken down with rows corresponding to dates. They had the open, close, high, low, and an adjusted close price. The rows also contain information as to the volume traded.

## Data Processing
Both datasets were provided in CSV format, and thus D3 interpreted all the values as strings. For processing, I (Ryan Slama) iterated through each row in each of the datasets and reinterpreted each value as the correct type through casting strings to numbers and creating date objects based on the text format of the date.

The next step in my processing was to compute monthly averages for all of the relevant statistics. For both datasets, I store those averages in a nested Javascript object with keys by year and then by month.

## The Argument
Our plot compares the slope between the adjusted close value of the S&P 500 and the real USD pledged for the average Kickstarter project this month. The intention is to show that the current state of the economy impacts amount of money that people are willing to spend at potentially risky projects that are many times trivial and may never materialize.

What we found was that as the S&P 500 grows, the number of projects grows along with it, however, there was no connection between the S&P 500 and the monthly success of projects. One factor that may be contributing to this is what we found in our third graph: as the economy (as indicated by the S&P 500) grows, projects tend to request larger amounts of money. 
