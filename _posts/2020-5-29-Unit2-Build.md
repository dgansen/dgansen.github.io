---
layout: post
title: Lambda School Unit 2 Build Project
subtitle: Re-evaluating South Korean Weather Prediction Data
tags: [weather]
bigimg: /img/backgroundunit2.jpg
---

# What confuses weather prediction models?

![](/img/sum_temps.png){: .center-block :}
*Data given is five years of summer temperature highs and lows*

![](/img/feature_top.png){: .center-block :}
*The high temp and low temp models did not apply importance to the same features. The non-temperature features that low temp model looked at most were station slope, elevation (DEM), and latitude. Meanwhile, the high temp model looked to the next day's predictions for humidity (LDAPS_RHmin), for early cloud cover (LDAPS_CC1), and for average latent heat flux (LDAPS_LH).*

![](/img/feature_bottom.png){: .center-block :}
*For the low temp model, the five **least** significant features incorporated were the four 6-hour sections of next-day predictions for average precipitation. For the high temp model, they were almost the same features that the low temp model most valued*
