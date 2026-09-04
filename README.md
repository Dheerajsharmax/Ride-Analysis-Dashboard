
# 🚕 Rides Analysis Dashboard

<img width="1302" height="727" alt="image" src="https://github.com/user-attachments/assets/6162e363-d70d-4c7b-b3fa-b79346827fef" />


## End-to-End Power BI Dashboard Documentation

---

# 1. Project Title

**Rides Analysis Dashboard**

### Technology Used

* **Microsoft Power BI**
* Power Query for data preparation
* DAX for analytical calculations
* Power BI Data Model for relationships
* Interactive slicers and visualizations
* Dynamic image URLs for vehicle-type visualization

### Project Type

**Business Intelligence / Data Analytics**

---

# 2. Project Overview

The **Rides Analysis Dashboard** is an interactive Business Intelligence solution developed in Power BI to analyze ride-service performance across multiple business dimensions.

The dashboard provides a consolidated view of:

* Ride volume
* Revenue
* Distance covered
* Customer ratings
* Successful rides
* Driver performance
* Vehicle performance
* Monthly revenue trends
* Payment methods
* Referral usage
* City-wise tips
* Ride status

The dashboard allows users to interactively filter the analysis using **City, Vehicle Type, Payment Method, Referral Used, and Ride Status**.

The objective is to transform raw ride-related data into meaningful business insights that can help management understand operational performance, revenue generation, driver contribution, customer behavior, and geographic performance.

---

# 3. Business Problem

A ride-service business generates data from multiple operational activities such as:

* Rides
* Drivers
* Users
* Payments
* Support tickets

When this information is stored separately, it becomes difficult to understand the overall business performance.

For example, management may want to answer questions such as:

* How many rides are being completed?
* How much revenue is being generated?
* Which vehicle type performs best?
* Which city generates the highest revenue or tips?
* Which drivers generate the most revenue?
* How is revenue changing month by month?
* How much distance is being covered?
* What is the average customer rating?
* How does performance change for cancelled, completed, or no-show rides?
* Does referral usage affect customer activity?
* Which payment methods are being used?

The **Rides Analysis Dashboard** addresses these requirements by bringing the relevant information into a single interactive analytical environment.

---

# 4. Project Objectives

The major objectives of the dashboard are:

1. Analyze total ride volume.
2. Monitor total revenue.
3. Analyze total distance covered.
4. Monitor customer/service rating.
5. Measure successful ride performance.
6. Compare current and previous month revenue.
7. Identify top-performing drivers.
8. Analyze monthly ride and revenue trends.
9. Compare vehicle categories.
10. Analyze city-level performance.
11. Analyze payment-method behavior.
12. Analyze referral usage.
13. Analyze ride status.
14. Analyze city-wise tips.
15. Provide an easy-to-use interactive dashboard for business users.

---

# 5. Dataset Overview

The project uses a **Rides_Details** dataset consisting of multiple related tables.

The main tables used in the analytical model are:

1. **Rides**
2. **Drivers**
3. **Users**
4. **Payments**
5. **SupportTickets / Support_Tickets**
6. **Date Table**
7. **Image Data**
8. **Measures**

The **Rides** table acts as the central table for ride-level analysis.

---

# 6. Dataset Tables

## 6.1 Rides Table

The Rides table contains ride-level transactional information.

The previously defined ride dataset contains the following fields:

| Column         | Description                                         |
| -------------- | --------------------------------------------------- |
| RideID         | Unique identifier for each ride                     |
| RideDate       | Date on which the ride occurred                     |
| UserID         | Identifier of the customer/user                     |
| DriverID       | Identifier of the driver                            |
| Start_Location | Starting location of the ride                       |
| End_Location   | Destination/end location                            |
| Distance_km    | Distance travelled in kilometers                    |
| Duration_min   | Ride duration in minutes                            |
| Fare           | Fare associated with the ride                       |
| Tip            | Tip received for the ride                           |
| Rating         | Customer/service rating                             |
| PaymentMethod  | Payment method used                                 |
| Revenue        | Revenue generated from the ride                     |
| Status         | Ride status such as Completed, Cancelled or No-show |

