#Summary
This stacked barchart presents flight delay data from http://www.transtats.bts.gov/OT_Delay/OT_DelayCause1.asp, and shows arrival delays depend on the carrier and that there are multiple contributions to delay due to security, weather, etc. The average delay, which is the delay divided by the total number of flights for a given delay reason, is the total delay due to all reasons is plotted against the carrier. An interactive legend enables different failure reasons to be selected or deselected, and delays at various airports (top 20 by traffic volume) can be chosen from a pull-down menu.

#Design
The purpose of the chart is to show which airlines have the best / worst performance in terms of delay, and to explain this delay in terms of various delay causes such as weather, security &c. The primary focus of the chart is the dependency of delay on carrier.

The chart is explanatory in terms of showing a dependency of delay on carrier, and showing that this delay is the sum of various components. It does not explain why the various components (e.g. weather) vary between different carriers or airports, which would require additional datasets and different visualisations. Nonetheless, I think that this chart shows a clear dependency of arrival delay on carrier.

R was also used to pre-process the data to calculate an average delay (divide total delay by the number of flights for a particular airport and month) and reshape the data for plotting with dimplejs. This reshaped data is in a file called 2014_airline_delay_ct_reshaped.csv.

A secondary purpose of the chart is to show variation between airports. Since this is secondary, I have put a list of airport choices in a pull-down menu, which is less conspicuous than a legend. I also limited the choice of airports to the top 20 by traffic volume, so as not to overwhelm the viewer with choices. The default option is "All airports", which is every single airport in the country. The title of the chart changes to indicate the new failure reason when a choice is made from this menu. There are interesting variations in arrival delays between airports, however explaining those goes beyond the scope of this type of chart and the dataset. I would say that all charts to some degree pose questions, and are a springboard to further investigation.

The Y axis was allowed to rescale when the legend or menu choices were changed, as the main focus of the chart is the variation in arrival delay between carriers, and rescaling makes optimal use of the screen.

The legend was made interactive so that delay reasons can be selected or deselected in order to make comparisons easier. This overcomes one of the limitations of a stacked bar-chart, which is that comparisons between different groups can be difficult for the individual components of a bar. There is a title for the legend to show the viewer that this legend is interactive. I later made it easier to select single or multiple carriers using SHIFT-click.


##Main versions:
* original_index.html - (Vertbar9.html) - uploaded and presented to first reviewer, changed from fixed y-axis scale to rescaled, made legend interactive
* index1.html - (Vertbar8) - an older version
* final_index.html - (Vertbar10.html) final version, after receiving feedback from the reviwers. Changed x-axis title from 'carrier' to 'airline', added explanation of delay reasons at the bottom of the chart, limited the number of choices of the airport to the top 20 by volume

#Feedback
##First reviewer - Sara
Q1. What do you notice in the visualisation?

*I noticed all U.S airport delays for 2014, and also I can choose the airline which has less chance of delay at any airport.*

Q2. What do you notice in the visualisation?

*I do not really understand the meanings of carrier delay and late aircraft delay.*

Q3. What do you notice in the visualisation?

*I realized the relationship of delays happened for all airlines and certain airlines in terms of each airport.*

Q4. If I want to avoid delays, I will choose the airline which has less chance of delays.

*I could easily find out the overall performance of all U.S airlines and the individual circumstance at each airport.*

Q5. What do you notice in the visualisation?

*I can understand it easily.*

In response to this reviewer's answer to question 2, I added an explanation of the various delay reasons to the bottom of the chart.

##Second reviewer - Ben
Q1. What do you notice in the visualisation?

*It is quite clear from the chart that Airtran Airlines Corp performs the best in terms of flight arrival delay, with 200 minutes in 2014, while Express Jet airlines Inc showed the worst performance, with about 340 minutes.*

Q2. What questions do you have about the data?

Q3. What relationships or trends do you notice?

*The analysis indicates that there are five important factors that contribute to the variation in delay between carriers, in different levels. Major impact factors include weather and security.*

Q4. What do you think is the main takeaway from this visualisation?

*It appears that weather plays very important role in the delay process.*

Q5. Is there something you don’t understand in the graphic?


##Third reviewer - Joseph
Q1. What do you notice in the visualisation?

