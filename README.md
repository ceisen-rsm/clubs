# Clubs Project Documentation

## Clubs Environment Setup

This guide outlines the steps to set up the required Python environment to process data for the Clubs project. It also includes instructions for updating the necessary PowerBI files

## About the Clubs Project
The Clubs project provides a comprehensive analysis of consolidated Club metrics at the State (Florida) and Regional (Through-out Florida) as well as a Dashboard that enables Clubs to benchmark against one another.

## Prerequisites

- Ensure that you have [Anaconda](https://www.anaconda.com/products/distribution) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html) installed on your system.
- Install [Visual Studio Code](https://code.visualstudio.com/) if it is not already installed.
- Install the **Python** and **Jupyter** extensions in VS Code. You can install extensions by navigating to the Extensions view (`Ctrl+Shift+X` or `Cmd+Shift+X` on macOS) and searching for "Python" and "Jupyter".
- PowerBI Desktop / PowerBI Pro

## Packages
Ensure the following packages and package versions are installed

- numpy (any version)
- pandas (any version)

## Key Stakeholders
Project stakeholders for the ESG Advisor project

- Product Owners: 
	- Philip Newman (Clubs Practice Leader)
	- Tammy Tassitano (Clubs Practice Leader)
	- Vanya Stefanov (Clubs Sr. Director)
	- Syma Molla-Ahmad (Clubs Sr. Director)
- Marketing Lead:
	- Christy Hritz (Marketing Lead – Florida Market, Private Clubs Industry and Public Sector Industry)

## Process Overview
The following processes detail how to update each PowerBI report and how each report are used.

### Clubs Smartsheet ETL.ipynb
Python notebook with ETL processes to update the Clubs Trends and Clubs Trends Marketing reports. 
- Download latest data from the smartsheet file (https://app.smartsheet.com/sheets/mXprHHRR5vvRmcC7qFCjvcxp7RWVh675J8mRFMW1) and store in the Dta folder
- Follow steps in the python notebook and connect to latest download
- Run script and process new data
- Write Smartsheet Upload PowerBI.xlsx file to the Dta/Smartsheet folder. This is the file that the PowerBI files read
- Write Smartsheet Data Extract.xlsx file to the Dta/Smartsheet folder. This is the file that is provided to the Clubs team to Audit metrics

### Clubs Trends Report
PowerBI file containing the aggregated Club metrics at the State and Regional level
- Refresh existing data model. Existing connections are made to the Smartsheet Upload PowerBI.xlsx file.
- Some metrics point to another Excel file (Clubs - Trends Sheet.xlsx). For some metrics that require historical benchmarking beyond 2022 input metrics in this file using the Smartsheet Upload PowerBI.xlsx as reference. These are unique cases where the data from previous years was misaligned or none-existent in historical data files and requires hardcoding. Various tabs are in accordance with sections in the report and input values based on the metrics they belong to each tab.
- After Clubs - Trends Sheet.xlsx and Smartsheet Upload PowerBI.xlsx are updated. All visuals should refresh accordingly
- **My recommendation is to consult with the Clubs Team and re-examine the periods used for benchmarking and use 2022/2023/2024 are the period to avoid having to update the Clubs - Trends Sheet.xlsx file manually. This enable a fast and more efficient refresh of the data and ensures better data management and governance**
- **Once Finalized** upload the PowerBI Report to a PowerBI Workspace that can be shared with the Clubs Team

### Clubs Trends Marketing Report
PowerBI file containing the aggregated Club metrics at the State and Regional level. This report is largely the same as the Clubs Trends Report but pages are seperated to generate a report and visuals specifically for the marketing team. All notes for the Clubs Trends Report apply for this report. 

### Clubs Benchmarking Dashboard Report
PowerBI file containing a **DIRECT** connection to the Clubs smartsheet that enables indivduals Clubs to benchmark against other Clubs or a single Club
- All the is required for this dashboard is to refresh the data and adjust filters to modify selected Club and benchmarked peers.
- Upload this file to a PowerBI Workspace that can shared with the Clubs Team
