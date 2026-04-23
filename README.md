# Manual Web Testing: Automation Exercise

**Target Website:** [https://automationexercise.com/](https://automationexercise.com/)  
**Tester:** Niyazbek  
**Testing Type:** Manual Smoke & Functional Testing  
**Environment:** Google Chrome Version 124.0.x (Official Build) / Windows 11 / Desktop  

---

## 📊 Test Execution Summary

| Metric | Value |
| :--- | :--- |
| **Total Test Cases** | 11 |
| **Passed** | 9 |
| **Failed** | 2 |
| **Bugs Found** | 2 |
| **Execution Date** | April 19, 2026 |
| **Status** | ⚠️ **At Risk** (Critical Bug Found) |

---

## 1. Module: User Registration

### TC_011: User Signup — Positive Test
* **Description:** Verify that a new user can successfully register an account.
* **Steps:**
    1. Navigate to [automationexercise.com/login](https://automationexercise.com/login).
    2. Enter Name and Email in "New User Signup!" section.
    3. Click "Signup".
    4. Fill in account details (Password, Address, Mobile Number).
    5. Click "Create Account".
* **Expected Result:** "ACCOUNT CREATED!" message is displayed.
* **Actual Result:** Account created successfully. Redirected to the success page.
* **Status:** PASSED ✅

---

## 2. Module: Shopping Cart

### TC_012: Add Product to Cart
* **Description:** Verify that a user can add a product to the shopping cart.
* **Steps:**
    1. Click on the 'Products' button at the top header.
    2. Hover over a product and click 'Add to cart'.
    3. Click 'View Cart' button in the pop-up.
* **Expected Result:** Product added with correct price/quantity. System should prevent negative values.
* **Actual Result:** Product is added, but system allows entering negative quantity, leading to negative price.
* **Status:** FAILED ❌ (See **BUG_002**)

---

## 3. Module: Search Functional

### TC_013: Search Product Functional Test
* **Status:** PASSED ✅

### TC_014: Search with Non-Existent Product
* **Status:** PASSED ✅

---

## 4. Module: Form Validation & Persistence

### TC_015: Contact Us Form — Required Fields Validation
* **Status:** PASSED ✅

### TC_016: Contact Us Form — Invalid Email Format
* **Description:** Verify if the system allows submitting the form with an incorrect email format.
* **Actual Result:** Form was submitted successfully without error (BUG).
* **Status:** FAILED ❌ (See **BUG_001**)

### TC_017: Cart Persistence After Logout
* **Status:** PASSED ✅

---

## 5. Module: UI & Navigation

### TC_018: Subscription in Footer | **Status:** PASSED ✅
### TC_019: Category Filter Navigation | **Status:** PASSED ✅
### TC_020: Product Detail Page View | **Status:** PASSED ✅
### TC_021: Logout Functionality | **Status:** PASSED ✅

---

## 🐞 Bug Reports

### BUG_001: Missing Domain Validation in Contact Us Form
* **Severity:** Medium | **Priority:** Medium
* **Steps to Reproduce:**
    1. Navigate to 'Contact Us' page.
    2. Enter an incomplete email address: `test@test` (missing .com/.net).
    3. Click 'Submit'.
* **Actual Result:** The system accepts the invalid email and submits the form.
* **Expected Result:** System should display an error message for missing domain suffix.

### BUG_002: Negative Product Quantity Leads to Negative Total Price
* **Severity:** Critical 🚨 | **Priority:** Highest
* **Description:** The shopping cart allows entering a negative quantity, which results in a negative total price. Financial logic bypass.
* **Steps to Reproduce:**
    1. Navigate to any product page.
    2. In 'Quantity', enter `-5`.
    3. Click 'Add to cart' -> 'View Cart'.
* **Actual Result:** Total price becomes negative (e.g., Rs. -5000).
* **Expected Result:** System should prevent quantities less than 1.
* **Attachment:** [View Bug Screenshot](./image_5.png)

---

## 🎯 Conclusion
The main functionality (Registration, Search, Categories) works correctly. However, two bugs were found. **BUG_002 is critical** as it allows order price manipulation, which could lead to financial loss. Immediate fix is required.
