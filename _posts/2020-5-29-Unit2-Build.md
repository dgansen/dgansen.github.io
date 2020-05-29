---
layout: post
title: Lambda School Unit 2 Build Project
subtitle: Re-evaluating South Korean Weather Prediction Data
tags: [weather]
bigimg: /img/backgroundunit2.jpg
gh-repo: dgansen/DS_Unit-2-Build
gh-badge: [star, follow]
---

# What confuses weather prediction models?
The weatherman is always wrong, so it's no wonder his head is in the clouds.  
This lame joke reflects an experience we all collectively have had. Weather is hard to predict. Machine learning tools in modern society are more powerful every day to assist in adding predictive power to the massive amounts of data being constantly collected. One question that it would be useful to answer on weather models is: why are they wrong? What factors can contribute to predictive errors? To briefly explore, I fitted a Random Forest Regressor model to the error of predictions within a five year dataset of South Korean summer weather data.


![](/img/sum_temps.png){: .center-block :}
*Data given is five years of summer temperature highs and lows, in degrees Celsius*

Notice in the data above that no season follows exactly the same pattern, though there is a drop off into the month of August. This simply illustrates the chaotic form weather data often takes.  

The regressor model was fit to a new column composed of the difference between the next day's actual high/low temperature with the high/low prediction, calculated by Local Data Assimilation and Prediction System (LDAPS) collected across 25 measurement sites. Generally, this prediction was only off by 1-2 degrees Celsius. **My goal is to find the variables that played the biggest role in confusing the model**, or the least important weather-related features.

![](/img/feature_top.png){: .center-block :}
*The high temp and low temp models did not apply importance to the same features. The non-temperature features that low temp model looked at most were station slope, elevation (DEM), and latitude. Meanwhile, the high temp model looked to the next day's predictions for humidity (LDAPS_RHmin), for early cloud cover (LDAPS_CC1), and for average latent heat flux (LDAPS_LH).*



![](/img/feature_bottom.png){: .center-block :}
*For the low temp model, the five **least** significant features incorporated were the four 6-hour sections of next-day predictions for average precipitation. For the high temp model, they were almost the same features that the low temp model most valued*

Data obtained at UC Irvine Machine Learning Repository, provided by:
Cho, D., Yoo, C., Im, J., & Cha, D. (2020). Comparative assessment of various machine learning-based bias correction methods for numerical weather prediction model forecasts of extreme air temperatures in urban areas. Earth and Space Science. (Accepted)
[link](https://archive.ics.uci.edu/ml/datasets/Bias+correction+of+numerical+prediction+model+temperature+forecast])
