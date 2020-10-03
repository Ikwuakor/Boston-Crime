# Boston Crime

## Problem Statement

>The following report examines crime incident reports provided by the Boston Police Department's new crime incident report system for the years 2015 to 2018. The data set documents the initial details surrounding an incident to which BPD officers respond, focused on capturing the type of incident as well as when and where it occurred. Time of day (in hours), location (latitude and longitude), day of the week, crime type, as well as some user generated statistics, like 'gun crime radius' and 'gun crime distance' will be used in the analysis. All data made available by Kaggle, provided by Analyze Boston.

In the fallout of recent mass shootings and what seem like daily news reports of gun related tragedies, gun violence, and how best to stop or reduce it, has been a lightning rod of American political discourse. With this data set, I aim to explore the city of Boston, as a microcosm of a greater national concern, and the areas inside of the city where gun crime is most prevalent; emphasis on shootings and gun-related homicides in particular. I will examine which parts of Boston, relative to the downtown Boston area, present the greatest risks of potential gun violence and towards which areas, or whether or not, gun activity is migrating within Boston. I will also examine which time of the day, days of the week, and months of the year gun violence is most likely to occur. The following report could serve as:

+ an advisory to cautious travelers and Boston residents
+ a precursor to future examinations from the crime incident report system, when it acquires more years of data
+ predictive analysis for any organizations or law enforcement agencies wishing to tackle gun violence in the city
+ a complement to data sets that explore various statistics for the city of Boston
+ a template for similar examinations on the state or national level
+ With this report, I aim to answer where, geographically, gun crime is most prevalent in Boston, when it's most prevalent, and most importantly, to provide some clarity on the predictability of the 'when' and 'where' of gun violence, from year to year. We begin with summary statistics for out data set.

![image](https://user-images.githubusercontent.com/42311832/94982019-7bc56f00-04f4-11eb-9b56-5654ff0cf6e8.png)

After plotting some yearly incident graphs, we can see from FIGURE 1 that the data for years 2015 and 2018 have not been collected over the course of an entire year. As a result, moving forward, I will only be using data for the complete years of 2016 and 2017 in my analysis, as the months June through September are the only months represented in all four years worth of data, thus rendering them over-represented in this data set.

After formatting our data set so that it only includes crime incidents occurring in the years 2015 and 2018, we can now gain an intuitive idea of the prevalence of overall crime, and gun crime specifically, in the city of Boston for the years 2016 and 2017. Let's take a look at a scatter plot where each crime incident has been plotted according to the geographic location of where it occurred.

![image](https://user-images.githubusercontent.com/42311832/94982080-d65ecb00-04f4-11eb-89cb-eb05bec2f02c.png)

## Crime Prevalence

Visually, from *IMAGE 1*, we can see that gun related crimes seem to cluster midway between the northern and southern parts of Boston as well as in the east. Overall crime incidents seem to be distributed far more evenly around the entire city while clustering in central and northern Boston. In the most northeastern part of the city, directly southwest of Winthrop, all crime incidents are infrequent. 

Notice that gun crime incidents correlate with overall crime incidents, that is, the areas in which our blue points cluster are the same areas where our pink points are also most prevalent. The lack of both crime incident and gun crime incidents in the green, forested areas implies that crime most likely correlates to population density.

In order to understand approximately how far crimes are taking place from downtown Boston area, I centralized downtown Boston at the origin of the following plots and graphs then converted latitudinal and longitudinal degrees into miles. Latitude-to-mile conversion stays consistent at approximately 69 miles per latitudinal degree since the difference between latitudes remains constant as we move further from the equator and closer to the poles. However, longitude is widest as the equator while converging to a distance of zero miles between longitudes as we approach the poles from the equator. Without getting too math heavy, there is a formula that accomplishes this for us:

- 1° of longitude = *cos*(latitude in radians) * 69.172 miles

According to Google Maps, downtown Boston is centrally located at 42.3557° N, 71.0572° W, near the intersection of Devonshire St. and Franklin St. These will be the coordinates we use to centralize our plots and the latitude we use to approximate our longitude-to-miles conversion (51.12 miles per longitudinal degree).
