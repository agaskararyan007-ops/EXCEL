# 🚖 OLA Ride Sales Dashboard | Microsoft Excel

## 🎯 Project Objective

The objective of this dashboard is to analyze ride-hailing performance and provide insights into ride volume, sales, net revenue, platform commission, cancellations, service types, regional and city performance, and payment preferences to support data-driven business decisions.

---

## 📊 Dataset Description

The dataset contains 15,000 ride records from 1 January 2023 to 31 December 2024, covering 7 cities, 4 regions and 5 service types. It is a synthetic practice dataset modelled on ride-hailing platforms such as Ola, Uber and Rapido, created to practise data cleaning, pivot tables and dashboard design. Each row represents one ride booking and includes fare, discount, distance, duration, ride status, customer type, payment mode, driver rating and the commission earned by the platform.

### Dataset Columns

| Column        | Description                                                  |
| ------------- | ------------------------------------------------------------ |
| ride_id       | Unique identifier for each ride                              |
| region        | Sales region (East, North, South, West)                      |
| city          | City where the ride took place                               |
| service_type  | Auto, Bike, Cab Mini, Cab Sedan, or Cab XL                   |
| fare          | Ride fare before discount (₹)                                |
| discount      | Discount applied to the fare, stored as a fraction (0.15 = 15%) |
| distance_km   | Distance travelled in kilometres                             |
| duration_min  | Duration of the ride in minutes                              |
| ride_date     | Date of the ride                                             |
| time_slot     | Morning, Afternoon, Evening, or Night                        |
| ride_status   | Completed or Cancelled                                       |
| customer_type | New, Regular, or Pass Holder                                 |
| payment_mode  | UPI, Cash, Card, Wallet, or Unknown                          |
| driver_rating | Rating given to the driver (1 to 5)                          |
| commission    | Commission earned by the platform on the ride (₹)            |

Cancelled rides have a fare, distance and duration of 0 and no driver rating.

---

## 🧹 Data Cleaning

The raw file contained duplicate rows, invalid values, inconsistent text (for example `upi`, `Bengaluru`, `CAB MINI`), numbers and dates stored as text, and missing regions and payment modes. These were fixed before analysis:

* Removed duplicate and invalid rows (negative fares or distances, impossible ratings and durations, dates outside 2023–2024).
* Standardized city, service type, time slot, ride status, customer type and payment mode names.
* Converted fares, distances, durations, discounts and dates to proper numeric and date formats.
* Filled missing regions using a city-to-region lookup, and labelled missing payment modes as "Unknown".

---

## 🧮 Calculated Fields

All revenue figures use completed rides only.

* **Month** – Grouped from ride_date in the pivot tables.
* **Net Revenue** – Fare after discount: fare × (1 − discount).
* **Discount Amount** – Fare × discount.
* **Net Revenue per KM** – Net revenue divided by total kilometres travelled.
* **Cancellation Rate** – Cancelled rides divided by total rides.
* **Average Fare per Ride** – Average fare of completed rides.

---

## 📈 Dashboard Features

### KPI Cards

* Total Rides
* Net Revenue
* Average Fare per Ride
* Net Revenue per KM
* Cancellation Rate
* Average Driver Rating

### Charts

* 📊 Commission by City and Service Type
* 🥧 Sales by Region
* 🍩 Sales by City
* 📊 Payment Mode Share
* 📊 Commission, Discount and Fare by Service Type
* 📈 Rides and Fare by Month

---

## 🗂️ Workbook Structure

| Sheet         | Purpose                                                          |
| ------------- | ---------------------------------------------------------------- |
| Ride Data     | The cleaned dataset (15,000 rows)                                |
| Q&A           | Business questions answered with Excel formulas                  |
| Pivot Tables  | Pivot tables and pivot charts that feed the dashboard            |
| OLA DASHBOARD | The final dashboard with KPI cards and charts                    |

---

## 📊 Dashboard Preview

<img width="1276" height="622" alt="Screenshot 2026-11-02 132045" src="https://github.com/user-attachments/assets/3b07892e-2181-4e61-8d17-c431e1877237" />


---

## 🔍 Key Insights

