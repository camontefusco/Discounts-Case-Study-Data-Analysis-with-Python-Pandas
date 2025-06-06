# 📊 Eniac Discounts Case Study — Data Analysis with Python & Pandas

![Eniac Banner](./A_banner_image_for_a_project_titled_"Eniac_Discoun.png)

## 💼 Overview

This project investigates whether **product discounts** help or harm **Eniac**, a fast-growing e-commerce company. It combines rigorous data cleaning, validation, categorization, and analysis using **Python**, **Pandas**, and visualization tools to support decision-making.

---

## 🧠 Business Context & Objectives

**Marketing Team** argues that discounts drive acquisition and retention, while the **Board of Investors** believes aggressive discounting increases volume but hurts revenue and profitability.

The goal is to use data to objectively determine whether discounts contribute positively to Eniac’s growth or erode long-term margins—and to develop a strategic recommendation based on that analysis.

---

## ❓ Business Questions

- How should products be categorized for better insights?
- What is the pricing and discount distribution across categories?
- Do discounts improve sales volume or order value?
- Do special events (e.g. Black Friday) drive better results?
- What pricing strategy should Eniac follow?

---

## 📂 Data Sources

| File             | Description                                                |
|------------------|------------------------------------------------------------|
| `orders.csv`      | Customer-level transactions                               |
| `orderlines.csv`  | Item-level breakdown of each order                        |
| `products.csv`    | Product catalog with regular and promotional prices       |
| `brands.csv`      | Brand metadata (redundancy and key inconsistencies)       |

---

## 🧹 Notebook Summaries

### `data_cleaning.ipynb`

**Goal**: Clean and prepare raw data for analysis.  
**Methods**:
- Converted string-based dates/prices to `datetime` and `float`.
- Removed 45% duplicate entries from `products.csv`.
- Suggested schema improvements (e.g., separating `promotions` into its own table).
- Introduced input validation for pricing fields.
- Proposed dedicated `shopping_cart` table for temporary orders.

---

### `data_quality.ipynb`

**Goal**: Validate and audit the cleaned data.  
**Checks Performed**:
- Missing values, duplication, and referential integrity.
- Ensured `promo_price` was always less than or equal to `regular_price`.
- Confirmed timestamp formatting and SKU alignment (with minor issues noted).

---

### `project_categories.ipynb`

**Goal**: Assign products to meaningful business categories and price tiers.  
**Process**:
- Used keyword matching on product names to assign categories and subcategories.
- Grouped products into tiers: **Low**, **Mid**, **High** based on price.
- Analyzed price and discount behavior within each category.

**Category Taxonomy**:

**Main Product Categories**:

| Category       | Subcategories                             | Example SKUs                    |
|----------------|--------------------------------------------|---------------------------------|
| **Storage**     | SSDs, HDDs, Flash Drives                   | Samsung EVO 1TB, WD Blue SSD    |
| **Accessories** | Mice, Keyboards, USB Hubs, Cables          | Logitech M100, Anker USB-C Hub  |
| **Components**  | RAM, Power Supplies, Cooling Pads          | Corsair Vengeance, Cooler Master PSU |
| **Networking**  | Routers, Ethernet Cables, Wi-Fi Dongles    | TP-Link Router, Netgear USB WiFi |
| **Audio**       | Headphones, Speakers, Microphones          | JBL Tune 500, Blue Yeti         |
| **Displays**    | Monitors, Mounts, Screen Protectors        | LG UltraFine, VESA Mount        |

✅ **76% of the catalog** was successfully categorized.

---

### `analysis.ipynb`

**Goal**: Measure the actual impact of discounts on performance.  
**Analysis Performed**:
- Calculated % of discounted products sold (95%).
- Evaluated revenue, volume, and AOP (Average Order Price) over time.
- Tagged special events like Black Friday & Christmas.
- Case study: Samsung SSD sold 328 times at over 40 price points.

**Findings**:
- Discounts did **not** significantly increase AOP.
- Special events like Black Friday led to sales peaks regardless of discount level.
- Excessive price variability on high-volume products indicates poor pricing strategy.

---

## 🔍 Key Insights

- **95% of sold products were discounted**, making discounting the default behavior.
- Discounts **did not meaningfully increase** average order price (AOP).
- **Seasonal events** outperformed discounts in boosting sales.
- Strategic inconsistencies were visible—e.g., **Samsung SSDs sold at 40+ price points**.
- **High-tier products** performed better under targeted, time-limited promotions.
- **Accessories** often saw deep discounts that **hurt profitability** without increasing volume proportionally.

---

## 📝 Strategic Recommendations

### 🎯 Balanced Discounting

- Use **moderate (10–20%) discounts** during high-traffic events like Black Friday.
- Avoid **frequent, platform-wide markdowns** that erode value perception and margins.

### 🗃️ Product Categorization

- Maintain structured hierarchy:
- Apply pricing logic based on category performance (e.g., avoid deep discounts on low-margin accessories).

### 🧽 Data Infrastructure

- Normalize the schema with:
- `brand_id` and `promotion_id` as foreign keys.
- A dedicated `promotions` table to handle time-based discounts.
- A `shopping_cart` table to track unfinalized purchases.
- Validate input for price format, duplicates, and missing fields before ingestion.

### 🧪 Controlled Testing

- Run **A/B tests** to evaluate:
- Discount depth (10% vs 30%)
- Timing (weekdays vs weekends)
- Conversion impact and order value

### 👤 Customer Segmentation

| Segment Type     | Criteria                                   |
|------------------|--------------------------------------------|
| Loyalty Level    | First-time vs returning                    |
| Spend Behavior   | High-AOV vs low-AOV                        |
| Promo Sensitivity| Response to past promotions                |

- Use customer segments to **tailor promotions**, improving efficiency and reducing margin waste.

---

## ✅ Final Verdict

> “Discounts alone won’t save us. Strategic pricing, clean data, and quality products will.”

The data supports the **Board of Investors' concerns**:

- Discounting by default has **not improved order value** or long-term performance.
- Strategic pricing around **seasonal events**, supported by **data-backed product categorization**, is far more effective.
- Eniac should transition from reactive discounting to **planned, segmented, and tested promotional strategies**.

📌 The future lies in **value-driven growth**, powered by data quality, category focus, and smart pricing—not blanket promotions.

---
