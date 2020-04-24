# Subreddit Classification

## Problem Statement: 

#### How does Language Predict Group Membership? 
Can a submission title predict the source subreddit thread? Can comments predict the  source subreddit thread? What similarities in language exist between related and unrelated threads?

## Executive Summary:
This analysis attempts to categorize subbreddit threads based on Submission Titles and Comments. Specifically, it explores the subreddit threads r/science and r/conspiracytheories. Reddit provides places for like-minded humans to digitally congregate and share ideas. These two threads are fascinating because they might allow us to measure whether the use of language alone can predict membership, which is perhaps a cautious first step towards predicting empirical proclivity. The ethical considerations of such predictions are complicated and require thought and research beyond the scope of this analysis.

#### Methodology:
Data collection used the Pushshift API to gather subreddit posts in 1000-document iterations as dataframes. Approximately 24,000 Submission titles and 36,600 comments were collected.

Standard EDA techniques checked for congruence of shape, data types, and missing values, and duplicates. The 'selftext' field from the Submissions data was not used in final analysis, given the amount of missing data. The Comments data required cleaning, but did not present missing data issues.

5,400 models were fit using combinations of Logistic Regression, Multinomial Naive Bayes, and Support Vector Machine (SVM) classifiers. Additional parameters for each model included CountVectorizer, Term Frequency-Inverse Document Frequency (TF-IDF), and several hyperparameters specific to each mode type. More details can be found in the notebooks and presentation files.

#### Findings:
We can predict subreddit membership based on Submission title with 89% accuracy, and membership based on Comments at 80% accuracy. While promising, Reddit’s daily comments based on a 10-year average total ~470,000, meanig we may be mislabeling up to 47k posts a day.   

Similarities do seem to exist in the frequencies of used words, but not in the words most predictive of membership.

It is tempting to consider extrapolating this method for user classification. However, before using any of this data for user categorization or classification, higher model accuracy, a deep understanding of inherent Type I and Type II error, and serious ethical considerations are required. See the final section on conclisions and recommendations for further research for more details. 


## File Directory: 
- notebooks
   - 01_collect_data.ipynb   
   - 02_eda.ipynb   
   - 03_cleaning_feature_engineering.ipynb
   - 04_model_submissions.ipynb  
   - 05_model_comments.ipynb 
   - 06_generate_outputs.ipynb
- data
   - conspire_pull_comments.csv
   - conspire_pull_subissions.csv
   - science_pull_comments.csv
   - science_pull_submissions.csv
   - merged_comments.csv
   - merged_submissions.csv
- output
   - comm_coeff_predictors.png
   - sub_coeff_predictors.png
   - conspire_sub_word_freq.png
   - conspire_coms_word_freq.png
   - science_coms_word_freq.png
   - science_sub_word_freq.png
   - roc_auc_sub_gs1.png
   - roc_auc_com_gs2
- presentation
   - subreddit_classification_20200423.pdf

## Data Summary/Dictionary:

### Comments Dictionary:
|Feature|Type|Description|
|---|---|---|
|created_utc|int64|UTC date/time of Comment creation|
|subreddit|object|Name of origin subreddit thread, r/science or r/conspiracytheories|
|body|object|Text of thread Comment|

### Submission Titles Dictionary:
|Feature|Type|Description|
|---|---|---|
|created_utc|int64|UTC date/time of Submission creation|
|subreddit|object|Name of origin subreddit thread, r/science or r/conspiracytheories|
|selftext|object|Unformatted text which includes the raw markup characters are escaped. Empty if not present.|
|title|object|Title of Submission|

## Recommendations for Further Research:
Before using any of this data for user categorization or classification, higher model accuracy, a deep understanding of inherent Type I and Type II error, and serious ethical considerations are required. Generating confusion matrices and evaluating measures of model sensitivity, specificity, and F1 scores should be considered. 

Additionally, the data was pulled by volume; ~24,000 submission titles and ~36,600 comments. This pull did not account for temporal abnormalities, evidenced by the prevalence of words in both frequency and predictive strength related to current issues (see slides for more details). Further research should include a random sampling of Submission Titles and Comments the over past two years to account for recency bias in the predictive strength of words found in Submission Titles and Comments.