### Role in Dashboard

The Rides table provides the majority of the dashboard's core metrics, including:

* Total Rides
* Revenue
* Distance
* Rating
* Tips
* Ride Status
* Payment Method
* Ride Date

---

# 7. Drivers Table

The Drivers table contains driver-related information.

Fields visible in the Power BI model include:

| Column      | Description                            |
| ----------- | -------------------------------------- |
| DriverID    | Unique driver identifier               |
| City        | Driver's associated city               |
| FName       | Driver first name                      |
| IsActive    | Indicates whether the driver is active |
| JoinDate    | Driver joining date                    |
| Name        | Driver name                            |
| TotalRides  | Total rides associated with the driver |
| VehicleType | Type of vehicle used                   |

<img width="366" height="265" alt="image" src="https://github.com/user-attachments/assets/3a0d52e5-2abf-4dd2-87ac-2b9837264da1" />


### Role in Dashboard

The Drivers table supports:

* Driver analysis
* Active driver analysis
* Non-active driver analysis
* Top 5 drivers by revenue
* Vehicle-type analysis
* City analysis

---

# 8. Users Table

The Users table contains customer information.

Fields visible in the model include:

| Column       | Description                          |
| ------------ | ------------------------------------ |
| UserID       | Unique customer identifier           |
| City         | User's city                          |
| FirstName    | Customer first name                  |
| LastName     | Customer last name                   |
| Name         | Customer name                        |
| JoinDate     | Customer joining date                |
| ReferralUsed | Whether referral was used            |
| TotalRides   | Total rides associated with the user |

### Role in Dashboard

The Users table enables analysis related to:

* Customer activity
* Referral usage
* City
* Total rides
* Customer segmentation

---

# 9. Payments Table

The Payments table contains payment transaction information.

Fields visible in the model include:

| Column        | Description                 |
| ------------- | --------------------------- |
| PaymentID     | Unique payment identifier   |
| RideID        | Associated ride             |
| PaymentDate   | Date of payment             |
| PaymentMethod | Payment channel             |
| Amount        | Payment amount              |
| PromoApplied  | Indicates promotional usage |
| Status        | Payment status              |

### Role in Dashboard

The Payments table allows analysis based on:

* Cash
* Credit Card
* UPI
* Wallet

It also provides the relationship between payment transactions and rides.

---

# 10. Support Tickets Table

The SupportTickets table contains customer-support information.

Fields visible in the model include:

| Column    | Description                         |
| --------- | ----------------------------------- |
| TicketID  | Unique support-ticket identifier    |
| RideID    | Ride associated with the ticket     |
| UserID    | Customer associated with the ticket |
| IssueType | Type of customer issue              |
| OpenDate  | Ticket opening date                 |
| CloseDate | Ticket closing date                 |
| Status    | Ticket status                       |

### Role in Analysis

This table can support future analysis of:

* Customer complaints
* Ride-related issues
* Support volume
* Ticket status
* Issue categories

It is connected to the Rides table using **RideID**.

---

# 11. Date Table

A dedicated **Date Table** is included in the Power BI model.

Visible fields include:

* Date
* Rider Per KM

The Date Table is particularly important for time-based analysis.

It supports:

* Monthly analysis
* Yearly analysis
* Current-month analysis
* Previous-month analysis
* Revenue trends
* Ride trends

The Rides table is connected to the Date Table through:

**Rides[RideDate] → Date Table[Date]**

---

# 12. Image Data Table

The Image Data table is a special supporting table used to display vehicle images dynamically.

It contains:

| Column      | Description                   |
| ----------- | ----------------------------- |
| VehicleType | Vehicle category              |
| Image link  | URL/link of the vehicle image |

Vehicle categories include:

