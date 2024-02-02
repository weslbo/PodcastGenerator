
# 
# Analyze sentiment

Sentiment analysis is used to evaluate how positive or negative a text document is, which can be useful in various workloads, such as:

- - Evaluating a movie, book, or product by quantifying sentiment based on reviews.
- - Prioritizing customer service responses to correspondence received through email or social media messaging.

When using Azure AI Language to evaluate sentiment, the response includes overall document sentiment and individual sentence sentiment for each document submitted to the service.

For example, you could submit a single document for sentiment analysis like this:

The response from the service might look like this:

Sentence sentiment is based on confidence scores for **positive**, **negative**, and **neutral** classification values between 0 and 1.

Overall document sentiment is based on sentences:

- - If all sentences are neutral, the overall sentiment is neutral.
- - If sentence classifications include only positive and neutral, the overall sentiment is positive.
- - If the sentence classifications include only negative and neutral, the overall sentiment is negative.
- - If the sentence classifications include positive and negative, the overall sentiment is mixed.

[Continue](/en-us/)

