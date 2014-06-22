---
title       : FIFA World Cup Stats
subtitle    : Interactive analyzer of world cup matches since 1930
author      : Vitaliy Baklikov
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
theme       : solarized
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
---

## Shiny app

In the spirit of FIFA World Cup 2014 that is undergoing at the time of this writing, this is an attempt to create an interactive Data Product that analyzes FIFA World Cup matches since the first tournament held in 1930. 

We will focus on 

1. World Cup dataset
2. Shiny app functionality
3. Future improvements and functionality

--- .class #id

## World Cup Dataset

To our surprise, there is not much open data on world cup matches. FIFA, the organizer of the tournament, does not disclose such data to public. The data that is being analyzed with this application is from open sources. A special thanks goes to [__openfootball__](https://github.com/openfootball/world-cup) administrators for making the database free and public. 

The dataset has been precompiled and filtered in R to the following resulting dataframe



```r
head(allFIFAwc, n=2)
```

```
##   id   gameType     team1  team2   gameDate score1 score2 score1et
## 1  1 Matchday 1    France Mexico 1930-07-13      4      1        0
## 2  2 Matchday 3 Argentina France 1930-07-15      1      0        0
##   score2et score1p score2p winner wcYear
## 1        0       0       0      1   1930
## 2        0       0       0      1   1930
```

---

## Shiny app functionality

The application has been developed with `library(shiny)` and `library(ggvis)` plotting to embrace interactivity. It is hosted with the help of shinyapps.io and can be tried at http://vbaklikov.github.io/testDeck/index.html. Currently, there are 3 options available to filter and display the data 

1. World Cup slider to filter the data based on range of tournaments
2. Text input to filter data for a specic team
3. Drop down to filter data based on tournament stage

The application displays the data according to filters in interactive mode and also _computes_ the number of games played and number of goals scored.   

---

## Future improvements

The application is currently limited in scope to a) the amount of data that it analyzes and b) number of filters that it makes available. The following improvements are coming in the subsequent releases


1. Data added on match statistics such as corners, possesion, shots on target, yellow/red cards
2. Data added on players for each match - name, age, appearance for the team, club affiliation
3. Match attendance data and country/city the game was played
