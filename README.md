# Discovering communities in global flight route graph

## Abstract
Global flight route information, which naturally reveals the connections and communication among countries and regions, has long been of great importance to political and economic area. 
Instead of possessing regularity, the derived flight route graph has been discovered to have various parts within which flights are denser than the others. 
This inconsistency motivates the attempt to figure out communities in the aforementioned graph.
In this project, we exploit the network analysis and machine learning techniques to discover communities in the flight routes graph in weakly supervised and unsupervised fashion.

## Prerequisites
The following python modules are required to re-produce the results obtained.

* [NumPy 1.15.0](http://www.numpy.org) `pip3 install --user numpy==1.15.0`
* [Matplotlib 3.0.3](https://matplotlib.org) `pip3 install --user matplotlib==3.0.3`
* [Networkx 2.3](https://networkx.github.io)    `pip install --user networkx==2.3`
* [Pandas 0.23.0](https://pandas.pydata.org)    `pip install --user pandas==0.23.0`
* [Geopy 1.20.0](https://geopy.readthedocs.io/en/stable/) `pip install --user geopy==1.20.0`
* [scipy 1.1.0](https://www.scipy.org/) `pip install --user scipy==1.1.0`
* [folium 0.8.0](https://python-visualization.github.io/folium/) `pip install --user folium==0.8.0`
* [scikit-learn 0.19.1](https://scikit-learn.org/) `pip3 install -user scikit-learn==0.19.1`
* [seaborn 0.8.1](https://seaborn.pydata.org/) `pip install -user seaborn==0.8.1`

## Datasets
The dataset used in the project consists of an airline database and a flight routes database from [https://openflights.org/data.html#route](https://openflights.org/data.html#route).

The airline database with 3188 entries provides the following essential information about airline:

|Attribute| Airport_id | Name | City | Country | IATA | ICAO | Latitude | Longitude | Timezone | Tzdatabase |
|---------| ---------- | ---- | ---- | ------- | ---- | ---- | -------- | --------- | -------- | ---------- | 
|Example  | 1665       | Geneva Cointrin International Airport | Geneva | Switzerland | GVA	| LSGG | 46.238098 | 6.10895 | 1 | Europe/Paris |

The routes database with 66771 entries provides the following essential information about routes:

| Attribute | Airline | Airline_id | Source_airport | Source_airport_id | Destination_airport | Destination_airport_id | Stops | Equipment |
| --------- | ------- | ---------- | -------------- | ----------------- | ------------------- | ---------------------- | ----- | --------- |
| Example   | AB      | 214        | GVA            | 1665              | MAD                 | 1229                   | 0     | 320 319   |


## Project Sturcture

`preprocessing.ipynb` contains the code for preprocessing. We remove the flights which contain unrecorded airports or do not specify source/destination airports. Based on the preprocessed data, we build the weighted and non-weighted adjacency matrices and the graph.

`explore_data.ipynb` contains the code for data exploration.  We explore the graph by computing degree distribution and centrality metrics. We also visualize all airports on the global map with continent borders.

`exploit_data.ipynb` contains the code for data exploitation. We implement spectral clustering algorithm and K-means algorithm on both weighted and non-weighted adjacency matrices. In order to discover communities without initialization, we also implement greedy modularity maximization and label propagation methods to detect communities.

`data` folder contains all raw data, preprocessed data and some other additional data used for visualization.

`map` folder contains all html files of the visualization results.

`doc` folder contains our report for this project.

## Visualizations
The visualizations of our results are availbale [here](https://wanhaozhou.github.io/docs/display.html).
## Authors
* **CAI Fengyu** [email](mailto:fengyu.cai@epfl.ch)
* **CHEN Liangwei** [email](mailto:liangwei.chen@epfl.ch)
* **LI Junze** [email](mailto:junze.li@epfl.ch)
* **ZHOU Wanhao** [email](mailto:wanhao.zhou@epfl.ch)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
