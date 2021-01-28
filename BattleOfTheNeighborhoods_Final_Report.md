<center>

<h1>FARMING IN CANADA</h1>   
    
</center>
<center>

<h3>By Joseph S. Lubinda</h3>

</center>
<hr>
<center>28/01/2021</center>
<hr>

<h3>INTRODUCTION</h3>

<p>Farming is one activity we sorely need for our survival as our global population grows. More people need more food. It is that simple.</p>

<p>In the study, we focus on Canada, a country with only about 7% of land that can be farmed, and a population that has growth from 29,446,857 in the first quarter of 1996, to 36,258,726 in the last quarter of 2016.</p> 

<p>We aim to aid an individual, new to the country and hence does not know Canada, but has interest in farming there. To do this, we answer the following questions:</p>
<ul>
<li>Has there been an increase in farming activities between 1996 and 2016? </li>
<li>For one who may be interested in becoming a farmer in Canada, which areas should they expect to use for farming and why? </li>
<li>Which product should he/she focus on based on economies of scale, supply and demand. </li>
</ul>

<p>We aim at bringing this data in such a way that one can easily make a decision with the backing of data.</p>

<br>
<br>
<h3>DATA PREPARATION</h3>

<p>Our major sources of data shall be the websites http://www.omafra.gov.on.ca/ and https://www150.statcan.gc.ca/ .</p>

<p>We will get data about farms from the url http://www.omafra.gov.on.ca/english/stats/census/number.htm . We shall get data about farm products by land mass from the url http://www.omafra.gov.on.ca/english/stats/census/summary.htm . We shall then compare the volumes to the selling prices of some processed products obtained directly from the crops/livestock from the url https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=1810000201&cubeTimeFrame.startMonth=08&cubeTimeFrame.startYear=1996&cubeTimeFrame.endMonth=12&cubeTimeFrame.endYear=2020&referencePeriods=19960801%2C20201201 . For some analysis, we shall use machine learning algorithms like regression to predict various outcomes, such as the prices of particular crop/livestock products and the number of farmers who will be envolved in producing particular crops or livestock.</p>

<p>We shall use the Four Square APIs, Sklearn Kmeans and Folium to study the distribution/clustering of farms in Canada and compare the findings with the above stated analysis to draw conclusions on the crops and livestock market potential.</p>

<p>To extract the data from our sources, we shall scrape the web pages of interest and load the results into Pandas DataFrames. We shall use Matplotlib for data visualization and Folium for displaying the clusters on a map. We shall get venues data from Four Square using their APIs.</p>

