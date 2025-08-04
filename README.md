%%writefile Readme.md

#  FIFO Mining Equipment Failure Predictor

AI-powered predictive maintenance system that uses **unsupervised machine learning** and **Generative AI** to predict equipment failures, demonstrated using the NASA Turbofan Engine Degradation dataset as a proxy for mining truck sensors.

##  Features

- Unsupervised Anomaly Detection**: Uses Isolation Forest to identify unusual equipment behavior without needing labeled failure data.
- Generative AI Insights**: Provides natural language explanations and maintenance recommendations.
- Interactive Dashboard**: Visualizes sensor trends, anomaly scores, and risk levels for specific equipment.
- Real-World Proxy**: Built using the NASA C-MAPSS dataset (FD001), which simulates sensor degradation over time.

##  How It Works

1.  **Data Loading**: Automatically finds and loads the `train_FD001.txt` dataset.
2.  **Preprocessing**: Normalizes sensor readings for each equipment unit (engine/truck).
3.  **Model Training**: Trains an Isolation Forest model to detect anomalous patterns in sensor data.
4.  **Risk Assessment**: Calculates an anomaly score for the latest data point of each unit and assigns a risk level (Low, Medium, High) based on percentiles.
5.  **AI Explanation**: Uses Google's FLAN-T5 model to generate a maintenance recommendation based on the risk level and sensor data.
6.  **Visualization**: Displays sensor trends, anomaly score history, and overall risk distribution.

##  Files

- `app.py`: The main Gradio application.
- `requirements.txt`: Python dependencies.
- `CMaps/train_FD001.txt`: The NASA Turbofan dataset (must be present).

## Quick Start (Locally)

1.  Ensure `CMaps/train_FD001.txt` is in the project directory.
2.  Install dependencies: `pip install -r requirements.txt`
3.  Run the app: `python app.py`

##  Deployment

This app is designed to be deployed on [Hugging Face Spaces](https://huggingface.co/spaces). Simply create a new Space, upload these files (including `CMaps/train_FD001.txt`), set the SDK to Gradio, and it should build and run.

##  Data Source

[NASA Turbofan Engine Degradation Simulation Data Set](https://ti.arc.nasa.gov/tech/dash/groups/pcoe/prognostic-data-repository/#turbofan)
