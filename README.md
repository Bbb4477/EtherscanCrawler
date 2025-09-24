# Etherscan Crawler

This repository contains a Python-based tool designed to crawl and process live Ethereum transaction data from the Etherscan API. The crawler is built as an external utility to support real-time data collection for machine learning models, particularly for projects focused on blockchain analysis, such as fraud detection systems. This project to be particular ([Ethereum Fraud Detection Project](https://github.com/Bbb4477/IAP401_EthereumTransactionAnomalyDetection))


## Overview

The Etherscan Crawler automates the retrieval of Ethereum transaction data, including ETH and ERC20 token activities, and transforms it into a standardized format compatible with pre-existing datasets (e.g., 47-feature datasets like those from Kaggle). It is intended as a standalone component that can be integrated into larger projects, providing a flexible and efficient way to fetch and preprocess blockchain data for predictive modeling.

## Features

- **Real-Time Data Crawling**: Fetches live data from Etherscan API endpoints (`txlist` for ETH transactions, `tokentx` for ERC20 tokens).
- **Data Processing**: Converts raw API responses into a row format matching a 47-feature dataset structure, ready for model input.
- **Rate Limit Compliance**: Implements 0.2-second delays to adhere to Etherscan API restrictions.
- **Output Storage**: Saves processed data to CSV files (e.g., `out.csv`, `transactions.csv`).
- **Error Handling**: Includes robust error management for reliable operation.
- **Configuration**: Uses a `.env` file to securely manage API keys.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Bbb4477/EtherscanCrawler.git
   cd EtherscanCrawler
   ```
2. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```
3. Set up your Etherscan API key:
Obtain an API key from [Etherscan](https://etherscan.io/).
Create a .env file in the root directory with the following content:

    ```bash
    ETHERSCAN_API_KEY=your_api_key_here
    ```


### Usage

    usage: EtherscanAPI.py [-h] --address ADDRESS [--api_key API_KEY]

    options:
    -h, --help         show this help message and exit
    --address ADDRESS
    --api_key API_KEY

API key can be typed in manually without need of .env

### Output structure

    out.csv     #This file will be use for prediction with ML model later (The predict module is underway)
    transactions.csv        #[raw data] Transaction history of address, 
    erc20_transactions.csv  #[raw data] Erc20 Transaction history of 
    contracts.json          #[raw data] Involved address in transaction history

