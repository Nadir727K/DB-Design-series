#  Instagram Thrift & Handmade Store — ER Diagram

##  Overview

This project models a database system for a small Instagram-based business selling **thrifted (unique)** and **handmade (multi-unit)** products.

The goal is to design a **normalized, scalable ER diagram** that supports:

* Product management
* Inventory tracking
* Customer orders
* Payment handling
* Shipment tracking

---

##  Problem Context

The business initially operates through Instagram DMs and WhatsApp. As it grows, the owner needs a structured system to:

* Track available products and stock
* Handle multiple customer orders
* Manage payments and delivery status
* Differentiate between **unique thrift items** and **repeatable handmade items**

---

##  System Design Approach

### 1. Separation of Concerns

The system is divided into logical layers:

* **Customer Layer** → who places orders
* **Product Layer** → what is being sold
* **Order Layer** → transaction details
* **Payment Layer** → financial tracking
* **Shipment Layer** → delivery tracking

---

### 2. Product Modeling (Key Design Decision)

Products are split using **specialization**:

* **Thrift Products**

  * Unique items (typically stock = 1)
  * Include condition (e.g., New, Good, Worn)

* **Handmade Products**

  * Can have multiple units
  * Scalable inventory

---

### 3. Inventory Strategy

Inventory is managed at the **Product Variant level**:

* Supports attributes like **size, color, price**
* Enables flexible stock management

---

### 4. Order Design

* A **Customer can place multiple Orders**
* An **Order can contain multiple Products**

This is handled using a junction table:

* `order_item` → resolves many-to-many relationship

---

### 5. Payment & Shipment

* **Payment** is stored separately for flexibility
* **Shipment** tracks delivery lifecycle

This avoids mixing unrelated data into a single entity.

---

---

##  Key Relationships

* Customer → Order (**1:N**)
* Order → Order_Item (**1:N**)
* Product_Variant → Order_Item (**1:N**)
* Product → Product_Variant (**1:N**)
* Product → Thrift / Handmade (**ISA relationship**)
* Category → Product (**1:N**)
* Order → Payment (**1:1**)
* Order → Shipment (**1:1**)

---

##  Design Highlights

*  Fully normalized schema
*  Clear separation of business concerns
*  Supports both unique and reusable inventory
*  Real-world order lifecycle modeling
*  Avoids redundancy and data anomalies

---

##  Visual Structure (Mental Model)

```
Customer → Order → Payment → Shipment
              ↓
         Order_Item
              ↑
     Product_Variant
              ↑
           Product
          /       \
   Thrift        Handmade

Category → Product
```


---



1. Open the ER diagram in Eraser.io
2. Follow the left → right flow
3. Observe how product data feeds into order processing

---



**Nadir Khan**
#NKCodes | #Code&Commerce

---

##  Final Note

This design focuses on **clarity, scalability, and real-world alignment**, making it suitable for both academic evaluation and practical implementation.
