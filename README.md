# Data for "Inferring Stop-Locations from WiFi"

This is a short documentation for the shared data-set following the paper "Inferring Stop-Locations from WiFi".

The data-set consists of the following files:
 - This readme-file: README.md
 - A JSON data file: plos_one_data.json

The JSON data file contains a Python-dictionary named **all_data** which in turn contains two Python lists **stops** and **wifi**.

The **wifi** list contains dictionaries each corresponding to a single WiFi-observation with attributes *timestamp* and *bssid_anonymised*, for example: ```{'timestamp': 1410270311, 'bssid_anonymised': 0}```. The *timestamp* attributed is the time of observation of the access point. The *bssid_anonymised* attribute is an anonymised version of the BSSID of the observed router.

The **stops** list contains dictionaries each corresponding to a ground truth stop. The attributes are *label* and *timestamp*, for example ```{'label': 'stand', 'timestamp': 1410271200}```. The *label*-attribute can be one of the following:
* **stand**: Stationary at some loction
* **bike**: Biking
* **bus**: In the bus
* **car**: In a car
* **run**: Running
* **train**: In a train
* **walk**: Walking
* **walk_shop**: Walking (shopping)
* **start_data**: Data gathering is starting
* **end_data**: Data gathering is ending

Note that data gathering is starting and ending multiple times.

The data can be loaded into Python with the following code:

```python
import json
data_file = open("plos_one_data.json", "rb")
all_data = json.load(data_file)
```