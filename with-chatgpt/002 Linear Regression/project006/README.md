# Project 006

Started on July 08, 2026

Completed on July 08, 2026

## Problem Statement

Before we dive into the mathematics, I'd like you to find three real-world regression problems.

For each, describe:

* Target (y): What are you predicting?
* Possible features (X): What information might help predict it?
* Would you expect the relationship to be approximately linear? Why or why not?

For example, don't just say "house prices."

Think deeper:

* Which features?
* Which ones might increase price linearly?
* Which ones might have nonlinear effects?

## Solution from Gemini

This document explores three distinct real-world regression problems across different domains, breaking down their target variables, features, and the expected linear or nonlinear nature of their relationships.

---

### 1. E-Commerce & Logistics: Delivery Time Estimation

#### Target ($y$)
* **Total Delivery Duration:** The total time elapsed (in minutes) from the moment a customer submits an order on a delivery platform to the moment the courier marks it as delivered at the doorstep.

#### Possible Features ($X$)
* **Distance:** Driving or routing distance between the merchant and the delivery destination (miles or kilometers).
* **Order Size:** Total count of individual items included in the order.
* **Driver Availability:** The ratio of active, unassigned couriers to open, unfulfilled orders in that specific geographic zone.
* **Time of Day:** The exact hour the order was placed (mapped against local rush hour patterns).

#### Linearity Assessment
* **Approximately Linear:**
    * **Distance:** The relationship between transit time and distance is fundamentally linear. Assuming a steady average traffic speed, doubling the distance (e.g., from 2 miles to 4 miles) roughly doubles the active driving time.
* **Nonlinear:**
    * **Order Size:** A small order (1–3 items) scales linearly as it takes minimal time to pack. However, an order of 30 items does not take 10 times longer than 3 items; it encounters a logarithmic ceiling or flattening curve due to bulk packaging efficiencies and merchant kitchen assembly limits.
    * **Driver Availability:** This demonstrates an exponential or step-function behavior. When courier availability drops below a critical threshold, delivery times do not increase linearly—they spike exponentially due to compounding queue backlogs.

---

### 2. Healthcare & Fitness: Daily Caloric Expenditure

#### Target ($y$)
* **Total Daily Energy Expenditure (TDEE):** The total number of calories an individual burns over a 24-hour period.

#### Possible Features ($X$)
* **Lean Body Mass:** The total physical weight of the individual's body minus their fat mass (measured in kilograms).
* **Step Count:** Total cumulative steps taken throughout the calendar day.
* **Age:** The chronological age of the individual in years.
* **Ambient Temperature:** The average outdoor temperature the individual is exposed to throughout the day.

#### Linearity Assessment
* **Approximately Linear:**
    * **Lean Body Mass:** Muscle tissue is highly metabolically active even at rest. Every additional kilogram of lean mass increases the baseline resting metabolic rate in a highly stable, predictable linear fashion.
    * **Step Count:** Within a standard human range (e.g., 2,000 to 15,000 steps), each additional step requires a constant, repeatable expenditure of mechanical energy based on body weight.
* **Nonlinear:**
    * **Age:** Metabolic decline does not follow a strict downward diagonal line across a lifespan. It remains relatively stable through young and middle adulthood and then exhibits a more pronounced, accelerating downward curve in later years due to hormonal shifts and cellular changes.
    * **Ambient Temperature:** This follows a classic **U-shaped nonlinear curve**. Caloric expenditure increases in extreme cold (due to involuntary shivering and thermogenesis) and also increases in extreme heat (due to heavy sweating and elevated cardiovascular load), while staying flat and minimal within a temperate comfort zone.

---

### 3. Real Estate & Urban Planning: Commercial Office Rental Prices

#### Target ($y$)
* **Monthly Rental Price per Square Foot:** The standardized lease cost of commercial office real estate.

#### Possible Features ($X$)
* **Total Square Footage:** The total contiguous physical footprint of the office space.
* **Proximity to Transit:** The exact walking distance (in meters) to the closest major subway or light rail hub.
* **Floor Level:** The vertical placement of the office suite within a skyscraper.
* **Internet Infrastructure:** Maximum available dedicated fiber-optic bandwidth speeds (measured in Gbps).

#### Linearity Assessment
* **Approximately Linear:**
    * **Internet Bandwidth:** Up to standard enterprise tiers, the premium a business is willing to pay scales linearly with network capability, as reliable high-speed data directly dictates operational capacity.
* **Nonlinear:**
    * **Total Square Footage:** While total overall rent goes up, the price *per square foot* exhibits diminishing marginal returns (a logarithmic curve). Larger commercial footprints almost always unlock a bulk volume discount per square unit.
    * **Proximity to Transit:** This effect is steeply nonlinear. Being within 100 to 300 meters of a transit hub yields an enormous financial premium, but the difference between being 2,000 meters away versus 2,500 meters away is virtually zero, as both fall completely outside a realistic walking radius.
    * **Floor Level:** Rent generally edges upward with higher floors due to better lighting and reduced street noise. However, this gradient hits a sharp polynomial or exponential spike once you hit the top "penthouse" tiers, which carry an outsized premium for corporate prestige and panoramic views.