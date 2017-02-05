README
================
Ellis Valentiner
2017-01-29

This is a look at the sentiment of tweets by President Trump (@realDonaldTrump).

The approach is similar to that by David Robinson's post [Text analysis of Trump's tweets confirms he writes only the (angrier) Android half](http://varianceexplained.org/r/trump-tweets/).

However I'm interested in whether the sentiment of Trump's tweets have changed over time.

Fetching all of the tweets
--------------------------

The Twitter API supports a maximum of 3,200 tweets per request. Fortunately we can make multiple requests.

Trump's tweets vs. his staff
----------------------------

In David Robinson's blog post, he determined tweets by Trump are made from his Android phone while his staff tweets from an iPhone. Therefore I restricted the data to tweets made from an Android phone.

Text processing
---------------

I unnested the tokens (words) from the tweets using regex and filtered stop words.

I then assigned each word a sentiment score. I used the AFINN word list to be consistent with David Robinson. Arguably the it would be good to compare to the `bing` and `nrc` lexicons.

Sentiment over time
-------------------

It is then pretty east to look at the sentiment of Trump's tweets over time. The sentiment score is a little noisy so, I included a right aligned 7-day moving average.

![](sentiment.svg)
