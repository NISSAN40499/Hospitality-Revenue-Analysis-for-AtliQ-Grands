<p align="center">
  <img src="https://github.com/NISSAN40499/Hospitality-Revenue-Analysis-for-AtliQ-Grands/blob/main/Logo%20%7C%20Template%20%7C%20Illustrations/AtliQ%20Grand.png" width="150">
</p>

# Hospitality Revenue Analysis-for AtliQ Grands

The **Hospitality Revenue Analysis** project aims to provide **AtliQ Grands** with data-driven insights to enhance revenue management and regain its competitive edge in the luxury and business hotel sector.  

By leveraging **Power BI** and data analytics, this project will help identify key revenue trends, customer behavior patterns, and market dynamics. The analysis will enable the company to make informed strategic decisions, optimize pricing models, and improve overall financial performance.  

Through interactive visualizations and in-depth reporting, this project will serve as a roadmap for AtliQ Grands to adapt to evolving market conditions and strengthen its position in the hospitality industry.  

## 🔗 Live Demo
##### https://app.powerbi.com/view?r=eyJrIjoiZDQxZDdiOTAtYWQ1Yi00ZGZmLWFkNDEtZjgyYTA1MTZiMGY5IiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9&pageName=ReportSection

---

## 🧰 Technologies Used

- **Frontend**: Power BI Desktop  
- **Data Modeling**: DAX (Data Analysis Expressions)  
- **Data Transformation**: Power Query (M language)  
- **Data Source**: Excel (.xlsx)

---

## ❓ Why These Technologies?

- **Power BI** enables fast, interactive dashboards for business intelligence.
- **DAX** allows for powerful, dynamic KPIs and time-intelligence metrics.
- **Power Query** makes ETL clean, manageable, and automated.
- **Excel** is used for simplicity and mock-data modeling, ideal for prototyping.

---

## 📁 Project Structure

Hospitality-Revenue-Dashboard/
│
├── 📁 Logo_Template_Illustrations/   → Logos, templates, and visual assets
├── 📁 Mockups/                       → Dashboard mockup (Hotel - My version)
│
├── 📄 LICENSE                        → Open-source license information
├── 📄 Problem Statement & Metadata.md  → Problem overview and dataset context
├── 📄 Project Charter Discussion Meeting.md → Project planning notes
├── 📄 Stakeholder meeting.md         → Stakeholder goals and expectations
├── 📄 README.md                      → This file – your project’s showcase


---

## 🌟 Features

### Executive View (Homepage)
- **KPI Cards**: Revenue, RevPAR, OCC%, ADR, DSRN, Realisation%
- **Comparisons**: Current vs Last Week, Week-over-Week (WoW) %
- **Trendline**: Line chart for RevPAR, ADR, and OCC% over time
- **Visuals**:
  - Revenue by City (LW shown via markers)
  - Donut chart: Luxury vs Business segments vs target
  - Treemap: Revenue by Booking Platform
  - Decomposition Tree: Day Type → Room Type with dynamic KPI switch

### Business Drilldown
- **Matrix View**: Property-level view with KPIs, data bars for Revenue and Rating
- **Line + Clustered Column Chart**: Platform-wise ADR and Realisation%
- **Custom Visuals**:
  - Nova Silva Dumbbell Chart: Compare KPIs (e.g., ADR vs Last Week)
  - Lollipop Chart: OCC% by Room Type or Platform
  - Scatter Plot: Revenue (x) vs Avg Rating (y), Size = Realisation %, Tooltip = DSRN
- **Dynamic Interactions**: Slicers for City, Platform, Room Type, Week No, etc.

---

## ✅ Challenges Solved

- Built dynamic WoW comparison using custom week logic without date hierarchy
- Balanced KPIs with mixed units (currency vs % vs rating) using smart chart types
- Designed compact yet expressive charts (Lollipop, Dumbbell) in tight layout
- Used parameters and toggles to switch KPIs in decomposition trees and scatter plots

---

## 🔮 Future Improvements

- Add real-time data via SQL/Azure DB connection  
- Embed targets via SharePoint or Power Apps integration  
- Add custom tooltip pages for more context (e.g., sparkline or card popups)  
- Extend to MoM and YTD tracking when more data is available  
- Role-based page views (e.g., GM vs Operations Manager)  
- Embed into Power BI Service with scheduled refresh and alerts  

---

