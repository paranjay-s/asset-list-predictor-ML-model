# Asset List Predictor and Recommendation System

## Overview
This project implements a market prediction and recommendation system using machine learning and sentiment analysis. The notebook fetches stock data, processes it, trains predictive models, evaluates them, and generates stock recommendations. The model primarily focuses on **BankNifty** stocks.

## Google Colab Notebook-
https://colab.research.google.com/drive/1opjElTZgKaDMISfxPs--S3GdGD6vOEa-?usp=sharing

## Workflow
### **Data Collection**
- Historical stock data is fetched using `yfinance`.
- Stocks from the **BankNifty index** are selected.
- Data is cleaned and structured for analysis.
- One can change the stock ticker list and can get the same outputs for different stock lists like S&P 500, Nifty, etc

### **Feature Engineering**
- Technical indicators from the `ta` library are applied.
- Additional statistical and volume-based features are computed.
- Data is normalized and formatted for model training.

### **Target Generation**
- A binary classification target is created.
- Stocks are labeled as **1** (buy signal) if price conditions are met within a future window.
- Otherwise, they are labeled as **0**.
- One can also generate a 'sell side' list by just commenting out the other target function in the notebook and commenting the buy side target code snippet

### **Model Training & Evaluation**
- Multiple machine learning models are trained for each stock.
- Evaluation metrics are stored in `model_dict`.

### **Stock Recommendations**
- The system filters stocks based on model performance and technical signals.
- A `buy_list` is generated.
- Final recommendations are made using sentiment analysis.

## Detailed Explanation
### **Model Evaluation Dictionary (`model_dict`)**
`model_dict` stores evaluation results for each trained stock model such as classification reports, confusion matrix, ROC curve, cross validation scores for test data as well as simulated stress tests, etc

 **Sample Output:**  

![Screenshot (494)](https://github.com/user-attachments/assets/9c420444-b611-49dc-b3a5-500e99081c5e)
![Screenshot (495)](https://github.com/user-attachments/assets/33bba189-2478-4068-ad0a-197a302b54ff)
![Screenshot (496)](https://github.com/user-attachments/assets/4fca5d16-a2d8-45bd-bec4-481f84600072)




### **Buy List (`buy_list`)**
The `buy_list` contains stocks that passed technical and model-based filters.

 **Sample Output:**  
![Screenshot (497)](https://github.com/user-attachments/assets/5229980b-bae6-48a5-ab22-487e34f722e7)


### ** Recommendations (`recommendations`)**
The recommendations list suggests the best stocks to invest in based on related stocks from the same sector(used Nifty 500 here) and with high correlation with the stocks in buy_list

 **Sample Output:**  
![Screenshot (498)](https://github.com/user-attachments/assets/9efcef4b-5cc5-477b-8961-5f51abbbd405)


### **Sentiment Score & Analysis**
The sentiment score assesses market news and trends using crew ai, site scrapping, agentic ai.

 **Sample Output:**  
![screenshot ssa](https://github.com/user-attachments/assets/75662e11-8de4-4701-a3e4-b54726c60de0)


### **Final Stock Recommendation**
The final stock recommendation is based on model confidence and sentiment analysis.

 **Sample Output:**  
![Screenshot (499)](https://github.com/user-attachments/assets/316af6fc-ebcc-4a73-ad4c-e1d685996607)


## 🔗 Technologies Used
- **Python** (Pandas, NumPy, scikit-learn, yfinance, ta, optuna)
- **Machine Learning** (XGBoost Classifier)
- **Sentiment Analysis** (crew ai, BeautifulSoup)
- **Finance & Quantitative Analysis** (correlation, target defining)

## Flowchart
```mermaid
graph TD;
    A[Fetch Stock Data] --> B[Feature Engineering];
    B --> C[Generate Targets];
    C --> D[Train ML Models];
    D -->|Store Metrics| E[Model Evaluation Dictionary];
    D -->|Select Best Stocks| F[Buy List];
    F --> G[Generate Recommendations];
    G --> H[Sentiment Analysis];
    H --> I[Final Stock Recommendation];
```

##  How to Use
1. Run the Google Colab notebook.
2. Analyze the outputs and and review the stocks wisely!

---

### 📢 Disclaimer
This project is for educational purposes only. It does not constitute financial advice.
