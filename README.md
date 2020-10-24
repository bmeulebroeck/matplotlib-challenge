# matplotlib-challenge

<h1> Pymaceuticals</h1>
File submitted for evaluation: pymaceuticals_final.ipynb
I used the other files as my 'working' files and they contain extra comments and notes I made as I worked through each step.

<h2>Merging the data and identifying the problem mouse</h2>
<p>Reading the csv's and merging into one df went well. To find the problem mouse I did a count by Mouse ID on Timepoint and returned a dataframe sorted in descending order. I saw that mouse g989 was the only mouse to have 13 timepoints, so I used .loc to create a dataframe that isolated only that mouse. There I confirmed that there were multiple tumor volumes for the same timepoint/drug regimen at several time points. I then used .loc again to create a dataframe with all mice except for g989, and I used that (clean_mousedata_df) to continue with the analysis.</p>

<h2>Summary Stats</h2>
<p>This section came together well for me. I used what we did on day 3 (Summary Stats) to set up variables and calculate the requested measures.</p>

<p>The aggregation method did cause me a few issues. I didn't remember covering it in class so I did a search and found info in the pandas documentation library, as well as a good explainer with examples on geeksforgeeks. With some trial and error I was able to get an output table that numberically matched what I had calculated previously.</p>

<p>After getting to the box and whisker plots - I came back to the summary stats section to calculate the min and max tumor volumes so that I could check my work.</p>

<h2>Bar and Pie Charts</h2>
<p>The first plot using pandas went smoothly for me. I needed to adjust the width on the bars so that it would look like the pyplot figure; by default it gave me really skinny looking bars with a lot of white space.</p>

<p>The pyplot figure gave me a few issues. I used the same variable to generate the y (drugcts), but I could not initally get the drug names on the x-axis to line up with the drug count. In the matplotlib documentation I found an example where a variable was plotted using (var.index, var) as the x and y. I used that method on mine and it fell in line.</p>

<p>The pie charts came together quickly. I referred back to the examples from class and was able to generate the pies using both methods.</p>

<h2>Quartiles, Outliers, and Boxplots</h2>
<p>I stumbled a bit on the setup for this one. I was able to get the final timepoints eventually, but I initially had only pulled the timepoints = 45. That caused me to lose some of the relevant data and it skewed my measurements and my boxplots. When I realized the error, I went back and corrected it so that I got the max timepoint per mouse, then merged that back with the clean_mousedata_df in order to get what I needed to proceed.</p>

<p>To get the IQR and figure out the outliers for each drug, I set up a separate df for each of the drugs requested and then ran all the calculations. To check my work on each drug I plotted them individually first.</p>

<p>To plot them all in one figure, I used .tolist() to pull out the tumor volumes for each drug into a separate list for each drug. I was then able to plot them into one figure by pulling in those lists and setting labels for them. I used the linked matplotlib documention to figure out the formatting on the outlier value for Infubinol (I used green diamonds).</p>

<h2>Line and Scatter Plots</h2>
<p>I referred back to the study results csv file in order to find a mouse treated with Capomulin. I chose g401, and set up a df to isolate the information. From there I generated the requested plot and set up the formatting.</p>

<p>For the scatter plot I set up variables for avg tumor volume and mouse weight. I added titles and a few formatting options to tidy it up.<p>

<p>I followed the examples from class to calculate the correlation coefficent and linear regression, then ran another scatter plot with the linear regression included.</p>