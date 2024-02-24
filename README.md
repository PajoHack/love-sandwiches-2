Love Sandwiches Data Automation
===============================

Overview
--------

This Python program is designed to automate data handling for a sandwich business named "Love Sandwiches." It interacts with Google Sheets to store and process sales data, calculate surplus and stock requirements, and maintain updated records for business analysis.

Features
--------

-   Data Collection: Collects sales data input from the user.
-   Data Validation: Ensures the collected data is in the correct format and meets specified criteria.
-   Worksheet Updating: Updates Google Sheets with sales, surplus, and stock data.
-   Surplus Calculation: Determines surplus by comparing sales with stock.
-   Stock Calculation: Calculates required stock based on recent sales data.

Prerequisites
-------------

-   Python 3
-   Google account with access to Google Sheets API
-   `gspread` and `google-auth` Python libraries
-   A Google Sheets document named 'love_sandwiches'

Installation
------------

1.  Install the required Python libraries:

    Copy code

    `pip install gspread google-auth`

2.  Set up Google Sheets API and Service Account:
    -   Follow Google's documentation to enable the Google Sheets API.
    -   Create a service account and download the credentials JSON file.

Setup
-----

1.  Rename the downloaded credentials file to `creds.json` and place it in the project directory.
2.  Share your Google Sheets document with the email found in your `creds.json` file.

Usage
-----

1.  Run the script:

    Copy code

    `python your_script_name.py`

2.  Follow the on-screen prompts to enter the sales data.

Functions
---------

-   `get_sales_data()`: Prompts the user for sales data input.
-   `validate_data(values)`: Validates the entered sales data.
-   `update_worksheet(data, worksheet)`: Updates the specified worksheet in the Google Sheets with the provided data.
-   `calculate_surplus_data(sales_row)`: Calculates the surplus data based on sales.
-   `get_last_5_entries_sales()`: Retrieves the last 5 entries of sales data from the worksheet.
-   `calculate_stock_data(data)`: Calculates the stock data based on sales history.
-   `main()`: Runs all program functions and initiates the data automation process.

### Deployment to Heroku

#### 1\. Prepare Your Application

Ensure your application is ready for deployment. This includes:

-   Installing all necessary libraries and dependencies.
-   Structuring your project with a `requirements.txt` file listing all dependencies.

Since your application uses `gspread` and Google OAuth credentials, make sure to include `gspread` and `google-auth` in your `requirements.txt`.

#### 2\. Heroku Account and Heroku CLI

If you haven't already:

-   Create a Heroku account.
-   Install the Heroku Command Line Interface (CLI) on your machine.

#### 3\. Setting Up Your Heroku App

From your terminal:

-   Navigate to your project directory.
-   Login to Heroku using `heroku login`.
-   Create a new Heroku app using `heroku create [app-name]`. Replace `[app-name]` with your desired app name.

#### 4\. Configuring Environment Variables

Since your app uses a `creds.json` file for Google credentials:

-   Convert your `creds.json` file to environment variables.
-   Set these variables in Heroku using `heroku config:set VAR_NAME=value`.

For example:

bashCopy code

`heroku config:set GSPREAD_CREDS='{"type": "service_account", "project_id": "your-project-id", ...}'`

Replace the value with your actual credentials in JSON format.

#### 5\. Deploying Your Application

-   Initialize a Git repository if you haven't already with `git init`.
-   Add Heroku remote repository using `heroku git:remote -a [app-name]`.
-   Commit your changes to Git.
-   Push to Heroku using `git push heroku master`.

#### 6\. Monitoring Your Application

-   Check the status of your app using `heroku ps`.
-   View logs for debugging using `heroku logs --tail`.

#### 7\. Additional Notes

-   Ensure your application is designed to run continuously or as a scheduled job since Heroku dynos sleep after 30 mins of inactivity.
-   Consider using Heroku Scheduler for periodic tasks.

Add this guide to your README under the section "Deployment to Heroku". Make sure to adjust any steps as per your specific requirements and configurations.

