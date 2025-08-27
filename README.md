# Hotel Booking Demand Analysis - EDA Report

> **A comprehensive exploratory data analysis of hotel booking demand patterns**

---

## Table of Contents

1. [Introduction](#introduction)
2. [Objectives](#objectives)
3. [Dataset Overview](#dataset-overview)
4. [Case Study Analysis](#case-study-analysis)
5. [Dataset Variables](#dataset-variables)
6. [Exploratory Data Analysis](#exploratory-data-analysis)
7. [Conclusions](#conclusions)
8. [Recommendations](#recommendations)
9. [Bibliography](#bibliography)

---

## 🎯 Introduction 

<div align="center">
  
![Hotel Booking Analysis](https://via.placeholder.com/600x300/4A90E2/FFFFFF?text=Hotel+Booking+Analysis)

</div>

The article titled **"Hotel Booking Demand Datasets"**, authored by Antonio Nuno de Almeida, Ana Nunes, and Luis, addresses the importance and utility of datasets related to hotel booking demand. Published on January 2, 2019, this work operates within a multidisciplinary context that combines aspects of data analysis, hotel management, and machine learning techniques.

The research focuses on collecting and analyzing hotel booking data, enabling researchers and industry professionals to better understand consumer behavior patterns. Through the use of these datasets, predictive models can be developed to help anticipate demand, optimize revenue management, and improve customer experience. This approach not only benefits hotels in terms of operational efficiency but also contributes to more informed decision-making based on concrete data.

> 💡 **Key Insight**: The work highlights the relevance of hotel demand datasets as key tools for analysis and continuous improvement in the tourism industry.

---

## 🎯 Objectives 

### General Objectives
- **Conduct comprehensive EDA**: Perform exploratory data analysis of the dataset, generating visualizations, preparing data, and extracting initial conclusions using R/RStudio
- **Explore consumer behavior**: Investigate different aspects of consumer behavior in the hotel sector

### 🎯 Specific Objectives
- **Develop prediction models**: Create models to classify the probability of hotel booking cancellations

---

## 📊 Dataset Overview

<div align="center">

### Dataset Statistics

| Metric | Value |
|--------|--------|
| **Total Records** | 119,390 |
| **Variables** | 32 |
| **Hotel Types** | Resort & City Hotels |
| **Time Period** | July 1, 2015 - August 31, 2017 |

</div>

The dataset contains **119,390 records** and **32 variables** sourced from ScienceDirect, a peer-reviewed academic bibliography platform by Elsevier. The article describes two hotel demand datasets: one from a resort hotel (**"Resort Hotel"**) and another from an urban hotel (**"City Hotel"**).

<div align="center">
  
![Dataset Overview](https://via.placeholder.com/600x200/FF6B6B/FFFFFF?text=Hotel+Datasets+Overview)

</div>

---

## 🔍 Case Study Analysis

### 📚 Data Origin
- **👥 Authors**: Antonio Nuno de Almeida, Ana Nunes, and Luis
- **📅 Publication Date**: January 2, 2019
- **🔗 Source**: ScienceDirect
- **🏛️ Institution**: University Institute of Lisbon, Portugal

### ✅ Data Credibility
The data originates from queries made to the hotels' Property Management System (PMS), stored in SQL format from previous administrative records, ensuring reliability.

### 🎯 Applicable Use Cases

| Stakeholder | Application |
|-------------|-------------|
| **Hotel Chains** | Portfolio optimization, customer satisfaction improvement, market expansion |
| **Independent Hotels** | Niche opportunities, service differentiation |
| **Academic Researchers** | Consumer behavior studies in tourism and hotel management |
| **Tourism Organizations** | Understanding tourist flow and policy development |

### 💼 Business Problems Addressed

- **Improve hotel profitability** through dynamic pricing strategies and promotions during low seasons
- **Enhance customer experience** with personalized services for returning customers  
- **Optimize revenue fluctuation** with appropriate marketing strategies for low-activity periods

### 💡 Key Insights

> **Cancellation Patterns**: High or low cancellation rates could indicate business problems. Potential factors include climate changes, high vacation seasons, overly flexible cancellation policies.

> **Dynamic Pricing Strategy**: Hotels should implement pricing strategies considering both seasonality and room type, offering discounts or special packages during high seasons for less visited rooms.

> **Seasonality Analysis**: Seasonality relates to both room types and seasons, allowing for price increases during high-demand periods.

> **Customer Loyalty**: Due to the existence of new and repeat customers, special services could be created for returning guests - premium access to hotel events, coupons, or visit credits.

### ❓ Key Analysis Questions

- How many bookings are made by hotel type?
- Is demand increasing over time?
- What are the high and low demand seasons?
- How many bookings include children and/or babies?
- Is parking space availability important?
- In which months are most booking cancellations made?

---

## 📝 Dataset Variables

<div align="center">

### Variable Dictionary

</div>

| Variable | Type | Description |
|----------|------|-------------|
| `hotel` | Categorical | Hotel Type (Resort - City) |
| `is_canceled` | Numeric | Indicates if booking was canceled (1 Yes / 0 No) |
| `lead_time` | Numeric | Days between booking and arrival |
| `arrival_date_year` | Numeric | Year of arrival date |
| `arrival_date_month` | Categorical | Month of arrival date |
| `arrival_date_week_number` | Numeric | Week number of arrival year |
| `arrival_date_day_of_month` | Numeric | Day of month of arrival |
| `stays_in_weekend_nights` | Numeric | Number of weekend nights stayed |
| `stays_in_week_nights` | Numeric | Number of weekday nights stayed |
| `adults` | Numeric | Number of adults in booking |
| `children` | Numeric | Number of children in booking |
| `babies` | Numeric | Number of babies in booking |
| `meal` | Categorical | Type of meal booked |
| `country` | Categorical | Customer's country |
| `market_segment` | Categorical | Market segment of booking |
| `distribution_channel` | Categorical | Booking distribution channel |
| `is_repeated_guest` | Numeric | Indicates if returning guest |
| `previous_cancellations` | Numeric | Number of previous canceled bookings |
| `reserved_room_type` | Categorical | Reserved room type |
| `assigned_room_type` | Categorical | Assigned room type |
| `booking_changes` | Numeric | Number of booking changes |
| `deposit_type` | Categorical | Deposit type (No Deposit, Non Refund, Refundable) |
| `agent` | Numeric | ID of booking agent |
| `company` | Numeric | ID of managing company |
| `days_in_waiting_list` | Numeric | Days on waiting list |
| `customer_type` | Categorical | Customer type |
| `adr` | Numeric | Average Daily Rate |
| `required_car_parking_spaces` | Numeric | Number of required parking spaces |
| `total_of_special_requests` | Numeric | Number of special requests |
| `reservation_status` | Categorical | Reservation status (Check-Out, Canceled, No-Show) |
| `reservation_status_date` | Date | Reservation status date |

---

## 📈 Exploratory Data Analysis {#exploratory-data-analysis}

### 🔧 Data Loading
```R
setwd("C:/Users/Usuario/OneDrive - Universidad Peruana de Ciencias/DATA SCIENCE")

datahotel <- read.csv("hotel_bookings.csv",header=T,sep = ",")
```

### 🔍 Data Inspection

#### Dataset dimensions
```R
dim(datahotel)
```
```
[1] 119390     32
```

#### Column names
```R
colnames(datahotel)
[1] "hotel"                         
 [2] "is_canceled"                   
 [3] "lead_time"                     
 [4] "arrival_date_year"             
 [5] "arrival_date_month"            
 [6] "arrival_date_week_number"      
 [7] "arrival_date_day_of_month"     
 [8] "stays_in_weekend_nights"       
 [9] "stays_in_week_nights"          
[10] "adults"                        
[11] "children"                      
[12] "babies"                        
[13] "meal"                          
[14] "country"                       
[15] "market_segment"                
[16] "distribution_channel"          
[17] "is_repeated_guest"             
[18] "previous_cancellations"        
[19] "previous_bookings_not_canceled"
[20] "reserved_room_type"            
[21] "assigned_room_type"            
[22] "booking_changes"               
[23] "deposit_type"                  
[24] "agent"                         
[25] "company"                       
[26] "days_in_waiting_list"          
[27] "customer_type"                 
[28] "adr"                           
[29] "required_car_parking_spaces"   
[30] "total_of_special_requests"     
[31] "reservation_status"            
[32] "reservation_status_date" 
```

#### Dataset structure
```R
str(datahotel)
'data.frame':	119390 obs. of  32 variables:
 $ hotel                         : chr  "Resort Hotel" "Resort Hotel" "Resort Hotel" "Resort Hotel" ...
 $ is_canceled                   : int  0 0 0 0 0 0 0 0 1 1 ...
 $ lead_time                     : int  342 737 7 13 14 14 0 9 85 75 ...
 $ arrival_date_year             : int  2015 2015 2015 2015 2015 2015 2015 2015 2015 2015 ...
 $ arrival_date_month            : chr  "July" "July" "July" "July" ...
 $ arrival_date_week_number      : int  27 27 27 27 27 27 27 27 27 27 ...
 $ arrival_date_day_of_month     : int  1 1 1 1 1 1 1 1 1 1 ...
 $ stays_in_weekend_nights       : int  0 0 0 0 0 0 0 0 0 0 ...
 $ stays_in_week_nights          : int  0 0 1 1 2 2 2 2 3 3 ...
 $ adults                        : int  2 2 1 1 2 2 2 2 2 2 ...
 $ children                      : int  0 0 0 0 0 0 0 0 0 0 ...
 $ babies                        : int  0 0 0 0 0 0 0 0 0 0 ...
 $ meal                          : chr  "BB" "BB" "BB" "BB" ...
 $ country                       : chr  "PRT" "PRT" "GBR" "GBR" ...
 $ market_segment                : chr  "Direct" "Direct" "Direct" "Corporate" ...
 $ distribution_channel          : chr  "Direct" "Direct" "Direct" "Corporate" ...
 $ is_repeated_guest             : int  0 0 0 0 0 0 0 0 0 0 ...
 $ previous_cancellations        : int  0 0 0 0 0 0 0 0 0 0 ...
 $ previous_bookings_not_canceled: int  0 0 0 0 0 0 0 0 0 0 ...
 $ reserved_room_type            : chr  "C" "C" "A" "A" ...
 $ assigned_room_type            : chr  "C" "C" "C" "A" ...
 $ booking_changes               : int  3 4 0 0 0 0 0 0 0 0 ...
 $ deposit_type                  : chr  "No Deposit" "No Deposit" "No Deposit" "No Deposit" ...
 $ agent                         : chr  "NULL" "NULL" "NULL" "304" ...
 $ company                       : chr  "NULL" "NULL" "NULL" "NULL" ...
 $ days_in_waiting_list          : int  0 0 0 0 0 0 0 0 0 0 ...
 $ customer_type                 : chr  "Transient" "Transient" "Transient" "Transient" ...
 $ adr                           : num  0 0 75 75 98 ...
 $ required_car_parking_spaces   : int  0 0 0 0 0 0 0 0 0 0 ...
 $ total_of_special_requests     : int  0 0 0 0 1 1 0 1 1 0 ...
 $ reservation_status            : chr  "Check-Out" "Check-Out" "Check-Out" "Check-Out" ...
 $ reservation_status_date       : chr  "2015-07-01" "2015-07-01" "2015-07-02" "2015-07-02" ...
```

### Data Processing

#### Missing Data Identification
```R
colSums(is.na(hotel_data))
                         hotel                    is_canceled 
                             0                              0 
                     lead_time              arrival_date_year 
                             0                              0 
            arrival_date_month       arrival_date_week_number 
                             0                              0 
     arrival_date_day_of_month        stays_in_weekend_nights 
                             0                              0 
          stays_in_week_nights                         adults 
                             0                              0 
                      children                         babies 
                             4                              0 
                          meal                        country 
                             0                              0 
                market_segment           distribution_channel 
                             0                              0 
             is_repeated_guest         previous_cancellations 
                             0                              0 
previous_bookings_not_canceled             reserved_room_type 
                             0                              0 
            assigned_room_type                booking_changes 
                             0                              0 
                  deposit_type                          agent 
                             0                              0 
                       company           days_in_waiting_list 
                             0                              0 
                 customer_type                            adr 
                             0                              0 
   required_car_parking_spaces      total_of_special_requests 
                             0                              0 
            reservation_status        reservation_status_date 
                             0                              0
```

#### Missing Data Treatment
```R
# Create helper dataset "dataset_clean"
dataset_clean <- na.omit(hotel_data)
# Remove columns with more than 50% NA values
dataset_clean <- hotel_data[, colMeans(is.na(hotel_data)) < 0.5]
View(dataset_clean)
```

#### Outlier Identification
```R
# Create boxplot to visualize outliers
boxplot(dataset_clean$adr, main = "Box Plot - ADR")

# Identify outliers using Interquartile Range (IQR)
Q1 <- quantile(dataset_clean$adr, 0.25, na.rm = TRUE)
Q3 <- quantile(dataset_clean$adr, 0.75, na.rm = TRUE)
IQR <- Q3 - Q1

# Define limits
lower_bound <- Q1 - 1.5 * IQR
upper_bound <- Q3 + 1.5 * IQR
outliers <- dataset_clean$adr[dataset_clean$adr < lower_bound | dataset_clean$adr > upper_bound]
```

| Statistic | Value |
|-----------|--------|
| **IQR** | 56.7 |
| **Lower Bound** | -15.8 |
| **Upper Bound** | 211 |
| **Q1** | 69.3 |
| **Q3** | 126 |
| **Outliers Count** | 3,793 |

#### Outlier Treatment
```R
# Winsorization to limit outliers
install.packages("DescTools")
library(DescTools)

# Calculate 5th and 95th percentiles
lower_bound <- quantile(dataset_clean$adr, 0.05, na.rm = TRUE)
upper_bound <- quantile(dataset_clean$adr, 0.95, na.rm = TRUE)

# Manual winsorization by replacing values outside limits
dataset_clean$adr[dataset_clean$adr < lower_bound] <- lower_bound
dataset_clean$adr[dataset_clean$adr > upper_bound] <- upper_bound

# Re-run BoxPlot
boxplot(dataset_clean$adr, main = "Box Plot - ADR (After Winsorization)")
```

### Data Visualization

#### Question 1: Bookings by Hotel Type
```R
hotel_count <- hotel_data %>%
  group_by(hotel) %>%
  summarise(count = n())

ggplot(hotel_count, aes(x = hotel, y = count, fill = hotel)) +
  geom_bar(stat = "identity") +
  labs(title = "Number of Bookings by Hotel Type", x = "Hotel Type", y = "Number of Bookings") +
  theme_minimal()
```

#### Question 2: Demand Over Time
```R
# Convert month name to number if necessary
hotel_data$arrival_date_month <- match(hotel_data$arrival_date_month, month.name)

# Create 'year_month' column combining year and month
hotel_data$year_month <- make_date(hotel_data$arrival_date_year, hotel_data$arrival_date_month, 1)

# Verify year_month column creation
head(hotel_data$year_month)

# Group by year_month and count bookings
demand_over_time <- hotel_data %>%
  group_by(year_month) %>%
  summarise(count = n())

# Visualization: line chart of demand over time
ggplot(demand_over_time, aes(x = year_month, y = count)) +
  geom_line(color = "blue") +
  labs(title = "Booking Demand Over Time", x = "Date", y = "Number of Bookings") +
  theme_minimal()
```

#### Question 3: Seasonal Patterns
```R
seasonality <- hotel_data %>%
  group_by(arrival_date_month) %>%
  summarise(count = n()) %>%
  arrange(match(arrival_date_month, month.name))

ggplot(seasonality, aes(x = factor(arrival_date_month, levels = month.name), y = count, fill = count)) +
  geom_bar(stat = "identity") +
  labs(title = "Booking Seasonality", x = "Month", y = "Number of Bookings") +
  theme_minimal()
```

#### Question 4: Lowest Demand Period
```R
lowest_demand_month <- seasonality[which.min(seasonality$count), ]
lowest_demand_month
```

#### Question 5: Bookings with Children/Babies
```R
children_bookings <- hotel_data %>%
  filter(children > 0 | babies > 0)

nrow(children_bookings)

ggplot(children_bookings, aes(x = factor(children > 0, levels = c(TRUE, FALSE)), fill = babies > 0)) +
  geom_bar() +
  labs(title = "Bookings with Children and/or Babies", x = "Children Present", y = "Number of Bookings") +
  theme_minimal()
```

#### Question 6: Parking Space Importance
```R
parking_spaces <- hotel_data %>%
  group_by(required_car_parking_spaces) %>%
  summarise(count = n())

ggplot(parking_spaces, aes(x = required_car_parking_spaces, y = count, fill = required_car_parking_spaces)) +
  geom_bar(stat = "identity") +
  labs(title = "Importance of Parking Spaces", x = "Number of Parking Spaces", y = "Number of Bookings") +
  theme_minimal()
```

#### Question 7: Monthly Cancellations
```R
hotel_data$arrival_date_month <- match(hotel_data$arrival_date_month, month.name)

hotel_data$year_month <- make_date(hotel_data$arrival_date_year, hotel_data$arrival_date_month, 1)

cancellations <- hotel_data %>%
  filter(is_canceled == 1) %>%
  group_by(year_month) %>%
  summarise(cancel_count = n())

ggplot(cancellations, aes(x = year_month, y = cancel_count)) +
  geom_bar(stat = "identity", fill = "red") +
  labs(title = "Monthly Cancellations", x = "Month", y = "Number of Cancellations") +
  theme_minimal()
```

---

## 📊 Conclusions {#conclusions}

> ### Hotel Type Analysis
> Based on booking data by hotel type, we can conclude that **city hotels** tend to be more popular than resorts. This could be due to various factors such as central location, business travel convenience, and urban amenities.

> ### Demand Trends
> When analyzing booking demand over time, we observe a **consistent increase** in bookings for both hotel types, especially during vacation months and special events.

> ### Seasonal Patterns
> **High seasons** coincide with vacation months (June, July, and August) and major festive events, where higher booking volumes are observed. This pattern provides valuable insights for revenue management strategies.

---

## 💡 Recommendations {#recommendations}

### Dynamic Pricing Strategy
Implement **dynamic rates adjusted to seasonality, demand, and room type**. During low seasons, offering specific promotions and discounts could incentivize bookings, while premium pricing during high seasons can maximize revenue.

### Cancellation Policy Review
Review cancellation policies, especially in months where higher cancellation rates are detected. Consider implementing **more restrictive policies** during peak periods while maintaining flexibility during low-demand periods.

### Customer Loyalty Programs
Create **loyalty programs** to reward returning customers, providing exclusive benefits such as discounts, room upgrades, event access, or personalized services. This can significantly improve customer retention and lifetime value.

### Continuous Service Improvement
Implement a **continuous improvement strategy** in customer service based on analysis of special requests. This will help personalize each guest's experience, improving satisfaction and retention rates.

### Data-Driven Decision Making
Establish regular **monitoring and analysis cycles** of booking patterns to quickly adapt to market changes and optimize operational strategies.

---

## Bibliography 

- Antonio, N., De Almeida, A., & Nunes, L. (2018). Hotel booking demand datasets. *Data In Brief*, 22, 41-49. https://doi.org/10.1016/j.dib.2018.11.126

- Gabara, E. (2024, July 18). What your hotel booking performance can tell you about demand patterns. *Cloudbeds*. https://www.cloudbeds.com/es/articulos/patrones-demanda-hotelera/

- International, S. (2024, June 23). Hotel market research. *SIS International Research*. https://www.sisinternational.com/es/pericia/industrias/investigacion-de-mercado-hotelero/

---

<div align="center">

### Analysis Complete

*This report was generated as part of the CC216 coursework for exploratory data analysis in the hospitality industry.*

**🔍 For more insights and detailed analysis, please refer to the complete dataset and R code implementations.**
Autor: Nicole Sihuincha
</div>
