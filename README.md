# Wi-Fi Device Counting Algorithm

This repository contains the code developed for estimating the number of distinct devices that generated Wi-Fi probe-request bursts.

The code takes as input a JSON file containing probe-request bursts and produces two CSV files as output: one containing the device-counting results and one containing the execution time.

The file `json_file_example` can be used as a reference for the required input format.

## Available versions

Two versions of the algorithm are provided:

* `Device_counter_ready_to_use`: the standard version of the algorithm. It achieves a median percentage error of approximately 17% on the tested datasets.
* `Device_counter_ready_to_use_weighted_version`: a weighted version of the algorithm that assigns different weights to the features used to compare bursts. This version is expected to provide better results, but it is still under evaluation.

## Configuration

Before running the code, the following variables must be configured:

* `PATH_DATASET_1`: path to the JSON file containing the dataset to be analyzed.
* `PATH_RESULTS_CSV`: path where the CSV file containing the results will be saved.
* `PATH_EXEC_TIME_CSV`: path where the CSV file containing the execution time will be saved.

For example:

```python
PATH_DATASET_1 = "path/to/dataset.json"
PATH_RESULTS_CSV = "path/to/results.csv"
PATH_EXEC_TIME_CSV = "path/to/execution_time.csv"
```

If the specified output files do not exist, they will be created automatically.

## Input format

The input JSON file must follow the structure shown in `json_file_example`.

The JSON file contains the probe-request bursts and the information required by the algorithm to estimate the number of distinct devices that generated them.

