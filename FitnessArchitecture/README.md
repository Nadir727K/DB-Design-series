# Fitness-Coaching-Architecture-DB-
System design and DB architecture for a fitness app. Includes ER diagrams, SQL schema, and data models for managing personalized coaching workflows at scale.

### 🛠 Tech Stack
 * **Modeling:** Eraser.io
 * **Database:** PostgreSQL / SQL
 * **Architecture:** Relational Schema (3NF)
### 📐 Schema Overview
This design implements a role-based architecture separating **Users** into **Clients** and **Trainers**, connected through a robust subscription and content delivery engine.
 * User Management : Centralized authentication with role-specific profiles.
 * Coaching Engine : Dynamic plans mapped to multiple sessions.
 * Monetization : subscriptions linked to payments with unique transaction auditing.
 * Retention : consultations and client_checkins for active engagement.
 * Analytics : progress_tracking for biometric data logging.
### 🗄 Core Entities
| Entity | Description |

* Users :  Master table for credentials and roles (Trainer/Client). |
* Plans & Sessions : The core product offered by influencers. |
* Subscriptions :  Tracks active access and plan validity. |
* Payments :  Financial audit trail for all transactions. |
* Progress : Time-series data for weight and body fat metrics. |
### 🚀 Implementation Details
 * Integrity: Strict Foreign Key constraints ensure data consistency across the plan-to-session hierarchy.
 * Auditability: Standardized created_at and updated_at timestamps on all tables.
 * Scalability: Optimized for high-frequency progress logging and complex scheduling queries.
*Developed for the COHORT 2026 Web Dev Project.*
