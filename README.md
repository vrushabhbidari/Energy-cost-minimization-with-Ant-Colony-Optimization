# Energy Cost Minimization with Ant Colony Optimization

**ACO-Based Smart Irrigation Energy Optimization**

## Overview

This project uses Ant Colony Optimization (ACO) to reduce energy costs in irrigation systems while maintaining optimal soil moisture. The system shifts irrigation from expensive daytime hours to cheaper nighttime periods using weather forecasting and time-of-use electricity pricing.

## Usage Manual

### Experiment A: Default Performance

**Goal:** Compare ACO algorithms with baseline system

1. Open `Conservative_ACO_and_MMAS.ipynb`
2. Use `data_2023.csv`
3. Run all cells

### Experiment B: Parameter Analysis

**Goal:** Test different algorithm parameters

1. Open `Conservative_ACO_and_MMAS.ipynb`
2. Modify parameters in `class ReactiveACO` or `class MaxMinAntSystem`:
   - `num_ants`
   - `num_iterations`
   - `alpha`
   - `beta`
   - `evaporation_rate`
   - `q0`
3. Test each configuration from Table 1 in the report

### Experiment C: No Forecasting Impact

**Goal:** See performance without weather prediction

1. Open `ACO_data_no_lookahead.ipynb`
2. Use `data_2023.csv`
3. Run all cells

### Experiment D: Different Weather Data

**Goal:** Test across different weather conditions

1. Run `Conservative_ACO_and_MMAS.ipynb` with `data_2023.csv`
2. Run again with `data_1_2022.csv`
3. Compare results

### Experiment E: Action Granularity

**Goal:** Test irrigation precision impact

1. Open `Conservative_ACO_and_MMAS.ipynb`
2. Find line: `self.possible_actions = np.linspace(0, max_irrigation, 12)`
3. Change `12` to `10` (reduced) or `15` (expanded)

## Configuration

### Dataset Switching

```python
weather_data = pd.read_csv('data_2023.csv')  # Change filename here
```

### Action Space

```python
self.possible_actions = np.linspace(0, max_irrigation, 12)  # Change 12 for granularity
```

## Files

- `Conservative_ACO_and_MMAS.ipynb` - Main notebook with ACO algorithms
- `ACO_data_no_lookahead.ipynb` - Notebook for testing without weather forecasting
- `data_2023.csv` - Primary weather dataset
- `data_1_2022.csv` - Alternative weather dataset for comparison

## Getting Started

1. Clone the repository
2. Install required dependencies
3. Run the desired experiment following the usage manual above
4. Analyze results and compare with baseline performance
