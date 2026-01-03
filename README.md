# 🚗 Smart Rent-A-Car Fleet Management System

A Java-based simulation of a car rental company that manages a dynamic fleet of vehicles. Unlike simple data-storage apps, this project implements **business logic** where vehicles age, accumulate mileage, and trigger maintenance alerts based on their specific types.

## 🎯 Project Overview
This project demonstrates **Concrete Inheritance** and **Polymorphism** without using Abstract classes or Interfaces. The core focus is on **State Management**: vehicles are not just static objects; they change status (Available -> Rented -> Maintenance) based on usage.

## ⚙️ Key Features
* **Dynamic Pricing Logic:**
    * **Standard Cars:** Flat daily rate.
    * **Sports Cars:** Multiplied rate due to risk factor + fixed insurance cost.
    * **Trucks:** Discounted rates for long-term rentals (>7 days).
* **Smart Wear & Tear System:**
    * Vehicles track their own mileage upon return.
    * **Polymorphic Maintenance:** While standard cars need maintenance every 10,000 km, `SportsCar` overrides this logic to trigger alerts every 3,000 km due to engine sensitivity.
* **Fleet Management:** Uses `ArrayList` to manage a mixed fleet of different vehicle types within a single list.
* **Super Keyword Usage:** effectively utilizes `super()` constructors and method calls (`super.teslimAl()`) to extend parent logic rather than rewriting it.

## 📂 Class Structure
* **`Car` (Base Class):** Represents a standard vehicle. Handles basic rental/return operations and checks for standard maintenance intervals.
* **`SportsCar` (Subclass):** Extends `Car`. Overrides the pricing method (higher cost) and the return method (stricter maintenance rules).
* **`Truck` (Subclass):** Extends `Car`. Overrides pricing to apply bulk discounts.
* **`RentalSystem` (Main):** The simulation loop that rents cars, calculates prices dynamically, handles returns, and auto-detects vehicles needing service.

## 💻 Code Example (Polymorphism)

```java
// Logic: SportsCar uses parent's logic for mileage but adds its own strict rule.
@Override
public void teslimAl(int km) {
    super.teslimAl(km); // Reusing parent logic (Code Reusability)

    // Specific Business Rule for Sports Cars
    if (getKilometre() > 3000) {
        System.out.println("⚠️ CRITICAL: High performance engine needs maintenance!");
        setBakimGerekiyorMu(true);
    }
}
