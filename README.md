# Time Series Analysis with Trend and Seasonality Decomposition

This project demonstrates how to decompose a time series dataset of tourist numbers into **trend** and **seasonality** components using Python. The code follows a clear process for trend extraction using a moving average and calculates seasonal weights based on the differences from the trend. Finally, the original data, trend, and seasonal components are plotted for visual inspection.

## Table of Contents
- [Dataset](#dataset)
- [Dependencies](#dependencies)
- [Code Explanation](#code-explanation)
- [Usage](#usage)
- [Results](#results)
- [License](#license)

## Dataset

The dataset used in this project is assumed to be in CSV format and contains the following columns:
- **Date**: The time period for each record (e.g., years, months, or days).
- **TouristNumber**: The recorded number of tourists for that specific time period.

The file must be named `data.csv` and placed in the working directory.

## Dependencies

To run this code, make sure you have the following Python libraries installed:

- `pandas`
- `matplotlib`

You can install these using pip:

```bash
pip install pandas matplotlib
```

## Code Explanation

1. **Loading the Data**:
   - The dataset is loaded using `pandas.read_csv()`.
   - We extract two columns: the date and the corresponding number of tourists.

2. **Trend Calculation**:
   - A moving average method is used to calculate the trend component.
   - The window size `d` determines how smooth the trend will be.
   - If `d` is even, a weighted average is used to handle boundary points.
   - For odd values of `d`, a simple averaging method is used.

3. **Storing Trend Values**:
   - Trend values are stored in a dictionary, where the key represents the time period (t), and the value is the corresponding trend component.
   - The trend is printed in a tabular format along with the original tourist number values.

4. **Seasonality Calculation**:
   - The deviations from the trend are used to calculate seasonal weights.
   - The seasonal component is derived by averaging the seasonal weights and applying them to each time period.

5. **Plotting the Results**:
   - `matplotlib` is used to create a plot that shows the original data, the trend, and the seasonal component.
   - The components are displayed in different colors for clarity.

## Usage

1. Ensure your dataset is in CSV format (`data.csv`), with `Date` and `TouristNumber` columns.
2. Run the script in Python:

```bash
python time_series_analysis.py
```

The output will show:
- A table of the original tourist numbers, trend values, and seasonal components.
- A plot that visualizes the original data, trend, and seasonality.

## Results

- **Table**: The code prints a table showing the original values, the trend, and the seasonal component for each time period.
- **Plot**: The original data, trend, and seasonal components are plotted on the same graph.

## License

This project is open source and available under the MIT License.
