# Email-Marketing-Campaign-Analysis
# https://colab.research.google.com/drive/1erzpKdN4ABV_3nQdN7S3bCuPqsE1H6aJ#scrollTo=DQhbAr4sQZ31
Email Marketing Campaign Analysis with Gradio Interface
Project Overview
This project analyzes an email marketing campaign for an e-commerce site to optimize click-through rates (CTR). It includes:

Calculating open rate and CTR.
Building a Random Forest model to predict link clicks.
Estimating CTR improvement through targeted sending.
Analyzing user segment patterns (country, email type, past purchases).
Deploying an interactive Gradio interface for easy access to results and visualizations.

The analysis is based on three CSV files (email_table.csv, email_opened_table.csv, link_clicked_table.csv) and uses Python libraries for data processing, modeling, and visualization.
Prerequisites

Python Version: 3.8 or higher.
Dependencies: Install required libraries using:pip install pandas numpy scikit-learn matplotlib seaborn gradio


Data Files:
email_table.csv: Details of sent emails (email_id, email_text, email_version, hour, weekday, user_country, user_past_purchases).
email_opened_table.csv: IDs of opened emails (email_id).
link_clicked_table.csv: IDs of emails with link clicks (email_id).
Ensure these files are in the working directory or update the code to specify paths.



Setup Instructions

Clone or Download: Obtain the project code (e.g., email_analysis_gradio.py).
Install Dependencies: Run the pip command above.
Place CSV Files: Ensure the three CSV files are in the same directory as the script.
Run the Script:python email_analysis_gradio.py


Access Gradio Interface: Open the provided URL (e.g., http://127.0.0.1:7860) in a browser.

Usage

Gradio Interface:
Dropdown: Select analysis type (All, Metrics, Model, CTR Improvement, Segments).
Run Analysis: Click the button to display results.
Outputs:
Text Results: Open rate, CTR, model performance, CTR improvement, and segment insights.
Tables: Performance by country, email type/version, and past purchases.
Visualizations: Bar plots and heatmap saved as visualizations.png.




Analysis Types:
Metrics: Shows open rate and CTR.
Model: Displays model performance and feature importance.
CTR Improvement: Estimates CTR gain with targeted sending.
Segments: Analyzes user segment patterns.
All: Runs all analyses and generates visualizations.



Expected Output

Sample Results (hypothetical, based on data):
Open Rate: 20.50%
CTR: 2.30%
Model ROC AUC: 0.9213
CTR Improvement: 1.80% (from 2.30% to 4.10%)
Segment Insights: Higher CTR for US, personalized short emails, and high-purchase users.


Visualizations:
Bar plot: CTR by country.
Heatmap: CTR by email type/version.
Bar plot: CTR by past purchase bins.
Bar plot: Feature importance.



Troubleshooting

CSV Files Missing:
Error: "One or more CSV files not found."
Solution: Verify file names and paths. Consider adding file upload inputs in Gradio (see Enhancements).


Gradio Interface Fails:
Solution: Ensure gradio is installed. Check for port conflicts (demo.launch(port=7861)).


Visualization Errors:
Solution: Confirm matplotlib and seaborn are installed. Check if visualizations.png is created.


Binning/Pivoting Errors:
Error: Issues with pd.qcut or pivot_table (e.g., insufficient unique values).
Solution: The code handles these gracefully, displaying error messages and skipping affected outputs.



Enhancements

File Uploads: Add Gradio file inputs for CSV uploads:email_file = gr.File(label="Upload email_table.csv")


Interactive Filters: Include dropdowns/sliders to filter segments (e.g., by country).
Real-Time Predictions: Allow users to input feature values and predict click probability.
Download Outputs: Add buttons to download tables or visualizations.

Notes

Data Assumptions:
The CSV files are assumed to have the correct structure (e.g., email_id as a unique key).
Hypothetical outputs are used for documentation; actual results depend on your data.


Gradio Deployment:
Local: Runs on http://127.0.0.1:7860 by default.
Public: Use demo.launch(share=True) for a temporary public URL (requires Gradio account).


Performance:
The Random Forest model may take time with large datasets. Consider optimizing with fewer trees or subsampling.


Extensibility:
Add more features (e.g., email subject lines) to improve model accuracy.
Integrate with a database for real-time data updates.



License
This project is for educational purposes. Ensure compliance with data privacy regulations when using real user data.
Contact
For questions or support, contact [Your Name/Email] or raise an issue in the project repository.
