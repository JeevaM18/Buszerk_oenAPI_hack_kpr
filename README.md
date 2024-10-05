# **Bus Passenger Prediction and Simulation**


Table of Contents
Introduction
Features
Installation
Usage
Data
Model Training and Evaluation
Simulation
Visualization
Results
Contributing
License
Contact
Introduction
Welcome to the Bus Passenger Prediction and Simulation project! This repository provides a framework for predicting passenger counts between bus stops using machine learning models and simulating bus operations based on these predictions. The project utilizes both standard and Intel-optimized machine learning libraries to enhance performance, making it suitable for large-scale deployments.

Features
Data Preprocessing: Efficient grouping and encoding of passenger count data based on boarding and destination stops.
Machine Learning Models:
Random Forest Regressor
XGBoost Regressor
Intel OneAPI Optimizations using sklearnex for acceleration on Intel hardware.
Model Evaluation: Metrics like Mean Squared Error (MSE), Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), and R² Score.
Bus Simulation: Simulates bus operations, predicting waiting passengers, boarding, alighting, and managing passenger counts.
Visualization: Horizontal bar charts comparing model performance.
Modular Code: Reusable functions for data preparation, model training, evaluation, and simulation.
Installation
Prerequisites
Python 3.7 or higher
pip package manager
Clone the Repository
bash
Copy code
git clone https://github.com/yourusername/bus-passenger-prediction-simulation.git
cd bus-passenger-prediction-simulation
Create a Virtual Environment (Optional but Recommended)
bash
Copy code
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install Dependencies
bash
Copy code
pip install -r requirements.txt
If requirements.txt is not provided, manually install the following packages:

bash
Copy code
pip install numpy pandas scikit-learn xgboost sklearnex matplotlib seaborn joblib
Usage
Preparing the Data
Ensure your dataset contains Boarding_Stop and Destination_Stop columns representing passenger counts between various stop pairs.

python
Copy code
import pandas as pd

 Load your dataset
df = pd.read_csv('path_to_your_data.csv')  # Replace with your data source

 Example DataFrame structure
 | Boarding_Stop | Destination_Stop |
 |---------------|------------------|
 | Stop_A        | Stop_B            |
 | Stop_A        | Stop_C            |
 | Stop_B        | Stop_D            |
 | ...           | ...               |

 Ensure Boarding_Stop and Destination_Stop are not the same
df = df[df['Boarding_Stop'] != df['Destination_Stop']]
Running the Script
The main script is encapsulated in the main function. You can execute it directly or import the functions into your own scripts.

bash
Copy code
python bus_passenger_prediction.py
Example Script Execution
An example is provided in the if __name__ == "__main__": block of the script. It demonstrates how to create a sample dataset, train models, evaluate them, and run simulations.

Data
The script assumes a DataFrame df with at least the following columns:

Boarding_Stop: Categorical variable representing the boarding bus stop.
Destination_Stop: Categorical variable representing the destination bus stop.

Model Training and Evaluation
The script trains two machine learning models:

Random Forest Regressor
XGBoost Regressor
Both models are evaluated using the following metrics:

Mean Squared Error (MSE)
Root Mean Squared Error (RMSE)
Mean Absolute Error (MAE)
R² Score
Example Output
yaml
Copy code

# Training and Evaluating Normal Models

Training Random Forest...
Random Forest trained in 12.34 seconds.

Training XGBoost...
XGBoost trained in 15.67 seconds.

Evaluating Random Forest...
Random Forest - MSE: 0.001234, RMSE: 0.035123, MAE: 0.025678, R²: 0.987654

Evaluating XGBoost...
XGBoost - MSE: 0.001567, RMSE: 0.039583, MAE: 0.028345, R²: 0.984321

# Training and Evaluating Intel Optimized Models 
![dd5f6c83-e003-4378-af2a-3023e13f9ff1](https://github.com/user-attachments/assets/dc203918-be5f-4795-8c0e-d3e9353f04ec)
![cfd2dc66-0a56-4e1f-bb0b-68ff8d3646e5](https://github.com/user-attachments/assets/17eac0d3-2917-4312-a4d2-7c3a91ca031c)

Training Random Forest...
Random Forest trained in 10.21 seconds.

Training XGBoost...
XGBoost trained in 12.45 seconds.

Evaluating Random Forest...
Random Forest - MSE: 0.001110, RMSE: 0.033316, MAE: 0.024890, R²: 0.989012

Evaluating XGBoost...
XGBoost - MSE: 0.001771, RMSE: 0.042068, MAE: 0.030123, R²: 0.982456
Simulation
The script includes a simulation of bus operations based on model predictions. It accounts for:

Predicted Waiting Passengers
Actual Passengers Boarding and Alighting
Current Passengers on the Bus
Available Seats
Standing Passengers
Example Simulation Output
yaml
Copy code

# Simulating Bus Stops with Intel Optimized XGBoost Model 

Stop: Stop_A
Destination Stop: Stop_B
Predicted waiting passengers: 12
Actual passengers getting off: 3
Passengers that boarded: 12
Current passengers: 39
Available seats: 1
Standing passengers: 0

Stop: Stop_B
Destination Stop: Stop_D
Predicted waiting passengers: 10
Actual passengers getting off: 2
Passengers that boarded: 1
Current passengers: 38
Available seats: 2
Standing passengers: 9
Visualization
The script generates horizontal bar charts to compare the Mean Squared Error (MSE) of standard and Intel-optimized models.



# Results
After training and evaluating both standard and Intel-optimized models, the script provides a comparison of their performance based on MSE and other metrics. The simulation outputs demonstrate how the models can effectively manage bus passenger flows.

Contributing
Contributions are welcome! Please follow these steps:

Fork the Repository

Create a Feature Branch


bash
Copy code
git checkout -b feature/YourFeature
Commit Your Changes


bash
Copy code
git commit -m "Add Your Feature"
Push to the Branch


bash
Copy code
git push origin feature/YourFeature
Open a Pull Request


License
This project is licensed under the MIT License.

Contact
For any questions or suggestions, feel free to reach out:


Email: jeeva59128@gmail.com

GitHub: JeevaM18
