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
