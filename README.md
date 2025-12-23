# Postman-Dummyjson-Framework

A scalable API test framework built using **Postman** on top of the **DummyJSON API**, focused on real-world API testing practices such as authentication flows, dynamic token handling, request chaining, and structured negative testing.

This project emphasizes **framework thinking over isolated requests**, with clean organization, reusable scripts, and documented handling of mock API limitations.

---

## 📌 Project Objectives

- Build a **scalable and maintainable API testing framework** using Postman
- Implement **real-world authentication flows** (Login, Access Token, Refresh Token)
- Avoid hardcoded values using **dynamic environment variables**
- Separate happy paths and negative scenarios clearly
- Apply **QA mindset**, not just tool usage

---

## 🧠 Tech Stack

- **Tool:** Postman  
- **API:** DummyJSON  
- **Scripting:** JavaScript (Postman scripts)  
- **Auth Type:** JWT-based (Mock implementation)

---

## 🔐 Authentication Flow

The framework implements a complete authentication lifecycle:

1. **Login**
   - User logs in using username & password
   - Access token and refresh token are extracted dynamically

2. **Get Current Auth User**
   - Access token is passed via `Authorization: Bearer <token>`
   - Validates that the token works for protected endpoints

3. **Refresh Auth Session**
   - Refresh token is used to generate a new access token
   - No username/password required

> ⚠️ Note:  
> DummyJSON is a mock API and allows reuse of refresh tokens.  
> This behavior is documented and handled accordingly in the framework.

---

## 📂 Collection Structure
DummyJSON API Framework<br>
│
├── 🔐 Auth<br>
│ └── Login<br>
│ ├── Login User and Get Tokens<br>
│ ├── Get Current Auth User<br>
│ └── Refresh Auth Session<br>
│
├── 👤 Users<br>
│ ├── Happy Path<br>
│ │ ├── Get All Users<br>
│ │ ├── Get User by ID<br>
│ │ ├── Create User<br>
│ │ ├── Update User<br>
│ │ └── Delete User<br>
│ │
│ └── Negative & Edge Cases<br>
│ ├── Invalid User ID<br>
│ ├── Missing Fields<br>
│ ├── Non-existing User<br>
│ └── Already Deleted User<br>
│
├── 📦 Products<br>
│ ├── Happy Path<br>
│ │ ├── Get All Products<br>
│ │ ├── Get Product by ID<br>
│ │ ├── Create Product<br>
│ │ └── Update Product<br>
│ │
│ └── Negative & Edge Cases<br>
│ ├── Invalid Product ID<br>
│ └── Invalid Product Data<br>
│
├── 🛒 Carts<br>
│ ├── Happy Path<br>
│ │ ├── Get Carts<br>
│ │ └── Add Product to Cart<br>
│ │
│ └── Negative Cases<br>
│ └── Add Product with Missing / Invalid Fields<br>
│
└── 🧪 Utilities (Planned)<br>
├── Common Assertions<br>
└── Helper Scripts<br>

---

## 🧪 Testing Approach

- **Happy Path Testing**
  - Valid inputs and expected successful responses
- **Negative Testing**
  - Missing fields, invalid IDs, incorrect payloads
- **Behavior-Based Assertions**
  - Status codes
  - Token presence
  - Response structure
- **No Hardcoding**
  - Tokens, IDs, and base URLs handled dynamically

---

## ⚠️ Known Limitations (Mock API)

- DummyJSON does not enforce strict validation in all scenarios
- Refresh token rotation is not implemented
- Some negative cases may return successful responses

These limitations are **documented intentionally** to reflect real QA analysis instead of forcing test failures.

---

## 🚀 How to Run the Collection

1. Import the collection into Postman
2. Create an environment and set:

   ```bash
   baseUrl = https://dummyjson.com
   ```
4. Run the **Login** request to generate tokens
5. Execute other requests — tokens are handled dynamically

---

## 📈 Current Progress

- [x] Auth module (Login, Access Token, Refresh Token)
- [x] Cart APIs (Happy Path + Negative Path)
- [x] Dynamic token handling
- [ ] Centralized auth logic (collection-level scripts)
- [ ] Reusable assertion utilities
- [ ] Data-driven testing
- [ ] Newman CLI integration

---

## 🎯 Learning Goals

- Strengthen API testing fundamentals
- Understand authentication workflows deeply
- Practice framework-level thinking
- Prepare for real-world QA / SDET roles

---

## 👤 Author

**Adarsh Mishra**  
BSc Computer Science | API & QA Testing Enthusiast  

---

## 📌 Updates

This README will be **updated regularly** as the framework evolves.
