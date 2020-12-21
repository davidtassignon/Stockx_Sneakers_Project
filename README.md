# Predicting the ROI of Sneakers on StockX.com
A Data Science Project where I used the sneaker data set of StockX is combination with an unofficial StockX API to predict the ROI for Yeezy and Off-White Sneakers.

## Background and Research Goal
Over the past 10 years flipping shoes (buying new sneakers and reselling the sneakers) is evolved to what is now the sneaker culture. You can think flipping sneakers for profit is silly, but this once niche market has grown to become a 2 billion market and it is projected to reach 6 billion by 2025.
One of the largest sneaker resale platforms is called StockX. It operates like a stock exchange website where users can place a bidding or asking prices, and when there is a match, the deal can come through. As you can imagine, this online marketplace is a Walhalla for data scientists or analysts as each day 7000 to 10000 deals are made.

The beautifull ting about this new marketplace is that all kind of people can now access a limited pair of sneakers. So this means that all kind of people can also participate on the StockX marketplace and make profit on reselling sneakers. The aim of my project was to identify which features boost the resale price of a pair of sneakers and give you as reseller the highest return on investment.   

## Project Overview
### StockX Dataset
For this project I used a dataset that StockX (see CSV_files/StockX-Data-Contest-2019.xlsx) published as a Challenge where people could win 1000 dollar. The data that was given consisted of a random sample of all Off-White x Nike and Yeezy 350 sales between 9/1/2017 and 13/02/2019. In total there were 99956 deals, 27,794 Off-White, and 72,162 Yeezy. To create this sample, they took a random, fixed percentage X of deals on StockX for each colorway, on each day since September 2017.
So for each day the Off-White Jordan 1 was on the market, they randomly selected X% of its sale from each day. 
Table 1 shows which variables were in the dataset.

![Screen Shot 2020-12-21 at 10 47 09](https://user-images.githubusercontent.com/70702631/102763476-ff675d00-4379-11eb-8e18-9722c5043a83.png)

Table 1: Variables in public StockX Dataset

### StockX Unofficial API
To get some extra information per sneaker name I decided to use an unofficial StockX API. As shown below, I iterated over each sneaker name that I had in my initial dataset returning me 37 extra variables. After closely investigating each variable, I decided to keep the variables in the table below.
```powershell
from stockxsdk import Stockx
stockx_ = Stockx()

large_sneaker_dict = {}
for sneakername in sneakernames:
    large_sneaker_dict[sneakername] = stockx_.search(sneakername)
```

![Screen Shot 2020-12-21 at 10 56 29](https://user-images.githubusercontent.com/70702631/102764457-73eecb80-437b-11eb-9925-524a30f9468b.png)

Table 2: Usefull variables for StockX API 

### Exploratory Data Analysis

