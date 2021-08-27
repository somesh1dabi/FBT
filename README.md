# E-commerce website transaction history based user segmentation
Exploring an E-Commerce transaction history for possible segmentations of users

## Table of Contents

- [A look into the dataset](#A-look-into-the-dataset)
- [Gist of the python file](#Gist-of-the-python-file)
- [How to use](#How-to-use)
- [Improvements](#Improvements)

## A look into the dataset

```python
dataset.head()
```
> <a href="https://imgur.com/lwWhIxo"><img src="https://i.imgur.com/lwWhIxo.jpg" title="head" alt="head" /></a>

```python
dataset.describe()
```
> <a href="https://imgur.com/QoQNG8e"><img src="https://imgur.com/QoQNG8e.jpg" title="describe" alt="describe" /></a>

## Gist of the python file

### Data pre-processing: 
- Identified and removed duplicate transactions, ‘UserId’= -1 cases, ‘ItemCode’= -1 cases. 
- Removed the pair of cancelled transactions which showed up in the dataset with same positive and negative ‘NumberOfItemsPurchased’ value, leading to a symmetric nature of the boxplot. 
- Dealt with the outliers in each column, including the hidden ones from the boxplot analysis.

### Analysis: 
- Modified the dataset to gain some insights on some simple patterns, produced 2 bar graphs representing number of users shopping each month or day for conclusion of the analysis.

### Segmentation 1: 
- Based on Expenditure by each user Introduced a new feature ‘TotalCost’ and made 6 segments under it: 
  - Very Small (0-500€) 
  - Small (500-2,500€) 
  - Normal (2,500-5,000€) 
  - Big (5,000-50,000€) 
  - Very Big (50,000-500,000€) 
  - Whales (500,000+ €) 
- The conclusion is represented by the produced graph. 
- The motive behind this segmentation being the ability to identify and better cater the users of each segment.

### Segmentation 2: 
- Based on frequency of shopping Identified the frequency of shopping of each user from the given 13 month data. *(Month was chosen as the basic unit and not week or quarter because the data mostly has bulk orders which are usually done with big intervals of time)* 
- Segmentation was done into 4 categories: 
  - One-Timer (1 Month) 
  - Occasional (2-6 Months) 
  - Frequent (7-12 Months) 
  - Regular (13 Months) 
- The conclusion is represented by the produced graph and output csv file.
- The motive behind this segmentation being the ability to identify and accordingly push schemes/offers to lower segments to convert them to higher segments.

**Other possible segmentations that I could think of were:**
  - Based on Items they usually buy, example: Crockery buyer, Stationary buyer, Toys buyer… But this would require an external dataset to determine the Item-Item similarity matrix for creating the aforementioned segments.
  - Based on the number of items purchased, example: Bulk buyer or not
  - Geographic segmentation, country-based segments.
  
  ## How to use
  + Download the zip containing 'transaction_data.csv' from the repo
  + Change the directories in the python notebook accordingly
  
  ## Improvements
  - Improvements for reducing runtime are mentioned as comments in the python code next to the possible areas
  
  
