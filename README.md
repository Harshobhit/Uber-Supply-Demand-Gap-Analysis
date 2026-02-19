## 🎯 Business Problem
In the ride-hailing industry, the "Supply-Demand Gap" is a critical bottleneck that directly affects revenue and user experience. When a request is not fulfilled, Uber faces two major operational failures:

1. **Cancellations:** Drivers frequently cancel requests, particularly for City-to-Airport trips during morning hours.
2. **Non-Availability:** A "No Cars Available" status occurs when demand outstrips supply, common at the Airport during evening peak hours.

### 📉 Impact on Uber
* **Revenue Loss:** Every unfulfilled request represents a direct loss of commission.
* **Customer Churn:** Poor reliability causes users to switch to competitors.
* **Inefficiency:** Misaligned driver distribution leads to wasted fuel and idle time.

**Objective:** To identify the temporal and geographic patterns behind these gaps and provide data-driven recommendations to improve ride fulfillment rates.

## 🛠️ Tech Stack

This project leverages the standard Python data science ecosystem to analyze and visualize urban mobility patterns.

* **Language:** `Python 3.x`
* **Data Manipulation:** `Pandas`, `NumPy`
* **Data Visualization:** `Matplotlib`, `Seaborn`
* **Environment:** `Jupyter Notebook`

## 📂 Repository Structure

```text
├── data/               # Uber masked dataset (CSV)
├── docs/               # Presentation and case study documentation
├── notebooks/          # Jupyter Notebook containing the end-to-end analysis
└── README.md           # Project overview and key findings
```

## 📊 Dataset
 **Source:**  
 
The dataset used for this analysis was provided as part of a Business Analytics Case Study. It contains masked real-world trip request data from Uber, focusing on two primary locations: the City and the Airport.

**Schema:**   

| Attribute | Description | Data Type |
| :--- | :--- | :--- |
| **Request id** | A unique identifier for each ride request. | Integer |
| **Time of request** | The date and time at which the customer made the trip request. | Datetime |
| **Drop-off time** | The drop-off date and time (Null for uncompleted trips). | Datetime |
| **Pick-up point** | The point from which the request was made (Airport / City). | Categorical |
| **Driver id** | The unique identification number of the assigned driver. | Integer |
| **Status of the request** | Final status: `Trip Completed`, `Cancelled`, or `No Cars Available`. | Categorical |

## 📌 Key Insights
* Morning Rush (5 AM - 10 AM): The primary issue is a high rate of Cancellations. Most requests during this period are from the City to the Airport.
* Evening Rush (5 PM - 10 PM): The primary issue is "No Cars Available". This is driven by a massive spike in demand for trips from the Airport to the City, coinciding with evening flight arrivals.
* Supply-Demand Gap: The gap is most severe during the evening hours at the airport, where the number of requests significantly exceeds the number of available drivers.
* **Root Causes:**
  * Drivers often cancel city-to-airport trips in the morning because they may face long idle times at the airport before getting a return passenger.
  * In the evening, there is a shortage of cars at the airport because most drivers are occupied with high demand within the city.
    
## 🚀 Future Work & Recommendations
* **Operational Improvements:**
 * Encourage drivers to move toward the airport between **4 PM and 12 AM** to meet the evening surge.
 * Provide specific financial incentives for drivers completing airport trips during peak hours to compensate for potential wait times.
 * Set a daily threshold for driver cancellations to improve reliability during the morning rush.

* **Data-Driven Strategies:**
 * Integrate real-time flight arrival data to notify drivers 15 minutes before large clusters of flights land, reducing their idle time.
 * Analyze historical cancellation patterns to create a "Priority Queue" at the airport for drivers who consistently complete city-to-airport trips.

* **Predictive Modeling:**
 * Develop a machine learning model to predict the supply-demand gap by the hour.
 * Implement automated surge pricing and driver notifications based on predicted demand bursts.
   
## 🚀 How to Reproduce
Follow these steps to set up the environment and run the analysis on your local machine:

* **Step 1: Clone the Repository**
  * Open your terminal and run:
    ```bash
    git clone [https://github.com/Harshobhit/Uber-Supply-Demand-Gap-Analysis.git](https://github.com/Harshobhit/Uber-Supply-Demand-Gap-Analysis.git)
    cd Uber-Supply-Demand-Gap-Analysis
    ```

* **Step 2: Set Up a Virtual Environment (Recommended)**
  * Create and activate a virtual environment to keep dependencies isolated:
    ```bash
    # Windows
    python -m venv venv
    .\venv\Scripts\activate

    # Mac/Linux
    python3 -m venv venv
    source venv/bin/activate
    ```

* **Step 3: Install Dependencies**
  * Use the `requirements.txt` file to install all necessary libraries:
    ```bash
    pip install -r requirements.txt
    ```

* **Step 4: Data Preparation**
  * Ensure the dataset `Uber Request Data.csv` is located in the `data/` folder.
  * Your directory structure should look like this:
    * `notebooks/uber_supply_demand_eda.ipynb`
    * `data/Uber Request Data.csv`

* **Step 5: Run the Analysis**
  * Launch the Jupyter interface:
    ```bash
    jupyter notebook
    ```
  * Navigate to the `notebooks/` directory and open `uber_supply_demand_eda.ipynb`.
  * Select **Cell > Run All** to generate the visualizations and insights.

