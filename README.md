# Multi-channel-Marketing-Spend-Optimization-using-Deep-Learning

## Introduction

#### What is digital marketing?
Marketing has always been about connecting with your audience in the right place and at the right time. Today, that means you need to meet them where they are already spending time: on the internet. Digital marketing encompasses all marketing efforts that use an electronic device or the internet. Businesses leverage digital channels such as search engines, social media, email, and other websites to connect with current and prospective customers.

While traditional advertising can be useful for certain goals, its biggest limitation is measurability. Digital marketing can give you a comprehensive, start-to-finish view of all the metrics that might matter to your company — including impressions, shares, views, clicks, and time on page. This is one of the biggest benefits of digital marketing. 

## Background and Problem Formulation

Millions of customers are exposed to advertisements over a wide range of digital channels. Organizations spend hefty money on platforms such as email advertising, Google AdWords, Instagram, Facebook, and Twitter for customers to purchase or subscribe to products(aka. Conversion). Marketers track all the customer journey data(aka. touchpoints) and try to measure the effectiveness of each advertising channel.  Any business that’s actively running marketing campaigns should be interested in identifying what marketing channels drive the actual conversions. So naturally, the return on investment (ROI) for their marketing efforts is a crucial KPI(Key Performance Indicator). The inference about the influence of each channel plays an important role in budget allocation and inventory pricing decisions. 

The number of platforms on which businesses can market themselves to customers has surged. Most customers are engaging with businesses on multiple channels, and it is vital to decide how we’re going to attribute these conversions to specific marketing channels. 

This leads us to the problem of marketing spend optimization, which requires estimating the true contribution of individual channels to the final outcome and optimally allocating budgets across these channels.

## Aim
This project aims to:
* To predict if a series of events in a customer's journey(touchpoints) leads to a purchase/product subscription (conversion). 
* Analyze sequences of customer interactions and assess attribution of each advertising channel towards final conversion.

## About the dataset
The data for this project has been obtained from this blog on Markov model. It is open-sourced and readily available to download. The dataset contains ~586,000 marketing touchpoints for ~240,000 unique customers which resulted in ~18,000 conversion events. 

For every unique customer and visit, our dataset contains the following information for every row:
* Cookie: Randomly generated customer id enabling us to tie subsequent visits back to the same customer.
* Timestamp: Date and time when the visit took place
* Interaction: Categorical variable indicating the type of interaction that took place
* Conversion: Boolean variable indicating whether a conversion took place
* Conversion Value: Value of the potential conversion event
* Channel: The marketing channel that brought the customer to our site

## Methodology
After the initial data collection, the following tasks will be implemented:
1. **Data pre-processing and feature selection**
* Downsample converted/non-converted journey's
* Data cleaning to remove null values
* Formatting all instances of a unique customer into a single row
* Creating new columns with one-hot encoding for categorical variables
2. **Data modeling and training**
* Perform data modeling using  supervised machine learning ( Attention LSTM, Last Touch Attribution, Time-decay Attribution, Logistic regression, Linear Attribution,  etc)
* Training sequences of customer's journey and testing with validation data to obtain model accuracy scores
* Calculating attribution weights of individual channels
3. **Model evaluation and tuning**
* Calculating Area Under the Curve (AUC) of Receiving Operator Characteristic (ROC) for all models
* Comparing the scores of models and tuning parameters to increase model performance

## References

* Ning Li, Sai Kumar Arava, Chen Dong, Zhenyu Yan, and Abhishek Pani. 2018. “Deep Neural Net with Attention for Multi-Channel Multi-Touch Attribution.” ArXiv.org. https://arxiv.org/abs/1809.02230
* Diemert, Eustache, Julien Meynet, Pierre Galland, and Damien Lefortier. 2017. “Attribution Modeling Increases Efficiency of Bidding in Display Advertising.” ArXiv.org. https://arxiv.org/abs/1707.06409
* Morten Hegewald. 2019. "Marketing Channel Attribution with Markov Chains in Python-2". https://towardsdatascience.com/marketing-channel-attribution-with-markov-chains-in-python-part-2-the-complete-walkthrough-733c65b23323
* Lucy Alexander. 2021. "The Who, What, Why, & How of Digital Marketing".  https://blog.hubspot.com/marketing/what-is-digital-marketing
* Shweta Verma. 2020. "Deep Neural Nets for Multi-Touch Attribution". expressanalytics.org. https://medium.com/@shweta_44668/deep-neural-nets-for-multi-touch-attribution-114c7e78f5a8#_nr2mj0nwahio

