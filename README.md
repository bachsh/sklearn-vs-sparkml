# sklearn-vs-sparkml
Simple demo of a clustering pipeline in Python Scikit-learn vs. Apache SparkML.
In this demo you will find:
1. A machine learning (clustering) pipeline made using Python Scikit-learn (in the 1<sup>st</sup> notebook).
2. The same pipeline implemented using Scala + Apache SparkML (in the 2<sup>nd</sup> notebook).
3. The same pipeline, using the model trained using Scikit-learn, exported to PMML and then loaded to Apache Spark (export at the end of the 1<sup>st</sup> notebook, import+evaluation at the end of the 2<sup>nd</sup> notebook).

## Prerequisites
If you don't have Python installed it is recommended to use the [Anaconda Python Distribution](https://www.anaconda.com/download/).

There are two notebooks in this repo, the first in Python and the second in Scala.
1. For the first notebook you are going to need the following:
    1. Jupyter
    1. Python scientific stack (specifically scikit-learn and matplotlib).
    1. sklearn2pmml package.
1. For the second notebook you are going to need [jupyter-scala](https://github.com/jupyter-scala/jupyter-scala). Follow the instruction on the repo page to install.

# Data
We are presented with a dataset containing aggregated data of DNS activity from different IPs connected to a leading ISP. In this dataset there are IPs that belong to home networks and offices/organizations. The task is to try and differentiate between the two.
The dataset contains a list of IPs (they are scrambled for anonymity) along with general counts of their activity volumes throughout a single weekday. The day is split into 6 time windows, 4 hours each, and we have the number of DNS queries made by the IP (user). The first time window (index 0) starts at 6AM GMT.
We have the following fields in the dataset:
1. user_ip - the IP of the user (anonymized).
1. count_hour[0-5] - DNS query count in each of the 6 time windows.
1. domain_count - Total distinct domains queried in a single day.
1. nxdomain_count - Total number of DNS requests answered with NXDOMAIN (DNS equivalent of 404).

