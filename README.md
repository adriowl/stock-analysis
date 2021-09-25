# ReadMe.md stock-analysis
## Module 2 Challenge Analysis

### Overview of Project
The purpose of this analysis was to analyze stock data from the years 2017 and 2018 in order to provide financial suggestions. We calculated certain useful indicators, like Yearly Return and Total Daily Volume, which provided insights as to which stocks would be a safe bet. Secondly, we refactored the original financial analysis code to make it run faster.

### Results
Comparing 2017 and 2018 data, the year 2017 performed much, much better for our stock selection, as 11 out of 12 stocks had positive returns. Comparatively, only 2 out of 12 stocks in 2018 had returns in the green. It seems that outward factors affected the market in 2018 and made it very shaky. This shows that data, especially financial, can be volatile and change quite a bit in a short amount of time. 
The execution times between the original script and the refactored script are as follows:

#### Original
- 2017
<img width="262" alt="Original_2017" src="https://user-images.githubusercontent.com/90166034/134776281-ed8c6d54-1fc4-406b-8525-28326d810d08.png">

- 2018
<img width="262" alt="Original_2018" src="https://user-images.githubusercontent.com/90166034/134776285-5546922f-689b-4821-9c32-caabdbfa1658.png">

#### Refactored:
- 2017
<img width="263" alt="VBA_Challenge_2017" src="https://user-images.githubusercontent.com/90166034/134776290-cacce0aa-92eb-428f-a02a-72d87682cabe.png">

- 2018
<img width="264" alt="VBA_Challenge_2018" src="https://user-images.githubusercontent.com/90166034/134776296-132e3b0f-07cb-4dc3-b9bb-16ba326dc9ae.png">

##### Explanation of Code Changes
This increase in performance time can be largely attributed to the fact that in the new code, we are looping through the data far less times than in our original. In the original green_stocks code, we are looping through rows 11 times! 11 multiplied by the rowcount is quite a big number, especially when you consider the size of the average dataset, which could be millions of rows. See original nested loops below:

<img width="255" alt="greenstocks_originalcode" src="https://user-images.githubusercontent.com/90166034/134776621-4035c7b4-cf13-4a21-8dbc-961d5893d8cf.png">

In our improved code, we get rid of the nested loops. We loop 11 times once, to initialize the tickerVolumes array values to 0, then loop over the rowCount once, checking for the tickers that we want as we go, which is much better for performance. Compared to looping over rowCount 11 times, this is a huge improvement! See improved loops below:

<img width="501" alt="vbachallenge_improvedcode" src="https://user-images.githubusercontent.com/90166034/134776626-ceeef344-0cf9-4961-91a4-1e1201d29911.png">

As a developer we want to always be vigilant of how our code runs. Primarily we do want it to work, yes, but if that code works but takes a whole day to run, then it's not very useful, is it? Especially in this example, since we're sending our script to a non-coder.


### Summary
There are virtually no big disadvantages to refactoring code. We always want our code to run as efficiently as possible. The second go through can help you find bugs, allow you to add more comments, and in general just make it better and easier to read. If anyone comes in after us, we don't want to leave this a mess - we want to help them out! These benefits apply directly to our code. Our runtime-improved VBA script runs much quicker, and that's something I'm commonly asked to do in my tech job. Redo this, make it better. There is of course one tiny disadvantage, which is the chance of introducing new bugs into your code. That's why it's so important to test your changes. Along with testing, along with benchmarks for comparison like the run times of the new and old scripts, you can eliminate this disadvantage, leaving only positive outcomes to refactoring your code. I believe there are no disadvantages to refactoring our VBA script, as it now runs better and has no added bugs, which I know because I tested it and it runs successfully. This gleans a valuable lesson into coding for this bootcamp, my career, and beyond; always take a second look at your code. Once it works upon initial development, it's only up from here!
