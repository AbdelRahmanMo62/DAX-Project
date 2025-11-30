# DAX-Project

#### **📊 DAX Calculations in Power BI**

**🔢 Core Metrics**
```dax
Total Cost = SUM(fbads_daily[Cost]) + SUM(googleads_daily[Cost])

Total Sessions = SUM(ga_daily[Sessions])

Total_Orders = SUM(ga_daily[Orders])

Total_Revenue = SUM(ga_daily[Revenue])

Cost per Session = DIVIDE([Total Cost] , [Total Paid_Sessions])

CPS = [Total Cost]/[Total Sessions]

Bounce Rate = AVERAGE(ga_daily[Bounces])
```

**📈 Facebook Ads Metrics**
```dax
FB Total_Cost = SUM(Fbads_Daily[Cost])

FB Max_Daily Cost = MAX(Fbads_Daily[Cost])
```

**🔍 Google Ads Metrics**
```dax
Google Total_Cost = SUM(googleads_daily[Cost])

Google Clicks = SUM(googleads_daily[Clicks])

Google CPC = googleads_daily[Google Total_Cost]/googleads_daily[Google Clicks]

Google Max_Daily Cost = MAX(googleads_daily[Cost])

Impressions Trend = SUM(googleads_daily[Impressions])
```

**⚖️ Platform Comparisons**
```dax
Cost Difference = [Google Total_Cost] - [FB Total_Cost]

ROAS = [Total Paid_Sessions]/[Total Sessions]

Total Paid_Sessions = SUM(ga_paid[Sessions])

Paid Sessions = ga_paid[Total Paid_Sessions]/[Total Sessions]

Paid Conversion_Rate = SUM(ga_paid[Orders])/SUM(ga_paid[Sessions])

Paid Bounce = SUM(ga_paid[Bounces])

Paid_Revenue = SUM(ga_paid[Revenue])
```

**🌱 Non-Paid (Organic) Metrics**
```dax
Total NonPaid Sessions = SUM('ga_non-paid'[Sessions])

Non-Paid Sessions = [Total NonPaid Sessions]/[Total Sessions] 

None_Paid Conversion Rate = SUM('ga_non-paid'[Paid_Orders])/SUM('ga_non-paid'[Sessions])

NonePaid Bounce = SUM('ga_non-paid'[Bounces])

NonPaid Revenue = sum('ga_non-paid'[Revenue])