* Auto
* Bike
* Hatchback
* Sedan
* SUV

### Purpose

When a vehicle type is selected, the corresponding vehicle image can be displayed in the dashboard.

For example:

**Auto → Auto image**

**Bike → Bike image**

**Sedan → Sedan image**

This makes the dashboard more visually interactive.

---

# 13. Measures Table

A dedicated **Measures** table is used to store DAX measures.

One visible measure is:

**Last Month Revenue**

Other dashboard KPIs are also measure-driven.

Keeping measures in a dedicated table makes the Power BI model easier to organize and maintain.

---

# 14. Data Model

The Power BI model is centered around the **Rides** table.

The main relationships shown in the supplied Power BI model are:

| From                   | Relationship | To                      |
| ---------------------- | ------------ | ----------------------- |
| Drivers[VehicleType]   | Many-to-One  | Image Data[VehicleType] |
| Payments[RideID]       | Many-to-One  | Rides[RideID]           |
| Rides[DriverID]        | Many-to-One  | Drivers[DriverID]       |
| Rides[RideDate]        | Many-to-One  | Date Table[Date]        |
| SupportTickets[RideID] | Many-to-One  | Rides[RideID]           |
| Users[UserID]          | Many-to-Many | Rides[UserID]           |

All relationships shown in the screenshot are **Active**.

---

# 15. Relationship Explanation

## Drivers → Rides

**Rides[DriverID] → Drivers[DriverID]**

This relationship allows ride data to be analyzed according to driver attributes.

For example:

* Driver revenue
* Driver rides
* Driver city
* Vehicle type
* Active/non-active driver analysis

---

## Payments → Rides

**Payments[RideID] → Rides[RideID]**

This connects payment transactions with individual rides.

It enables payment-related filtering and analysis.

---

## Rides → Date Table

**Rides[RideDate] → Date Table[Date]**

This relationship enables time-based analysis.

It is important for:

* Revenue by month
* Revenue by year
* Previous-month revenue
* Current-month revenue
* Trend analysis

---

## SupportTickets → Rides

**SupportTickets[RideID] → Rides[RideID]**

This connects support activity to ride transactions.

It provides an opportunity to analyze customer-service issues against ride activity.

---

## Users ↔ Rides

The supplied model shows a **Many-to-Many** relationship between:

**Users[UserID] ↔ Rides[UserID]**

This connects users with their ride activity.

---

## Drivers → Image Data

The model connects:

**Drivers[VehicleType] → Image Data[VehicleType]**

This supports the dashboard's dynamic vehicle-image functionality.

---

# 16. Data Preparation

The overall data-preparation workflow consists of:

### Step 1 — Import Data

Import the required tables into Power BI.

### Step 2 — Validate Data Types

Ensure appropriate data types for:

* Dates
* Numeric values
* IDs
* Text fields
* Revenue
* Distance
* Rating

### Step 3 — Identify Keys

Important keys include:

* RideID
* DriverID
* UserID
* PaymentID
* TicketID

### Step 4 — Create Relationships

Connect the tables using their respective keys.

### Step 5 — Create Date Table

Create/use a dedicated Date Table for time intelligence.

### Step 6 — Create Image Mapping

Create the Image Data table with:

* VehicleType
* Image link

### Step 7 — Create DAX Measures

Create reusable measures for dashboard KPIs.

### Step 8 — Build Visualizations

Create the required KPI cards, charts and interactive controls.

### Step 9 — Validate Dashboard

Check whether filtering changes the relevant KPIs and visuals correctly.

---

# 17. Dashboard Design

The dashboard is titled:

# **Rides Analysis Dashboard**

The dashboard has a modern analytical layout containing:

* Header
* KPI cards
* Status selectors
* Vehicle selectors
* City slicer
* Payment-method slicer
* Referral slicer
* Dynamic vehicle image
* Revenue trend
* Driver ranking
* Monthly revenue/ride trend
* City-wise tip analysis

---

# 18. KPI Cards

