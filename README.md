# Zeotap
Rule Engine and Weather Monitoring

# Rule Engine Interactive UI in Google Colab

This project is an interactive Rule Engine implemented in Google Colab using `ipywidgets` for creating a graphical user interface (UI). It allows users to define rules, create an Abstract Syntax Tree (AST) from those rules, and evaluate them against input data. The UI is designed with styled text areas for rule and data input, buttons for creating the AST and evaluating rules, and output areas for displaying results.

## Table of Contents
- [Project Overview](#project-overview)
- [Dependencies](#dependencies)
- [Setup Instructions](#setup-instructions)
- [Using the Rule Engine](#using-the-rule-engine)
- [Code Structure](#code-structure)
- [Troubleshooting](#troubleshooting)
- [Extending the Code](#extending-the-code)

## Project Overview

The Rule Engine UI provides an easy-to-use interface where:
- Users can input a rule expression and a data JSON.
- The rule expression is parsed to create an Abstract Syntax Tree (AST).
- The input data is evaluated against the generated AST.
- Results of the evaluation (whether the data satisfies the rule) are displayed.

## Dependencies

The code uses the following dependencies:
- **Google Colab**: This project is designed to run within a Google Colab notebook.
- **ipywidgets**: Used for creating interactive UI elements.

Install the required dependency using:
```python
!pip install ipywidgets

## Setup Instructions
Clone or Download the Notebook: Download the notebook or clone the repository if available.
Open Google Colab: Open the downloaded notebook in Google Colab.
Install Dependencies: Run the command to install ipywidgets:
python
Copy code
!pip install ipywidgets
Run the Provided Code Snippets: Execute each code cell in sequence. This will initialize the UI components and set up the rule engine.
Using the Rule Engine
Rule Input:

Input your rule expression in the "Rule" text area. The default rule is:
scss
Copy code
((age > 30 AND department == 'Sales') OR (age < 25 AND department == 'Marketing')) AND (salary > 50000 OR experience > 5)
You can modify the rule as needed.
Data Input:

Input the JSON data against which you want to evaluate the rule in the "Data" text area. The default data is:
json
Copy code
{"age": 35, "department": "Sales", "salary": 60000, "experience": 3}
Ensure the JSON format is valid.
Creating the AST:

Click the "Create AST" button to parse the rule and generate the Abstract Syntax Tree.
The AST output will be displayed in the "AST Output" tab.
Evaluating the Rule:

Click the "Evaluate Rule" button to evaluate the input data against the generated AST.
The result will be shown in the "Evaluation Result" tab, indicating whether the data satisfies the rule ("Eligible" or "Not Eligible").
Clearing Outputs:

Click the "Clear Outputs" button to reset the AST and evaluation output areas.


# Real-Time Weather Monitoring System

This project is a real-time data processing system that monitors weather conditions using the OpenWeatherMap API. It provides summarized insights through daily rollups and aggregates, and it can send alerts based on user-configurable thresholds.

## Table of Contents

1. [Objective](#objective)
2. [Data Source](#data-source)
3. [Dependencies](#dependencies)
4. [Build Instructions](#build-instructions)
5. [Design Choices](#design-choices)
6. [Usage](#usage)
7. [Testing](#testing)
8. [License](#license)

## Objective

Develop a real-time data processing system to monitor weather conditions and provide summarized insights using rollups and aggregates. The system will utilize data from the OpenWeatherMap API.

## Data Source

The system retrieves weather data from the OpenWeatherMap API. You will need to sign up for a free API key to access the data. The API provides various weather parameters, and for this assignment, we focus on:

- **main**: Main weather condition (e.g., Rain, Snow, Clear)
- **temp**: Current temperature in Centigrade
- **feels_like**: Perceived temperature in Centigrade
- **dt**: Time of the data update (Unix timestamp)

## Dependencies

To run this application on Google Colab, you need the following dependencies:

- Python 3.x
- `requests`: For making HTTP requests to the OpenWeatherMap API
- `pandas`: For data manipulation and analysis
- `matplotlib`: For plotting data visualizations

### Install Dependencies

You can install the required libraries using the following command in your Google Colab notebook:

```python
!pip install requests pandas matplotlib

Build Instructions
Sign Up for OpenWeatherMap:

Go to OpenWeatherMap and sign up for a free account.
Obtain your API key from the API keys section of your account dashboard.
Clone the Repository (if using GitHub):

bash
Copy code
git clone https://github.com/yourusername/weather-monitoring-system.git
cd weather-monitoring-system
Set Up Your Google Colab Environment:

Open a new Google Colab notebook.
Copy and paste the contents of the repository into the Colab notebook.
Run the Notebook:

Make sure to replace YOUR_API_KEY in the code with your actual OpenWeatherMap API key.
Execute the cells to start monitoring the weather data.
Design Choices
Architecture: The application is designed to run as a single-threaded script in a Google Colab environment. It continuously fetches weather data at specified intervals and processes the information.

Data Processing: Weather data is stored in-memory, and daily summaries are calculated based on the received updates. Alerts are triggered when specified thresholds are exceeded.

Visualization: The application provides visualizations of daily weather summaries using Matplotlib, allowing users to observe trends over time.

Usage
Modify the INTERVAL variable to change the frequency of data retrieval (in seconds).
Configure alert thresholds by adjusting the relevant variables in the code.
Run the entire notebook to start monitoring the weather.
