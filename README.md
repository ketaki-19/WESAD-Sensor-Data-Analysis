# WESAD-Sensor-Data-Analysis
```markdown
# FDA Project 2: Mental State Analysis from Physiological Signals

## Project Overview
This project aims to analyze various mental states (baseline, stress, amusement, meditation) using physiological signals collected from multiple subjects. The data is processed to extract meaningful features like Permutation Entropy (PE) and Complexity, which are then visualized to understand the differences across mental states.

## Data Sources
The project utilizes `.pkl` files containing physiological data (chest signals) and corresponding labels for different subjects (S7, S8, S9, S10, S13).

## Data Processing Steps
1.  **Loading Data:** Physiological data (ACC, ECG, EMG, EDA, Temp, Resp) and labels are loaded from `.pkl` files for each subject.
2.  **DataFrame Creation:** Raw signal data is converted into pandas DataFrames, including a 'label' column (representing the mental state) and a 'subject' column.
3.  **Filtering:** Only data corresponding to specific mental states (1: baseline, 2: stress, 3: amusement, 4: meditation) is retained.
4.  **Combining Data:** Filtered data from all subjects is concatenated into a single DataFrame (`df_combined`).
5.  **Sampling:** For each subject and each mental state, 10 non-overlapping samples, each of 4096 data points, are extracted. This ensures uniform segments for feature extraction.

## Feature Engineering: Permutation Entropy and Complexity
The project calculates two key features for each sampled signal:
*   **Permutation Entropy (PE):** A measure of the complexity and predictability of a time series, indicating the order or disorder of the signal.
*   **Complexity:** A measure related to the structural complexity of the time series, often used in conjunction with entropy.

These features are computed for the following chest signals:
*   `s_ACC_X`, `s_ACC_Y`, `s_ACC_Z` (Accelerometer data in X, Y, Z directions)
*   `s_ECG` (Electrocardiogram)
*   `s_EMG` (Electromyography)
*   `s_Temp` (Temperature)
*   `s_Resp` (Respiration)
*   `s_EDA` (Electrodermal Activity)

## Analysis and Visualization
After feature extraction, the calculated Permutation Entropy and Complexity values are plotted against each other for each signal and subject. These scatter plots help visualize how the mental states cluster in the PE-Complexity space, potentially revealing distinct patterns for different emotional and cognitive conditions.

## Libraries Used
*   `pandas`: For data manipulation and analysis.
*   `numpy`: For numerical operations.
*   `matplotlib.pyplot`: For creating static, interactive, and animated visualizations.
*   `seaborn`: For drawing attractive and informative statistical graphics.

## How to Run
1.  Ensure all required `.pkl` data files (S7.pkl, S8.pkl, S9.pkl, S10.pkl, S13.pkl) are present in the designated `/content/drive/My Drive/FDA/Project2` directory.
2.  Run the Jupyter/Colab notebook cells sequentially to load data, process it, extract features, and generate visualizations.
```