The dashboard contains the following major KPIs.

## 18.1 Total Rides by Vehicle

This KPI measures the ride volume associated with the selected vehicle context.

### Business Purpose

It helps identify the scale of ride activity associated with different vehicle categories.

---

## 18.2 Total Revenue

This KPI measures total revenue generated within the current filter context.

### Business Purpose

Revenue is one of the primary financial performance indicators.

---

## 18.3 Total Distance Covered KM

This KPI measures the total distance covered by rides.

### Business Purpose

It helps understand operational activity and utilization.

---

## 18.4 Rating

This KPI displays the rating metric based on the ride rating data.

### Business Purpose

It helps monitor service quality and customer experience.

---

## 18.5 Successful Ride Ratio

This KPI measures the proportion of successful rides according to the dashboard's calculation logic.

### Business Purpose

It helps evaluate ride completion performance.

---

## 18.6 Last Month Revenue

This KPI shows revenue from the previous month relative to the current analysis period.

### Business Purpose

It provides a historical benchmark for revenue comparison.

---

# 19. KPI Snapshot — Bangalore + Auto

The screenshot you provided represents the dashboard with:

### City:

**Bangalore**

### Vehicle:

**Auto**

The displayed KPI values are:

| KPI                    |       Value |
| ---------------------- | ----------: |
| Total Rides by Vehicle |    **160K** |
| Total Revenue          | **$97.40K** |
| Total Distance Covered |   **4K KM** |
| Rating                 |    **2.94** |
| Successful Ride Ratio  |  **100.0%** |
| Last Month Revenue     | **$13.52K** |

These values should be interpreted specifically as the **displayed filtered dashboard state**, not automatically as universal values for the entire dataset.

---

# 20. Dashboard Filters

The dashboard provides several interactive filters.

## City

Available cities:

* Bangalore
* Chennai
* Delhi
* Hyderabad
* Mumbai
* Pune

### Purpose

Allows users to analyze performance geographically.

---

# 21. Vehicle Type Filter

Available vehicle types:

* Auto
* Bike
* Hatchback
* Sedan
* SUV

### Purpose

Allows comparison between vehicle categories.

The selected vehicle also controls the vehicle image displayed in the dashboard.

---

# 22. Payment Method Filter

Available payment methods:

* Cash
* Credit Card
* UPI
* Wallet

### Purpose

Allows users to understand ride/payment behavior by payment channel.

---

# 23. Referral Used Filter

Available values:

* NO
* YES

### Purpose

Allows comparison between users who used a referral and those who did not.

---

# 24. Ride Status Filter

The dashboard provides ride-status selections:

* Cancelled
* Completed
* No-show

### Purpose

This allows users to analyze different ride outcomes.

For example:

**Completed** → successful rides

**Cancelled** → rides that did not proceed successfully

**No-show** → rides where the expected participant did not show up

---

# 25. Revenue Trend Visual

## Chart Title

**Last Month Revenue Vs Current Month Total Revenue**

### Description

This visual compares revenue trends between:

* Last Month Revenue
* Current Month Total Revenue

The chart uses a time-based daily trend.

### Business Purpose

This visual helps identify:

* Revenue peaks
* Revenue declines
* Daily fluctuations
* Current vs previous month behavior

It allows management to understand whether current revenue performance is improving or declining compared with the previous period.

---

# 26. Top 5 Driver by Revenue

## Chart Title

**Top 5 Driver By Revenue**

This visual ranks the five drivers generating the highest revenue.

The screenshot shows approximately:

| Driver       | Revenue |
| ------------ | ------: |
| Vikram Yadav |   3.86K |
| Ritika Patel |   3.55K |
| Anjali Joshi |   3.50K |
| Vikram Joshi |   3.24K |
| Ravi Sharma  |   3.11K |

### Business Purpose

This visual helps identify the strongest driver contributors.

Management can use this analysis to:

* Identify high-performing drivers
* Compare driver contributions
* Investigate performance differences
* Recognize high revenue contributors

