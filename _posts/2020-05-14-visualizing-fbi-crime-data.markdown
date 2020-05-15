---
layout: post
title:  "Using Twitter to Publicize and Visualize FBI Crime Data"
date:   2020-05-15 00:00:00 -4000
categories: data 
---

In highschool, I taught myself Python and created a Twitter-based API [@guardiancrime][twitter] that leveraged raw data from the [FBI Uniform Crime Report][ucr] to curate visualizations of local crime. With a tweet, users assessed property and violent crime in any one of nearly 10,000 American communities with available crime data. I recieved the FBI Outstanding Achievment Award for my work.

<p align="center">
  <img src="/assets/guardian_twitter_screenshots.jpg" style="zoom:50%;">
</p>

Users on Twitter took three simple steps to speak to the API: 

1. compose a tweet and mention [@guardiancrime][twitter],
2. include the hashtag #data to trigger an API response, and
3. choose a `city, state`-style location.

The API [@guardiancrime][twitter], which constantly monitored mentions, would then be promptly activated. The server-side, back-end application took three actions:

1. query a local SQL database of FBI crime data for information on the user-provided location,
2. generate a visualization, i.e., an infographic, of crime data for that location, and
3. reply to the user, supplying the visualization and some other helpful information.

Visualizations looked like the one below, shedding light on crime trends, totals, and more. New homeowners, college-goers, travelers, and more likely benefited from the insight offered. 

<p align="center">
  <img src="/assets/nyc_guardian.jpeg" style="zoom:20%;">
</p>

The project garnered attention, both from the FBI and from [journalists](https://www.crimetraveller.org/2016/01/fbi-crime-statistics-guardian-crime-project/). With time, the U.S. government developed the [Crime Data Explorer][cde], a successor of sorts to [@guardiancrime][twitter]. In retrospect, [@guardiancrime][twitter] offered innovative insight on esoteric data to the general public. For more information on the project, reach out to me or visit the [Spark guide][guide]. 

<blockquote class="twitter-tweet tw-align-center"><p lang="en" dir="ltr">Agents in RI recognize 5 seniors <a href="https://twitter.com/lasalleacadri?ref_src=twsrc%5Etfw">@lasalleacadri</a> for their creative interpretation of the FBI&#39;s Uniform Crime Report. <a href="https://t.co/soekuNit5B">pic.twitter.com/soekuNit5B</a></p>&mdash; FBI Boston (@FBIBoston) <a href="https://twitter.com/FBIBoston/status/725035898333700096?ref_src=twsrc%5Etfw">April 26, 2016</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>



[twitter]: https://twitter.com/guardiancrime
[guide]: https://spark.adobe.com/page/PIXhJ/
[ucr]: https://www.fbi.gov/services/cjis/ucr
[cde]: https://crime-data-explorer.fr.cloud.gov/

