#Predictive Maintenance of Industrial Machines#

Project Overview
This project focuses on predicting machine failures using a dataset containing 10,000 records with 14 features related to machine operating conditions. The dataset includes various machine parameters such as temperature, rotational speed, torque, and tool wear, along with a binary classification label indicating machine failure. By leveraging machine learning techniques, this project aims to build a predictive maintenance model that can forecast failures and minimize downtime in industrial settings.

Dataset Description
The dataset consists of:

UID: A unique identifier for each data point.
Product ID: Represents product quality variants—Low (L), Medium (M), and High (H)—with different wear characteristics.
Air Temperature (K): Generated using a random walk process with a standard deviation of 2K around 300K.
Process Temperature (K): Derived from air temperature plus 10K, with an additional standard deviation of 1K.
Rotational Speed (RPM): A function of the power applied (2860W) with normally distributed noise.
Torque (Nm): Normally distributed around 40 Nm (σ = 10 Nm), ensuring no negative values.
Tool Wear (min): The time for which the tool has been in use, varying based on product quality (H = +5 mins, M = +3 mins, L = +2 mins).
Machine Failure (Binary Label): Indicates whether the machine has failed due to one or more failure modes.
Failure Modes
Machine failure is determined by the occurrence of at least one of the following five independent failure modes:

Tool Wear Failure (TWF): Tools fail randomly between 200–240 minutes of wear (69 replacements, 51 failures in the dataset).
Heat Dissipation Failure (HDF): Occurs when the process temperature and air temperature difference falls below 8.6K, and rotational speed is below 1380 RPM (115 instances).
Power Failure (PWF): Failure occurs if the power (torque × rotational speed in rad/s) is below 3500W or above 9000W (95 instances).
Overstrain Failure (OSF): If the product of tool wear and torque exceeds predefined limits based on product quality (L: 11,000 minNm, M: 12,000 minNm, H: 13,000 minNm), the machine fails (98 instances).
Random Failures (RNF): A small probability-based failure, occurring randomly in 0.1% of processes (5 instances).
Since machine failure is a combined event influenced by these independent modes, the dataset does not explicitly indicate the specific cause of failure. This creates a real-world challenge where machine learning models must infer patterns based on historical data.
