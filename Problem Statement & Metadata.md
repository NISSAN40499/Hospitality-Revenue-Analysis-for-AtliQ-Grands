# Hospitality Revenue Analysis Project

## **Problem Statement**

AtliQ Grands is a leading hospitality brand that owns multiple five-star hotels across India. With over 20 years in the hospitality industry, the company has long been a symbol of luxury and business-class accommodations. However, recent strategic moves from competitors and ineffective decision-making at the management level have caused AtliQ Grands to lose its market share and revenue in the luxury and business hotels sector.

In response to this, the Managing Director of AtliQ Grands decided to incorporate "Business and Data Intelligence" to regain their market position. But, there’s a significant challenge: **AtliQ Grands** does not have an in-house data analytics team capable of delivering the actionable insights necessary for strategic decision-making.

As part of the strategy, AtliQ Grands' Revenue Management Team decided to partner with an external data analytics service provider who can offer valuable insights derived from their historical data. This project aims to leverage data analytics to improve operational efficiency, revenue generation, and market share.

---

## **Project Objective**

I, as a **Data Analyst**, have been provided with sample data from AtliQ Grands and a mock-up dashboard to analyze the historical data and create actionable insights. My objective is to:

1. **Create Metrics**: Based on the provided list, create relevant metrics that align with the business objectives of AtliQ Grands.
2. **Dashboard Creation**: Develop a dashboard according to the mock-up provided by the stakeholders to visualize the metrics and KPIs effectively.
3. **Generate Additional Insights**: Analyze the data and provide any additional insights that might be useful for improving the company's operations, increasing revenue, and regaining market share.

---

## **Metadata Overview**

To aid my analysis, the metadata provides detailed information regarding the columns in the provided datasets. I have been given **five CSV files** to work with, each containing data that is crucial for analyzing various aspects of AtliQ Grands' hotel operations.

Here’s a breakdown of each file and its columns:

### 1. **dim_date**
This file provides information about the dates, weeks, and types of days (weekends vs weekdays).
- **date**: The specific date (for May, June, and July).
- **mmm yy**: Date formatted as 'Month Year' (e.g., Jun 23).
- **week no**: Unique week number for the given date.
- **day_type**: Weekend or Weekday classification.

### 2. **dim_hotels**
This file holds information about the hotels in the AtliQ Grands portfolio.
- **property_id**: Unique ID for each hotel.
- **property_name**: Name of the hotel.
- **category**: Classification (Luxury or Business).
- **city**: City in which the hotel is located.

### 3. **dim_rooms**
This file describes the rooms available in the hotels.
- **room_id**: The type of room (RT1, RT2, RT3, RT4).
- **room_class**: Room class (Standard, Elite, Premium, Presidential).

### 4. **fact_aggregated_bookings**
This file holds aggregated data about bookings made for various room categories across hotels.
- **property_id**: Unique ID for the hotel.
- **check_in_date**: Date when customers checked in.
- **room_category**: Type of room booked.
- **successful_bookings**: Number of successful bookings for that room type.
- **capacity**: Maximum room availability for that type on a given date.

### 5. **fact_bookings**
This file contains individual booking data, providing detailed insights into customer bookings.
- **booking_id**: Unique booking ID for each customer.
- **property_id**: Unique ID for the hotel.
- **booking_date**: Date the booking was made.
- **check_in_date**: Date the customer checked in.
- **check_out_date**: Date the customer checked out.
- **no_guests**: Number of guests staying in the room.
- **room_category**: Type of room (RT1, RT2, RT3, RT4).
- **booking_platform**: Platform used to make the booking.
- **ratings_given**: Customer rating for hotel services.
- **booking_status**: Status of the booking (Cancelled, Checked Out, No Show).
- **revenue_generated**: Total revenue generated from the booking.
- **revenue_realized**: Revenue realized after adjusting for booking status (if cancelled, 40% of revenue is refunded).

---

## **Project Deliverables**

### 1. **Metrics Development**
- Define key metrics such as:
  - Occupancy rate by room category.
  - Revenue per available room (RevPAR).
  - Average daily rate (ADR).
  - Daily sellable rooms per night (DSRN).
  - Realization = URN/BRN
  - Total revenue by hotel, city, and category.
  - Cancellation rate by hotel and room type.

### 2. **Dashboard Development**
- Build a Power BI dashboard based on the mock-up to visualize the metrics and key performance indicators (KPIs).
- Ensure the dashboard is user-friendly and provides actionable insights.

### 3. **Insight Generation**
- Identify patterns in the data that could reveal areas for improvement, such as:
  - Identifying trends in booking cancellations.
  - Highlighting revenue generation discrepancies between different hotel categories.
  - Analyzing occupancy patterns and suggesting potential strategies to increase bookings.

---

## **Conclusion**

This project will provide AtliQ Grands with valuable insights from their historical booking data, allowing them to make more informed decisions about how to reclaim their market share and boost their revenue. By leveraging data intelligence, the company can identify operational inefficiencies, understand customer preferences, and strategically position itself to outpace competitors.

**My analysis and recommendations will help AtliQ Grands not only survive but thrive in the competitive hospitality industry.**

---
