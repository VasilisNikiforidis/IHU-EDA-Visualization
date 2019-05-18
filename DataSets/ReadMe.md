The final form of the data sets used to create the visualizations.

## Original DataSets

[Crimes - 2001 to present](https://catalog.data.gov/dataset/crimes-2001-to-present-398a4) \
[Airbnb Listings](http://tiny.cc/dvcw6y) (chicago) \
[Taxi Trips](http://tiny.cc/i1cw6y)


## Preprocess

#### 1. Snapshots
The Crime and Taxi Trips datasets were huge in comparison to the Airbnb Listings, so it was decided to take snapshot of the two datasets so that the results can be comparable. \
We also kept only columns that we deemed as most relevant for the analysis we wanted to do.

#### 2. Area Codes to Area Names
The Crime and Taxi Trips datasets had a column named "Area Code" which had area codes as values (duh!), while the Airbnb dataset had a "Community Area Name" column with values the actual names of the Chicago neighborhoods. 

We needed to have at least one column as a point of reference across all three datasets, and the area names was deemed to be the most usefull one. Thus we wanted to translate the area code to area names (instead of the reverse which would be faster, but much less intuitive). 

We found a very helpfull table on github (https://github.com/dssg/411-on-311/blob/master/data/chicago-community-areas.csv), were we used the first two rows "Community Area" and "name", after loading the datasets to Excel, to form an "IFS" formula and translate the area codes to their respective names. 

Then the datasets were loaded on Tableau and the connection among them were possible using the new column we created, "Community Area Names".

#### 3. Date
In the Taxi Trips dataset, the date column had multiple formats, not all of which were recognized by Tableau. \
So, we used a Tableau built-in functionality, the Calculated Field, which helped resolve this issue by "telling" Tableau that each value corresponds to a specific format we used.

#### 4. Null values
In most cases null values were excluded, but there were some cases where this did not happen for a reason. \
For example, in the Crimes dataset, for the Spreadsheet like graph, null values were not excluded, because they were considered as any possible point where the Crime took place.

