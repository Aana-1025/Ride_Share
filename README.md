# Ride_Share Backend Application

**Application Name:** Ride_Share  
**Student Name:** Antara Utane  
**Roll Number:** 10106  

---

## Project Overview

Ride_Share is a backend application inspired by real-world ride-sharing platforms like Uber. This project is built using **Spring Boot**, **MongoDB**, and **JWT-based authentication**. It demonstrates important backend concepts such as authentication, role-based access control, REST APIs, MongoDB queries, and aggregation pipelines.

The system supports two types of users: **Passengers** and **Drivers**, manages the complete ride lifecycle, and provides analytics for insights.

---

## Features

- User registration and login using JWT authentication  
- Role-based access (Passenger and Driver)  
- Create, accept, and complete rides  
- Secure APIs using Spring Security  
- MongoDB queries: search, filter, sort, and pagination  
- MongoDB aggregation pipelines for analytics  
- Clean and modular folder structure  
- Proper validation and error handling  

---

## Tech Stack

- Backend: Spring Boot (Java)  
- Database: MongoDB  
- Security: Spring Security + JWT  
- ORM: Spring Data MongoDB  
- Build Tool: Maven  

---

## Project Folder Structure

```src/main/java/org.example.rideshare
├── config
│ ├── SecurityConfig.java
│ └── JwtFilter.java
├── controller
│ ├── AuthController.java
│ ├── RideController.java
│ └── AnalyticsController.java
├── model
│ ├── User.java
│ └── Ride.java
├── repository
│ ├── UserRepository.java
│ └── RideRepository.java
├── service
│ ├── UserService.java
│ ├── RideService.java
│ └── AnalyticsService.java
└── util
└── JwtUtil.java```


---

## Roles

| Role | Description |
|-----|-------------|
| ROLE_USER | Passenger |
| ROLE_DRIVER | Driver |

---

## Ride Status Flow

**REQUESTED → ACCEPTED → COMPLETED**

---

## Authentication APIs

| Endpoint | Method | Description |
|--------|--------|-------------|
| /api/auth/register | POST | Register a new user |
| /api/auth/login | POST | Login and receive JWT token |

---

## Ride APIs

| Endpoint | Method | Description |
|--------|--------|-------------|
| /api/rides | POST | Create a new ride |
| /api/rides/accept/{id} | POST | Driver accepts a ride |
| /api/rides/complete/{id} | POST | Complete a ride |

---

## Analytics APIs

| Endpoint | Method | Description |
|--------|--------|-------------|
| /api/analytics/driver/{driver}/earnings | GET | Get total earnings of a driver |

---

## API Master Table (Advanced Queries and Aggregations)

| No | Endpoint | Method | Concepts Used |
|----|---------|--------|---------------|
| 1 | /api/v1/rides/search | GET | OR query, Regex search |
| 2 | /api/v1/rides/filter-distance | GET | Range filter (gte, lte) |
| 3 | /api/v1/rides/filter-date-range | GET | Date range filtering |
| 4 | /api/v1/rides/sort | GET | Sorting |
| 5 | /api/v1/rides/user/{userId} | GET | Equality filter |
| 6 | /api/v1/rides/user/{userId}/status/{status} | GET | AND condition |
| 7 | /api/v1/driver/{driverId}/active-rides | GET | Fixed status filtering |
| 8 | /api/v1/rides/filter-status | GET | AND + OR combination |
| 9 | /api/v1/rides/advanced-search | GET | Pagination and sorting |
| 10 | /api/v1/analytics/rides-per-day | GET | Group and sort aggregation |
| 11 | /api/v1/analytics/driver/{id}/summary | GET | Aggregation metrics |
| 12 | /api/v1/analytics/user/{id}/spending | GET | Sum and count aggregation |
| 13 | /api/v1/analytics/status-summary | GET | Group by status |
| 14 | /api/v1/rides/date/{date} | GET | LocalDate filtering |

---

## Concepts Learned

- JWT token generation and validation  
- Spring Security filter chain  
- Role-based authorization  
- MongoDB Criteria queries  
- Regex and case-insensitive search  
- Range and date-based filtering  
- Pagination and sorting  
- Aggregation pipelines (match, group, project)  
- Transaction management  

---

## Sample API Calls

- POST /api/auth/register  
- POST /api/auth/login  
- POST /api/rides  
- POST /api/rides/accept/{id}  
- POST /api/rides/complete/{id}  
- GET /api/analytics/driver/{driver}/earnings  

---

## Conclusion

Ride_Share is a complete backend application that demonstrates real-world backend development practices using Spring Boot and MongoDB. It includes secure authentication, structured APIs, and analytics, making it a strong foundation for scalable backend systems.

---

Developed by **Antara Utane**  
Roll Number: **10106**
