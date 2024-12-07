# Personal-Budgeting-Tool
Personal Finance Planner
Description
The Personal Finance Planner is a Flask-based web application designed to help users manage their financial data. It provides features like income and expense tracking, personalized expense predictions using machine learning, and interactive visualizations of expense breakdowns.

The application uses a Random Forest Regressor for predicting expenses based on user input (monthly income and month) and visualizes expense categories dynamically using Plotly.

Features
Dashboard:
Input monthly income and month to predict expenses.
View current transaction data in a table format.
Expense Prediction:
Machine learning-based predictions using a trained Random Forest model.
Visualization:
Interactive pie chart of expense breakdowns.
Error handling for empty or missing data.
Data Management:
Dynamic updates to user transactions stored in a CSV file.
Handles both income and expense records.
Technologies Used
Backend:
Flask
pandas
scikit-learn
joblib
Frontend:
HTML
Bootstrap
Plotly (for interactive visualizations)
Machine Learning:
Random Forest Regressor for expense predictions
Installation and Setup
Prerequisites
Python 3.7 or later
pip (Python package manager)
Clone the Repository
Download the project to your local machine:

bash
Copy code
git clone <repository-url>
cd personal_finance
Install Dependencies
Install the required Python libraries:

bash
Copy code
pip install -r requirements.txt
Folder Structure
Ensure the following folder structure exists:

php
Copy code
personal_finance/
├── app.py                # Main Flask application
├── train_model.py        # Script to train and save the model
├── templates/            # HTML templates for rendering views
│   ├── base.html
│   ├── index.html
│   ├── dashboard.html
│   ├── visualize.html
├── static/               # Optional for CSS/JS files
├── models/               # Directory for saved model file
│   ├── expense_model.pkl # Trained model (created by train_model.py)
├── data/                 # Directory for user data (CSV files)
│   ├── user_data.csv     # User transactions
├── requirements.txt      # Python dependencies
Usage
Train the Model: Run the following command to train the Random Forest model:

bash
Copy code
python train_model.py
This creates expense_model.pkl in the models/ directory.

Start the Application: Run the Flask app:

bash
Copy code
python app.py
The app will start on http://127.0.0.1:5000/.

Access the Features:

Homepage: View a welcome message and links to features.
Dashboard: Input data and see expense predictions.
Visualization: Explore interactive charts of expense breakdowns.
Sample Data
Add sample data to data/user_data.csv for testing:

csv
Copy code
Date / Time,Mode,Category,Sub category,Income/Expense,Debit/Credit
Friday, January 1, 2021,CUB - online payment,Allowance,From dad,Income,8000
Friday, January 1, 2021,CUB - online payment,Food,Snacks,Expense,85
Sunday, January 3, 2021,CUB - online payment,Other,From dad,Income,500
Sunday, January 3, 2021,CUB - online payment,Household,Stuffs,Expense,6667
Sunday, January 3, 2021,CUB - online payment,Transportation,Metro,Expense,30
Deployment
To deploy the app online, consider using platforms like:

Heroku
Render
AWS Elastic Beanstalk
Deployment Steps for Heroku
Install the Heroku CLI.
Create a Procfile:
makefile
Copy code
web: python app.py
Deploy to Heroku:
bash
Copy code
heroku login
git init
git add .
git commit -m "Initial commit"
heroku create
git push heroku master
Future Enhancements
Add user authentication for personalized tracking.
Enable downloadable reports (PDF/Excel).
Integrate APIs for real-time financial data (e.g., stock prices).
Improve the machine learning model with additional features and real-world data.