---

# 27. Monthly Revenue & Ride Analysis

## Chart Title

**Total Revenue and Total Rides by Year and Month**

This visual analyzes performance across different months.

The screenshot displays a monthly trend for **2025**, including:

* February
* March
* April
* May
* June
* July

### Business Purpose

It helps identify:

* Revenue growth
* Revenue decline
* Monthly fluctuations
* High-performing months
* Low-performing months
* Seasonal patterns

The supplied dashboard shows a visible rise toward June followed by a significant decline in July.

---

# 28. Total Tips by City

The dashboard contains a donut chart titled:

**Total Tips**

The chart provides a city-level breakdown of tips.

Visible values include approximately:

| City      | Total Tips |
| --------- | ---------: |
| Chennai   |      2.08K |
| Pune      |      1.90K |
| Delhi     |      1.72K |
| Bangalore |      1.68K |
| Mumbai    |      1.59K |
| Hyderabad |      1.32K |

### Total Tips Displayed

**8.10K**

### Business Purpose

This visual helps understand how tip contribution differs between cities.

Tips can provide an additional indicator of customer engagement and perceived service value.

---

# 29. Dynamic Vehicle Image

One of the unique features of the dashboard is the dynamic vehicle image.

The dashboard displays an image corresponding to the selected vehicle.

For example:

| Selected Vehicle | Displayed Image |
| ---------------- | --------------- |
| Auto             | Auto image      |
| Bike             | Bike image      |
| Hatchback        | Hatchback image |
| Sedan            | Sedan image     |
| SUV              | SUV image       |

This functionality is supported through the:

**Drivers → Image Data**

relationship based on:

**VehicleType**

The Image Data table stores the image URL/link.

---

# 30. Dashboard Interactivity

The dashboard is not a static report.

Users can interact with the dashboard by selecting different combinations of filters.

For example:

### Scenario 1

**City = Bangalore**

**Vehicle = Auto**

The dashboard displays the Bangalore Auto analysis.

### Scenario 2

**City = Delhi**

**Vehicle = Sedan**

The dashboard updates to the selected segment.

### Scenario 3

**Vehicle = SUV**

The dynamic image changes to the SUV image.

### Scenario 4

**Payment Method = UPI**

The dashboard can be analyzed according to UPI-related transactions.

### Scenario 5

**Referral Used = YES**

The analysis can focus on users who came through referral usage.

### Scenario 6

**Status = Completed**

The dashboard can focus on completed rides.

This filter-driven design enables users to perform **self-service analysis** without creating separate reports for every segment.

---

# 31. DAX Measure Layer

The dashboard uses DAX-based calculations.

The visible Measures table contains:

**Last Month Revenue**

The major KPI calculations conceptually include:

### Total Rides

Counts rides in the current filter context.

### Total Revenue

Aggregates revenue from the relevant ride records.

### Total Distance

Aggregates `Distance_km`.

### Rating

Calculates the dashboard's rating metric based on the rating field and selected filter context.

### Successful Ride Ratio

Calculates successful/completed ride performance relative to the relevant ride population according to the dashboard's logic.

### Last Month Revenue

Uses the Date Table to calculate revenue for the previous month.

---

# 32. Time Intelligence

Time-based analysis is one of the important components of the dashboard.

The Date Table allows the dashboard to perform:

* Year analysis
* Month analysis
* Current-month analysis
* Previous-month analysis
* Revenue trend analysis
* Ride trend analysis

The relationship:

**Rides[RideDate] → Date Table[Date]**

provides the foundation for this analysis.

---

# 33. Business Questions Answered by the Dashboard

The dashboard is designed to answer questions such as:

### Ride Performance

1. How many rides are being completed?
2. How many rides are associated with each vehicle?
3. What is the total ride volume?

### Revenue

4. How much revenue is generated?
5. How does current-month revenue compare with previous-month revenue?
6. Which drivers generate the highest revenue?
7. How does revenue change month by month?

