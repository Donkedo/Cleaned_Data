# Mobile Phone Specifications Data Cleaning and Feature Engineering

## Project Overview

This project focuses on cleaning and transforming a raw mobile phone specifications dataset into an analysis-ready dataset using Python, Pandas, NumPy, and Regular Expressions.

The original dataset contained unstructured text fields where multiple specifications were stored in a single column. The goal was to extract meaningful features, standardize formats, handle missing values, and create a dataset suitable for exploratory data analysis and machine learning.

---

## Dataset

The dataset contains specifications of more than 1000 mobile phones, including:

* Mobile Name
* Price
* Display Specifications
* Processor Information
* Camera Specifications
* Battery Details
* Connectivity Features
* Operating System Information
* Storage and Memory Details

---

## Data Cleaning Process

### 1. Price Cleaning

* Removed currency symbols and separators.
* Converted prices to numeric format.

### 2. Display Feature Extraction

Extracted:

* Screen Size (inches)
* Screen Resolution
* Refresh Rate (Hz)

Converted extracted values into numeric columns.

### 3. RAM and Storage Extraction

Parsed memory specifications and created:

* RAM (GB)
* Internal Storage (GB)

Standardized storage units where necessary.

### 4. External Storage Processing

Extracted:

* Memory Card Support Status
* Maximum Expandable Storage

Converted TB values into equivalent GB values.

Examples:

* 1 TB → 1024 GB
* 2 TB → 2048 GB

### 5. Camera Feature Engineering

Extracted individual camera sensor resolutions from text descriptions.

Created:

* camera1_mp
* camera2_mp
* camera3_mp

Supported:

* Single Camera Phones
* Dual Camera Phones
* Triple Camera Phones

Missing sensors were stored as null values.

### 6. Processor Cleaning

Extracted processor information into separate features:

* Processor Name
* Core Count
* Clock Speed (GHz)

Examples:

* Snapdragon 8+ Gen1
* Helio G95
* Dimensity 9300

Extracted clock speeds and standardized units.

### 7. Battery Feature Extraction

Created:

* battery_capacity_mAh
* charging_capacity_Watt
* charging_type

Examples:

* 5000 mAh
* 67 W Fast Charging
* 120 W SuperVOOC Charging

### 8. Operating System Recovery and Cleaning

One challenge was that some operating system values were incorrectly stored in other columns.

Detected and recovered operating systems such as:

* Android
* iOS
* HarmonyOS
* Hongmeng
* Flyme
* RTOS
* KAI OS
* Symbian
* Mocor
* Nucleus

Created:

* os
* os_name
* os_version

Examples:

| Original Value | OS Name | OS Version |
| -------------- | ------- | ---------- |
| Android v14    | Android | 14         |
| Android 13     | Android | 13         |
| iOS v17.2      | iOS     | 17.2       |

### 9. Connectivity Features

Converted connectivity information into binary features:

* 5G Support
* VoLTE Support
* NFC Support
* Wi-Fi Support

Encoding:

* Yes → 1
* No → 0

### 10. Missing Value Handling

* Identified invalid records.
* Preserved genuine missing values.
* Used NaN values where information was unavailable.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Regular Expressions (Regex)

---

## Skills Demonstrated

* Data Cleaning
* Feature Engineering
* Text Processing
* Regular Expressions
* Missing Value Handling
* Data Transformation
* Data Preparation for Machine Learning

---

## Final Dataset

The cleaned dataset contains structured numerical and categorical features extracted from raw specification text and is ready for:

* Exploratory Data Analysis (EDA)
* Visualization
* Machine Learning
* Statistical Analysis

---

## Author

Aaman Manzar

This project was created as a practical exercise in real-world data cleaning and feature engineering using Python.
