# Zen City Bike Sharing Optimization

Optimize the bike sharing business for increased rentals in Q2 2022 through a deep-dive analysis of Q1 2022 data.

## Project Goal
Analyze existing bike rental data from the first quarter of 2022 (January to March) to identify growth opportunities, operational inefficiencies, and usage patterns to maximize performance in the upcoming quarter.

## Key Insights & Analysis Topics
- **Seasonality & Weather**: Evaluating how climate shifts and seasonal trends impact daily ride counts.
- **User Segmentation**: Analyzing behavior differences between subscriber types.
- **Asset Popularity**: Comparing the demand for "Classic" vs. "Electric" bikes.
- **Temporal Trends**: Identifying peak hours and variations between weekdays and weekends.

## Critical Findings

### Data Integrity & "Station Gap"
The analysis revealed a discrepancy between active registered stations and actual trip endpoints:
- **Graveyard Stations**: Users are returning bikes to stations officially marked as "Closed" (e.g., Station 3455).
- **Orphan Stations**: Trips frequently end at IDs not registered in the official database (e.g., 7188, 7125, 7131).
- **Data Inconsistency**: Multiple names assigned to single station IDs (82 names vs 80 IDs).

### Station Flow Analysis
- **"Bleeding" Stations**: Stations with heavy departures but low returns, posing a supply failure risk.
- **"Accumulation" Stations**: Stations acting as "Graveyards" where bikes pile up, requiring manual rebalancing.

## Data Cleaning Strategy
- **Location Patching**: Missing coordinates for popular orphan stations were estimated using nearby proxy stations.
- **ID Normalization**: Consistent conversion of `end_station_id` to integer formats to match central databases.
- **Status Flagging**: Explicitly labeling "Unregistered" and "Officially Closed" active endpoints for better operational reporting.

## Technologies Used
- **Python**: Core logic and data manipulation.
- **Pandas & Numpy**: Data cleaning and aggregation.
- **Seaborn & Matplotlib**: Visualizing distributions and trends.

## Repository Structure
- `zen_city.ipynb`: Complete data analysis, cleaning logic, and visualizations.
- `README.md`: Project summary and key findings.
