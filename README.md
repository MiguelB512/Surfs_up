# Surfs Up: A weather analysis for a potential Surf n' Shake shop 

## Overview 

There's few things better than Ice Cream and Surfing on a hot summer day. That's why for this project, we will be analyzing weather statistics for different months to present to a business partner who is interesting in helping open a Surf n' Shake shop in Hawaii. After all, a business is no good if it is limited to operating during certain months. For this analysis We will be looking at the two opposite ends of the year, June and December. 

## Results 

To create this output, we pulled the data from an `SQLite` file using `SQLAlchemy` and `Python`. Once this data was inside of Python, `Pandas` was used to pull certain months and run statistical analysis on that part of the year for all the years of data that we have (2010 - 2017). Below is an example of the code used to retrieve the data from the SQLite file for 2010 - 2017. 

```
june_results = session.query(Measurment.date, Measurment.tobs, Measurment.prcp).\
    filter(extract('month', Measurment.date)==6)

june_results = session.query(Measurment.date, Measurment.tobs, Measurment.prcp).\
    filter(extract('month', Measurment.date)==6).all()
```

For June, we can see a Mean of 75 with a max of 85, along with other statistics. <br>
This is quite enjoyable weather for both surfing and ice cream, which is good news.

![june_temps](https://user-images.githubusercontent.com/60283799/178846297-2eb0a5f7-4c10-400d-8701-ccbe154b17b5.PNG)

For December, the numbers don't change too much. We have a mean, or average, temperature of 71 and a max of 83.<br>
Things are good for our potential business ventures. 

![december_temps](https://user-images.githubusercontent.com/60283799/178846313-b6796596-608a-48e6-8b9f-1605a86161f9.PNG)

When comparing the two months, we can make a few key observations:
- Differences in June and December are not too drastic, which is good for the business. 
- The temperature hovers in the low to mid 70's year-round.
- With the high still reaching 83 in December, that shows that there are still great Surfing and Ice Cream days throughout the year. 


## Summary 

When it comes to opening up a Surf n' Shake shop, it's clear that Oahu, Hawaii is a great destination based on the data we gathered here. The weather is nice and warm all year-round, meaning that both Ice Cream and Surfing would be in high demand. However, one other important factor that we have not yet considered is rain. Rain could both ruin a surfing day, and also sway customers to stay home and not want ice cream. 

If we change our SQLAlchemy query to include rain, we can get a little more insight on the total weather outlook. To do this, we add prcp (precipitation) to our query and append this to our DataFrame so we can see it alongside. 

![june_prcp_and_temp](https://user-images.githubusercontent.com/60283799/178885901-624df593-dc2f-4c8f-bb73-74a7fc27b280.PNG)
![dec_prcp_and_temp](https://user-images.githubusercontent.com/60283799/178885966-d6df2d22-3e52-4d7c-977f-60c2198a3b19.PNG)

From this, we can gather that the mean rain percentage in June is 14% and for December it is 22%. The rain percentage tells us much more about how our customers might act and whether the shop could be successful or not. 
