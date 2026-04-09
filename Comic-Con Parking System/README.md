# Comic-Con Event Parking System – ER Diagram

## Overview

This project presents the **database design for a large event parking management system** used at a convention venue hosting **Comic-Con India**. During the event, thousands of visitors arrive using different vehicle types and require organized parking across multiple zones and levels.

The goal of this assignment was to design an **Entity-Relationship Diagram (ERD)** that models how vehicles enter the facility, receive parking tickets, occupy parking spots, and complete a parking session with payment processing.

---

## Problem Context

A large convention venue must manage high-volume vehicle traffic across multiple days of the event. Vehicles arriving at the venue include bikes, cars, SUVs, cabs, and EVs. The parking facility is structured into multiple **zones and levels**, with some spots reserved for specific categories such as:

* Cosplayers with props
* Exhibitors
* Creators
* VIP guests
* Staff members
* EV charging vehicles

The system must track vehicle entries, assign appropriate parking spots, record entry and exit times, calculate parking fees, and store payment records.

---

## System Objectives

The designed ERD allows the system to:

* Track vehicles entering the parking facility
* Identify the type of vehicle entering
* Issue parking tickets upon entry
* Assign parking spots based on availability and type
* Track parking sessions with entry and exit timestamps
* Determine which zone and level a parking spot belongs to
* Apply pricing rules for parking fees
* Record payment information for each session
* Track spot availability across the venue
* Support multiple visits by the same vehicle across different days

---

## Core Entities in the Design

### Vehicles

Stores information about vehicles entering the venue including license plate, vehicle type, and owner category.

### Parking Tickets

Represents the token issued when a vehicle enters the parking facility. This ticket is used later to validate exit and retrieve the parking session.

### Parking Sessions

The central entity of the system. A parking session records the lifecycle of parking including entry time, exit time, assigned spot, fee calculation, and payment status.

### Parking Spots

Represents individual parking locations inside the venue. Each spot belongs to a specific zone and may be reserved for particular categories such as VIP, staff, or EV charging.

### Zones

Represents the physical parking structure of the venue. Zones can correspond to specific levels or sections of the parking facility.

### Fee Rules

Defines the pricing logic used to calculate parking fees based on vehicle type, owner category, and hourly rates.

### Payments

Stores payment records associated with completed parking sessions.

---

## Key Design Considerations

* **One vehicle can enter multiple times** during the event.
* **One parking spot can serve many vehicles over time**.
* **Parking sessions track entry and exit timestamps**.
* **Parking tickets act as entry tokens but do not store session details**.
* **Parking sessions manage spot assignment and fee calculation**.
* **Parking spots belong to zones for structured facility management**.
* **Fee rules allow flexible pricing logic for different vehicle categories**.

---

## ERD Design Approach

The diagram follows a logical system flow:

**Vehicle → Ticket Issued → Parking Session → Spot Allocation → Payment**

Infrastructure elements like **zones and parking spots** define the physical structure, while **fee rules and payments** handle operational and financial logic.

This structure ensures the system remains **normalized, scalable, and suitable for high-volume event parking environments**.

---

## Learning Outcome

This assignment focused on translating a real-world operational scenario into a structured database design. It helped reinforce key database modeling concepts such as:

* Entity separation and normalization
* Relationship modeling
* Lifecycle-based entity design
* Handling transactional records in relational systems

Designing this ERD strengthened practical understanding of **database architecture used in real event management and parking systems**.

---

## Tools Used

* **Eraser.io** – for designing the ER diagram
* **GitHub** – for version control and project documentation

---

## Author

**Nadir Khan**

#NKCodes
#Code&Commerce
