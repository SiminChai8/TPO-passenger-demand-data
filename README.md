This repository contains the data of the instances used in the computational experiments of the paper *Train Platoon Optimization for Coordinating Feeder and Collector Lines in Urban Rail Networks*.
It contains input parameters and passenger demand data.

## 1. `instances/` JSON Input Paramters

This folder contains **10 JSON instance files**:

- File names: &nbsp; `instance_1.json  …  instance_10.json`

Each JSON file stores the complete model input parameters, including sets, capacities, headways, and other operational parameters.

## 2. `metro demand.csv` : Metro Passenger Arrival Data

The file `metro demand.csv` contains the passenger arrival numbers at each metro station at a resolution of one minute between 07:00 and 09:00.

Each row corresponds to a pair *(station, time)*.
Element `q[s,t]` denotes the number of arriving passengers at station *s* during minute *t*.
The matrix is flattened along the time axis in row-major order:

```
station_1, t=1, q[1,1]
station_1, t=2, q[1,2]
...
station_2, t=1, q[2,1]
station_2, t=2, q[2,2]
...
```

### Example CSV Format

```csv
Anheqiao Bei, 7:00, 97
Anheqiao Bei, 7:01, 115
...
Beigongmen, 7:00, 30
Beigongmen, 7:01, 31
...
```



## 3. `feeder demand.csv` : Transfer Passenger Demand Data

The file `feeder demand.csv` contains the demand of transfer passengers coming from ten feeder trains at two transfer stations.
The dataset covers two transfer stations, Beijing South Railway Station and Xizhimen Station, across two directions (Upstream and Downstream) and ten feeder train indices.

Each row corresponds to an entry *(station, direction, feeder_train_index)*.
Element `p[l,s]` denotes the number of transfer passengers from feeder train *l* at station *s*.
The structure of the file is as follows:

```
station_1, direction=Upstream, feeder_train_index=1, p[1,1]
station_1, direction=Upstream, feeder_train_index=2, p[2,1]
...
station_2, direction=Downstream, feeder_train_index=10, p[10,2]
...
```
### Example CSV Format
```csv
Beijing South Railway Station, Upstream, 1, 840
Beijing South Railway Station, Upstream, 2, 875
...
Xizhimen Station, Downstream, 1, 740
Xizhimen Station, Downstream, 2, 775
...
```





