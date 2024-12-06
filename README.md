# AI-Powered Phishing Detector

This project implements an **AI-powered phishing link detection system** designed to identify and alert users about phishing attacks. The system leverages machine learning models to automatically detect phishing links in web pages, email apps, social media, and other platforms.

## Phishing Attack Detection

### Why are phishing links dangerous?

Phishing attacks are one of the most prevalent forms of cyber threats today. Phishing is responsible for a significant portion of data breaches. Here are some alarming statistics:

- Phishing attacks are responsible for **90% of data breaches**.
- The global average cost of a data breach caused by phishing is $3.86 million.
- In 2020, phishing attacks saw a **22% increase** compared to the previous year.
- One in every 99 emails is a phishing attempt.
- **Phishing emails** account for 80% of all reported security incidents.
- **94% of malware** is delivered via phishing emails.

Given these risks, an effective solution to detect phishing links before they can cause harm is essential.

## Solution Approach

To combat the growing threat of phishing, we have developed a system that uses machine learning to automatically detect phishing links in real-time. The solution can be easily integrated into browsers as an extension.

### 1. Training the Model

We used the [Malicious URLs dataset](https://www.kaggle.com/eswarchandt/phishing-website-detector) to train the model. The following steps were followed during the process:

- **Loading the data** – We imported the dataset to work with it.
- **Exploratory Data Analysis (EDA)** – We performed data analysis to understand the data structure and identify important patterns.
- **Data visualization** – Visualization techniques were employed to understand correlations between features.
- **Model Training** – Several models were trained, including:
  - Logistic Regression
  - K-Nearest Neighbors
  - Support Vector Classifier
  - Naive Bayes
  - Decision Tree
  - Random Forest
  - **Gradient Boosting**
  - Catboost
  - Multilayer Perceptrons

After evaluating the latency and accuracy of these models, **Gradient Boosting** demonstrated the best balance between speed and accuracy, making it the model of choice.

### 2. Building the Extension

The extension integrates the model into a browser-friendly format. Key steps include:

- **Manifest Configuration** – Configurations were set up for the extension’s activation and permissions.
- **background.js** – This file handles the URL fetching and ensures the extension operates as expected.
- **contentScript.js** – This script manipulates the DOM of websites to integrate the extension seamlessly.
- **Popup Interface** – HTML, JavaScript, and CSS files manage the user interface of the extension.

### 3. Integrating the Model with the Extension

- The trained model is saved as a pickle file.
- The pickle file is served using Flask, which acts as a lightweight backend server.
- The Flask server exposes the model for input, allowing predictions to be fed directly into the extension for real-time analysis.

## Usage

To use the phishing detection extension, follow these steps:

1. **Download the Extension**:
   - The CRX file is available [here](https://github.com/microstarinc/AI-Powered-Phishing-Detector/raw/master/extension/PhisShield-extension.crx).

2. **Install the Extension**:
   - Follow the instructions for installing CRX files on your browser:
     - [How to Manually Install A Chrome Extension](https://www.thesslstore.com/blog/install-a-chrome-extension/)
     - [Load CRX files in browser](https://stackoverflow.com/questions/9931906/crx-file-install-in-chrome)
     - [Alternative Methods for Installing Browser Add-ons](https://docs.oracle.com/en/applications/enterprise-performance-management/smart-view/21.200/icgsv/browser_add_on_alternative_install.html)

3. **Clone the Repository**:
   - Clone the repository using the following command:
     ```
     git clone https://github.com/microstarinc/AI-Powered-Phishing-Detector.git
     ```

4. **Enable Developer Mode**:
   - Go to **Extensions** in your browser and enable **Developer mode**.
   - Click on **Load unpacked** and select the cloned repository to load the extension.
