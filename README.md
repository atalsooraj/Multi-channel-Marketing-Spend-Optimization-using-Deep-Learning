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

Key figures

* 2.4 GB uncompressed

* 16.5M impressions

* 45K conversions

* 700 campaigns

The data for this project has been obtained from [this](https://ailab.criteo.com/criteo-attribution-modeling-bidding-dataset/) Criteo AI Lab website. It is open-sourced and readily available to download. This dataset represents a sample of 30 days of Criteo live traffic data. Each line corresponds to one impression (a banner) that was displayed to a user. For each banner we have detailed information about the context, if it was clicked, if it led to a conversion, and if it led to a conversion that was attributed to Criteo or not. Data has been sub-sampled and anonymized so as not to disclose proprietary elements.

Here is a detailed description of the fields (they are tab-separated in the file):

* timestamp: timestamp of the impression (starting from 0 for the first impression). The dataset is sorted according to timestamp.

* uid: a unique user identifier

* campaign: a unique identifier for the campaign

* conversion: 1 if there was a conversion in the 30 days after the impression (independently of whether this impression was last click or not)

* conversion_timestamp: the timestamp of the conversion or -1 if no conversion was observed

* conversion_id: a unique identifier for each conversion (so that timelines can be reconstructed if needed). -1 if there was no conversion

* attribution: 1 if the conversion was attributed to Criteo, 0 otherwise

* click: 1 if the impression was clicked, 0 otherwise

* click_pos: the position of the click before a conversion (0 for first-click)

* click_nb number of clicks: More than 1 if there was several clicks before a conversion

* cost: the price paid by Criteo for this display (disclaimer: not the real price, only a transformed version of it)

* cpo: the cost-per-order in case of attributed conversion (disclaimer: not the real price, only a transformed version of it)

* time_since_last_click: the time since the last click (in s) for the given impression

* cat[1-9]: contextual features associated to the display. Can be used to learn the click/conversion models. We do not disclose the meaning of these features but it is not relevant for this study. Each column is a categorical variable. In the experiments, they are mapped to a fixed dimensionality space using the Hashing Trick (see paper for reference).

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

