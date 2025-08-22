# ☕ Coffee Sales Analysis (Excel) — 2024–2025

**Author:** Prabhat Singh (Aspiring Data Analyst)  
**Workbook:** `project_01 Coffe_sales.xlsx`  
**Data window:** 2024-03-01 → 2025-03-23  

**Rows (transactions):** 3,636  
**Total Sales:** 115,431.58 (currency as captured in the dataset)  
**Average Order Value (AOV):** 31.75

---

## 🔎 Project Overview
This project analyzes one year of coffee shop transactions using Microsoft Excel. I built a clean “working sheet”, a dashboard for at–a–glance KPIs, and a space for forecasting. The analysis answers what sells, when it sells, and how customers pay—then turns those findings into actionable recommendations.

---

## 🎯 Objectives
- Create a clean, analysis-ready table from raw timestamps and product logs.
- Build time-based features for richer insights (hour, weekday, month, time-of-day buckets).
- Identify best-selling products and peak sales windows.
- Understand payment behavior and seasonality.
- Summarize insights and provide clear business recommendations.

---

## 📁 File & Sheet Structure
- **`working sheet`** — cleaned tabular data used for pivots & charts.  
- **`DashBoard`** — interactive Excel dashboard (pivots/charts) built on the working sheet.  
- **`Sales Forecasting`** — prepared area for projecting monthly sales (can be extended with Excel `FORECAST.ETS` or moving averages).

> Tip: Open the **DashBoard** sheet to interact with the visuals.

---

## 🧹 Data Preparation (in Excel)
Derived helper columns for analysis:
- `hour_of_day` → `=HOUR([@[datetime]])`
- `Time_of_Day` → `=IF([@[hour_of_day]]<12,"Morning",IF([@[hour_of_day]]<18,"Afternoon","Night"))`
- `Weekday` → `=TEXT([@[date]],"ddd")`
- `Month_name` → `=TEXT([@[date]],"mmm")`

Basic checks performed:
- Verified datatypes (date/time/timestamps as datetime, money numeric).  
- Quick scan for nulls/outliers and consistency across time-derived columns.  
- Ensured product names are standardized (8 unique drinks).

---

## 🧾 Data Dictionary
| Column | Description |
|---|---|
| `date` | Calendar date of the transaction |
| `datetime` | Full timestamp of the transaction |
| `time` | Time (hh:mm:ss) component |
| `hour_of_day` | Hour extracted from timestamp (0–23) |
| `cash_type` | Payment method (`card` / `cash`) |
| `money` | Order value (currency as recorded) |
| `coffee_name` | Beverage ordered (8 unique items) |
| `Time_of_Day` | Bucketed daypart: Morning / Afternoon / Night |
| `Weekday` | Day of week (Mon–Sun) |
| `Month_name` | Month (Jan–Dec) |

---

## 📊 Key KPIs
- **Total Sales:** 115,431.58  
- **Average Order Value (AOV):** 31.75  
- **Transactions:** 3,636  
- **Payment Mix:** 97.55% card, 2.45% cash  
- **Busiest Hour:** 10:00 (Sales ≈ 10,994.52)

---

## 🥇 Top Products
**By Revenue**
| Coffee | Total Sales |
|---|---:|
| Latte | 27,866.30 |
| Americano with Milk | 25,269.12 |
| Cappuccino | 18,034.14 |
| Americano | 15,062.26 |
| Hot Chocolate | 10,172.46 |

**By Orders**
| Coffee | Orders |
|---|---:|
| Americano with Milk | 824 |
| Latte | 782 |
| Americano | 578 |
| Cappuccino | 501 |
| Cortado | 292 |

**Avg Order Value by Product**
| Coffee | Avg Order Value |
|---|---:|
| Hot Chocolate | 36.07 |
| Cappuccino | 36.00 |
| Cocoa | 35.71 |
| Latte | 35.63 |
| Americano with Milk | 30.67 |
| Americano | 26.06 |
| Cortado | 25.80 |
| Espresso | 21.00 |

> **Highlights:** Latte and Americano with Milk are the biggest revenue drivers. Espresso is the lowest priced item on average, while Hot Chocolate/Cappuccino command the highest average order values.

---

## ⏰ When Do We Sell The Most?
**By Time of Day (Total Sales)**
| Time of Day | Total Sales |
|---|---:|
| Night | 39,033.34 |
| Afternoon | 39,018.04 |
| Morning | 37,380.20 |

