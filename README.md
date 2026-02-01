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

## 🗂️ Repository Structure
├── data/               # Uber masked dataset
├── docs/               # Presentation of the case study
├── notebooks/          # Jupyter notebook containing analysis
└── README.md           # Project documentation

## 📊 Dataset
- **Source:** 
The dataset used for this analysis was provided as part of a Business Analytics Case Study. It contains masked real-world trip request data from Uber, focusing on two primary locations: the City and the Airport.

- **Schema:**  
| Attribute | Description | Data Type |
| :--- | :--- | :--- |
| **Request id** | A unique identifier for each ride request. | Integer |
| **Time of request** | The date and time at which the customer made the trip request. | Datetime |
| **Drop-off time** | The drop-off date and time (Null for uncompleted trips). | Datetime |
| **Pick-up point** | The point from which the request was made (Airport / City). | Categorical |
| **Driver id** | The unique identification number of the assigned driver. | Integer |
| **Status of the request** | Final status: `Trip Completed`, `Cancelled`, or `No Cars Available`. | Categorical |


