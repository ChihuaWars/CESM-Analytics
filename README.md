# CESM Analytics

This project creates a novel database and calculates usage metrics for CESM2, a climate model developed by the National Center for Atmospheric Research (NCAR). This work began under a summer internship through the Summer Internships in Parallel Computing Science (SIParCS) in 2019 by me, Lolita Mannik. This repo was created as a place to share, manage, and continue the project as a thesis required to complete my master's degree in data science from Regis University in Denver. 

I’d like to specifically showcase database skills, data cleaning, and statistical and machine learning methods. 

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.  


### Built With

* [Python 3.7 version from Anaconda](https://www.anaconda.com/distribution/) - Programming language
* [Jupyter Notebook](https://jupyter.org/install) - IDE for Python
* This project was run on Windows 10.

## Directory of Repo Files
* Practicum Proposal. A complete description of the background for the project and week-by-week outline of steps.
* Data Dictionary. Dictionary of features parsed from CESM timing files.
* sample_timing_file. Look at an original .txt file before it's been parsed.
* cmip_09_10_2019.json. JSON file containing 6088 timing files from CMIP6 experiments: July 20, 2018 through September 20, 2019.
* CESM JSON to SQL + Outlier Detection Thesis1.ipynb. Jupyter Notebook (Python) that takes the cmip_09_10_2019.json file, converts to a Pandas dataframe, sets datatypes, removes outliers, and saves the results as df_NoOutlier-Thesis.csv.
* df-NoOutlier-Thesis.csv. Data file used in CESM Upgrade Analysis Thesis 1.ipynb and ATM Component Analysis Thesis 1.ipynb.
* CESM Upgrade Analysis Thesis 1.ipynb. Using df_NoOutlier-Thesis.csv created from the CESM JSON to SQL + Outlier Detection Thesis1 notebook, this Jupyter Notebook establishes basic metrics for CMIP6 experiments on CESM2 and analyzes the performance of cases and ensembles before and after a system upgrade on the Cheyenne supercomputer.
* ATM Component Analysis Thesis 1.ipynb. Using df_NoOutlier-Thesis.csv, this Jupyter Notebook analyzes the performance of the atmospheric component before and after a system upgrade on the Cheyenne supercomputer.
* Lolita Mannik Practicum I.pptx. Power point presentation for part I of the thesis probject (EDA and upgrade analysis). 




Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running Jupyter Notebooks

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```




## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Lolita Mannik** - *Data Scientist* - [ChihuaWars](https://github.com/chihuawars)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc
