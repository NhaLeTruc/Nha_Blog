---
layout: post
title: "Chi-square goodness-of-fit test"
excerpt: "Simple statistical tool for business"
categories: articles
tags: [R, statistics]
comments: true
share: true
---

#Basic Data Analysis with RStudio: Chi-square goodness-of-fit test

The premise:

This blogpost is another implementation example of using R in business settings for technically challenged office workers. Today subject is testing whether an assumption about a population distribution is statistically corrected. A population distribution is how the population spread out on a scale of measurement. For example, the distribution of your office personnel age is 23 people in their 20s; 11 in their 30s; and 5 in their 40s. That means if a person if randomly picked from your team. The chance is 59% or roughly 3 times out of 5 times; he/she will be between 20 to 29 years old; 28% or 1 out of 3 between 30 to 39; and 13% or 1 out of 10 between 40 and 49. 

For much larger population, say your customer base in a particular city, this population distribution will be much harder to quantify in such a way. Thus you need statistical researches to make an educated guess, on how your population of interested is distributed. But statistical researches are expensive and time consuming. Plus their usefulness run out overtime. So you want to use their findings as often as you could, but for how long you ask. This is where the chi-square goodness-of-fit test aka Pearson’s chi-square test come in. It was designed to test how ‘fit’ a good sample is to the expected population distribution. 

So let say you have a market research report a few years back. That concluded with good faith that your customers’ age-distribution in city A is as follow:

=== population distribution table ===

You want to use this report findings for your current report, but unsure if the findings still hold any value after all those years. Instead of conduct a full scale survey of your market area, which is nice if conduct well, but you have neither time nor money for. You could conduct a small scale survey instead, and test how your new result fit with the old findings. 

The experiment:

The first step is determined how large a sample you would need to ensure your result is significant enough. If you don’t want to deal with too much technical stuff, just use the statisticians’ rule of thumb and go with at least 400 people. We will use this rule in our case. So now you know if a study states it have less than 400 samples examined, that findings on the population wouldn’t be too robust.
Those who looking for a formula to calculate sample size base on population size need to stop. The point of grouping an amount of anything into an ensemble like population is that they are similar enough, to behave similarly in your interested field of study. If 400 to 1000 units of this population do not reflect the population behaviours. Your problem is not sample size. Your problem is you’re studying more than one populations at once. If so no matter how large your sample is, your findings will not hold any value. Since it is contaminated. 
So let say your survey result came back like this:

=== survey table ===

Now let’s do the chi-square goodness-of-fit test. First let’s fire up RStudio and load your new small survey study and old full-scale survey findings

=== R code ===

Load the the necessary package for this test:

=== R code ===

Let find out how many age group there are in your survey:

=== R code ===

Then how many people said they are in these age group:

=== R code ===

Assign the old survey findings into another variable:

=== R code ===

Run the chi-square test in R:

=== R code ===

The result:

If everything’d gone well, you would receive a view like this:

=== result ===

The null hypothesis of chi-square test is that the sample distribution fit the expected distribution. At 95% confidence, there’s only 5% chance that we make a type I error and mistakenly reject the null hypothesis. If you’re shock at this, please remember statistics don’t deal in fact, it’s all about probability and confidence. Yet, empires were fell and raised thank to its power. 
Interpreting the chi-square test result is quite easy. If the p-value is larger than the default 0.05 significant level (= 1 - 95% confidence), we do not reject the null hypothesis. So if your p-value > 0.05, your new sample has not discover any change in your population distribution, compare to the last time it was studied. 

Again, think of this as pointing a search light into a dark room, to see if there is any monster in it. Statistically speaking, the more time you do it, the more likely you would see something frightful. But after a set amount of times, and no monster have been spotted, no one would blame you to be reckless entering the room. After all life is all about taking risk, 100% guarantee will never happen. So the best way gain a slight edge is for you to take a smart calculated risk; using a simply brilliant tool; before you cross that threshold. 
