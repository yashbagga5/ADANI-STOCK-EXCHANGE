# ADANI-STOCK-EXCHANGE
Power BI | DAX | Excel | Data Visualization | Financial Analysis


📁 Overview
This project presents a dynamic and interactive stock market analysis dashboard focusing on the Adani Group companies listed on the NSE (National Stock Exchange of India). Built using Power BI, with data preparation in Microsoft Excel and advanced DAX (Data Analysis Expressions) for measures and calculated columns, this dashboard enables users to monitor, compare, and analyze stock trends, trading volumes, volatility, and performance metrics over time.


🎯 Project Objectives
- To build an insightful and interactive dashboard that visualizes stock movement of Adani companies.
- To track and compare daily closing prices, volumes, volatility, and moving averages.
- To implement DAX formulas for intelligent insights such as YoY change, % growth, and technical indicators.
- To identify patterns, trends, and anomalies for individual companies and the group as a whole.
- To create a tool for investors, analysts, and students to interpret financial time-series data easily.


📌 Key Features
- 📅 Date Slicer: Select specific time periods for customized analysis.
- 📈 Stock Price Trends: Line charts showing daily closing prices.
- 📊 Trading Volume: Bar charts representing the number of shares traded per day.
- 🔁 Moving Averages: 7-day, 14-day, and 30-day moving averages using DAX.
- 📉 Volatility Chart: Calculated standard deviation of price changes over rolling periods.
- 💹 Year-over-Year Comparison: % growth in stock value across months and years.
- 📍 Company-wise Filters: Interactive slicers to focus on a single Adani entity.
- 📑 Dynamic KPIs: Cards showing current price, highest high, lowest low, and average closing.


🏗 Tools & Technologies Used
- Tool/Technology:	Purpose
- Power BI:	Dashboard development and visualization
- Excel:	Data cleaning, formatting, and preprocessing
- DAX:	Custom measures, calculated columns, KPIs
- NSE India Website:	Source for historical stock data (CSV exports)

📦 Dataset Description
- Source: https://www.nseindia.com
- Time Frame: April 1, 2024 – April 1, 2025


Stocks Covered:
- Adani Enterprises
- Adani Green Energy
- Adani Ports
- Adani Total Gas
- Adani Transmission
- Adani Power
- ACC
- Ambuja Cements


Fields Used:
- Date
- Open
- High
- Low
- Close
- Volume
- %Change (calculated)


📐 DAX Formulas Used
Sample Calculated Measures


- 7-Day Moving Average = AVERAGEX(
    LASTN(7, FILTER('StockData', 'StockData'[Company] = SELECTEDVALUE('StockData'[Company]))),
    'StockData'[Close]
)


- Year-over-Year Change = 
VAR CurrentYear = YEAR(MAX('StockData'[Date]))
VAR PrevYear = CurrentYear - 1
RETURN
DIVIDE(
    CALCULATE(SUM('StockData'[Close]), YEAR('StockData'[Date]) = CurrentYear) -
    CALCULATE(SUM('StockData'[Close]), YEAR('StockData'[Date]) = PrevYear),
    CALCULATE(SUM('StockData'[Close]), YEAR('StockData'[Date]) = PrevYear)
)


- Volatility (30-day Std Dev) =
STDEVX.P(
    LASTN(30, FILTER('StockData', 'StockData'[Company] = SELECTEDVALUE('StockData'[Company]))),
    'StockData'[Close]
)


Dynamic KPI Cards
- Current Close Price
- Max High of Selected Period
- Avg Close of Selected Period
- % Gain or Loss over Selected Range

📂 Folder Structure
Adani-Dashboard
│
├── data/
│   └── adani_stock_data.xlsx
│
├── dashboard/
│   └── adani_stock_dashboard.pbix
│
├── screenshots/
│   ├── kpis-overview.png
│   └── volume-trends.png
│
├── README.md
└── LICENSE

🚀 Future Scope
- Integration of real-time stock feeds via API
- Addition of fundamental indicators (PE ratio, EPS, Market Cap)
- Sector benchmarking with peer companies
- Predictive analytics using machine learning models in Power BI or Python

🧠 Learnings
- Gained hands-on experience with financial time-series data
- Developed proficiency in DAX for complex business logic
- Understood the importance of storytelling through visualization
- Strengthened the ability to derive strategic insights from raw data

👤 Author
- Yash Bagga
- Data Enthusiast | Power BI Developer | Excel & DAX Learner
- Feel free to connect on LinkedIn or message for collaboration or feedback!
