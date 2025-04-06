# **Stakeholder Discussion Meeting**

After receiving the necessary data and creating the initial mockups for the Hospitality Revenue Analysis project, a stakeholder meeting was conducted to review the mockups and align on key metrics and expectations. The session included key personnel such as **Mr. Abhishek Anand** (Domain Expert) and **Mr. Hemanand Vedival** (Senior Data Analyst). The meeting focused on validating the current direction and identifying any gaps that needed to be addressed before the final dashboard build.

---

### **Initial Feedback on Mockups**

The meeting began with Mr. Hemanand asking Mr. Abhishek a critical question:

> *“Based on the mockups and the available data, how much can we use as-is, and how much needs to be modified?”*

Mr. Abhishek responded by **praising the mockups** I had created, highlighting the thoughtful inclusion of KPIs such as **Revenue, Occupancy %, and Average Rating**. He mentioned these are **very useful and industry-relevant** metrics for the hospitality business. 

He also added that the mockups were *"interesting and well-aligned with the business needs."*

---

### **Additional Metrics Identified**

Mr. Abhishek emphasized the importance of introducing a few more **critical industry-standard metrics** that would elevate the analysis:

1. **REVPAR (Revenue per Available Room)**  
   - **Formula 1:** Total Revenue / Total Available Rooms to Sell  
   - **Formula 2 (Alternative):** ADR × Occupancy %  
   - Example: If a hotel has 50 available rooms on a Sunday and 25 rooms are occupied, the **occupancy is 50%** for that day.

2. **ADR (Average Daily Rate)**  
   - **Formula:** Total Room Revenue / Number of Rooms Sold  
   - Example: If 50 rooms are sold for ₹1,000 each, the ADR is ₹1,000.  
   - *Insight:* If **occupancy = 100%**, then **ADR = REVPAR**.

---

### **Important Concept: SRN & DSRN**

Mr. Hemanand noted that “available rooms” seem to play a crucial role and asked if there’s an industry term for that.

Mr. Abhishek confirmed:
- **SRN (Sellable Rooms per Night)** — number of rooms that are available to be sold.
- **DSRN (Daily Sellable Rooms per Night)** — the same, but **viewed on a daily basis**.

He stressed the importance of **DSRN** in this project, as it allows for analysis on **room availability, maintenance, and anomalies** at a granular level.

---

### **Confirmed KPIs After This Discussion**
From this part of the meeting, we **confirmed five core KPIs** for the dashboard:
- **Revenue**
- **Occupancy %**
- **ADR**
- **REVPAR**
- **DSRN**

---

### **Introduction of Realization Metric**

When asked if anything else should be added, Mr. Abhishek introduced the concept of **Realization**, which required tracking two more metrics:

1. **URN (Utilized Rooms per Night)** – Rooms that were actually used/stayed in.
2. **BRN (Booked Rooms per Night)** – Total number of rooms that were booked (includes cancellations and no-shows).

He explained:
- **Realization = URN / BRN**
- **BRN = URN + No-shows + Cancellations**

**Example:**  
If 100 rooms are available, 60 are booked, but only 50 were actually used (10 were cancelled/no-shows), then:
- **BRN = 60**
- **URN = 50**
- **Realization = 50 / 60 = ~83.33%**

---

### **Revenue Implications of Booking Types**

Mr. Hemanand raised a nuanced question:

> *"If there’s a cancellation or no-show, how is that revenue treated?"*

Mr. Abhishek explained the two key booking types:
- **Prepaid Bookings:** Done via platforms like *BookMyHotel*, *Goibibo*, *MakeMyTrip*, etc.
- **Pay at Hotel:** Revenue is only realized if the guest shows up.

In case of **no-shows**:
- Some platforms might refund the full amount if the reason is valid.
- If not, they keep a percentage and pass on the rest to the hotel.

That partial amount isn’t considered in the **top-line revenue** but is accounted for in the **bottom line**, which still adds value to the business.

---

### **Weekend vs Weekday Definition**

For filtering and trend analysis, Mr. Abhishek clarified the **business-specific definition**:
- **Weekend:** Friday & Saturday
- **Weekday:** Sunday to Thursday

This distinction is important for slicing performance and patterns correctly.

---

### **Trends & Delta Analysis**

For time-based insights, Mr. Abhishek suggested:
- **Weekly Trend Charts**
- **Delta Analysis**: Comparing **current week vs previous week** for performance shifts.

---

### **Platform-Level Analysis**

Mr. Hemanand introduced the idea of a **three-level diagnostic framework**:
- **Level 1**: Is there a problem?
- **Level 2**: Where is the problem? (City, Process, Category)
- **Level 3**: What exactly is causing the problem? (e.g., Couple Rooms, General Rooms)

Mr. Abhishek agreed and emphasized that a **great dashboard should answer at least three "Why"s** — a classic principle of root cause analysis.

---

### **Design Innovation: Flipped KPI Cards & Maps**

We also discussed modern UI/UX elements:
- **Flipped KPI Cards**: Mr. Abhishek loved the idea and said it resonates with the **Gen Z vibe** and would make the report stand out visually.
- **City-wise Performance Map**: He appreciated the idea of an interactive map showing city-level performance.
  - He also committed to sharing a **CSV file containing all location coordinates** to support this.

---

### **Final Agreement**

After the discussion, it was clear that while the initial mockup was strong, several **important enhancements were needed**. So, we aligned with Mr. Abhishek on the following:

> ✅ We’ll go ahead and **build 80% of the dashboard** incorporating the new metrics and improvements.  
> ✅ After presenting this revised version, we’ll review again and **add any additional elements** if necessary.

Mr. Abhishek concluded the meeting by **praising the overall mockup design**, mentioning that if we can execute it well, **“it will definitely be an impactful and professional-level report.”**
