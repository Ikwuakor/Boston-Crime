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

![image](https://user-images.githubusercontent.com/42311832/94983857-c5698600-0503-11eb-842d-93dce0e2d364.png)

After plotting some yearly incident graphs, we can see from FIGURE 1 that the data for years 2015 and 2018 have not been collected over the course of an entire year. As a result, moving forward, I will only be using data for the complete years of 2016 and 2017 in my analysis, as the months June through September are the only months represented in all four years worth of data, thus rendering them over-represented in this data set.

After formatting our data set so that it only includes crime incidents occurring in the years 2015 and 2018, we can now gain an intuitive idea of the prevalence of overall crime, and gun crime specifically, in the city of Boston for the years 2016 and 2017. Let's take a look at a scatter plot where each crime incident has been plotted according to the geographic location of where it occurred.

![image](https://user-images.githubusercontent.com/42311832/94982080-d65ecb00-04f4-11eb-89cb-eb05bec2f02c.png)

## Crime Prevalence

Visually, from *IMAGE 1*, we can see that gun related crimes seem to cluster midway between the northern and southern parts of Boston as well as in the east. Overall crime incidents seem to be distributed far more evenly around the entire city while clustering in central and northern Boston. In the most northeastern part of the city, directly southwest of Winthrop, all crime incidents are infrequent. 

Notice that gun crime incidents correlate with overall crime incidents, that is, the areas in which our blue points cluster are the same areas where our pink points are also most prevalent. The lack of both crime incident and gun crime incidents in the green, forested areas implies that crime most likely correlates to population density.

In order to understand approximately how far crimes are taking place from downtown Boston area, I centralized downtown Boston at the origin of the following plots and graphs then converted latitudinal and longitudinal degrees into miles. Latitude-to-mile conversion stays consistent at approximately 69 miles per latitudinal degree since the difference between latitudes remains constant as we move further from the equator and closer to the poles. However, longitude is widest as the equator while converging to a distance of zero miles between longitudes as we approach the poles from the equator. Without getting too math heavy, there is a formula that accomplishes this for us:

- 1° of longitude = *cos*(latitude in radians) * 69.172 miles

According to Google Maps, downtown Boston is centrally located at 42.3557° N, 71.0572° W, near the intersection of Devonshire St. and Franklin St. These will be the coordinates we use to centralize our plots and the latitude we use to approximate our longitude-to-miles conversion (51.12 miles per longitudinal degree).

![image](https://user-images.githubusercontent.com/42311832/94982177-bd0a4e80-04f5-11eb-8751-d7cfeda1d9b6.png)

## Crime Distance

*FIGURE 2* confirms what we could already see from *IMAGE 1* above. However, now we know approximately how far the gun violence hot spots are from downtown Boston. It's from about one mile to about five or six miles south of downtown Boston that gun violence is the most prevalent, with about three miles south being the latitude of peak activity. We can also see that the bulk of gun violence occurs within two miles west of downtown Boston's longitude.

The Cartesian distance can be thought of as the 'true' distance from downtown Boston in which most gun violence occurs.  Each bin in the Cartesian histogram represents a ring, the inner and outer radius of which correspond with the lower and upper bounds of each bin, ie. each ring is a mile wide. Since each bin represents a geographical ring with ever increasing area, we have an ever increasing ratio of area to gun violence events. So although the radius is helpful in determining the distance of crimes, the prevalence of crimes might be skewed since a larger gun violence count could simply be accounted for by the larger area encapsulated by the ring. That being said, the Cartesian graph doesn't assign the largest gun violence counts to the outermost rings, therefore, we still have confirmation that gun violence is still clustered at most within a four mile radius.

With this information, outreach programs can focus their efforts to the parts of the city that fall within their desired proximity of downtown. Law enforcement could use this information to focus their patrol or surveillance efforts in strategically advantageous proximity as well.

![image](https://user-images.githubusercontent.com/42311832/94982195-ec20c000-04f5-11eb-8bba-9dc6364a062d.png)

## Central Tendency of Crime and Homicide Coordinates

With a data set like that compiled by the BPD's crime incident report system, mean latitudes and mean longitudes for specific crimes can be plotted, and the distances between mean coordinates and various locales can be measured. For the purposes of this report, the central coordinates for overall crime, _Crime Central_ , and for homicides,  _Homicide Central_ , have been plotted to provide insight, visually, into how far from downtown homicides cluster, as well as just how far they cluster from each other. From our previous map plot, we could see that where crime incidents tend to clutter, so did shootings and homicides. With this plot, however, we can see that although crime and homicides have mean coordinates to the southwest of downtown Boston, there is a bit of divergence between the two. In the case of _Homicide Central_ , the distance and location is consistent with the distances and directions we discussed with _FIGURE 2_. It would appear that something else, in addition to overall crime, is influencing the geographic location of gun crime, and homicides in particular. Nonetheless, gun crime follows a trend which, even without knowing all of its causes, remains remarkably consistent from 2016 to 2017.

![image](https://user-images.githubusercontent.com/42311832/94983761-204ead80-0503-11eb-9c69-0fcf5365dbb6.png)

## Central Tendency Migration

In the interest of gaining an even better grasp of which direction gun violence, and homicides in particular, is trending, we can analyze the yearly migration of the mean crime and mean homicide coordinates themselves.

Interestingly, when we plot the geographic coordinates for _Crime Central_ from 2016 and 2017, we find that the distance between the two is less than 40 feet apart in the Kensington Park neighborhood, according to Google maps (the image on the left). Perhaps this makes sense given the high quantity of crime incidents. As the number of crime incidents rises, we would expect their mean geographic coordinates to begin to display an ever-narrowing central tendency. What's remarkable, however, is that even with far less homicides recorded each year than total crime incidents, we still find that _Homicide Central_  (located in Boston's Dudley/Brunswick King neighborhood near the intersection of Intervale St. and Coleus Park), for 2016 is only 0.1 miles walking distance from 2017's _Homicide Central_ (image on the right). With only 45 (2016) and 50 (2017) homicides respectively, the short distance between each year's mean homicide coordinates is interesting to say the least. If crime and gun violence prevention groups knew that overall crime and homicides display proximal central tendencies each year, then, as stated before with the latitudinal and longitudinal coordinates, they could choose to strategically condense their outreach and prevention efforts, geographically, with some desired distance from crime and homicide central tendency coordinates.

_Homicide Central_ is located approximately 3 miles south and 1 mile west of downtown Boston can assume a normal distribution of homicides relative to _Homicide Central_ , which isn't far-fetched if we consider the distributions found above in _FIGURE 2_ around the 3 mile marker and 1 mile marker, for latitude and longitude respectively. With a latitudinal standard deviation of about 1.8 miles, and a longitudinal standard deviation of about one mile, we can draw a border around the rectangular space where approximately 68% of all homicides occur. We can see this area represented by the red rectangle shown above in the 'Central Tendencies' map. Granted the measurement is just a ballpark, but this information provides a more specific area of Boston where anti-gun violence measures can be focused and concentrated.

![image](https://user-images.githubusercontent.com/42311832/94984095-bd124a80-0505-11eb-861f-1c434f31c332.png)

## Crime Fluctuation

In examining the monthly crime fluctuations ( _FIGURE 3_ ), for both overall crime and gun crime, we can learn whether to expect a general increase or decrease in both from month to month. Although we see a noticeable uptick in overall crime from 2016 to 2017, especially during the months of May through October, the monthly distribution is consistent, with crime gradually increasing from February to August, before gradually dipping again. Gun crime seems to follow it's own monthly distribution that doesn't adhere to the same monthly fluctuations as overall crime, indicating that something else, other than crime itself, is having a significant influence on gun crime fluctuations, despite seeing an uptick in overall shootings just like we see with overall crime. For example, it's the month of April that sees the highest uptick in shootings from 2016 to 2017 despite seeing the second lowest number of shooting incidents in 2016 along with an overall decrease in crime from 2016 to 2017. Although the Boston Police Department's crime incident report system still in its infancy, more data, across more years could shed some light onto which year shows anomalous behavior for the month of April.

With gun crime, we can see that the 2017 fluctuations from month to month maintain the same upward and downward trends that they displayed in 2016, with the exceptions of April and September, indicating that there might be a correlation between weather and shootings, or perhaps holidays and shootings. Whatever the actual cause(s), the fluctuations in shootings seems to follow a seasonal distribution.  If so, seasonal outreach measures might make sense for anti-gun violence organizations as such information could be used to align their counter-violence measures with when gun violence is at its peak.

Interestingly, these upticks in shootings don't seem to be predictive of a similar uptick in homicides, themselves, let alone in regards to monthly distribution. Although shootings increased over 34% from 269 shootings in 2016 to 361 shootings in 2017, this led to an increase in homicides of only about 11% (45 homicides in 2016 to 50 homicides in 2017).

![image](https://user-images.githubusercontent.com/42311832/94984073-71f83780-0505-11eb-871e-1c88fc33ea2c.png)
![image](https://user-images.githubusercontent.com/42311832/94984115-ee8b1600-0505-11eb-9c35-56521e5e3c32.png)

## Day of the Week

Although it may not be surprising to see that most shootings and homicides occur on the weekends, ie. Friday, Saturday and Sunday ( _FIGURE 4.1_ ), it's not until we examine the hours of the day that shootings occur that we gain additional insight into gun violence behavior, as well as a concerning trend in data entry that might be skewing the perception on what time of day gun violence tends to occur.

In _FIGURE 4.2_ , we can see that gun violence between the hours of 5 AM and 10 AM is relatively infrequent when compared to nighttime gun activity. If we were to expand the swarmplot portion of -FIGURE 4.2_ horizontally, we would also see that there is an unusual amount of shootings that are documented as occurring at midnight. The fact that there are so many more shootings occurring at midnight than at, say, 11 PM or 1 AM makes me wonder if police document any shooting that occurs "in the middle of the night" as having occurred at midnight, when a precise time of shooting is unknown. This is a concern that warrants further investigation. If, for now, we assume the data is accurate, or at least that a significant amount of midnight shootings actually occurred at midnight, we can take a closer look at the hourly distribution of shootings and perhaps why early AM shootings are treated as outliers in the boxplot portion of _FIGURE 4.2_ .

![image](https://user-images.githubusercontent.com/42311832/94984284-c56b8500-0507-11eb-8c7a-32a393d13640.png)

## Hour of the Day

When we begin to examine the hours of the day that shootings take place, it becomes a bit more clear that the day of the week that the shootings take place is not quite as telling as we may originally have thought. If we look at _FIGURE 5.1_ , it would appear that the mean hour of daily shootings would fall somewhere between 1 PM and 8 PM (as the boxplots in _FIGURE 4.2_ would attest). This sort of distribution could make it seem that early AM shootings are outside of the bulk of most daily shootings. However, if we consider that the beginning and ending hour of a particular day is arbitrary and that, perhaps, the daily human behavior we wish to observe doesn't necessarily begin and end at those same hours, we can choose to observe gun violence behavior at different times, like from 8 AM until 8 AM the next day. If we do that, we can see that gun violence seems to have a multi-modal, natural distribution, one of the modes being the suspicious midnight hour we discussed previously.

Combining this information with the daily distribution information, we can deduce that gun activity is most prevalent during the afternoon and nighttime hours, of around 4 PM to about 2 AM, and from Friday night into Saturday morning, Saturday night into Sunday morning, and Sunday night into Monday morning. So how could all the information we've gathered from this data, and summarized in the previous plots and charts, be used to curb gun violence?

Based on the analysis of this report, one might recommend that law enforcement provide extra patrols in the Dudley/Brunswick King neighborhood, 1.8 miles north and south and one mile east and west of the intersection at Intervale St. and Coleus Park, between the hours of 4 PM and 2 AM, Friday night through Monday morning...perhaps between the months of May and October? This is just one example of how this analysis could help target anti-gun violence measures in the city of Boston.

## Future Work

This report is simply the tip of the iceberg. The geographical crime data contained in this report can be combined with with geographical data for:

- zoning maps, waterways, railways, and highways
- airports, bus stops, schools, housing developments, and office buildings
- churches, banks, and retail/shopping spaces
- weather data and moon phase (night lighting/visibility)
- population and employment rates

The data in this data set could serve as a complement to data sets like those mentioned above, the parameters therein, and to what extent gun violence, and overall crime, migrate in response to changes in those parameters.

I've also experimented with creating a sort of crime 'wind plot' which would indicate in which direction crime, or gun violence specifically, is migrating from year to year, for every square mile of the city. Each square mile would have the crime/gun violence trend indicated by a vector that indicates direction, and perhaps the magnitude of the vector used to indicate the distance in which that crime migrated. I'll also have to find a way to plot the data points a little bit more accurately upon the map, although at this point I'm not sure if I might have to find some way to account for the curvature of the earth.

### To see the entire project, complete with code, click <a href="https://github.com/Ikwuakor/Boston-Crime/blob/master/Boston%20Crime.ipynb">here</a>.
