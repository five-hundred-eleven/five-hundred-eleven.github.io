The goal of this project was to identify interesting trends in MMA by exploring publicly available UFC data.

## Research Question
For each of a few countries with high UFC participation, plot the proportion of wins to total number of fights by year. "Wins" are further broken down into Decisions, TKOs, and Submissions.

## Which countries have high UFC participation?

The first part of our question requires us to find countries of interest i.e. countries with high UFC participation. There are potentially several metrics we could use:

1. Countries in which the greatest total number of UFC fighters were born
2. Countries in which the greatest per capita number of UFC fighters were born
3. Countries which are hosting the greatest total number of fighters
4. Countries which are hosting the greatest per capita number of fighters

I was not able to find existing datasets that include birthplaces of UFC fighters (there are websites that have this information but I don't have time to scrape them). Therefore, I had to use "countries that host UFC fighters" instead of "countries in which UFC fighters were born". This was disappointing because there are some countries such as Nigeria in which several high-profile fighters were born but none were hosted. Moving forward we should keep in mind that the countries we are looking at may host fighters that were not born there.

The following plots were made using Sherdog's UFC datasets (linked at the bottom of the page).

<iframe id="igraph-num-fighters" scrolling="no" width="100%" height="500px" src="https://stromsy.nfshost.com/content/num-ufc-fighters.html"></iframe>

We see that the highest total participation is in the U.S. and Brazil. This might be explained by these countries having high populations. Therefore we will also look at the per capita participation.

<iframe id="igraph-num-fighters" scrolling="no" width="100%" height="500px" src="https://stromsy.nfshost.com/content/per-capita-ufc-fighters.html"></iframe>

We now see some lower population countries darkly shaded including Australia, Canada, Iceland, Ireland, Sweden, Poland, and Russia. Since Iceland, Ireland, and Sweden have a low number of total fighters we will rule these countries out. Our final list of countries of interest is the U.S., Brazil, Japan, Poland, Canada, and Russia.

## Which outcomes are common among fighters from each country?

The below charts, for each country, show the percentage of fights won by **decision** (split or unanimous), **submission**, or **knockout** out of the **total number of fights**. The fights that were lost or that were ended by disqualification are not shown.

#### Brazil

Early on we see 100% of fights were won by decision (Joyce Gracie). The ratios even out as time goes on. Interestingly in 2018 we see more wins by TKOs than Decisions for the first time since 2008. Notable Brazilian athletes that achieved TKOs in 2018 include Amanda Nunes.

<iframe id="igraph-num-fighters" scrolling="no" width="100%" height="500px" src="https://stromsy.nfshost.com/content/ufc-fight-outcomes-Brazil.html"></iframe>

#### USA
<iframe id="igraph-num-fighters" scrolling="no" width="100%" height="500px" src="https://stromsy.nfshost.com/content/ufc-fight-outcomes-United States.html"></iframe>

#### Japan
<iframe id="igraph-num-fighters" scrolling="no" width="100%" height="500px" src="https://stromsy.nfshost.com/content/ufc-fight-outcomes-Japan.html"></iframe>

#### Russia
<iframe id="igraph-num-fighters" scrolling="no" width="100%" height="500px" src="https://stromsy.nfshost.com/content/ufc-fight-outcomes-Russia.html"></iframe>

#### Canada
<iframe id="igraph-num-fighters" scrolling="no" width="100%" height="500px" src="https://stromsy.nfshost.com/content/ufc-fight-outcomes-Canada.html"></iframe>

#### Poland
<iframe id="igraph-num-fighters" scrolling="no" width="100%" height="500px" src="https://stromsy.nfshost.com/content/ufc-fight-outcomes-Poland.html"></iframe>

## Resources
* [Notebook](https://github.com/ekoly/DS-Unit-1-Build/blob/master/ipynb/explore_data.ipynb)
* [Fight Data from Kaggle](https://www.kaggle.com/rajeevw/ufcdata)
* [Fighter Data from Sherdog](https://docs.google.com/spreadsheets/d/1z3QX0uWXv-XHX2Nfuj6zZHrfEeXI3A9CKWkrGaBzB8s/edit#gid=0)
