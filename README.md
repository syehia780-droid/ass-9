# Database Design – ERD Assignments

Entity Relationship Diagrams (ERD) drawn in **Chen notation** for two database systems:

1. **Hospital Management System**
2. **Hotel Reservation & Management System**

The full document (2 pages, A3 landscape) is available here: [`ERD_Hospital_and_Hotel.pdf`](ERD_Hospital_and_Hotel.pdf)

---

## 📁 Repository Structure

```
.
├── ERD_Hospital_and_Hotel.pdf   # Final deliverable (Page 1: Hospital, Page 2: Hotel)
├── images/
│   ├── hospital_erd.png         # Preview of page 1
│   └── hotel_erd.png            # Preview of page 2
└── README.md
```

---

## 🏨 Hotel Reservation & Management System

### Problem Statement

A hotel wants a database system to manage its **guests, rooms, room types, reservations, services, and payments**.

### ERD

![Hotel ERD](images/hotel_erd.png)

### Entities and Attributes

| Entity | Primary Key | Attributes |
|---|---|---|
| **guest** | `guest ID` | name, email, phone number, nationality, date of birth |
| **reservation** | `reservation ID` | booking date, check-in date, check-out date, number of guests, status |
| **room** | `room number` | floor number, status |
| **room type** | `room type ID` | name, description, max guests, price per night |
| **service** | `service ID` | name, description, price |
| **payment** | `payment ID` | payment date, amount, payment method, status |

### Relationships and Cardinality

| # | Relationship | Entities | Cardinality | Type | Relationship Attributes |
|---|---|---|---|---|---|
| 1 | makes | guest – reservation | 1 : M | One-to-Many | – |
| 2 | includes | reservation – room | M : N | Many-to-Many | price per night (agreed for that reservation) |
| 3 | is of type | room type – room | 1 : M | One-to-Many | – |
| 4 | requests | reservation – service | M : N | Many-to-Many | quantity, request date & time |
| 5 | has | reservation – payment | 1 : M | One-to-Many | – |

### Business Rules

- A guest can make many reservations; each reservation belongs to exactly one guest.
- A reservation can include one or more rooms, and a room can appear in many reservations over time.
- Every room belongs to one room type; one room type can be assigned to many rooms.
- A reservation can have many service requests, and the same service can be requested in many reservations.
- A reservation can have one or more payments; each payment belongs to one reservation.

---

## 🏥 Hospital Management System

### ERD

![Hospital ERD](images/hospital_erd.png)

### Entities

`department`, `doctor`, `patient`, `appointment` (weak), `medical record` (weak), `treatment` (weak)

---

## 🖊️ Notation (Chen)

| Symbol | Meaning |
|---|---|
| Rectangle | Entity |
| Double rectangle | Weak entity |
| Diamond | Relationship |
| Double diamond | Identifying relationship |
| Ellipse | Attribute |
| Underlined ellipse | Key attribute |
| Double ellipse | Multivalued attribute |
| Dashed ellipse | Derived attribute |

---

## 🛠️ Tools

- [draw.io (diagrams.net)](https://app.diagrams.net/) – original diagrams
- Python (`reportlab`, `pypdf`) – final PDF layout

---

## 👤 Author

_Your Name_ – _Your University / Course_
