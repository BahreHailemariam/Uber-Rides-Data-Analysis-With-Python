
# 🚗 Uber Rides Data Analysis using Python  

## 📊 Project Overview  
This project focuses on analyzing Uber ride data to uncover key insights about user demand, ride distribution, time-based trends, and fare optimization. Using Python for data cleaning, transformation, visualization, and statistical analysis, this project helps understand urban mobility patterns and improve operational efficiency for ride-sharing businesses.  

## 🧠 Business Problem  
Uber wants to optimize ride supply and pricing by analyzing:  
- Peak ride hours and high-demand locations  
- Seasonal and day-of-week trends  
- Impact of weather or holidays on rides  
- Trip duration vs distance and fare correlation  

These insights help Uber in:  
- Driver allocation during rush hours  
- Surge pricing optimization  
- Improving customer satisfaction  

## 🗂️ Data Sources  
1. Uber Ride Dataset (CSV) – includes fields such as:  
   - Date/Time, Lat, Lon, Base, Fare, Distance, Pickup_area  
2. External Datasets (Optional):  
   - Weather API data  
   - Public holiday dataset  

Dataset Example: [Uber Rides Dataset on Kaggle](https://www.kaggle.com/fivethirtyeight/uber-pickups-in-new-york-city)

## ⚙️ Tools & Technologies  
- Python: pandas, numpy, matplotlib, seaborn, plotly, scikit-learn  
- Power BI: visualization and reporting  
- GitHub: version control and documentation  

## 🧹 Python Workflow  

### 1. Data Source Identification  
```python
import pandas as pd
data = pd.read_csv("uber_rides.csv")
data.head()
```

### 2. Data Cleaning  
```python
data.drop_duplicates(inplace=True)
data['Date/Time'] = pd.to_datetime(data['Date/Time'])
data = data.dropna()
```

### 3. Data Transformation  
```python
data['hour'] = data['Date/Time'].dt.hour
data['day'] = data['Date/Time'].dt.day_name()
data['month'] = data['Date/Time'].dt.month_name()
```

### 4. Visualization & Insights  
```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.countplot(x='hour', data=data)
plt.title("Hourly Ride Demand")
plt.show()
```

**Insights:**  
- Highest demand observed between 5–9 PM.  
- Weekend evenings show the most rides.  
- Central city areas have the highest pickup density.  

### 5. Predictive Modeling (Optional)  
```python
from sklearn.linear_model import LinearRegression

X = data[['hour']]
y = data['Fare']
model = LinearRegression()
model.fit(X, y)
```

### 6. Recommendations  
- Increase driver incentives during 5–9 PM.  
- Apply surge pricing in central business districts.  
- Monitor weather data to adjust ride availability.  

## 📈 Power BI Dashboard  
- Clean and model data with Power Query  
- Create DAX measures for KPIs: Total Rides, Avg Fare, Peak Hour  
- Build heat maps, line charts, and trend analysis visuals  
- Apply RLS for regional security  

## 📘 Documentation & Governance  
- Version control with GitHub  
- Includes README.md, data dictionary, ETL pipeline notebook  
- Ensure anonymized location data and privacy compliance  

## 🚀 Project Folder Structure  
```
Uber-Rides-Analysis/
├── data/
│   └── uber_rides.csv
├── notebooks/
│   └── uber_analysis.ipynb
├── reports/
│   └── PowerBI_Dashboard.pbix
├── src/
│   ├── data_cleaning.py
│   ├── visualization.py
│   └── model_training.py
├── README.md
└── requirements.txt
```

## 📦 Installation  
```bash
pip install -r requirements.txt
```

## ▶️ Run Notebook  
```bash
jupyter notebook notebooks/uber_analysis.ipynb
```

## 📊 Example Outputs  
- Total Rides per Month: 1.2M  
- Peak Hour: 7 PM  
- Average Fare: $18.5  
- Top Pickup Zones: Manhattan, Brooklyn  

## 🧭 Future Enhancements  
- Real-time data streaming with Kafka  
- Predictive model integration with Flask/FastAPI  
- Automated daily Power BI refresh

## 👤 Author
**Bahre Hailemariam**  
📍 _Data Analyst & BI Developer_  
📩 [Email Adress](bahre.hail@gmail.com) | 🌐[Portfolio](https://bahre-hailemariam-data-analyst.crd.co/) |💼[LinkedIn](https://www.linkedin.com/in/bahre-hailemariam/) | 📊[GitHub](https://github.com/BahreHailemariam)
