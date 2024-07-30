# Seismic Array in Wittewierum, Netherlands – Python Exercise

## Introduction

This project focuses on analyzing seismic data collected from a network of sensors in Wittewierum, Netherlands. The dataset provides valuable insights into the region's microseismicity, critical for understanding natural and induced seismic activities. These sensors, installed at a shallow depth of approximately 1 meter, were primarily designed to monitor microseismic events. The shallow installation allows for high-resolution data collection of local seismic activity, although it also makes the sensors susceptible to recording surface-level activities.

## LightningChart Python

### Overview of LightningChart Python Usability for this Specific Project

LightningChart Python is an excellent tool for visualizing large-scale seismic data due to its high performance and customizable features. This project enabled the creation of detailed and interactive waveform graphs crucial for analyzing seismic events over time.

## Setting Up Python Environment

### Installing Python and Necessary Libraries

Ensure you have [Python ](https://www.python.org/downloads/)installed.

### Overview of Libraries Used

- **[NumPy](https://numpy.org/):** For numerical operations
- **[Pandas](https://pandas.pydata.org/):** For data manipulation and analysis
- **[ObsPy](https://docs.obspy.org/):** For accessing and processing seismic data
- **[LightningChart Python](https://lightningchart.com/python-charts/):** For advanced high performance data visualization

### Setting Up Your Development Environment

1. Install Python.
2. Use `pip` to install the required libraries:
   ```shell
   pip install numpy pandas obspy lightningchart
   ```
3. Set up your development environment by creating a new project directory and installing the required libraries. Ensure that LightningChart Python is properly licensed and configured.

## Loading and Processing Data

### Overview of the Data

The seismic data is collected from sensors installed at a depth of 1 meter in Wittewierum, Netherlands. These high-gain sensors were operational from July 12, 2016, to August 29, 2016, with some outages. The dataset includes three components (HHE, HHN, and HHZ) from each station, recording continuous seismic activity.

### How to Load Data Files

Using ObsPy, you can access and download the seismic data:

```python
from obspy.clients.fdsn import Client
from obspy import UTCDateTime

client = Client("GFZ")

starttime = UTCDateTime("2016-07-12T00:00:00")
endtime = UTCDateTime("2016-07-12T23:59:59")
station = "WAR1"

st = client.get_waveforms(network="1C", station=station, location="--", channel="HHZ", starttime=starttime, endtime=endtime)
```

### Basic Data Processing Techniques

Process the waveform data to extract meaningful information, such as calculating seismic event magnitudes and filtering noise.

### Handling and Preprocessing Data

Preprocess the data to handle missing values, normalize the data, and apply necessary filters to enhance data quality. Use Pandas for efficient data manipulation and analysis.

## Visualizing Data with LightningChart

### Creating Waveform Graphs

Here's an example of a visualization from the Jupyter Notebook file `seismicAnalysis_Netherlands.ipynb` where we generate waveform graphs to visualize seismic activity over time. This involves plotting raw waveform data for each sensor component.

![1722335508097](image/README/1722335508097.png)

### Customizing Visualizations

Tailor the visualizations to highlight specific aspects of the data, such as seismic event magnitudes and trigger points.

### Streaming and Updating Data in Real-Time

Although not implemented in this project, LightningChart Python allows for real-time data streaming and updating, which is beneficial for continuous monitoring applications.

### Displaying Real-Time Ground Shaking Activity Data

Utilize LightningChart to display real-time seismic activity data, providing immediate insights into ongoing seismic events.

### Displacement and Acceleration Visualizations

In addition to waveform and velocity visualizations, displacement and acceleration charts were created. These visualizations typically show lower values due to the sensors' focus on detecting microseismic events. Microseismicity involves small-scale seismic events with minor ground movements, leading to lower values in these physical units.

### Dashboard Visualization

This visualization is also from the Jupyter Notebook file `seismicAnalysis_Netherlands.ipynb` where we combined different kinds of data from WAR1 sensor into one dashboard

![1722330363886](image/README/1722330363886.png)

## Conclusion

### Recap of the Python Data Processing Workflow

This project demonstrated the process of accessing, processing, and visualizing seismic data using Python and LightningChart. The workflow included data acquisition from ObsPy, preprocessing, and creating detailed visualizations.

### Benefits of Using LightningChart Python

LightningChart Python proved to be an effective tool for handling large-scale seismic data visualizations, offering high performance and customization options crucial for seismic data analysis.

### Additional Context

The sensors used in this project were installed at a depth of 1 meter and designed to monitor microseismic events. While beneficial for high-resolution data
collection, this shallow installation also made the sensors prone to picking up surface activities. The Netherlands experiences both natural and induced seismic activities, with natural tectonic movements in the southeast and induced seismicity due to gas extraction in the northeast.

### Challenges Encountered

Accessing the complete dataset was time-consuming, and data retrieval through ObsPy proved inefficient. Due to time constraints, smaller chunks of data were used to manage the analysis effectively.

### Note to Readers

Please refer to the accompanying Jupyter Notebook file for detailed code examples and visualizations. The notebook provides comprehensive insights into this project's data processing and visualization steps.  `seismicAnalysis_Netherlands.ipynb`

### Map View

![1722331299548](image/README/1722331299548.png)

### Satellite View

![1722331337555](image/README/1722331337555.png)

These images help visualize the geographic distribution of the sensors.

## Sources

* [GEOFON](https://geofon.gfz-potsdam.de/doi/network/1C/2016)
* [EGU - European Geoscienses Union](https://nhess.copernicus.org/articles/22/41/2022/#Ch1.F2)
* Google Maps