### Operations

8. How much distance has been covered?
9. What is the successful ride ratio?
10. How do cancelled, completed and no-show rides compare?

### Driver Analysis

11. Who are the top five drivers by revenue?
12. How does driver performance differ?

### Vehicle Analysis

13. Which vehicle category is being analyzed?
14. How does performance change between Auto, Bike, Hatchback, Sedan and SUV?

### Geographic Analysis

15. How does performance differ between Bangalore, Chennai, Delhi, Hyderabad, Mumbai and Pune?
16. Which city contributes the highest tips?

### Customer/Marketing

17. How does performance vary based on referral usage?

### Payment Analysis

18. How does ride activity differ across Cash, Credit Card, UPI and Wallet?

---

# 34. Key Insights from the Provided Dashboard State

For the supplied **Bangalore + Auto** dashboard state:

### Revenue

The dashboard displays:

**Total Revenue = $97.40K**

and:

**Last Month Revenue = $13.52K**

This provides a direct comparison between the overall/current analytical revenue context and the previous-month KPI.

---

### Ride Volume

The dashboard displays:

**Total Rides by Vehicle = 160K**

This indicates substantial ride activity within the displayed analytical context.

---

### Distance

The dashboard displays:

**4K KM**

for total distance covered.

---

### Rating

The displayed rating is:

**2.94**

This provides a customer/service-quality indicator.

---

### Successful Ride Ratio

The dashboard displays:

**100.0%**

for Successful Ride Ratio in the illustrated filter state.

---

### Driver Performance

The Top 5 Driver visual shows the leading displayed driver at approximately:

**3.86K revenue**

followed by other high-performing drivers.

---

### Monthly Trend

The monthly revenue visual shows a noticeable increase through the displayed months, reaching a visible high around **June 2025**, followed by a sharp decline in **July 2025**.

This type of pattern should be investigated further to understand whether it is caused by:

* Ride volume
* Seasonality
* Vehicle mix
* City performance
* Revenue changes
* Data-period effects

---

### Tips

The dashboard displays:

**Total Tips = 8.10K**

with contributions from the six cities.

Chennai has the highest displayed tip value at approximately:

**2.08K**

while Hyderabad has the lowest displayed value at approximately:

**1.32K** among the cities shown.

---

# 35. Business Recommendations

Based on the dashboard structure and available analysis, the business can use the dashboard to:

### 1. Monitor Revenue

Track revenue regularly and compare current performance with previous months.

### 2. Investigate Revenue Drops

When monthly revenue declines, use City and Vehicle filters to identify the segment responsible.

### 3. Analyze Driver Performance

Use the Top 5 Driver analysis to identify high-performing drivers and understand what drives their performance.

### 4. Optimize Vehicle Mix

Compare Auto, Bike, Hatchback, Sedan and SUV performance to understand vehicle demand and revenue contribution.

### 5. Monitor Ride Outcomes

Analyze Completed, Cancelled and No-show rides separately.

### 6. Improve Customer Experience

Track Rating and Successful Ride Ratio alongside revenue and ride volume.

### 7. Analyze Payment Behavior

Compare Cash, Credit Card, UPI and Wallet usage.

### 8. Evaluate Referral Performance

Compare users with and without referral usage.

### 9. Analyze Geographic Performance

Compare cities to identify high-performing and underperforming locations.

### 10. Monitor Tips

City-wise tip analysis can provide an additional indicator of customer satisfaction and service engagement.

---

# 36. Technical Architecture

The overall architecture can be represented as:

**Raw Data**

↓

**Data Preparation**

↓

**Power BI Data Model**

↓

**Relationships**

↓

**DAX Measures**

↓

**KPI Cards**

↓

**Interactive Visualizations**

↓

**Filters / Slicers**

↓

**Business Insights**

↓

**Decision Making**

---

# 37. End-to-End Power BI Development Process

## Phase 1 — Requirement Understanding

