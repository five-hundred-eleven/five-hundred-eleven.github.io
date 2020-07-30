This project is inspired by [this post about how well population density predicts voting](https://observablehq.com/@jake-low/how-well-does-population-density-predict-u-s-voting-outcome).
The author runs a logarithmic regression on population density vs voting patterns and finds that it
has an R<sup>2</sup> score of 0.219, commenting that this is "not great". Then he creates a difference-from-trend
chloropleth map of the actual voting patterns minus predicted voting patterns and notes that the areas with the largest
difference tend to be ethnically African American or hispanic.

I was interested in trying to replicate his work in Python and further determine if population density plus percent non-white population
could more accuarately predict voting patterns.

The source for my work can be found in this github repo: https://github.com/ekoly/county-voting

### 2016 County Level Election Map
![2016 voting county map](https://stromsy.nfshost.com/content/voting_df.png)

source: https://github.com/tonmcg/US_County_Level_Election_Results_08-16

### Population Density Map
(yellow is more dense, purple is less dense)
![population density map](https://stromsy.nfshost.com/content/dens_df.png)

source (population): https://www2.census.gov/

source (land area): https://www.census.gov/library/publications/2011/compendia/usa-counties-2011.html

### Trends
I ran a RandomForestRegressor (max depth of 5 to minimize overfit) with population density as X and voting trends as y. This yielded an R<sup>2</sup> score of 0.315.
This is higher than Low's logarithmic regression. I then subtracted the predicted voting patterns
from the actual voting patterns and came up with the following choropleth.

Blue means democratic voters are underestimated, red means republican voters are underestimated.
![difference from trend for population density](https://stromsy.nfshost.com/content/diff_df1.png)

The areas in the South East that underestimated Democrats are consistent with areas with high populations of African Americans or Hispanics.
The following is a chloropleth map that shows high percentage of African Americans or
Hispanics in yellow.
![difference from trend for population density and non-white](https://stromsy.nfshost.com/content/minorities.png)

I ran a second RandomForestRegressor with population density and percent African American or Hispanic as X and voting trends as y.
This yielded an R<sup>2</sup> score of 0.559, a notable improvement over using just population density. This lead to
the following difference-from-trend chloropleth:
![difference from trend for population density and non-white](https://stromsy.nfshost.com/content/diff_df2.png)

The predictions in the South are much improved, but some other areas of the country are still quite far off or even worse than
using only population density. Interestingly, many ethnically diverse regions still underestimate Democratic voting, and many predominantly white
regions still underestimate Republican voting. This suggests that whites in diverse areas are more likely to vote Democrat
and non-whites in predominantly white areas are more likely to vote Republican. This does not hold true in the North East and Vermont in particular
is entirely much more blue than its population density and ethnicity would suggest. 

### Conclusions
The R<sup>2</sup> scores suggest that there is a medium correlation between population density and voting as well as between
ethnicity and voting. There are clearly regional trends in terms of voting patterns that override both population density
and ethnicity.
