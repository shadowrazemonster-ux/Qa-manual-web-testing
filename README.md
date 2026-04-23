Manual Web Testing: Automation Exercise
Target Website: [https://automationexercise.com/](https://automationexercise.com/)  
Tester: Niyazbek  
Testing Type: Manual Smoke & Functional Testing  
Environment: Google Chrome / Windows 11 / Desktop  

1. Module: User Registration

TC_011: User Signup — Positive Test
Description: Verify that a new user can successfully register an account.

Steps:
1. Navigate to [automationexercise.com/login](https://automationexercise.com/login).
2. Enter Name and Email in "New User Signup!" section.
3. Click "Signup".
4. Fill in account details (Password, Address, Mobile Number).
5. Click "Create Account".

Expected Result: "ACCOUNT CREATED!" message is displayed.
Actual Result: Account created successfully. Redirected to the success page.
Status: PASSED ✅

2. Module: Shopping Cart

TC_012: Add Product to Cart
Description: Verify that a user can add a product to the shopping cart.

Steps:
1. Click on the 'Products' button at the top header.
2. Hover over a product and click 'Add to cart'.
3. Click 'View Cart' button in the pop-up.

Expected Result: The product is added to the cart and displayed with the correct price and quantity.
Actual Result: Product is visible in the cart. Price and quantity are correct.
Status: PASSED ✅

3. Module: Search Functional

TC_013: Search Product Functional Test
Description: Verify that the search bar returns relevant results.

Steps:
1. Click on 'Products' button.
2. Enter 'dress' in search input and click the search button.

Expected Result: All visible products contain the word 'dress'.
Actual Result: Search results show 9 products, all relevant to the keyword.

tatus: PASSED ✅

TC_014: Search with Non-Existent Product
Description: Verify system behavior when searching for an item that is not in the catalog.
Steps:
1. Navigate to 'Products' page.
2. Enter 'Tesla Cybertruck' in search bar and click the search icon.
Expected Result: No products are displayed, and a "No results found" message appears.
Actual Result: Product list is empty. UI is stable.
Status: PASSED ✅

TC_015: Contact Us Form — Required Fields Validation
Description: Verify that the form cannot be submitted if mandatory fields are empty.
Steps:
1. Navigate to 'Contact Us' page.
2. Leave Name, Email, and Message fields empty.
3. Click 'Submit' button.
Expected Result: Browser alert or validation message appears ("Please fill out this field").
Actual Result: Submission blocked by browser validation.
Status: PASSED ✅

TC_016: Contact Us Form — Invalid Email Format
Description: Verify if the system allows submitting the form with an incorrect email format.
Steps:
1. Navigate to 'Contact Us' page.
2. Fill all fields but enter 'wrong_email_format' (without @) in the Email field.
3. Click 'Submit'.
Expected Result: Form should be rejected, and an error message should appear.
Actual Result: Form was submitted successfully without error (BUG).
Status: FAILED ❌

TC_017: Cart Persistence After Logout
Description: Verify that items in the cart are saved after the user logs out.
Steps:
1. Add any product to the cart.
2. Click 'Logout' button.
3. Log in again with the same account.
4. Open the 'Cart' page.
Expected Result: The previously added item is still present in the cart.
Actual Result: The product is saved in the cart as expected.
Status: PASSED ✅

TC_018: Subscription in Footer
Description: Verify that the user can successfully subscribe to the newsletter.
Steps:
1. Scroll down to the Footer of any page.
2. Enter a valid email address in the 'Subscription' input.
3. Click the arrow button next to the input.
Expected Result: A success message "You have been successfully subscribed!" is displayed.
Actual Result: Success message appeared as expected.
Status: PASSED ✅

TC_019: Category Filter Navigation
Description: Verify that clicking on a category correctly filters the products.
Steps:
1. Click on 'Women' category in the left sidebar.
2. Select the 'Dress' sub-category.
Expected Result: User is redirected to the page displaying only Women's dresses.
Actual Result: Filter applied successfully. All items are relevant.
Status: PASSED ✅

TC_020: Product Detail Page View
Description: Verify that the product detail page displays correct information.
Steps:
1. Click on 'Products' in the header.
2. Click 'View Product' on the first item in the list.
Expected Result: Product details (name, category, price, availability) are visible.
Actual Result: All details are correctly displayed on the product page.
Status: PASSED ✅

TC_021: Logout Functionality
Description: Verify that the 'Logout' button terminates the user session.
Steps:
1. Ensure you are currently logged in.
2. Click the 'Logout' button in the top menu.
Expected Result: User is redirected to the 'Login' page, and the session is closed.
Actual Result: Redirected to login page. Access to account restricted.
Status: PASSED ✅


5. Bug Reports

BUG_001: Missing Domain Validation in Contact Us Form
Severity: Medium
Priority: Medium

Steps to Reproduce:
1. Navigate to 'Contact Us' page.
2. Fill in Name, Subject, and Message fields.
3. Enter an incomplete email address: test@test (missing top-level domain like .com or .net).
4. Click 'Submit' and then click 'OK' on the browser confirmation popup.

Actual Result: The system accepts the invalid email format and submits the form successfully.
Expected Result: The system should validate the email format completely and display an error message if the domain suffix is missing.

6. Test Summary

| Total Test Cases | Passed | Failed | Bugs Found |
| :--- | :--- | :--- | :--- |
| 11 (TC_011 - TC_021) | 10 | 2 | 2|

Execution Date: April 19, 2026
Conclusion: The main functionality (Registration, Cart, Search, Categories) is working correctly. However, the Contact Us form lacks proper email validation, which needs to be fixed.
---
BUG_002: Negative Product Quantity Leads to Negative Total Price
Severity: Critical 🚨
Priority: Highest

Description: The shopping cart allows entering a negative quantity for products, which results in a negative total order price. This could lead to massive financial losses and order logic bypass.

Steps to Reproduce:
1. Navigate to any product detail page.
2. In the 'Quantity' input field, enter a negative number (e.g., `-5`).
3. Click 'Add to cart'.
4. Click 'View Cart' in the popup.

Actual Result: Product is added with quantity -5, and the total price becomes negative (e.g., Rs. -5000).
Expected Result: System should prevent adding products with quantity less than 1. An error message should appear.

Attachment:
[View Bug Screenshot](./image_5.png) 
*(Note: Ensure you uploaded the screenshot to your repository with the same name)*
