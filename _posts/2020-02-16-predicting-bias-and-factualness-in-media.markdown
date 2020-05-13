---
layout: post
title:  "Classifying sentiment in news articles" 
date:   2020-02-16 23:30:00 -4000
categories: learning 
---

[Natural language processing](https://en.wikipedia.org/wiki/Natural_language_processing) and [sentiment analysis](https://en.wikipedia.org/wiki/Sentiment_analysis) present interesting oppurtunities to classify writing in news media. Tools like [Doc2vec](https://radimrehurek.com/gensim/models/doc2vec.html) offer vector embeddings of written text that can be leveraged with tools like [scikit-learn](https://scikit-learn.org/stable/). 

I built the back end for [Sapience News](https://sapiencenews.com), which aims to predict bias and factualness in news articles. An API built from [FlaskRESTful](https://flask-restful.readthedocs.io/en/latest/) and [gunicorn](https://gunicorn.org/) lives at `https://hacker.domains:5555/sapience_api/query`. `$ curl https://hacker.domains:5555/sapience_api/query -d "url=NEWS_ARTICLE_URL" -X POST` will yield predictions. The API's underlying classifiers were trained on 143,000 American news articles provided by [this database](https://www.kaggle.com/snapcrack/all-the-news).  

Here's a [promo video]({{ site.url }}/assets/sapience_promo.mp4).
