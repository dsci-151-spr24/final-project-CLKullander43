Pizza
================
by Caeden Kullander

## Summary

Today we’re looking at Pizza. I pulled this data from tidy-Tuesday. It contains data from the “One Bite” pizza app, which has reviews on hundreds of different pizza restaurants. 

Our primary goal with this is to know how to know what ratings you can expect from varying pizza places, and, importantly, to know how to identify the best Pizza restaurants. What’s the motivation behind this? What kind of male college student isn’t interested in pizza?

I started by checking for geographical relationships. New York is known for it’s Pizza. Let’s see whether this data reflects that. Now, looking at these histograms, we can tell that they are relatively the same. We see this spike in New York, but the main difference is that New York City has more observations as a whole, but doesn’t do quite as well on average, as reflected by these summary statistics. We can see that, according to this data, New York is around half a point worse.

Next I looked at the influence of price level. With community reviews, a price level of two (0 being the lowest prices and 3 being the highest) is most likely to have a higher rating. There are also a few with a level of three that have notably high ratings, but there aren’t many restaurants with a price level of 3. This tells us we should try to stick to moderately expensive but still reasonable pizza restaurants. Good pizza still can be found at the other levels, but this is the most consistent level.

Now let’s look at the same thing for critic ratings. Surely critic ratings would help us know the quality of a restaurant. Also, this will help us see if they only like expensive restaurants. What we can see with this plot is that price levels of one and two both seem viable.

However, the main thing se can see is that there aren’t very many critic ratings. A simple count tells us that there are only sixty observations that have any reviews, and just one with more than one. This isn’t going to be very helpful for our purposes, as we can’t even get useful averages from this.

With this in mind, I cut out the critic reviews entirely. I also stopped to make sure the community reviews would work. These are a lot better. We should be able to get decent averages with these. While here, though, I went ahead and remove the observations without any reviews.

While thinking about the number of reviews, I took a look at how review count affects ratings. I found that if there is a very low number of reviews, the rating can fall just about anywhere. This isn’t surprising, as these are averages. Now, there is a bit of a slope in the range of 5-50 reviews. Then it begins to plateau as it gets above 50 reviews.

Next, after creating a quick model for this, I saw that starting at 6.89, we can expect the average rating to go up by 0.01 for every review it has. Really, all this data tells us is that we are more likely to find good pizza by going to restaurants with a high number of reviews. This model isn’t super useful, as we already know that a high review count is good.

So, I made another model, this one only for when the number of observations is between 5 and 50. This new model shows that starting at 6.73, we can expect review score to go up by 0.03. This one is more useful, because we know what we want our cutoff point to be, this will give us a general idea of how many reviews it will take to get there.
In the end, we can say that to consistently find the best pizza, look for a restaurant with mid-range pricing and a lot of reviews. 

## Presentation

My presentation can be found [here](presentation/presentation.html).

## Data

I pulled the dataset from a Tidytuesday repository, which credits the data to Tyler Richards.
Data Retrieved on 3/15/2025.
https://github.com/rfordatascience/tidytuesday/tree/main/data/2019/2019-10-01

## References
Dataset:
https://github.com/rfordatascience/tidytuesday/tree/main/data/2019/2019-10-01
