# Red Ventures Data Science Interview: Technical Assessment

## Problem
You are on the Red Ventures data science team and helping a financial services partner. The partner's primary product is a high-value credit card associated with high customer lifetime values (LTVs). The partner is looking to reduce losses from customer defaults by offering a new, lower-value card that supports balance management and helps customers avoid default.

The partner has asked Red Ventures to help increase overall customer LTVs by downgrading risky customers to the new balance management card while keeping good customers in the high-LTV traditional card. You are tasked with identifying which customers are likely to default under the traditional credit card plan and should be downgraded to the balance management card.

## Timing
We recommend spending no more than 4-5 hours on this assessment. The description of specific deliverables is described below. You should submit your deliverables as a single, compressed archive, labeled `<name>.zip` For example, `William_Gosset.zip`. This archive should be emailed to **insert recruiter email here**.

## Data

### Description
These data consist of attributes about 30,000 traditional credit card customers and their credit card billing and payment history from April to September. Additionally, their default status in October is given.
For assessment purposes, these data have been partitioned into 2 sets:
- `train.csv`
- `test.csv`

`train.csv` includes 80% of the original data with labels. `test.csv` contains 20% of the original data without labels. You will use `test.csv` to make predictions for submission.

### Codebook
- `limit_bal`: Amount of the given credit in dollars: it includes both the individual consumer credit and his/her family (supplementary) credit.
- `sex`: Gender (1 = male; 2 = female).
- `education`: Education (1 = graduate school; 2 = university; 3 = high school; 4 = others).
- `marriage`: Marital status (1 = married; 2 = single; 3 = others).
- `age`: Age (year).
- `pay_1:pay_6`: History of past payment. We tracked the past monthly payment records (from April to September) as follows: `pay_1` = the repayment status in September; `pay_2` = the repayment status in August; . . .;`pay_6` = the repayment status in April. The measurement scale for the repayment status is: -1 = pay duly; 1 = payment delay for one month; 2 = payment delay for two months; . . .; 8 = payment delay for eight months; 9 = payment delay for nine months and above.
- `bill_amt1:bill_amt6`: Amount of bill statement in dollars. `bill_amt1` = amount of bill statement in September; `bill_amt2` = amount of bill statement in August; . . .; `bill_amt6` = amount of bill statement in April.
- `pay_amt1:pay_amt6`: Amount of previous payment in dollars. `pay_amt1` = amount paid in September; `pay_amt2` = amount paid in August; . . .;`pay_amt6` = amount paid in April.
- `default_oct`: response in ${yes, no}$ of default in October

### Scoring
You are asked to make predictions on an unlabeled test set `test.csv`. The predictions should be the probability of defaulting $Pr(default = yes)$ in [0, 1].

#### Evaluation Metric
[Log Loss](http://www.exegetic.biz/blog/2015/12/making-sense-logarithmic-loss/) will be used to score the fitness of your classifier. In short, log loss penalizes models that are highly confident about wrong answers. 0 is a perfect score. The `train()` function from `caret` in R, and `sklearn.metrics` from python both include a log loss metric for model optimization.

## Deliverables

You will be assessed in two ways. First, you will be objectively scored on how well your classifier is able to predict a customer's likelihood to default. Secondly, you will be assessed on the quality of your methodology and ability to describe and justify your design decisions. Your submission archive should contain:
1. `<name>_predictions.csv` Your predictions on the test set. Format is described below.
2. `code/` a directory containing the code you used to make predictions. This code should be reproducible. That is, given your code and the train and test data sets, we should be able to exactly reproduce your predictions CSV.

### Submitting Predictions
As part of your submission archive, create a CSV with two columns [`customer_id`, `pr_y`] that contain your predicted probabilities for each `customer_id` in the test set. The file-name should follow the format `<name>_predictions.csv`, for example `Gosset_predictions.csv`. Three files are included to help ensure your predictions are in the correct format:
- `example_predictions.csv`
- `make_submission.R`
- `make_submission.py`

`example_predicions.csv` is an example of what your submission CSV should look like. Additionally, convenience functions for both python and R have been provided to turn data frames into the appropriately formatted CSV.

### Code

You may use anything you would like to make the predictions, however whatever you do should be reproducible. That is, given your code and the train and test data files, we should be able to exactly reproduce your predictions CSV. You may wish to include a README that describes how to reproduce your predictions, given your code. We are not expecting that you include any software with your submission. Since you will also be evaluated on your methodology and design decisions, please include any exploratory or ad hoc analyses that you performed during your work.

## Email Final Submission Archive
Email your final submission archive to Kaitlin Schneider: kaobrien@redventures.com.