*Graph plots delays vs airline for airport, airlines and broken down into reasons for the delay*

Q2. What questions do you have about the data?

*Does the height of the bars indicate the total number of delayed flights?*

Q3. What relationships do you notice?

*Weather caused the most delays*

Q4. What do you think is the main takeaway from this visualisation?

*All airlines suffer delays of one form or another and there is no real standout performer*

Q5. Is there something you don’t understand in the graphic?

*The carrier axis is off with the names not lining up with the graph and the names are hard to read.*

This reviewer was unsure of what the height of the bars represented, although the y-axis is labelled in minutes. To address the problem of the readability of the airline axis, I changed from a vertical to a horizontal stacked bar chart.
##Resources
  * http://stat-computing.org/dataexpo/2009/the-data.html
  * http://www.transtats.bts.gov/OT_Delay/OT_DelayCause1.asp
  * http://www.transtats.bts.gov/Fields.asp?Table_ID=236
  * http://www.rita.dot.gov/bts/help/aviation/html/understanding.html#q4
  * http://dimplejs.org/examples_index.html
  * http://dimplejs.org/examples_viewer.html?id=bars_vertical_stacked_100pct
  * http://dimplejs.org/advanced_examples_viewer.html?id=advanced_interactive_legends
  * http://dimplejs.org/advanced_examples_viewer.html?id=advanced_storyboard_control
  * http://dimplejs.org/advanced_examples_viewer.html?id=advanced_bar_labels
  * http://dimplejs.org/examples_viewer.html?id=scatter_standard
  * http://www.w3schools.com/cssref/pr_font_font-size.asp
  * http://stackoverflow.com/questions/23810128/wrong-result-in-dimplejs-scatterplot
  * https://github.com/PMSI-AlignAlytics/dimple/wiki/dimple.chart#addSeries
  * https://github.com/PMSI-AlignAlytics/dimple/wiki/dimple.storyboard
  * https://github.com/PMSI-AlignAlytics/dimple/wiki/dimple.eventArgs
  * https://github.com/PMSI-AlignAlytics/dimple/wiki/dimple.chart
  * http://thecodingtutorials.blogspot.com.au/2012/08/using-multi-column-data-with-d3-part-1.html
  * https://github.com/mbostock/d3/wiki/Gallery
  * http://christopheviau.com/d3list/
  * http://mikemcdearmon.com/portfolio/techposts/charting-libraries-using-d3
  * http://annapawlicka.com/pretty-charts-with-dimple-js/
  * http://blog.visual.ly/creating-animations-and-transitions-with-d3-js/
  * http://jsfiddle.net/nf57j/27/
  * http://stackoverflow.com/questions/23530434/in-dimple-how-do-you-change-the-order-of-the-series-ina-legend
  * http://stackoverflow.com/questions/26145982/change-chart-type-in-dimple-js-to-automate-chart-production
  * http://www.w3schools.com/cssref/css_selectors.asp
  * https://github.com/PMSI-AlignAlytics/dimple/wiki/dimple.chart#addLegend
  * https://leanpub.com/D3-Tips-and-Tricks/read
  * https://leanpub.com/D3-Tips-and-Tricks
  * http://stackoverflow.com/questions/23291200/dimple-js-how-can-i-change-the-labels-of-a-chart-axis-without-changing-the-data
  * http://stackoverflow.com/questions/25774821/dimple-js-axis-labels
  * http://stackoverflow.com/questions/20477224/removing-svg-text-elements-with-d3-js
  * http://cdn.oreillystatic.com/en/assets/1/event/91/D3_js%20tutorial%20Presentation.pdf
  * http://stackoverflow.com/questions/19387898/how-to-assign-unique-id-to-svg-text-element-in-d3-javascript
  * http://stackoverflow.com/questions/11903709/adding-drop-down-menu-using-d3-js
  * http://codekea.com/B7jlBrEGwAOo/finding-the-user-selected-options-from-a-multiple-drop-down-menu-using-d3.html
  * http://stackoverflow.com/questions/16805684/javascript-disable-text-select
  * http://fiddle.jshell.net/7KJC7/2/
  * https://en.wikipedia.org/wiki/List_of_the_busiest_airports_in_the_United_States
