# PowerWeather Dataset: Weather Prediction Using Graphical Learning Models and Household Energy Data

This project was conducted as part of the course CS274B Learning in Graphical Models at the University of California, Irvine, Spring 2024, taught by Prof. Erik Sudderth.

## Overview

This project aims to develop a predictive model for weather conditions using graphical learning algorithms applied to the PowerWeather Dataset. By correlating detailed records of household energy consumption with historical weather data, we leverage this dataset to infer and predict weather patterns.

## Dataset

The dataset used in this project includes:

1. **PECAN Street Dataset**: Provides power consumption recordings for each household at 15-minute intervals, covering three states: California (CA), Texas (TX), and New York (NY). It includes a detailed breakdown of power consumption by appliance for each household.
2. **US City Dataset from Simplemaps**: Provides precise latitude and longitude locations for all cities in the US.
3. **Open-Meteo Weather API**: Historical weather data including temperature, humidity, rain, and cloud cover.

<!--- The combined PowerWeather Dataset is available [here](link-to-dataset). -->

### Files

The repository contains the following files:

- Discretized versions:
  - Train sets
    - `/PECAN-Weather-train/CA_discretized.csv`
    - `/PECAN-Weather-train/TX_discretized.csv`
    - `/PECAN-Weather-train/NY_discretized.csv`
  - Test sets
    - `/PECAN-Weather-test/CA_discretized.csv`
    - `/PECAN-Weather-test/TX_discretized.csv`
    - `/PECAN-Weather-test/NY_discretized.csv`
- Discretized versions:
  - Train sets
    - `/PECAN-Weather-test/TX.csv`
    - `/PECAN-Weather-test/CA.csv`
    - `/PECAN-Weather-test/NY.csv`
  - Test sets
    - `/PECAN-Weather-train/TX.csv`
    - `/PECAN-Weather-train/CA.csv`
    - `/PECAN-Weather-train/NY.csv`

### Columns

Each CSV file in the dataset includes the following columns:

1. **Household Energy Consumption Columns**:
   - `air1`
   - `airwindowunit1`
   - `aquarium1`
   - `bathroom1`
   - `bedroom1`
   - `battery1`
   - `car1`
   - `circpump1`
   - `clotheswasher1`
   - `clotheswasher_dryg1`
   - `diningroom1`
   - `dishwasher1`
   - `disposal1`
   - `drye1`
   - `dryg1`
   - `freezer1`
   - `furnace1`
   - `garage1`
   - `grid`
   - `heater1`
   - `housefan1`
   - `icemaker1`
   - `jacuzzi1`
   - `kitchen1`
   - `kitchenapp1`
   - `lights_plugs1`
   - `livingroom1`
   - `microwave1`
   - `office1`
   - `outsidelights_plugs1`
   - `oven1`
   - `pool1`
   - `poollight1`
   - `poolpump1`
   - `pump1`
   - `range1`
   - `refrigerator1`
   - `security1`
   - `sewerpump1`
   - `shed1`
   - `solar`
   - `sprinkler1`
   - `sumppump1`
   - `utilityroom1`
   - `venthood1`
   - `waterheater1`
   - `wellpump1`
   - `winecooler1`

2. **Weather Columns**:
   - `weather_temperature`
   - `weather_humidity`
   - `weather_rain`
   - `weather_snowfall`
   - `weather_cloud_cover`

## Data Collection and Preprocessing

1. **Data Retrieval**:
   - Power consumption data from PECAN Street dataset.
   - City locations from Simplemaps.
   - Historical weather data from Open-Meteo API.

2. **Data Merging**:
   - Merged power consumption data with weather measurement data.
   - Adjusted the 15-minute power consumption recordings to match the hourly weather data.

3. **Data Discretization**:
   - To support the graphical models such as Bayesian Network models, we discretized continuous values into categorical bins.
   - We created 4 bins based on the minimum value, the 1st to 3rd quartile values, and the maximum value for each column.
   - The discretized values are represented as follows:
     - 0: $\text{min} \leq v < \text{q1}$
     - 1: $\text{q1} \leq v < \text{q2}$
     - 2: $\text{q2} \leq v < \text{q3}$
     - 3: $\text{q3} \leq v \leq \text{max}$

## Future Impact

Through our benchmarking with this dataset, we found a positive correlation between energy consumption and weather measurements. With more detailed datasets and specialized graph neural networks, there is potential for developing cost-efficient alternative solutions for weather forecasting systems, especially in regions with power grid infrastructure but lacking traditional weather observation systems.

## Contributors

- Sanggeon Yun (sanggeoy@uci.edu)
- Ryozo Masukawa (rmasukawa@uci.edu)

<!--
## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
-->

## Acknowledgements

We would like to thank the PECAN Street Project for providing the energy consumption data and the developers of the Simplemaps US City Dataset and Open-Meteo API for their valuable data sources.

---

Feel free to open issues or pull requests if you have any questions or contributions!