<br>
<br>
<h3>METHODOLOGY</h3>
<ul>
<li>1) In order to understand people's propensity towards farming in Canada, we got the Number of Census Farms, Canada and the Provinces, 1996, 2001, 2006, 2011 and 2016 from the Web Page http://www.omafra.gov.on.ca/english/stats/census/number.htm and loaded the data into a Pandas Dataframe. If the number of farms in on the increase, it is very likely that available land is on the decrease, whereas, if the number of farms is reducing, it is very likely that finding available land for farming would be easier. This is a big issue because only 7% of the land in Canada can be used for farming. To further investigate this angle, we examine the area of land used for farming between 1996 and 2016. The data is available on the same webpage (http://www.omafra.gov.on.ca/english/stats/census/number.htm) and load the data into a Pandas Dataframe. We shall then use Matplotlib to visualize the data. If the amount of land used is indeed on a decline, then the probability of finding land available for farming grows, where as, if the amount of land used for farming is on the incline, then it may be harder to find available land for farming.</li>
<li>2) Another aspect we have to consider is the size of the population. If the population is reducing, there will be less need for food, whereas if it is growing, the demand for food grows in direct proportion. We therefore got the Regional Population Estimates for Canada and its Provinces, between 1996, 2001, 2006, 2011 and 2016 from the Web Page https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=1710000901&cubeTimeFrame.startMonth=01&cubeTimeFrame.startYear=1996&cubeTimeFrame.endMonth=10&cubeTimeFrame.endYear=2016&referencePeriods=19960101%2C20161001 and loaded the data into a Pandas Dataframe.</li>
<li>3) For the sake of understanding which areas in Canada resulted in a higher success rate for farmers, we loading data from the web page https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=3210005201 into pandas dataframe, one for each province. We then get the Net Income attribute of each dataframe and combine them into one dataframe representing the net income of farmers in Canada by province. When plotted onto a bar chart, it will be easy to compare and narrow down on which location has the most successful farmers. This is important because one of the factors of successful farming, especially when it comes to crops, is the quality of soil/land. Another aspect is, if sucessful farmers are close by, asking them for help, or simply observing how they do it, it easier.</li>
<li>4) We used Sklearn's KMeans clustering to analyse the clusters and using Folium, we displayed them clusters on a map. </li>
<li>5) It is always easier to start selling goods to customers within one's vicinity and so, we will use Four Square to get an idea of who can be considered as potential clients. Eating places have a regular and high need for agricultural produce, and are therefore a favourite in this case. We shall study the Neighbourhoods to see if the number of eating places would be enough to justify focusing on them as a viable business.</li>
</ul>
<br>
<br>
<h3>RESULTS</h3>
<p>
<img src="https://github.com/jlubinda/Coursera_Capstone/blob/master/images/population.jpg?raw=true"><br>
From the bar chart, we can see that the four most populous provinces are Ontario, followed by Quebec, British Columbia and Alberta, in order of the highest to the lowest population. It can also be noted that from the year 1996, through to 2016, population growth in these four provinces has been steadily on the incline, while the others hardly changed at all. 
</p>
<p>
<img src="https://github.com/jlubinda/Coursera_Capstone/blob/master/images/farm_land_size.jpg?raw=true"><br>
Looking at this bar chart, we can see that the amount of land used for farming is highest in Saskatchewan, followed by Alberta, Manitoba, Ontario, Quebec and British Columbia in decending order of magnitude. It is clear that Saskatchewan and Alberta have significantly more land dedicated to farming than all the other areas combined. It is also clear that the amount of land being used for farming in Canada is on the decline. 
</p>
<p>
<img src="https://github.com/jlubinda/Coursera_Capstone/blob/master/images/farms_count.jpg?raw=true"><br>
From the bar chart above, we caan deduce that Ontario has the highest number of farms followed by Alberta, Saskatchewan, Quebec and British Columbia. Considering that the landmass available for farming is low in Ontario, it is likely that farmers would lie to be closer to finanial centers and populous cities, probbly because they are the largest local market or because of the venues found in the areas
</p>
<p>
<img src="https://github.com/jlubinda/Coursera_Capstone/blob/master/images/farms_income.jpg?raw=true"><br>
In the bar chart above, we explore the net earnings of the farms in the provinces. We can see that with the exception of 2006, farmers have been increasing their net earnings rather quickly. The province that eared the most is Saskatchewan, followed by Albert and Ontario. It is worth noting that in the year 2006, Alberta and British Columbia recorded losses, with Alberta loosing the most. In the year 2011, British Columbia recorded losses, yet again. The streak continued in 2016. Generally, all provinces recorded lower incomes in 2006. Alberta rebounded very strongly, becoming the second highest earner after Saskatchewan which consistently recorded profits from 1996 to 2016. Another province of interest is Ontario, which though having among the least land masses devoted to agriculture, was consistently increasing its earning, sometimes coming out second, and other times third.
</p>
<p>
<img src="https://github.com/jlubinda/Coursera_Capstone/blob/master/images/eating_places_count.jpg?raw=true"><br>
Looking at the contents of the DataFrame as displayed above, the largest number of venues in Saskatchewan are eating places, making up 38% of the venues retrieved. This is a very interesting fact.
</p>
<p>
<img src="https://github.com/jlubinda/Coursera_Capstone/blob/master/images/cluster_map.jpg?raw=true"><br>
As can be seen from the map above, the clusters are fairly evenly distributed in Saskatchewan.
</p>

<br>
<br>
<h3>DISCUSSION</h3>
<p>
Saskatchewan is known for agriculture, how it feeds Canada and exports to the world too. The population of Saskatchewan has been fairly constant from the year 1996 to the year 2016 with the land mass being used for agricultural purposes on the steady decline. Production has been on the increase, as can be seen from the high revenue earnings recorded. This is interesting because the number of farms has reduced steadily too. The probability is that farmers there are using more effecient farming methods in order to meet the demands of the growing population of Canada. Another high possibility is that the amount of land that can be given to one who desires to begin, is likely to be higher than other provinces. Land must not be as scarce there as it is in other provinces.
</p>
<p>
Considering how high the population density for Ontario is, it is interesting how it is a significatly high earner in te field of agriculture. It warrants a detailed study on this.
</p>
<p>
Looking at this bar chart, we can see that the amount of land used for farming is highest in Saskatchewan, followed by Alberta, Manitoba, Ontario, Quebec and British Columbia in decending order of magnitude. It is clear that Saskatchewan and Alberta have significantly more land dedicated to farming than all the other areas combined. It is also clear that the amount of land being used for farming in Canada is on the decline. This means the number of people involved in farming or interested in it is on the decline. It means the pressure of meeting the nutritional needs of the population of on an every reducing number of people. It means too that there are real opportunities for would-be farmers in Canada. It also means the use of more effective farming methods for sustainability.
</p>
<p>
As a note from the data so far, I would recommend either Saskatchewan or Alberta, with preference for Saskatchewan, as the best province for farming.
</p>
<p>
The number of eating places in Saskatchewan is high, making about 38% of the venues, a farm that focuses on supplying their needs, makes sense.
</p>

<h3>CONCLUSION</h3>
<p>
Despite the fact that Canada has very little land available for farming, they have invested in modern farming methods and techniques that ensure increased production even in the wake of fewer people taking up farming. This study has not only brought this to light but has created a brief, but data backed roadmap for anyone who is new to farming in Canada. 
</p>