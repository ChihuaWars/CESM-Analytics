# CESM Analytics

This project creates a novel database and calculates usage metrics for CESM2, a climate model developed by the National Center for Atmospheric Research (NCAR). This work began under a summer internship through the Summer Internships in Parallel Computing Science (SIParCS) in 2019 by me, Lolita Mannik. This repo was created as a place to share, manage, and continue the project as a thesis required to complete my master's degree in data science from Regis University in Denver. 

I’d like to specifically demonstrate database skills, data cleaning, and statistical and machine learning methods. 

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.  

### Built With

* [Python 3.7 version from Anaconda](https://www.anaconda.com/distribution/) - Programming language
* [Jupyter Notebook](https://jupyter.org/install) - IDE for Python
* This project was run on Windows 10.

## Prerequisites
Once Python and Jupyter Notebook are installed, the following Python packages are required:

* sqlalchemy 
* json
* pandas
* datetime
* re
* collections


* numpy 
* scipy.stats
* statsmodels.api
* sklearn


* matplotlib.pyplot 
* seaborn 
* pylab
* plotly.express


## File Descriptions
**Practicum Proposal** - A complete description of the background for the project and week-by-week outline of steps.

**Data Dictionary** - Dictionary of features parsed from CESM timing files.

**sample_timing_file** - Look at an original .txt file before it's been parsed.

**cmip_09_10_2019.json** - JSON file containing 6088 timing files from CMIP6 experiments: July 20, 2018 through September 20, 2019.

**CESM JSON to SQL + Outlier Detection Thesis1.ipynb** - Jupyter Notebook (Python) that takes the cmip_09_10_2019.json file, converts to a Pandas dataframe, sets datatypes, removes outliers, and saves the results as df_NoOutlier-Thesis.csv.

**df-NoOutlier-Thesis.csv** - Data file used in CESM Upgrade Analysis Thesis 1.ipynb and ATM Component Analysis Thesis 1.ipynb.

**CESM Upgrade Analysis Thesis 1.ipynb** - Using df_NoOutlier-Thesis.csv created from the CESM JSON to SQL + Outlier Detection Thesis1 notebook, this Jupyter Notebook establishes basic metrics for CMIP6 experiments on CESM2 and analyzes the performance (model cost) of cases and ensembles before and after a system upgrade on the Cheyenne supercomputer. Among overall model cost, normalized model cost, or model cost by individual case or ensemble, none of the data was normal according to KS and Shapiro_Wilk tests. Performance degradation (5 to 28%) is correlated with the highest count of atmospheric processors (3,456 processors) for cases that span the upgrade, however, performance improvement (11 to 20%) is found in cases with 1,800 atmospheric processors. Testing for statistical significance (Kruskal-Wallis) on before/after upgrade performance was also calculated on cases and ensembles that span the upgrade. Writes out df_CaseSpan.csv and df_BaseSpan.csv.

**ATM Component Analysis Thesis 1.ipynb** - Using df_NoOutlier-Thesis.csv, this Jupyter Notebook analyzes the performance (model cost) of the atmospheric component before and after a system upgrade on the Cheyenne supercomputer. Groups of matching atmospheric component, atmospheric processor count and oceanic processor count are created and analyzed before and after the upgrade. The same testing for normality, performance changes, and statistical significance is performed as in the previous notebook. Again, performance degradation (2 to 19%) for groups with 3,456 atmospheric processors is found. In this analysis, performance degradation (4%) also occured in groups with 1,800 atmospheric processors, although performance improvement (5%) was found in groups with 1080 atmospheric processors.

**df_CaseSpan.csv** - Dataset with run information for cases that spanned the upgrade

**df_BaseSpan.csv** - Dataset with run information for ensembles that spanned the upgrade

**CESM Upgrade Analysis Machine Learning Thesis 2.ipynb** - This notebook builds upon CESM Upgrade Analysis Thesis 1.ipynb and seeks to find the factors that contribute to performance improvement or degradation. Here, I create a trinary performance indicator (improved, degraded, or stayed the same) for analysis with multinomial logistic regression and random forest using df_BaseSpan.csv and df_CaseSpan.csv, which were prepared by CESM Upgrade Analysis Thesis 1.ipynb.

**CESM Upgrade Results Report.xlsx** - Excel file listing the identifying features found in CESM Upgrade Analysis Machine Learning Thesis 2.ipynb

**df_Glade.csv** - 483,000 CESM timing files were capture and parsed from the Glade directory. This file contains data from 9 years and  are over two dozen machines. (Not available on GitHub. Please contact us for access to the database).

**CESM SQL and EDA Glade Data Thesis 2.ipynb** - CESM timing files were collected by scraping the Glade directory and converting to JSON. (My script (CESM JSON to SQL + Outlier Detection Thesis 1.ipynb) was used to convert the JSON to SQL and write the data out to df_Glade.csv.) This notebook reads df_Glade.csv (483,000 rows), cleans and prepares the data, and writes the data out to df_ML-Thesis2.csv, which is used for machine learning exercises in CESM Predictive Modeling Glade Data Thesis 2.ipynb. This notebook uses public data from 9/19/19.

**df_ML-Thesis2.csv** - Data written out from the preparation in CESM SQL and EDA Glade Data Thesis 2.ipynb. 314,961 rows. (Not available on GitHub. Please contact us for access to the database.)

**CESM Predictive Modeling Glade Data Thesis 2.ipynb** - I have prepared the data for modeling in CESM SQL and EDA Glade Data - Thesis 2.ipynb, and here I read in df_ML-Thesis2.csv (314,961 rows) to see if I can predict the run time of the model. The primary way to assess model performance is by looking at model cost (pe-hours/simulated year), which is calculated by taking the time it takes the model to run (overall run time in seconds (wall clock time)), multiplied by the number of processors used in the simulation (pes), divided by the number of simulated years. Since we know the number of processors and simulated years in the runs (because the scientists designate those), I will predict overall run time (seconds). This notebook uses public data from 9/19/19.

**Lolita Mannik Practicum I.pptx or .pdf** - Final presentation for submission of part I of the thesis project (EDA and upgrade analysis). 
**Lolita Mannik Practicum II.pptx or .pdf** - Final presentation for submission of part II of the thesis project (Machine learning on the upgrade analysis and large Glad dataset). I created two slightly different presentations - one for Regis University and one for NCAR. 

## Authors

* **Lolita Mannik** - *Data Scientist* - [ChihuaWars](https://github.com/chihuawars)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## Acknowledgments

* Thanks to Brian Dobbins and John Dennis, mentors at the National Center for Atmospheric Research
* Also thanks to Mike Busch,  Christy Pearson, and Nate George, professors at Regis University for advising on the project
