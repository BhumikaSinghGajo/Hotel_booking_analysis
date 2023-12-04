
**Hotel Booking Analysis**

Our primary goal is to apply EDA to the provided dataset and derive insightful findings regarding overall patterns in hotel reservations and the interplay of various factors influencing hotel reservations.

This data set includes reservation details for both city and resort hotels, including the date of the reservation, the duration of the stay, the number of adults, children, and/or infants, and the quantity of parking spaces that are available, among other details. All data that could be used to identify an individual has been deleted.



## Problem Statement

Ever wonder when is the ideal time of year to reserve a hotel room? or the ideal duration of stay to obtain the best daily rate? What if you could forecast whether a hotel would be the target of an unusually high volume of special requests? Use this hotel booking dataset to investigate those inquiries! This data set includes reservation details for both city and resort hotels, including the date of the reservation, the duration of the stay, the number of adults, children, and/or infants, and the quantity of parking spaces that are available, among other details. All data that could be used to identify an individual has been deleted. Investigate and evaluate the information to identify crucial elements.
## Dataset

A hotel bookings dataset is provided to us. Reservation details for both city and resort hotels are included in this dataset. The following characteristics are present in it.

```bash
  Hotel : Kind of hotel (Resort or City)
is_cancelled : Whether the reservation was canceled(1) or not (0)
Lead_time: Days that are left before the guests actually arrive
arrival_date_year: Year of arrival date
arrival_date_month: Month of arrival date
arrival_date_week_number : The week and year of the arrival
arrival_date_day_of_month: Day of arrival date
stays_in_weekend_nights:How many weekends (Saturday or Sunday) do customers stay at the hotel?
stays_in_weel_nights:The number of weeknights (Monday through Friday) that visitors stay at the hotel.
adults: Number of adults among the guests
children: Number of children
babies: Number of babies
meal: Type of meal booked
country: country of the guests
market_segment:Segmentation of the market
distribution_channel: The channel name for booking distribution
is_repeated_guest: If the reservation came from a returning customer(1) or not (0)
previous_cancellation:The number of earlier reservations that the client canceled before the current reservation
previous_bookings_not_cancelled:The number of prior bookings that the customer did not cancel before the current booking
reserved_room_type: Code from room type reserved
assigned_room_type: Code of room type assigned
booking_changes: Number of changes made to the booking
deposit_type: Type of deposite made by the guest
agent: ID of travel agent who made the booking
comapny: ID of the company that made the booking
days_in_waiting_list: Number of the days the booking was in the waiting list
customer_type: Type of customer, assuming one of four categories
adr: Average daily rate
required_car_parking_spaces : The quantity of parking spaces needed, but the client
total_of_special_requesrs:The quantity of unique requests the client has made
reservation_statuse: Status of reservation (cancelled, checked out, or no-show)
reservation_status_date:Date of the most recent update to the reservation status
```


## Data cleaning

**1.Removing Duplicate rows:-**
 Every duplicate row was removed.

**2.Handling null values:-**
  * Null values in columns ```company``` and ```agent``` were replaced by 0.
  * Null values in column ```country``` were replaced by others.
  * Null values in column ```children``` were replaced by the mean of the column.

**3.Converting columns to appropriate data types :-**
  * Changed data type of ```children```, ```company```, ```agent``` to int type.
  * Changed data type of ```reservation_status_date``` to date type.

**4.Removing outliers**
  * One outlier was found in the ```adr``` column. Simply dropped it.

**5.Creating new columns:-**
  * Created new column ``` total_stay ``` by adding ```stays_in_weekend_nights```+```stays_in_week_nights```.
  * Created new column ```total_people ``` by adding ```adults```+```children```+```babies```.






## Exploratory Data Analysis
Carried out EDA and attempted to respond to the following queries:

```bash
1.Which type of hotel is mostly prefered by the guests?
2.Which agent made the most bookings?
3.What is the percentage of repeated guests?
4.What is the most prefered room type by the customers?
5.What type of food is mostly prefered by the guests?
6.In which month most of the bookings happened?
7.which distribution channel is mostly used for hotel booking?
8.which year had highest bookings?
9.What percentage of bookings are canceled?
10.Which type of hotel having longer waiting time?
11.Comparison of no of adults VS Booking
12.Which type of hotel have highest ADR? 
```

Mainly performed using Matplotlib and Seaborn library and the following graph and plots had been used:

  * Bar plots
  * Scatter plots
  * Histogram
  * Pie chart
  * Box plots
  * Heatmap
  * Line plots

## Conclusion

```bash
1.The majority of visitors prefer the city hotel.
2.The most reservations were made by agent no. 9.
3.The percentage of returning visitors is lower, at 3.86%.
4.The majority of people prefer room type A.
5.Food of the BB type is generally favored.
6.July has the most reservations after August, with August having the most.
7.The majority of distribution channels, or 79.13%, are TA/TO.
8.Hotel City has the highest ADR. Revenue is increased by the highest ADR.
9.The year 2016 saw the highest number of bookings, totaling 42313.
10.Longer wait times at city hotels indicate that they are busier.
11.The GDS distribution channel made the largest contribution to ADR in city hotels, but not at all in resort hotels.
12.Less than seven days is the ideal stay duration for both types of hotels.
13.Not only do returning visitors not cancel their reservations, but so do regular visitors.
14.A higher ADR translates into higher revenue if there are more people.
15.There is a -0.51 negative correlation between the arrival date week number and arrival date year columns.
16.The correlation between stays_in_week_nights and total_stays is positive (0.95).
```