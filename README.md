# Airbnb Data Visualisation 

![download](https://github.com/Payal03Gawande/AirBnb/assets/132563037/ec214118-5b8f-4dd5-879b-09048f317e73)
# About Dataset:-
Airbnb, Inc is an American company that operates an online marketplace for lodging, primarily homestays for vacation rentals, and tourism activities. Based in San Francisco, California, the platform is accessible via website and mobile app. Airbnb does not own any of the listed properties; instead, it profits by receiving commission from each booking. The company was founded in 2008. Airbnb is a shortened version of its original name, AirBedandBreakfast.com.
Since 2008, guests and hosts have used Airbnb to travel in a more unique, personalized way. As part of the Airbnb Inside initiative, this dataset describes the listing activity of homestays in New York City

**Content**

The following Airbnb activity is included in this New York dataset:
Listings, including full descriptions and average review score Reviews, including unique id for each reviewer and detailed comments Calendar, including listing id and the price and availability for that day

**Data Dictionary**

Data dictionaries are used to provide detailed information about the contents of a dataset or database, such as the names of measured variables, their data types or formats, and text descriptions. A data dictionary provides a concise guide to understanding and using the data.
https://docs.google.com/spreadsheets/d/1b_dvmyhb_kAJhUmv81rAxl4KcXn0Pymz

**Inspiration**

Learn Data Cleaning

Data Cleaning Challenge

Data Cleaning Practice for beginners

Handling missing values

Handling Outliers

Handle inconsistent data

Data Visualization

Data analysis

What can we learn about different hosts and areas?

What can we learn from predictions? (ex: locations, prices, reviews, etc)

Which hosts are the busiest and why?

# Data Perception
* DataFrame Information:
The DataFrame contains 102,599 rows and 26 columns.
* Null Values: The DataFrame has null values in various columns that need to be addressed. Appropriate methods such as dropping rows/columns, imputing missing values, or ignoring irrelevant columns can be applied.
* Outliers in 'minimum nights': The 'minimum nights' column has outliers, including a minimum value of -1223 and a maximum value of 5645. These extreme values indicate potential errors or data entry issues that require further investigation.
* Negative value in 'availability 365': The 'availability 365' column contains a negative value of -10, which seems incorrect since availability should be a positive value representing the number of days an accommodation is available. It is essential to examine and resolve this issue to ensure data integrity.
* Handling Null Values: Various methods such as dropping rows/columns, imputing missing values, or ignoring irrelevant columns can be employed to handle null values in the DataFrame.
* Correcting Data Types: To correct wrong data types in different columns, you can use pandas functions for data type conversion.

# Data Cleaning Description
Create a Woking_df with all the essential columns we requried for analysis.

* id" which is our "Primary Key" columns has duplicates. so we drop all the duplicated values .

* Host_identify_verified" has 289 null Values and 2 unique value i.e 'unconfirmed' And 'confirmed'. Assuming that the null values host are unconfirmed ones, we replace the null values with "unconfirmed".

* Neighbourhood Group((States))" has 29 null values. We find the Neighbourhood((Cites)) w.r.t to each Null Neighbourhood Group and for that city we find the states they are belongings to and replace the null values with the corresponding states.

* Neighbourhood" has 16 Null values. For this we follow the same approch of finding the stastes w.r.t them and then replace it with the highest repeated values. Both "Lat" and "Long" has 8 null values for the same index number. we took and the cities w.r.t to the null values and find their corresponding lat and long . once we get the values we replace the null values with them.

* Intant_bookable" has 105 null values and the column contains only boolean values. We corelate "Instant_bookable" with "Minimum Nights" in a way that the airbnb having high mininum nights values are prebooked and has less chances to available for instant booking. For most of the null values the minimum night is less than 30. So we replace the null values in this with "False" .

* Cancellation Policy" has 76 null values and 3 unique values i.e "Moderate","Strict", & "Flexible". We find the instant booking feature values wrt to 76 null values and find out that for all values "Instant Booking" is False. Then we find out that for "False" instant booking moslty the cancellation properties are "moderate" , so we replace the null values with the "moderate".

* Construction Year" has 214 null values. We replace all the null values with "Not Available".

* Service Fee" has 273 null values. we replace all the null values with Mean value of "service fee"

* Price" has 214 null values. we replace all the null values with Mean value of "price".

* Minimum Nights" has 409 null values. We replace null values with mode of minimum nights i.e 1.

* Number of Reviews" has 183 null values. we replace all the null values with "Median" value of reviews as it a highly skewed data and in such data it's advised to replace null with median.

* Last review" has 15893 null values and the only column which we can use for datetime analysis. we use interpolation method to replace all the null values in it. To treat the null values of date columns "interpolation" is good technique to used.

* Review Per month" 15879 null values . We replace the null values the mean value of the field.

# Conclusion
**Popular Neighborhoods:**
Manhattan is the most popular neighborhood on Airbnb, followed by Brooklyn.
Bedford-Stuyvesant has the highest number of Airbnb listings, while Williamsburg is the second highest.
**Price and Service Fees:**
There is a strong positive correlation (1) between the price of listings and the associated service fees.
**Reviews and Average Reviews per Month:** A moderate positive correlation (0.59) exists between the number of reviews a listing has received and the average number of reviews per month.
**Pricing Trends:**
The highest average prices were observed between 2012 and 2014, followed by a significant decrease after 2014.
**Property Types by Neighborhood:**
The most prevalent property type in Manhattan is the entire room/apartment, while private rooms are more common in Brooklyn.
**Factors Affecting Pricing:**
The pricing of listings depends on factors such as room type, neighborhood, and minimum number of bookings.
**Host IDs and Reviews:**
There are 102,052 unique host IDs for the given reviews, with one host (ID: 20032806094) having the highest average reviews per month at 90.00.
The top two neighborhood groups based on reviews per month are Brooklyn (46,866.76) and Manhattan (45,222.96), while the top two neighborhood groups based on the number of reviews are Brooklyn (1,189,991.0) and Manhattan (1,050,741.0).
**Price Variation by Property Type:**
Hotel rooms tend to be more expensive than apartment or house rentals.
**Neighborhood Rate Comparisons:**
Certain neighborhoods like "New Dorp," "Fort Wadsworth," and "Chelsea, Staten Island" have higher Airbnb rates compared to "Rossville," "Spuyten Duyvil," and "Lighthouse Hill."
**Pricing and Minimum Booking Requirement:**
Listings with a minimum booking requirement of more than a year generally have higher prices.
**Instant Booking and Cancellation Policies:**
Approximately 49.7% of customers use Instant booking, while 50.3% do not.
The cancellation policy distribution shows that 33.5% have a moderate policy, and 33.2% have either strict or flexible policies.
**Construction Year Distribution:**
The highest value counts for construction year occur in 2014, while the minimum counts are in 2016.
**Popular Property Types:**
The most popular property type is "Home away from home," followed by "Hillside Hotel."
**Popular Host Names:**
Among hosts, the most popular name is Michael, followed by David.
