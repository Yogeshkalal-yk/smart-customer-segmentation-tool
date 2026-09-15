# Smart Customer Segmentation Tool

Smart Customer Segmentation Tool is a Python-based Streamlit application that analyzes customer transaction data and groups customers according to their spending behavior and purchase frequency. It also uses Google Gemini AI to generate practical business recommendations.

## Features

- Upload customer transaction data through the Streamlit interface
- Clean missing categories, cities, discounts, and transaction amounts
- Calculate customer-level metrics:
  - Total spending
  - Number of transactions
  - Total quantity purchased
  - Average order value
  - Product category diversity
- Classify customers into:
  - High Value
  - Regular
  - Occasional
- Display transaction data and segment summaries
- Visualize customers by segment
- Generate AI-powered marketing insights using Gemini

## Technology Stack

- Python
- Streamlit
- Pandas
- Google Gemini API
- CSV data processing

Input CSV Format
Uploaded CSV files should contain these columns:

transaction_id
customer_id
transaction_date
product
category
quantity
unit_price
discount_pct
amount
city

Segmentation Logic
Customers are segmented using spending and transaction-frequency thresholds.

High Value: Spending and transaction count are both in the top 30%.
Occasional: Spending and transaction count are both in the bottom 30%.
Regular: Customers who do not match the other two categories.
The segmentation thresholds are calculated dynamically from the uploaded dataset.

AI Business Insights
The AI Insights tab sends the segment summary to Google Gemini. Gemini analyzes the available data and provides:

Key customer behavior observations
The most valuable customer segment
The segment requiring attention
Marketing recommendations
Suggested business actions
To use this feature, enter a valid Gemini API key in the application. Do not store API keys directly in the source code or commit them to GitHub.

Business Use Cases
This application can help businesses:

Identify loyal and high-spending customers
Re-engage customers with low purchase activity
Design targeted marketing campaigns
Improve customer retention
Create personalized offers
Understand revenue contribution by customer segment
Important Limitations
Customer recency is not currently included.
Transaction count is used as order frequency.
Category diversity is calculated as a metric but does not currently determine the segment.
Results depend on the quality and structure of the uploaded CSV data.
Gemini AI requires a valid API key and internet access.


Future Improvements
Add Recency, Frequency, and Monetary (RFM) analysis
Add customer lifetime value prediction
Add interactive filters for city and product category
Add downloadable reports
Add advanced charts and trend analysis
Store API keys securely using Streamlit secrets
Add machine-learning-based clustering

## Project Structure

```text
Smart Customer Segmentation Tool/
|
|-- app.py
|-- requirements.txt
|-- README.md
|-- .gitignore
|-- data/
|   `-- customers.csv
|-- src/
|   |-- data_processing.py
|   |-- segmentation.py
|   `-- ai_insights.py
`-- myenv/

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/your-repository-name.git
cd "Smart Customer Segmentation Tool"

2. Create a Virtual Environment
python -m venv myenv

3. Activate the Virtual Environment
For Windows PowerShell:
Activate.ps1

For Windows Command Prompt:
myenv\Scripts\activate

4. Install Dependencies
pip install -r requirements.txt

5. Run the Application
streamlit run app.py

3. Activate the Virtual Environment
For Windows PowerShell:
Activate.ps1


Also make sure your requirements.txt contains:

```text
streamlit
pandas
google-genai
