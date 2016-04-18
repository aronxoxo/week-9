# Final Project Proposal

## Problem / Question

The application I am developing will give the Chicago Department of Public
Health’s Food Protection Program a better way to allocate the limited health
inspectors for restaurants in Chicago.
The traditional way is tedious. There are too many restaurants to go through.
And the restaurant selection and inspection routes will affect the resource allocation.


## The data

The dataset I am using for this application are all from the Open Data Portal
of City of Chicago. The datasets include: The health inspection result data,  
restaurants' built-up year data, license expiration data, rodent complaint data,
sanitation complaints data, crime data, and environmental complaints data. They
are all accessible from the open data portal, and they have location attributes.


## Technologies used

First, build the prediction model. The data will be aggregated: the inspection
passage data (o or 1) will be treated as dependent variable, and others will be
treated as predictors. I will first use logistic regression model to train the
dataset from 2013, and use stepwise regression model to keep those statistically
significant variables. Then, I will test this prediction model on 2014 dataset.
The result will be tested through several metrics like ROC, AUC, etc. This
process will be done in R.

Then, build the index system. The estimation result will be transformed into an
index system using leaflet, turf, jQuery, underscore, D3. The system will fulfill
two needs: one, find a number of restaurants (user specify the amount, like the
ranking between two numbers) in the whole city that are most likely to fail the
health inspection, and give the route from the start and end point (user specified);
two, draw a polygon to limit the area of interest, and then rank the failing possibility
from high to low, and then generate the route from the start and end point (user specified).

Last, give the users "behind the scene" stories. Upon selection, each predictor will
be displayed as a layer represented by a density distribution map, euclidean distance
map, etc., to give users a sense of feeling "why the prediction is like this". These
layers will be displayed with the search result according to users' selection.

## Design spec

#### User experience

The user of this application will be staffs from the Chicago Department of Public
Health’s Food Protection Program.
Using this application will let the program better allocate the inspectors, and
target those restaurants who are highly likely to fail the health inspection.

#### Layouts and visual design

On the right side of the page will be boxes only for search purposes: search by
numbers or search by a polygon. They will be floating on the map.
The results will be shown on the left side of the page. This part will be hidden
until the search results and the routes are generated.
So basically, the user will only see the search boxes and a map from the beginning.


## Anticipated difficulties

First, The robustness of the prediction model. Second, I haven't written/used
any function for generating routes. Third, using D3 to generate beautiful graphs
seems to need some efforts.


## Missing pieces

Well, the regression will likely not be a problem, because I have done some similar
model building projects last semester. I may have some trouble in dealing with the
difficulties mentioned above.
