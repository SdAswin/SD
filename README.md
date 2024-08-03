# SD
#Sentiment Analysis on Twitter Data
#Use the tweepy library to fetch tweets and nltk for sentiment analysis..

import tweepy
from textblob import TextBlob

# Twitter API credentials
consumer_key = 'YOUR_CONSUMER_KEY'
consumer_secret = 'YOUR_CONSUMER_SECRET'
access_token = 'YOUR_ACCESS_TOKEN'
access_token_secret = 'YOUR_ACCESS_TOKEN_SECRET'

# Authenticate to Twitter
auth = tweepy.OAuth1UserHandler(consumer_key, consumer_secret, access_token, access_token_secret)
api = tweepy.API(auth)

# Fetch tweets
public_tweets = api.home_timeline(count=10)
for tweet in public_tweets:
    analysis = TextBlob(tweet.text)
    print(f"Tweet: {tweet.text}")
    print(f"Sentiment: {analysis.sentiment}\n")
