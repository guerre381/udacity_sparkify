# Disaster Response Pipeline Project
<!-- PROJECT SHIELDS -->

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]


<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/guerre381/udacity_sparkify">
    <img src="data/logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Sparkify data analysis</h3>

  <p align="center">
    UDACITY online training in Data Science  
    <br />
    <a href="https://github.com/guerre381/udacity_sparkify">View Demo</a>
    ·
    <a href="https://github.com/guerre381/udacity_sparkify/issues">Report Bug</a>
    ·
    <a href="https://github.com/guerre381/udacity_sparkify/issues">Request Feature</a>
  </p>
</p>


<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">Table of Contents</h2></summary>
  <ol>
    <li><a href="#about-the-project">About The Project</a></li>
    <li><a href="#built-with">Built With</a></li>
    <li><a href="#ml-pipeline">Ml-Pipeline</a></li>
    <li><a href="#content">Content</a></li>
    <li><a href="#getting-started">Getting Started</a></li>
    <li><a href="#installation">Installation</a></li>
    <li><a href="#contributing">Contributing</a></li>
     <li><a href="#acknowledgements">Acknowledgements</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->
## About The Project
 
Sparkify is a fake digital music service similar to Spotify or Pandora. Many users stream their favorite songs everyday.
They either use the free tier that plays advertisement between the songs, 
or the premium  subscription model where they are not getting annoyed against a monthly flat rate. 

The users can cancel at any time. 

Their interaction with the service generates data containing the key insights to predict which users are at risk to churn.
Identifying them before they leave could help taking certain measures (discounts) to keep them using the service.

Our problem is clearly to identify users about to churn their subscription. 

This project follows a simple process apparent to CRISP-DM. It is articulated in 6 chapters:
* Spark set up
* Data cleaning
* Exploration and Data Analysis
* Feature engineering
* Modeling
* Summary


<!-- Built with -->
## Built With

The project was partially hosted on IBM cloud. 
It stored Saprkify raw data and provided distributed computing resources with a default environment composed of
[Spark 3.0 & Python 3.7](https://www.ibm.com/support/producthub/icpdata/docs/content/SSQNUZ_latest/wsj/analyze-data/spark-envs.html).

Python cloud environment:
* [pandas 1.0.5](https://pandas.pydata.org/)
* [wordcloud 1.8.1](http://amueller.github.io/word_cloud/)
* [pyspark 3.0.1](https://spark.apache.org/docs/latest/api/python/)


Although very small, the rest of the project was continued locally on [Python 3.8](https://www.python.org/downloads/release/python-380/) because some libraries were not available on the cloud. 


Python local environment:
* [pandas 1.2.1](https://pandas.pydata.org/)
* [geopandas 0.8.2](https://geopandas.org/)
* [geoplot 0.4.1](https://residentmario.github.io/geoplot/)

<!-- ML-Pipeline -->
## ML-Pipeline

The end goal of this project was to build a model able to identify users about to churn their subscription based on their interaction with the platform.

Classification problem:
* Inputs:   text , numerical, and time data, 
* outputs:  2 categories (1/0)

The ML pipeline is constructed with the spark´s machine learning library. It was built in 2 parts to allow 
the trial of different estimators until the best one got selected after comparison of metrics.

Final pipeline:
1. Featurization pipeline composed of String indexers, One-Hot encoder, Count vectorizer,  MinMax scaler, and Vector assembler.
2. Estimator: Gradient boosted trees

Evaluation:

| Attempt | Accuracy | Precision | Recall | F-score | AUC |
| :---: | :---: | :---: | :---: | :---: | :---: | 
| Seconds | 0.93 | 0.93 | 0.71  | 0.81 | 0.97 | 

<!-- Content -->
## Content
The main study holds on a single notebook. It is meant to run on distributed machines via IBM cloud. 
The raw data are available on UDACITY, they ae not part of this repository. 

The data folder is a storage for the outcomes of the first notebook. 
It holds information dedicated to the second notebook. This one is meant to run locally for 
visualizing geo data.

    ├── data
    │   ├── logo.png                        # read me logo
    │   ├── users_states_distribution.csv   # outcome from sparkify_distributed.ipynb
    │   └── states.json                     # 2D map of USA
    │
    ├── map_plot_local.ipynb                # visualization notebook
    ├── main_distributed.ipynb              # main notebook to be run on cloud
    ├── requirements.txt                    # python environment requirements
    └── README.md                           # current file

<!-- GETTING STARTED -->
## Getting Started

To get a local copy up and running follow these simple steps:
1. create a virtual environment for Python 3.7 or higher.
2. clone udacity_sparkify repository
3. install all required libraries from requirements.txt
4. follow instructions

### Instructions:

main_distributed.ipynb:

1. Open a Watson session on IBM cloud.
2. Start new project
3. Upload Sparkify raw data and main notebook on the cloud.
4. Attach the correct environment to notebook (Spark 3.0 and Python 3.7)
5. Change credentials data in chapter 1 (Spark Set Up).
5. Run notebook

map_plot_local.ipynb:

1. Start jupyter notebook locally
2. Run notebook


<!-- INSTALLATION -->
## Installation

Clone the udacity_project_2 repository
   ```sh
   git clone https://github.com/guerre381/udacity_sparkify.git
   ```

<!-- CONTRIBUTING -->
## Contributing

If you want to continue the analysis and get more from the data, your contribution would be appreciated.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
* [Udacity](https://review.udacity.com/#!/rubrics/2345/view)
* [IBM cloud](https://cloud.ibm.com/login)
* [SHIHAO RAN blog](https://shihaojran.com/distributed-machine-learning-using-pyspark/)

<!-- CONTACT -->
## Contact

Romain Guerre - guerre_romain38@hotmail.com

Project Link: [https://github.com/guerre381/udacity_sparkify](https://github.com/guerre381/udacity_sparkify)


[contributors-shield]: https://img.shields.io/github/contributors/guerre381/udacity_project_2.svg?style=for-the-badge
[contributors-url]: https://github.com/guerre381/udacity_sparkify/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/guerre381/udacity_project_2.svg?style=for-the-badge
[forks-url]: https://github.com/guerre381/udacity_sparkify/network/members
[stars-shield]: https://img.shields.io/github/stars/guerre381/udacity_project_2.svg?style=for-the-badge
[stars-url]: https://github.com/guerre381/udacity_sparkify/stargazers
[issues-shield]: https://img.shields.io/github/issues/guerre381/udacity_project_2.svg?style=for-the-badge
[issues-url]: https://github.com/guerre381/udacity_sparkify/issues
[license-shield]: https://img.shields.io/github/license/guerre381/udacity_project_2.svg?style=for-the-badge
[license-url]: https://github.com/guerre381/udacity_sparkify/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/romain-guerre-14b4a891/