Identify the business questions that need to be answered.

---

## Phase 2 — Data Collection

Collect the required tables:

* Rides
* Drivers
* Users
* Payments
* SupportTickets

---

## Phase 3 — Data Preparation

Clean and validate the data.

Check:

* Missing values
* Data types
* Duplicate records
* IDs
* Date fields
* Numeric fields
* Text fields

---

## Phase 4 — Data Modeling

Build relationships between tables.

The Rides table becomes the central analytical table.

---

## Phase 5 — Date Modeling

Create/connect the Date Table.

This enables proper time-based calculations.

---

## Phase 6 — DAX Development

Create reusable measures for:

* Total rides
* Total revenue
* Total distance
* Rating
* Successful ride ratio
* Last month revenue
* Other required analytical calculations

---

## Phase 7 — Dashboard Development

Create:

* KPI Cards
* Line/area charts
* Bar chart
* Donut chart
* Slicers
* Dynamic vehicle image

---

## Phase 8 — Interactivity

Add:

* City filter
* Vehicle filter
* Payment filter
* Referral filter
* Ride-status filter

---

## Phase 9 — Validation

Check:

* KPI calculations
* Filter interactions
* Relationship behavior
* Date calculations
* Dynamic images
* Visual consistency

---

## Phase 10 — Business Analysis

Interpret the dashboard results and identify:

* Revenue trends
* Driver performance
* Vehicle performance
* Geographic differences
* Customer behavior
* Operational patterns

---

# 38. Dashboard Strengths

The major strengths of the dashboard are:

### ✔ Interactive

Users can dynamically filter the analysis.

### ✔ Multi-dimensional

It combines:

* Financial
* Operational
* Customer
* Driver
* Vehicle
* Geographic
* Payment

analysis.

### ✔ KPI-driven

Important business metrics are immediately visible.

### ✔ Time-based

Revenue and ride trends can be analyzed by month and year.

### ✔ Driver-focused

Top revenue-generating drivers are highlighted.

### ✔ Geographic

Cities can be analyzed individually.

### ✔ Visual

Dynamic vehicle images improve the dashboard experience.

### ✔ Scalable

The relational model allows additional measures and visuals to be added later.

---

# 39. Potential Future Enhancements

The current dashboard can be extended with:

### Additional KPIs

* Cancellation Rate
* Average Fare
* Revenue per Ride
* Revenue per KM
* Average Distance per Ride
* Average Ride Duration
* Average Tip per Ride
* Active Drivers
* Non-Active Drivers

### Driver Analytics

* Rides per Driver
* Revenue per Driver
* Driver utilization
* Driver rating
* Driver cancellation rate

### Customer Analytics

* New vs existing users
* Repeat customers
* Customer lifetime value
* Customer retention

### Support Analytics

* Number of support tickets
* Tickets per ride
* Most common issue types
* Average ticket resolution time

### Advanced Analytics

* Revenue forecasting
* Ride demand forecasting
* Customer segmentation
* Driver performance scoring
* City performance ranking

---

# 40. Important Dashboard KPI Definitions

For professional documentation, the KPIs can be defined as follows:

| KPI                           | Definition                                                                                      |
| ----------------------------- | ----------------------------------------------------------------------------------------------- |
| **Total Rides by Vehicle**    | Number of rides analyzed under the selected vehicle context                                     |
| **Total Revenue**             | Total revenue generated within the active filter context                                        |
| **Total Distance Covered KM** | Sum of ride distances in kilometers                                                             |
| **Rating**                    | Rating metric calculated from ride rating data                                                  |
| **Successful Ride Ratio**     | Percentage of rides considered successful/completed according to the implemented business logic |
| **Last Month Revenue**        | Revenue generated during the previous month relative to the analysis period                     |

---

# 41. Example User Journey

A business manager opens the dashboard.

### Step 1

They select:

**Bangalore**

### Step 2

They select:

**Auto**

### Step 3