**Top Hours (by total sales)**
| Hour (24h) | Total Sales |
|---|---:|
| 10 | 10,994.52 |
| 16 | 9,185.84 |
| 11 | 8,849.10 |
| 19 | 7,966.96 |
| 17 | 7,960.76 |

**By Weekday (Total Sales)**
| Weekday | Total Sales |
|---|---:|
| Tue | 18,637.38 |
| Mon | 17,925.10 |
| Fri | 17,257.66 |
| Thu | 16,477.40 |
| Wed | 16,093.46 |
| Sat | 15,182.52 |
| Sun | 13,858.06 |

**By Month (Total Sales)**
| Month | Total Sales |
|---|---:|
| Jan | 6,398.86 |
| Feb | 13,215.48 |
| Mar | 17,036.64 |
| Apr | 6,720.56 |
| May | 9,063.42 |
| Jun | 7,758.76 |
| Jul | 6,915.94 |
| Aug | 7,613.84 |
| Sep | 9,988.64 |
| Oct | 13,891.16 |
| Nov | 8,590.54 |
| Dec | 8,237.74 |

> **Patterns:** Night barely edges Afternoon for revenue, with Morning close behind — a well-balanced daypart profile. **Tuesdays** lead and **Sundays** are soft. Seasonality peaks around **March**, **October**, and **February**; **January** is the lowest.

---

## 🧠 Insights (Data-Backed)
1. **Product mix drives revenue:** *Latte* (≈ 27,866.30) and *Americano with Milk* (≈ 25,269.12) together contribute a large share of sales volume and value.
2. **Premium pricing power exists:** *Hot Chocolate* (avg ≈ 36.07) and *Cappuccino* (avg ≈ 36.00) carry the highest average order values.
3. **Peak selling windows:** 10:00, 16:00 and 11:00 are top-performing hours.
4. **Strong card preference:** ~97.55% of orders are paid by card; cash is minimal (~2.45%).
5. **Seasonal demand:** **Mar, Oct, Feb** are the best months; plan inventory and campaigns accordingly.
6. **Weekday dynamics:** **Tue** is consistently strongest; **Sun** underperforms, indicating opportunity for weekend-specific offers.

---

## ✅ Recommendations
1. **10–11 AM “Latte Rush” combo** to monetize the busiest hour; pair with a quick-bite upsell.  
2. **Evening bundles** (Americano with Milk / Latte + snack) to capitalize on strong Night revenue.  
3. **Sunday uplift plan:** launch a *family/duo* offer or **Hot Chocolate** promo to improve the softest day.  
4. **Lean into premium items:** Spotlight *Cappuccino* and *Hot Chocolate* in signage and loyalty rewards for higher AOV.  
5. **Pricing tests:** Consider a modest price review for *Espresso* and *Cortado*; monitor elasticity without hurting volume.  
6. **Inventory & staffing:** Align schedules with **10–11 AM** and **4–7 PM** peaks; ensure milk/chocolate inventory before **Mar/Oct**.  
7. **Frictionless payments:** Since ~97.55% use cards, keep contactless terminals prominent; train staff for speed.
8. **Seasonal campaigns:** Pre-load marketing before **Feb → Mar** and **Sep → Oct** peaks.

---

## 📈 Forecasting (How to Extend)
- Build **Monthly Sales** pivot from `working sheet` and add a line chart with trendline.  
- Use **`FORECAST.ETS`** or **3/6-month moving average** to project next quarter.  
- Compare forecast vs. actuals monthly and adjust promotions/inventory.

---

## 🧪 Reproduce the Analysis
1. Open **`project_01 Coffe_sales.xlsx`** in Excel.  
2. Go to **`DashBoard`** to view KPIs and charts (slicers can be added for item/time filters).  
3. Use **PivotTables** on `working sheet` to replicate the tables above.  
4. Modify the formulas in **Data Preparation** if you need different daypart splits or formats.

---

## 🔒 Assumptions & Limitations
- Currency is not specified; values are shown as recorded.  
- No customer-level IDs, store IDs, or discounts included; analysis is transaction-level only.  
- “Sales Forecasting” tab is provided as a scaffold; add your preferred forecasting formulas.

---

## 🤝 About
I’m **Prabhat Singh**, an aspiring Data Analyst.  
If this helped you, ⭐ the repo and connect with me!# Excel

