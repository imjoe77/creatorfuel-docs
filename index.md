# CreatorFuel – Full Documentation

## Introduction
CreatorFuel is a full stack web application built to allow creators to receive payments and manage their content.
It acts as a fund raiser website for the creators where their fans can directly tip to their favourite creators.

This project was built using Next.js,MongoDb, Razorpay API, HTML, CSS, Tailwind-css.

---

## Problem Statement
Many small creators do not have an easy way to accept payments.
CreatorFuel solves this by providing a simple platform where users receive tips from fans without any hidden charges from the platform.

---

## Tech Stack

Framework:
- Next.js (Frontend + Backend API Routes)

- Frontend framework (styling):
  Tailwind-css

Language:
- JavaScript 

Database:
- MongoDB

Authentication:
- NextAuth

Payments:
- Razorpay API

Deployment:
- Vercel


---

#Components
1. Navbar components:
Three separate navbar components are used accross the project to show versatile functionality where one shows the default features like navigations,one is dedicated for the creators page where it has a search bar using which the users can search for their favourite creators and the other navbar is reused across other components which is also for navigations and other functionality like login,signout,etc

2. Footer component:
Usual footer component, same fotter component used accross the website wherein the github option takes the users to the repository of the source code of the website.

3. PaymentPage component -
The function accepts parameters username, payments, profilePic, bannerPic, stats. The functions starts with -
* useeffect- Which runs a toast on successful payment and psuhes back to username page which avoids re-running of the toast while on payment success page.

* handleChange function - Is used to handle form inputs to correctly capture and display

* isDisabled - Check form inputs and allows button functionality

* pay - This is the main function which handles the payment,
 • It first check for session which verifies whether the user is logged in or not,throws a toast if not ad pushes to login page.
 • Inputs validations check for length,amount and specifies using toasts.Another toast
• Display loading notification while initiating payment
• Call backend function to create Razorpay order
• Receive keyId and orderId from server
• Configure Razorpay checkout options
• Open Razorpay payment popup
• Prefill user details in payment form
• Use callback URL for payment verification
• Handle errors if payment configuration fails

* Top Payments logic - in the payments collection we slice from index 0-5

  4. SearchBar component:
 • Implemented a client-side search bar using Next.js
• useState used for query, results, and dropdown state
• Calls backend action searchUsers() for filtering users
• Results displayed dynamically using map()
• Link component used for navigation to profile page
• Each search result is wrapped inside Next.js Link component
• Link automatically navigates to the given URL
• useRef used to handle blur and close dropdown safely
• Conditional rendering used for dropdown visibility
• Shows fallback message when no users found

5. SessionWrapper component -
Inbuilt library which provides session check to the whole website
   
## Features

### Useractions

1.updateProfile function -
* This function is used to handle changes and updates made by the user to his proifle in the dashboard page of the website.
* Uses a try-catch block where the try block starts with session check for login then we use the user's email as a unique constraint to fetch the user's information from the database and store inside currentUser variable.
* This compares current values with the one in the database before updating to maintain integrity and dupliacte values in crucial fields.Also checks if current name saved in database and updating name is unique this prevents from unneccessary database communication.

  2.initiate function -
  * This function handles the payment logic as to how the payment reaches the user,who sends it,etc.
  * Firsts connects to the database,then stores current creator's information in a variable creator so we can track who gets the money,if creators has not set up payment details error toast pops up.
  * Then we set up the razorpay api wherein we provide keyId and secret of the creator,parse amount from paise to ruppee and currency to INR
  * Create a variable x which holds the orders then create and save payment collection with details


### Authentication
- Login
- Register
- Session handling

### Creator Dashboard
- Profile
- Payment link
- Stats

### Payment Integration
- Razorpay keys
- Order creation
- Webhook handling

---

## How it works (Flow)

User → Creator page → Payment → Razorpay → Backend → Database

---

## Challenges I faced

- Razorpay live key issue
- Session handling
- Database connection errors
- Deployment problems

---

## What I learned

- Full stack workflow
- API integration
- Debugging backend
- Real world project structure

---

## Future Improvements

- Better UI
- More payment options
- Admin panel
- Analytics

---

## Author

Joel Bandi  
BCA Student  
Aspiring Backend / DevOps Engineer