* **Total Rides:** 15,000 (13,800 completed and 1,200 cancelled)
* **Total Sales (gross fare):** ₹23,08,765
* **Total Net Revenue:** ₹20,79,020
* **Total Discount Given:** ₹2,29,746 (about 10% of sales)
* **Total Commission:** ₹3,94,344 (about 17.1% of sales and 19.0% of net revenue)
* **Average Fare per Ride:** ₹167.30
* **Net Revenue per KM:** ₹19.24
* **Cancellation Rate:** 8.0%
* **Average Driver Rating:** 4.38

### Regional Performance

* **South** is the highest-performing region, generating about **₹9.79 lakh** in sales (42.4% of the total).
* **West** follows with about **₹6.86 lakh** (29.7%), then **North** with about **₹4.62 lakh** (20.0%).
* **East** has the lowest sales at about **₹1.83 lakh** (7.9%).
* Regional totals largely reflect the number of cities in each region: South includes Bangalore, Hyderabad and Chennai, while East has only Kolkata.

### City Performance

* **Mumbai, Delhi and Bangalore** are almost equal, each generating about **₹4.6 lakh** in sales (around 20% of the total each).
* **Hyderabad** (12.5%), **Chennai** (9.9%) and **Pune** (9.6%) form the middle group.
* **Kolkata** has the lowest sales at about **₹1.83 lakh** (7.9%) and the lowest commission at about **₹31,462**.
* Commission follows the same pattern as sales across cities.

### Service Type Performance

* **Cab Mini** has the highest sales at about **₹5.20 lakh**, closely followed by **Auto** at about **₹5.14 lakh**.
* **Bike** has the lowest sales at about **₹3.62 lakh**, even though it has the most completed rides (4,117).
* **Cab Sedan** earns the highest commission at about **₹98,760**, followed by **Cab XL** (about ₹93,912) and **Cab Mini** (about ₹93,253).
* **Bike** earns the lowest commission at about **₹39,060**.

### Payment Mode

* **UPI** is the most-used payment mode at about **44.6%** of rides.
* **Cash** accounts for about **24.5%**, **Wallet** about **15.2%** and **Card** about **14.7%**.
* About **1.1%** of rides have no recorded payment mode ("Unknown").

### Monthly Trend

* Ride volume and sales stay fairly steady through the year, with no sharp peaks or drops (figures combine 2023 and 2024 by calendar month).
* **December** has the most rides (1,313), followed by **May** (1,305).
* **February** has the fewest rides (1,182) and the lowest sales at about **₹1.85 lakh**.
* **November** has the highest monthly sales at about **₹2.00 lakh**.

---

## ❓ Business Questions Answered

* What are the total rides, total sales and total net revenue?
* How much discount has been given, and how much commission did the platform earn?
* What is the cancellation rate?
* What is the average fare per ride and the net revenue per kilometre?
* Which region generates the highest sales?
* Which cities generate the highest and lowest sales?
* Which service type earns the most sales and the most commission?
* Which payment mode is used the most?
* How do rides and sales change month by month?
* How do commission and sales vary across cities and service types?

---

## 📝 Conclusion

The OLA Ride Dashboard provides a consolidated view of ride volume, sales, net revenue, commission, cancellations, and customer payment behaviour.

The analysis shows that the business handled **15,000 rides**, generating **₹23.09 lakh in sales**, **₹20.79 lakh in net revenue** and **₹3.94 lakh in commission**, with an **8.0% cancellation rate** and an average driver rating of **4.38**. Mumbai, Delhi and Bangalore lead city-level sales almost equally, while South is the strongest region overall.

Cab Mini and Auto lead on sales, Cab Sedan leads on commission, and Bike brings the most rides but the lowest earnings. UPI is by far the most-used payment mode, and monthly performance is steady with no strong seasonal swings.

Overall, the dashboard helps identify **high-performing regions, cities and service types, payment preferences and monthly patterns**, making it easier to monitor performance and support data-driven decisions.

---

## 🛠️ Tools & Technologies

* Microsoft Excel
* Pivot Tables
* Pivot Charts
* Excel Formulas
* Data Cleaning
* Dashboard Design
* Data Analysis
