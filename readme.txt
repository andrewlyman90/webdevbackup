Andrew Lyman
9.23.2021
COMP5800. UMASS, Lowell
Assignment 1 Network Metrics

PANDAS is only external library required for this program.  Please download if needed using "pip3 install pandas"

To run compute-metrics.py on Windows/Linux enter "python compute-metrics.py net-sample.txt" to command line

For Mac, most likely python2 is installed as default, so use "python3 compute-metrics.py net-sample.txt" to explicitly call python3 to execute program.

Make sure the "net-sample.txt" file is in same directory as program.  Make sure terminal is in same directory as program.  

A new "output.txt" file will be generated in working directory with each execution of the program.  




Equation Used for Node Degree Centrality = (Number of Edges of Node)/N-1

Equation Used for Node Closeness Centrality = N-1/(Sum of all Distances to other Nodes)

*Entire Graph was treated as UNDIRECTED
**All Nodes NOT connected were given a distance of 1000 (per assignment instructions).  This also impacts the calculated Node Closeness Centrality values.




I've been playing around backtesting opening up Iron Condors against the S&P500, creating a strategy that relies on a very high win rate to make up for the low return.  The strategy shown in the pic is using Bollinger Bands with 60 day window and 5 standard deviations, but plenty of other slight variations like 90 day 3 standard deviations get similar results.  
For the backtesting, I open up the Iron Condor on the 1st trading day of the month, and close it on the last.  From looking at current option prices based on the model's current recommended strikes, I estimate I can get at least %4 return, and no greater than %10 return, but I'd like to get historical Option prices to verify.  
This Monday, from the proposed strike prices I was able to open a condor expiring 11/10 for 6% (strikes at 415/416 & 470/471) and another condor on 11/19 for 9% (so $6-$9 for each 100$ of collateral.  Benefit of a condor, as I'm sure many of you know, you effectively double your collateral since only one side can expire in the money).   
I'd say the results below are the best I've achieved, which probably means I've overfitted, but nevertheless experimenting with other Bollinger Band parameters and also using 200 Day MA I've gotten Win rates of +95%, which, assuming I receive 6% return on each Condor, should keep the strategy at least profitable.  
I'd say there is definitely additional risk opening up these spreads when below the 200 Day MA, so in real life I may increase my spread or just sit it out.  But typically, above the 200 Day MA, the market behaves in the nice expected trend line until the next Black Swan Crash event. 
Please provide any feedback, especially any concerns I may have missed about this proposed strategy! As mentioned, I've already put money to test this method, so far it appears to be behaving as expected but it is a bit nervewracking since just 1 loss will wipe out about 12 months of gains.  Psy

Rules & Assumptions for this model:
~$6 Credit per Iron Condor with Collateral of $100, Max loss of $94
-Open Condor at start of Month, expiration at end of Month
-Condor Strike Prices defined by Bollinger Bands w/ 60 day window and 5 standard deviations
-Let Condor Run to Expiration for each Month
-No Rolling, Condor either expires ITM for Max Loss of $94 or OTM for Max Gain of $6
_________________________________________________________________________________
RESULTS:
_________________________________________________________________________________
Backtesting for 5 years: Wins: 49 Losses: 1 -> Win Percentage: 98.0 % 
6$ per Condor Not Compounding: Hypothetical Profits w/50k $233,000.0
6$ per Condor Compounding 25% of Profits: Hypothetical Profits:  $827,612.08
__________________________________________________________________________________________________
Backtesting for 10 years:  Wins: 109 Losses: 2  ->  Win Percentage: 98.2 %
6$ per Condor Not Compounding: Hypothetical Profits w/50k $233,000.0
6$ per Condor Compounding 25% of Profits: Hypothetical Profits:  $827,612.08
__________________________________________________________________________________________________
Backtesting for 28 years (max from Yahoo Finance):  Wins: 334 Losses: 5 Win Percentage: 98.5%
6$ per Condor Not Compounding: Hypothetical Profits w/50k $767,000.0
6$ per Condor Compounding 25% of Profits: Hypothetical Profits:  $17,545,594.45
   
