# 🚀 RideShare Backend – Student Helper Document  
**(In-Class Mini Project – No Testing Version)**

**Project Name:** RideShare Backend  
**Student Name:** Antara Utane  
**Roll Number:** 10106  

---

## 1️⃣ Project Overview

RideShare Backend is a mini ride-sharing backend application built using:

- Spring Boot  
- MongoDB  
- JWT Authentication  
- Input Validation  
- Global Exception Handling  

This project combines all the concepts learned in previous classes, following a clean architecture pattern:

- Mongo Repository  
- DTOs  
- Validation  
- JWT Login & Authorization  
- Controller → Service → Repository flow  

---

## 2️⃣ Entities & Relationships

### 📌 User Entity

##User

```├─ id : String
├─ username : String
├─ password : String
├─ role : String → ROLE_USER / ROLE_DRIVER```


### 📌 Ride Entity

```Ride
├─ id : String
├─ userId : String → Passenger
├─ driverId : String? → Driver
├─ pickupLocation : String
├─ dropLocation : String
├─ status : String → REQUESTED / ACCEPTED / COMPLETED
├─ createdAt : Date```

### 📌 Relationship Diagram

```USER (ROLE_USER) DRIVER (ROLE_DRIVER)
│ │
│ requests │ accepts
▼ ▼
┌────────────────────────────────┐
│ RIDE │
├────────────────────────────────┤
│ userId → USER.id │
│ driverId → DRIVER.id │
│ status → REQUESTED/ACCEPT │
└────────────────────────────────┘```

---

## 3️⃣ Folder Structure (Must Follow Exactly)

```
```src/
├── main/
│ ├── java/
│ │ └── org/example/rideshare/
│ │ ├── model/
│ │ ├── repository/
│ │ ├── service/
│ │ ├── controller/
│ │ ├── config/
│ │ ├── dto/
│ │ ├── exception/
│ │ └── util/
│ └── resources/
│ └── application.properties```

---

## 4️⃣ Features Implemented

### 🧑‍🤝‍🧑 User Registration & Login (JWT)

**Endpoints**
- `POST /api/auth/register`
- `POST /api/auth/login`

**Rules**
- Passwords are stored using BCrypt encoding  
- JWT token is returned on successful login  
- Roles supported: `ROLE_USER`, `ROLE_DRIVER`

---

### 🚕 Request a Ride (Passenger)

**Endpoint**
- `POST /api/v1/rides`

**Request Body**
```json
{
  "pickupLocation": "Koramangala",
  "dropLocation": "Indiranagar"
}
