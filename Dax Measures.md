
# 📊 DAX Measures – AtliQ Grands Hospitality Dashboard

This file contains all the DAX measures and calculated columns used in the **AtliQ Grands Hospitality Revenue Analysis Power BI dashboard**. These are categorized for clarity and context.

---

## 🎯 Dynamic Homepage DAX

### Greeting
```dax
Greeting = 
VAR userMap =
    SWITCH(
        TRUE(),
        USERNAME() = "MSI\\USER", "Kaizen",
        CONTAINSSTRING(USERNAME(), "atliq"), "Kaizen",
        "Guest"
    )
VAR hour = HOUR(UTCNOW()) + 6
VAR adjustedHour = MOD(hour, 24)
RETURN
    SWITCH(
        TRUE(),
        adjustedHour < 12, "☀️Good morning! " & userMap,
        adjustedHour < 18, "🌤️Good afternoon! " & userMap,
        "🌙Good evening! " & userMap
    )
```

### Small Message
```dax
Small Message = 
VAR hours = HOUR(NOW())
RETURN
SWITCH(
    TRUE(),
    hours < 4, "Wishing you a restful night and smooth operations ahead.",
    hours < 8, "Let data lead the way to smarter hospitality.",
    hours < 12, "Your dashboard. Your domain.",
    hours < 16, "Welcome to your hospitality command center.",
    hours < 20, "Turning numbers into memorable stays.",
    "Crafting excellence, one insight at a time."
)
```

### Motto Message
```dax
Motto Message = 
VAR hours = HOUR(NOW())
RETURN
SWITCH(
    TRUE(),
    hours < 6, 
        "“In a world of five-star luxury, data became our sixth star.”" & UNICHAR(10) &
        "AtliQ Grands blends timeless hospitality with real-time intelligence —" & UNICHAR(10) &
        "empowering decisions that turn every stay into a story worth remembering.",
        
    hours < 12, 
        "“Every guest leaves a footprint. Every number tells a tale.”" & UNICHAR(10) &
        "This dashboard is where those stories come alive —" & UNICHAR(10) &
        "guiding AtliQ Grands toward smarter service and lasting impressions.",
        
    hours < 18, 
        "“Behind every smile at AtliQ Grands lies a thousand data points.”" & UNICHAR(10) &
        "With each insight, we don't just grow revenue —" & UNICHAR(10) &
        "we grow trust, loyalty, and unforgettable guest experiences.",
        
    "“From check-in to checkout, data never sleeps.”" & UNICHAR(10) &
    "AtliQ Grands uses this living dashboard to stay ahead," & UNICHAR(10) &
    "ensuring every decision reflects the excellence we promise."
)
```

## 📅 Date & Time Calculations

### wn – Week Number
```dax
wn = WEEKNUM(dim_date[date])
```

### day type
```dax
day type = 
VAR wkd = WEEKDAY(dim_date[date],1)
RETURN IF(wkd>5,"Weekend","Weekday")
```

## 💰 Core KPIs – Revenue & Performance

### Revenue
```dax
Revenue = SUM(fact_bookings[revenue_realized])
```

### Total Bookings
```dax
Total Bookings = COUNT(fact_bookings[booking_id])
```

### Total Capacity
```dax
Total Capacity = SUM(fact_aggregated_bookings[capacity])
```

### Total Successful Bookings
```dax
Total Successful Bookings = SUM(fact_aggregated_bookings[successful_bookings])
```

### Occupancy %
```dax
Occupancy % = DIVIDE([Total Successful Bookings], [Total Capacity], 0)
```

### Average Rating
```dax
Average Rating = AVERAGE(fact_bookings[ratings_given])
```

### No of days
```dax
No of days = DATEDIFF(MIN(dim_date[date]),MAX(dim_date[date]),DAY)+1
```

### Total Cancelled Bookings
```dax
Total Cancelled Bookings = CALCULATE([Total Bookings],fact_bookings[booking_status]="Cancelled")
```

### Cancellation %
```dax
Cancellation % = DIVIDE([Total Cancelled Bookings], [Total Bookings])
```

### Total Checked Out
```dax
Total Checked Out = CALCULATE([Total Bookings],fact_bookings[booking_status]="Checked Out")
```

### Total No Show Bookings
```dax
Total No Show Bookings = CALCULATE([Total Bookings],fact_bookings[booking_status]="No Show")
```

