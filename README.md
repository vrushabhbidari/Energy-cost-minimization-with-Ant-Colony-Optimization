# Energy-cost-minimization-with-Ant-Colony-Optimization

ACO-Based Smart Irrigation Energy Optimization
Overview
This project uses Ant Colony Optimization (ACO) to reduce energy costs in irrigation systems while maintaining optimal soil moisture. The system shifts irrigation from expensive daytime hours to cheaper nighttime periods using weather forecasting and time-of-use electricity pricing.
Usage Manual
Experiment A: Default Performance
Goal: Compare ACO algorithms with baseline system
•	Open Conservative_ACO_and_MMAS.ipynb
•	Use data_2023.csv
•	Run all cells
Experiment B: Parameter Analysis
Goal: Test different algorithm parameters
•	Open Conservative_ACO_and_MMAS.ipynb
•	Modify parameters in class ReactiveACO or class MaxMinAntSystem: 
o	num_ants, num_iterations, alpha, beta, evaporation_rate, q0
•	Test each configuration from Table 1 in the report
Experiment C: No Forecasting Impact
Goal: See performance without weather prediction
•	Open ACO_data_no_lookahead.ipynb
•	Use data_2023.csv
•	Run all cells
Experiment D: Different Weather Data
Goal: Test across different weather conditions
•	Run Conservative_ACO_and_MMAS.ipynb with data_2023.csv
•	Run again with data_1_2022.csv
•	Compare results
Experiment E: Action Granularity
Goal: Test irrigation precision impact
•	Open Conservative_ACO_and_MMAS.ipynb
•	Find line: self.possible_actions = np.linspace(0, max_irrigation, 12)
•	Change 12 to 10 (reduced) or 15 (expanded)
Dataset Switching
weather_data = pd.read_csv('data_2023.csv')  # Change filename here
Action Space
self.possible_actions = np.linspace(0, max_irrigation, 12)  # Change 12 for granularity
