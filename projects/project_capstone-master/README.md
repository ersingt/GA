# Geodemographic Segmentation of DC

## Problem Statement:
What areas of DC are similar to each other across social, economic, housing, and demographic characteristics? 
In other words, where and to what extent is DC similar and dissimilar across a host of socio-demographic variables? 
How can we measure groups or clusters of likeness across those variables?

## Executive Summary:
DC is rarely socio-demographically or economicaly explored at a hyper-local level. Some commercial products exist, but they tend to generalize the district using zip codes or larger units of analysis. Commercial models also tend to be proprietary black boxes. We don’t know how they’re defining their clusters. This analysis aims to build a model for DC that is more granular than zip codes and more transparent than proprietary algorithms.

#### Methods:
Geodemographic segmentation takes a host of inpiut variables and clusters them using standard statistical practices. It then maps those clusters back into space on an actual map.

Contemporary analysis of DC socio-demographic characteristics typically observe only one or two variables at a time--maps of median income vs X demographic variable, maps displaying the ethnic segregation of DC, etc. Lately, we see maps of poverty vs. COVID and ethnicity vs COVID. Such analysis can still be elucidating or useful, but with only bivariate comparisons, we are left to infer the deeper sociodemographic nuances of our own neighborhoods. When it comes to policy, beliefs generated from anecdotal evidence often lead to systems-level bias and injustice. For example, some commentary refers to Anacostia in tones that are, at best, sweeping generalizations of geography and, at worst, racist. We see the same thing in NE, Columbia Heights, and other neighborhoods. When it comes to policy and social good, beliefs and generalizations generated from anecdotal evidence tend to lead to systems-level bias and injustice. This is particularly salient, given the times. 

For the clustering algorithm, this analysis uses a Gaussian Mixture Model (GMM). This is an unsupervised machine learning algorithm falling in the family of "fuzzy or "soft" clustering algorithms. This means they allow outliers to be captured as a cluster, and they are particularly good at representing subpopulations within an overall population.

A K-means clustering model was compared with GMM. Each model was run 100 times per cluster size (2-30), resulting in 2800 models. The optimal number of clusters was six.

#### Data:
This analysis gathered the social, economic, housing, and demographic characteristics from the American COmmunity Survey Data Profiles (https://www.census.gov/acs/www/data/data-tables-and-tools/data-profiles/). The most recent data avaiable are from 2018, and varaible selection accounted for margins of error--those census tracts with a margin of error greater than 5% were dropped. This is outlined in further detail in the feature engineering section of the project.

This analysis collected 26 initial variables of interest, and after standard exploratory data analysis dropped the most highly-correlated variables, resulting in 12 variables for modeling. These are listed in detail in the data dictionary.

From 179 DC Census tracts, I dropped two with low populations and little data. These tracts were the National Mall and Georgetown University.

#### Results:
This analysis mapped the mean z-scores of each variable within each cluster to a radar plot (sometimes called a spider plot). These show us relative average values that define each cluster. These clusters were then mapped back to the actual census tracts, shown below, and available for further investigation in the below Tableau Dashboard.

-[Click Here to View Tableau Dashboard](https://public.tableau.com/profile/eric.schultz3116#!/vizhome/DCGeodemographicSegmentation/Dashboard)

#### Cluster Definition Results (See slides for further information):
 Radar/Spider Plots of Clusters:
 <image src = "images/radar_results.png" width = "600">
 Mapping of Clusters:
 <image src = "images/mapped_results.png" width = "600">

#### Conclusions, Recommendations, and Next Steps:
This project set oput hoping to understand where and to what extent DC is similar and dissimilar across socio-demographic characteristics. The model succeeded in that purpose, but it is somewhat surprising to see how empirically obvious social disparity is in our city. In an ideal world, we might expect a sort of tapestry in which segmented clusters were randomly distributed around the city. That is not what we observe. This analysis offers a fairly bleak reality of our city, and it is our responsibility to investigate and understand those nuances further. Below are conclusions from this analysis, as well as some ways to undertake further investigation:

1. At the census-tract level, DC is geographically segregated. This analysis offers a fairly bleak reality of DC. 
2. The spatial outliers are worth further exploration.
3. Consider running dimensionality reduction on a broader range of variables.
4. Consider Hierarchical Clustering techniques.
5. Consider using a smaller unit of analysis, such as 2020 Census Blocks (these will be available late 2021).



