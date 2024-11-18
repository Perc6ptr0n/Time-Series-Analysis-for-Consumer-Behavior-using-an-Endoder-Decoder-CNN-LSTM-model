# **Time-Series Analysis for Consumer Behavior using an Encoder-Decoder CNN-LSTM Model**

![Energy Management Banner](https://github.com/user-attachments/assets/6ce5801e-d626-4f55-b8c1-fb504f4c80cc)

---

## **Overview**
This project tackles the intricate challenge of forecasting energy consumption and production patterns of **prosumers**—entities that both produce and consume energy. With the increasing integration of renewable energy sources and prosumer behavior, traditional energy grids face growing complexity, necessitating robust, data-driven prediction models.

This repository provides a comprehensive guide to implementing an **Encoder-Decoder CNN-LSTM model** for sequential data analysis, focusing on the critical aspects of energy grid management, dataset architecture, and feature engineering.

---

## **Enhanced Problem Statement**

### 1.1 Core Challenge
The rise of prosumers has introduced bidirectional energy flows that vary significantly based on weather conditions, time of day, and economic incentives. Accurate predictions are vital to maintaining grid stability and ensuring efficient energy distribution.

#### Key Challenges:
- **Grid Stability Management**: 
  - Overgeneration risks (e.g., system overloads) and undergeneration risks (e.g., brownouts).
  - Maintaining frequency within strict bounds (e.g., 50/60 Hz ± 0.5%).
  - Handling intermittent energy sources like solar and wind power.

- **Economic Impact**:
  - Increased costs for advanced monitoring and control systems.
  - Rapid grid wear and tear due to fluctuating power flows.
  - Volatility in market prices influencing prosumer decisions.

---

## **Data Architecture Analysis**

### 2.1 Core Datasets Overview
The project employs multiple datasets that provide hourly snapshots of energy flow and contextual information. These include:

#### **Training Data (train.csv)**:
- **Geographic Segmentation**:
  - Analysis of regional patterns and local conditions.
  - Enables clustering of similar behavior and targeted predictions.

- **Consumer Type Classification (`is_business`)**:
  - Differentiates residential vs. business energy usage.
  - Provides unique modeling strategies for each category.

- **Contract Type (`product_type`)**:
  - Categories: Combined, Fixed, General service, and Spot pricing.
  - Each contract type correlates with specific economic behaviors.

#### **Weather Data**:
- **Forecast Data**:
  - **Temperature & Dewpoint**: Key for heating/cooling demand and solar efficiency.
  - **Cloud Cover**: Critical for predicting solar energy generation.
  - **Wind Components**: Indicators of energy demand and ventilation needs.

- **Historical Weather Data**:
  - Validates forecast accuracy.
  - Enables seasonal and cyclical pattern recognition.

#### **Price Data**:
- **Electricity Prices**:
  - Hourly granularity aligns with prediction targets.
  - Volatility reflects market dynamics.
  
- **Gas Prices**:
  - Complementary data for correlation and feature engineering.

---

### 2.2 Feature Engineering
Sophisticated features are engineered to enhance the model's ability to capture patterns:
- **Temporal Features**:
  - Hour of Day: Captures daily cycles (e.g., peak/off-peak hours).
  - Day of Week: Accounts for weekend/weekday variances.
  - Seasonal Indicators: Reflects long-term cycles (e.g., solar potential).

- **Dynamic Features**:
  - Weather variability.
  - Price trends.
  - Behavioral signatures.

---

## **Model Architecture**

### 3.1 Encoder-Decoder Design
The **Encoder-Decoder CNN-LSTM model** is tailored for sequential data and long-term dependency capture. It is split into:

#### **Encoder**:
- **Purpose**: Extract features and recognize patterns.
- **Components**:
  - **Bidirectional LSTM Layers**: Capture forward and backward temporal dependencies.
  - **Convolutional Layers**: Detect local patterns (e.g., rapid changes in energy flow).
  - **Attention Mechanism**: Dynamically weigh feature importance.

#### **Latent Space**:
- **Static Context**: Geographic, consumer type, and contract details.
- **Dynamic Context**: Weather, price, and temporal patterns.

#### **Decoder**:
- **Purpose**: Generate predictions while adhering to physical constraints.
- **Components**:
  - Sequential processing layers.
  - Mechanisms to maintain temporal consistency.

---

## **Implementation Steps**

1. **Data Preprocessing**:
   - Handle missing values and normalize datasets.
   - Feature encoding for categorical variables (e.g., contract types).

2. **Feature Engineering**:
   - Generate temporal, seasonal, and price-based features.

3. **Model Training**:
   - Implement and fine-tune the Encoder-Decoder CNN-LSTM architecture.
   - Use advanced optimizers (e.g., Nadam) and validation techniques.

4. **Evaluation**:
   - Metrics: RMSE, MAE, and MAPE.
   - Generate visualizations comparing predicted vs. actual values.

5. **Recursive Forecasting**:
   - Predict next-hour and 24-hour windows using historical data.

---

## **Results and Insights**
- **Key Metrics**: Achieved RMSE and MAE within acceptable bounds for grid stability.
- **Visualization**:
  - Predictions align closely with observed data across varying weather and price conditions.
  - Clear patterns observed in weekday/weekend and seasonal cycles.

---

## **Future Work**
- Expand datasets to include more prosumer profiles and diverse geographic regions.
- Integrate real-time streaming data for continuous prediction updates.
- Explore advanced architectures like Transformer models for further improvement.

---

## **How to Run**
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/time-series-analysis

##**Contributors**
John (Ioannis) Laios – Data Scientist and Project Lead
