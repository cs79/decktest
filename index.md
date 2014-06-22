---
title       : Pitch Deck
subtitle    : Online Financial KPI Tracker
author      : Alex Lee
job         : 
framework   : html5slides        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Financial Key Performance Indicators (KPIs): Online Dashboard

We are introducing a new, online, financial management oversight tool to track our company's performance, built in R.

What this tool offers:
* Live financial ratio calculation
* User-defined alert thresholds
* Easy, online accessibility with a graphical frontend
* Customizable in R without web development knowledge

Where to find it:
* Online at: https://cs79.shinyapps.io/Financial-KPI-Tool/

--- .class #id 

## What Metrics are Covered?

By default, this online tool supports:
* Current Ratio: $Current Liabilities/Current Assets$
* Quick Ratio: $Current Assets-Inventory/Current Liabilities$
* Working Capital Ratio: $Current Assets/Current Liabilities$
* Debt Ratio: $Liabilities/Assets$

By virtue of being written in R with Shiny, it is easily extensible to cover other metrics as needed by management.

--- .class #id

## How it Works: Example in R

In conjunction with the Shiny web framework for R, this application uses R to compute ratios and track indicators.  As an example, the app's Quick Ratio function looks like this:

```r
qRat <- function(curAssets, inv, curLiab) { round((curAssets-inv)/curLiab, 2) }
```
If we knew the formula Current Assets offhand, we could pass it to the function directly, along with our current liabilities:

```r
cash = 100; marketableSecurities = 200; inventory = 300; accountsReceivable = 500; otherLiquidAssets = 1500; liabilities = 790
qRat(sum(cash, marketableSecurities, inventory, accountsReceivable, otherLiquidAssets), inventory, liabilities)
```

```
## [1] 2.91
```
The web app saves users the trouble of having to know formulae like this; individual figures can be plugged directly into the interface and the app computes them automatically.

--- .class #id

## What else should I know?

* The app provides a graphical interface for entering financial figures and setting thresholds -- no need to use R code directly as on the previous slide.
* The app can track multiple metrics simultaneously, and will recompute KPIs on the fly as figures are adjusted for all ratios for which those figures are relevant.
* The application also allows custom specification of alert levels: alert thresholds can be specified on a per-ratio basis, and notify the user if they are being approached and/or exceeded.
* The app can be used from anywhere with web access -- no more worrying about having the right spreadsheet.  This is a new one-stop-shop for financial analysis for management.

--- .class #id 

## Recap

This new financial management application provides:
* An easy-to-use interface for financial metric analysis without the need to know R code or specific formulae offhand: just enter figures from a financial statement, and the app handles the rest.
* Multiple metric analysis available simultaneously, and the application platform is easily extensible to cover new financial metrics.
* Availability anywhere you have an internet connection.

Try it today!  

Bookmark this page: 
https://cs79.shinyapps.io/Financial-KPI-Tool/
