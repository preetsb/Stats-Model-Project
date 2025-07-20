# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
To parse data from an API to see if there are any insights or connections to make. 

Using the API from CityBikes, which provides the details of bike sharing spots all over the world, we connected to two other APIs to find places of interest based on the location of the bike shares. The two other APIs used were from Foursquare, which provides detailed location data for a number of places, and Yelp, which is essentially a rating app used mostly for restaurants. 

The was to see if there was any correlation between the use of the bike shares and places of interest that might be within a kilometre of the bike station. 

## Process

At first I wanted to do the bike stations in Medina, Saudi Arabia because I assumed there would be a pattern with religious observances or even days of the week (like Fridays) but then I discovered that there is no Yelp or Foursquare data from Saudi Arabia and they are primarily North American based apps. 

I picked a random city in the USA and landed on Bentonville, Arkansas which turned out to be the headquarters of Walmart. 

So I requested the data from CityBikes, which was in .JSON format, looked through to find the details for Bentonville, put it into a DataFrame. Cleaned it up and got the location data for each bike station. Did similar with the Yelp and Foursquare API, but instead got the location data for restaurants that were close to each bike station. 

Joined the Yelp and Foursquare location data with the CityBikes, and realized that not much would be gained by combining the two (since it was the same bike station data with some different restaurants). So I first combined the Bentonville data with the Foursquare data, then combined the same Bentonville data with the Yelp data. Plotted a few graphs to see if anything was obvious. Nothing stuck out other than plotting the empty bikes and free bike plots with the distance to the restaurant from the bike station showed roughly opposite results. The further restaurants had fewer free bikes than the closer restaurants, and vice versa.

## Results
The quality of the APIs were similar but Foursquare does have more detailed data since they crowdsource from it's Swarm app where you 'check-in'. Yelp, since it is primarily used for reviewing places, has less detailed data but it does have better categories than Foursquare. Foursquare appears to classify anywhere with food as a restaurant (including bakeries and cafes) while Yelp only classifies as restaurants as places with a sit-down or takeout option for food. 

Yelp is more up-to-date since it is used more than Foursquare, but Foursquare has more detailed location data. Either way it can not provide any truly useful insights in this case without more information. The relatively simple Linear Regression model used did not show much of a correlation between distance and bike usage.  

## Challenges 
 There were the usual challenges that come with a project like this while learning. My first parsing of the CityBikes data did not provide distance from _each_ bike station but just gave too much information because it was giving me distance from every bike station. With some assistance I fixed that got more useful information. 

 Then I realized that because it was the headquarters of Walmart that the patterns would undoubetdly be different than other cities. Walmart is the biggest employer in Bentonville with over 18,000 people working there. The bike usage pattern is most likely influenced by the time of day, likely normal work hours with different usage over the weekends. 

 But the real challenge was simply not knowing _where_ the bikes were going. That would require GPS data. More empty slots or more available bikes can mean anything (is there a special event? What is the weather? Etc etc)


## Future Goals
If I had more time I would get information for different hours and different days and build a less simple model. Are there more bikes available during the day or evening? Are there more bikes being used over the weekend? Was there a major event happening that people would prefer to bike to instead of drive? 
