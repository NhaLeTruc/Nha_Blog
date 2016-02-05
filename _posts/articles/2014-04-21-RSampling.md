---
layout: post
title: "RStudio Exercise I"
excerpt: "Simple statistical tool for business"
categories: articles
tags: [R, statistics]
comments: true
share: true
---

#RStudio Exercise I: Sampling data for quality control

The premise:

So you have adopted RStudio or at least researching to see how it could be useful to you. Good for you! In this article, I will walk you through a basic but pragmatic implementation, sampling data for quality control using Excel and R. 
Let presume you work for a chain of convenient stores. Thus, naturally there are dozens of thousands of vendors and millions of products. The products are input into the system using an online portal, which allow each vendor to perform this task themselves at any given time. Problem is since there can be virtually endless variations of products, and the people who doing the data entry task is not from your company. So they input information the way that make sense to them, and they all have their own interpretation of products’ specifications. 

=== chart ===

Facing this challenge, the COO decided to hire a team of a hundred or so people to perform quality control on this daily influx of product through the company’s vendor portal. While you are tasked with providing this team with the information necessary for them to do their job. The products which were input yesterday, are sent to you in a csv file, with two or three hundred thousand rows every morning. You are required to sample from this population 10,000 products from 100 different categories and subcategories. By noon, you must have the sample in a csv file ready for the team. 

=== csv pic ===

Using Excel
-----------

So let try solving this problem with Excel first. Naturally, you would pivot the table. Then filtering the product by individual category, so that you could select; copy and finally paste value of the first 100 rows. Do this for each of the 100 categories, a total of 400 actions of clicking and dragging your computer mouse. You realized this is too error prone and tedious, so you decide to record a macro for the task. You’re happy with yourself for a while, then the company decided that they should have a bonus scheme. Vendors who input their products’ specifications with the best precisions and volumes are rewarded. So now you have to track the performance of each vendor base on their unique ID, keep in mind that you still need to insure sufficient sample per product category.

=== Excel pic ===

From this point, you could try to build VBA script that allow you to manipulate the data right on the spreadsheet instead of going through the pivot table. And as more requirements for you data coming in; remember murphy law; the script would become increasingly convoluted. Excel would also have to work on a fully rendered dataset, further downgrade your computer performance. As your dataset grow, this will become a real grind to maintain and transfer to your newer colleagues.

Using R
-------

After playing this mental exercise in your head, you’re determined in finding a better alternative to Excel. So you try on this new thing call R and RStudio. You find that R is perfectly compatible with Excel. You could read all those rows from your dataset with just 1 line of R code. 

=== R pic ===

You then write another few line of codes to filter the data by vendor ID, then easily sample for each vendor. Check the result to see if enough samples per category have been selected. You could easily remove or add more samples to fit the 10,000 capacity you QC team require every day.

=== R code ===

If you’re used to work with SQL queries, you could install RMySQL package and query your data set right in RStudio.

=== R code ===

The best thing about it all, is that now you could see exactly what you did with your dataset in one view. The syntax could often self-explanatory, otherwise a few simple comments would help. As most complicated stuff have been packaged nicely for you by other R enthusiasts.
That’s it, now you are connected with a community of data scientists and data engineers who work constantly to improve R capacity. You’re no longer alone and the tool you wield are versatile and ever evolving. You can get your team out of almost any tight spot that normal office work could offer. Beware though, R has its limitation, as the data get above 3 Gigabyte, performance will begin to deteriorate. At that point, you have entered the outer realm of big data. But that topic is for another time. 