The dashboard updates the KPIs.

They can now see:

* 160K rides
* $97.40K revenue
* 4K KM distance
* 2.94 rating
* 100% successful ride ratio
* $13.52K last-month revenue

### Step 4

They examine the Top 5 Drivers.

### Step 5

They examine monthly revenue performance.

### Step 6

They analyze tips by city.

### Step 7

They change the vehicle from **Auto → Bike**.

The dashboard updates to the Bike context and the vehicle image changes.

### Step 8

They change the payment method to **UPI**.

Now the analysis can be examined within the UPI payment context.

This workflow allows a business user to explore the data without needing SQL or programming knowledge.

---

# 42. Portfolio Project Description

For a resume or portfolio, the project can be described as:

> **Rides Analysis Dashboard | Power BI**
>
> Developed an interactive Power BI dashboard to analyze ride-service performance across revenue, ride volume, distance, ratings, successful rides, drivers, vehicle types, cities, payment methods and referral usage. Built a relational data model connecting Rides with Drivers, Users, Payments, SupportTickets and a dedicated Date Table. Created DAX-based KPIs for revenue, rides, distance, rating, successful ride ratio and previous-month revenue. Implemented interactive slicers and dynamic vehicle images to enable segment-level analysis and improve dashboard usability.

---

# 43. Interview Explanation

If an interviewer asks:

### “Tell me about your Power BI project.”

You can explain:

> “I created a Rides Analysis Dashboard using Power BI to analyze ride-service performance. The main objective was to provide a single interactive dashboard for monitoring rides, revenue, distance, ratings, successful ride performance and driver contribution.
>
> I built a data model around the Rides table and connected it with Drivers, Users, Payments, SupportTickets and a Date Table. I also created an Image Data table to dynamically display vehicle images based on the selected vehicle type.
>
> I created KPI measures for Total Revenue, Total Rides by Vehicle, Total Distance Covered, Rating, Successful Ride Ratio and Last Month Revenue.
>
> The dashboard includes interactive filters for City, Vehicle Type, Payment Method, Referral Used and Ride Status. It also contains revenue trend analysis, Top 5 Drivers by Revenue, monthly revenue and ride analysis, and city-wise tip analysis.
>
> The dashboard helps business users identify revenue trends, driver performance, geographic differences and operational patterns without manually analyzing the underlying data.”

---

# 44. Project Outcome

The final outcome of the project is an interactive **Rides Analysis Dashboard** that converts multiple ride-related datasets into a single decision-support solution.

The dashboard provides:

**Ride Performance + Revenue Analysis + Driver Analysis + Vehicle Analysis + Customer Analysis + Payment Analysis + Geographic Analysis + Time Analysis**

in one Power BI report.

---

# 45. Final Project Summary

The **Rides Analysis Dashboard** demonstrates an end-to-end Business Intelligence workflow:

> **Data Collection**
> ↓
> **Data Preparation**
> ↓
> **Data Modeling**
> ↓
> **Relationships**
> ↓
> **DAX Measures**
> ↓
> **KPIs**
> ↓
> **Interactive Visualizations**
> ↓
> **Business Analysis**
> ↓
> **Insights**
> ↓
> **Recommendations**

The dashboard is designed to give decision-makers a **single source of analytical information** for understanding ride operations and revenue performance.

Its strongest feature is the combination of **KPI-driven analysis and interactive filtering**, allowing users to move from an overall business view to detailed analysis by **city, vehicle, payment method, referral usage and ride status**.

The **dynamic vehicle-image functionality** further enhances the dashboard's visual storytelling and demonstrates practical use of Power BI relationships beyond traditional charts.

Overall, this project demonstrates practical skills in:

* **Power BI**
* **Data Modeling**
* **DAX**
* **Power Query**
* **Time Intelligence**
* **Interactive Dashboard Design**
* **Business Analysis**
* **Data Visualization**
* **KPI Development**
* **Analytical Storytelling**

---

