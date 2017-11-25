---
layout: post
title: Data Analysis Workflow Guide
category: learning
tags: 
keywords: 
---

## Introduction
I have complied a list of good data analysis workflow tips from Professor Roger Peng's Analytic Mind, ep2. where he did a live data analysis on an air quality dataset. Roger Peng is a Professor in the Department of Biostatistics at the John Hopkins Bloomberg School of Public Health. He is also teaching the Data Science Specialization and Computing for Data Analysis course on Coursera.  

### 1. Updating packages and R startup script
He starts off the analysis with checking for R updates. I am not sure that this is necessary for every R session, but it is important to **update your packages regularly**. If you are trying to make reproducible work, you should also log your package updates.  

Another tip is to set up an R startup script. There are many cool things you could automate such as loading the `tidyverse` library and setting `stringAsFactor` to false. If you do not do this, when you read in a dataset, it will think "?" or "Null" as a factor. 

To make a startup file, you need to create a file called .Rprofile, put your desired startup commands, then place it in either 

1. your work directory
2. HOME directory
3.  R's installation folder/directory

R will look up the .Rprofile file in the same order and only run one. 

Details of setting it up can be found at **[EfficientR](https://csgillespie.github.io/efficientR/3-3-r-startup.html#r-startup)**. There are a lot more R pro tips there. If you want to learn more about the power of .Rprofile, you could check this **[Rblogger Post](https://www.r-bloggers.com/fun-with-rprofile-and-customizing-r-startup/)**.

### 2. Renaming 
#### Renaming column names
If not strictly prohibited, you may want to rename your column names so that they are understandable. If you would like to examine the column names of your dataset, you can run this command:
```r
colnames(dataset)
```

Even shortening some column names would help a lot. I actually don't do this very often, but maybe I should try this a few things to explore the effectiveness of doing so.  

#### Renaming things in general (refactoring)
In the video, he renamed the dataset 'smoke' to 'wildfire' because the dataset has columns 'smoke' and 'nonsmoke' so he doesn't want to write operations like 'smoke\$smoke' and 'smoke\$nonsmoke' It is very important that your namings make sense and don't conflict with others. It is especially important when you have to present and share your codes with others.


### 3. Looking at the data, at least the summary
Reading off some summary statistics for each column could help at lot. I often only do that for a few columns but I think it is helpful to examine all of them if you don't have a strict analysis deadline or don't know the data well. Peng used function **str** which I don't often, here is how it looks, see for youself if you find that useful or not:  
<img src="http://imgur.com/WDsBepwl.png" />

### 4. Don't load the whole package if you only use one function to avoid conflict
I always import the whole library and so far there is no problem. But I do believe Peng's approach is better since I don't have to go back the R chunk where I import my library and add the library. Below is the sample code for importing only one function from a package.  
<img src="https://i.imgur.com/5zLGZ5yl.png" />

### 5. Double checking if the model is working properly
After making a regression model, Peng computed the model in a different way to ensure his model is working. Working does not mean performance but doing what it is supposed to do. Sometimes when you make a mistake in your code, such as writing minus instead of plus in your formula, the model may still outputs something and you may be fooled by the incorrect results.  

When I was taking my deep learning class, there are many cases when my models compute something but different from the expected result. I often have to update my codes multiple times to get the right answer. Hence I expect others, or I in the future will run into similar problems as well.  

When you run a model, ideally you want to have some ways to test if it is doing what it is supposed to do. Or double, triple check your codes, do unit testing, before computing the model or training your data, _**ESPECIALLY WHEN IT TAKES A LONG TIME TO TRAIN A MODEL**_.

### 6. Get Familar with Your Data Analysis Tools
I remember at a certain point I believe that either R or Python they are just tools, learning them is not as important as learning more stats knowledge. But knowing R and Python or whatever tools you use well can really ramp up your productivity. At least you don't want to let writing code and debugging slow down or interupt the flow of your analysis.     

I highly recommend to use *tidyverse* for data manipulation and ggplot2 for graphing. The graph below shows the speed between using a *tidyverse* function and the *apply* function in base R, on a dataset with 280k rows and 14 columns.
<a href="https://imgur.com/gEjqoVN"><img src="https://i.imgur.com/gEjqoVN.png" title="source: imgur.com" /></a>