### No Show Rate %
```dax
No Show Rate % = DIVIDE([Total No Show Bookings], [Total Bookings])
```

## 🎯 Booking % by Categories

### Booking % by Platform
```dax
Booking % by Platform = 
VAR platformWiseBookings = 
    CALCULATE([Total Bookings], ALLEXCEPT(dim_platform, dim_platform[platform]))

RETURN 
    DIVIDE(platformWiseBookings, [Total Bookings])
```

### Booking % by Room Class
```dax
Booking % by Room Class = 
VAR roomWiseBookings = 
    CALCULATE([Total Bookings], ALLEXCEPT(dim_room_class, dim_room_class[room_class]))

RETURN 
    DIVIDE(roomWiseBookings, [Total Bookings])
```

## 📊 Profitability Metrics

### ADR – Average Daily Rate
```dax
ADR = DIVIDE([Revenue], [Total Bookings], 0)
```

### Realisation %
```dax
Realisation % = 1 - ([Cancellation %] + [No Show Rate %])
```

### RevPAR – Revenue Per Available Room
```dax
RevPAR = DIVIDE([Revenue],[Total Capacity])
```

### DBRN – Daily Booking Run-Rate
```dax
DBRN = DIVIDE([Total Bookings], [No of days])
```

### DSRN – Daily Supply Run-Rate
```dax
DSRN = DIVIDE([Total Capacity], [No of days])
```

### DURN – Daily Utilized Run-Rate
```dax
DURN = DIVIDE([Total Checked Out],[No of days])
```

## 🔁 WoW Metrics

### This Week Revenue
```dax
This Week Revenue = 
VAR currentWn = MAX(dim_date[wn])
RETURN
CALCULATE([Revenue],dim_date[wn]=currentWn)
```

### Revenue LW – Last Week
```dax
Revenue LW = 
VAR currentWn = MAX(dim_date[wn])
RETURN
CALCULATE([Revenue],dim_date[wn]=currentWn-1)
```

### Revenue WoW change %
```dax
Revenue WoW change % = 
VAR currentWn = MAX(dim_date[wn])
VAR thisWeekRevenue = CALCULATE([Revenue],dim_date[wn]=currentWn)
VAR lastWeekRevenue = CALCULATE([Revenue],dim_date[wn]=currentWn-1)

RETURN DIVIDE((thisWeekRevenue - lastWeekRevenue),lastWeekRevenue)
```

### Occ LW – Occupancy Last Week
```dax
Occ LW = 
VAR currentWn = MAX(dim_date[wn])
RETURN
CALCULATE([Occupancy %],dim_date[wn]=currentWn-1)
```

### Occupancy WoW change %
```dax
Occupancy WoW change % = 
VAR currentWn = MAX(dim_date[wn])
VAR thisWeekOcc = CALCULATE([Occupancy %],dim_date[wn]=currentWn)
VAR lastWeekOcc = CALCULATE([Occupancy %],dim_date[wn]=currentWn-1)

RETURN DIVIDE((thisWeekOcc - lastWeekOcc),lastWeekOcc)
```

### ADR LW – Last Week
```dax
ADR LW = 
VAR currentWn = MAX(dim_date[wn])
RETURN
CALCULATE([ADR],dim_date[wn]=currentWn-1)
```

### ADR WoW change %
```dax
ADR WoW change % = 
VAR currentWn = MAX(dim_date[wn])
VAR thisWeekADR = CALCULATE([ADR],dim_date[wn]=currentWn)
VAR lastWeekADR = CALCULATE([ADR],dim_date[wn]=currentWn-1)

RETURN DIVIDE((thisWeekADR - lastWeekADR),lastWeekADR)
```

### RevPAR LW
```dax
RevPAR LW = 
VAR currentWn = MAX(dim_date[wn])
RETURN
CALCULATE([RevPAR],dim_date[wn]=currentWn-1)
```

### RevPAR WoW change %
```dax
RevPAR WoW change % = 
VAR currentWn = MAX(dim_date[wn])
VAR thisWeekRevPAR = CALCULATE([RevPAR],dim_date[wn]=currentWn)
VAR lastWeekRevPAR = CALCULATE([RevPAR],dim_date[wn]=currentWn-1)

RETURN DIVIDE((thisWeekRevPAR - lastWeekRevPAR),lastWeekRevPAR)
```
