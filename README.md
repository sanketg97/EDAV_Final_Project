
Summary:

My data visualization sources coffee production data by country and by year from 1990-2014
 from the International Coffee Organization, and create a world choropleth map to visualize
 coffee production over time, year-by-year.  The objective of this map is to trace the evolution 
 of coffee production by country over that time period.  

Visualization:

http://rawgit.com/patelmm79/Map-Global-Coffee-Production-d3/master/index.html


Overview:

I hope that certain findings are clear to users of this data:

1) Brazil has dominated coffee production by far for the time period;
2) Most countries have not significantly changed level of production; the most notable exception
to this rule is Vietnam, which in 1990 was not even amongst the top 10 global producers, but
ranked #2 on the list in 2014--even ahead of Colombia, whose name is synonymous with coffee
and had the #2 position in 1990.



Design:

My initial design incorporated a choropleth map of the world, in which countries would be shaded
based on the production of coffee.  The map also included a slider that would allow 
for specification of the year, to select the coffee production per country for that year.

Initial design was specified in included file index_basic.html.

The base reference map that I used (http://techslides.com/demos/d3/d3-world-population-density.html).  
Specifically,  I sourced the topojson methods of using map data and integrating production 
data onto the map. I also sourced the tooltip code to allow for display of specific 
production data upon rolling over the cursor over the country.

I chose a continuous scale to shade the countries based on coffee production data.  Initially
I chose a linear scale to shade the countries.  However, this method of shading did not allow 
someone to substantially distinguish between countries: Brazil, with the highest production levels
by far, was shaded in the darkest colour, but other coffee-producing countries barely registered.

I resolved this problem by using a logarithmic scale; all coffee-producing countries registered
a distinct shade of color.

I added a legend on the upper right hand side so that the user can understand what the shading
represents.  However, user feedback indicated that users would want the option to drill
down into the data to understand specific values by country.  One way to obtain the
specific data is to view via the tooltip  (hovering over the country).

I also added a table to the lower left corner, to show the top 10 producers by year, and 
their annual production.  This table is another way that end users can see the actual values,
and also very clearly understand the relative production (and change of production) by producer.

Styling choices based on feedback was to select a different font from the default, and to
stylize the slider bar for a skinnier look.

Finally, I created a guided tour via a series of text boxes, that select certain years and explains
the most significant aspects of the changes of data, while highlighting selected countries 
in the data table and country borders.

Feedback:

Feedback that I received included as follows:

* When I applied the linear scale, the color was indistinguishable for countries that were
not Brazil.  Additionally, the use of certain colors at the zero production end of scale 
proved to be distracting; I thus adapted white  as the base color, to show zero production.

* Users felt there was not enough information to distinguish coffee production solely
based on the shading and legend.

* The initial font, which was used on the World Cup map produced in course (what we might refer to as a basic web font) was 
considered to be too "generic" and "characterless" for the purposes of creating an attractive
design.  

* It was suggested to me to change the shading color at the high production end of the scale
from dark blue to a dark coffee-like color, reflecting the thematic focus of the map.

* One user found it annoying that the size of the column width of the table would shift year-by-year based on the
length of the longest country name.  

* Users suggested ways to make the d3 slider more elegant, including making the sliding 
bar and sliding handle to be skinnier.

* First Udacity reviewer indicated that my initial code was only exploratory, not explanatory.
So I added components to make it explanatory.

Resources:

**http://techslides.com/demos/d3/d3-world-population-density.html: base for creation of World choropleth
http://www.ico.org/historical/1990%20onwards/Excel/1a%20-%20Total%20production.xlsx : source of coffee production data

** http://bl.ocks.org/darrenjaworski/5397202  : source for linear choropleth visualization and legend
**https://gist.github.com/bradllj/8090200, 
  https://volumelabs.net/making-maps-with-d3/ : reference for how to filter then feed coffee production data 
into Choropleth
** https://github.com/mbostock/d3/wiki/Arrays: reference for array data management
** http://thematicmapping.org/playground/d3/d3.slider/ D3 slider guidance
** http://bl.ocks.org/zanarmstrong/ab12887fd8882490b5ae used for font styling on title and slider
** http://stackoverflow.com/questions/16211095/how-can-i-get-numeric-values-instead-of-logarthmic-values-in-d3-axis-scale   how to set up log scale legend
** http://stackoverflow.com/questions/5453370/displaying-one-div-on-top-of-another (to bring tooltip div on top)
** http://bl.ocks.org/d3noob/5d47df5374d210b6f651  table guidance
