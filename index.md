# CreatorFuel Documentation
![Next.js](https://img.shields.io/badge/Next.js-FullStack-black)
![MongoDB](https://img.shields.io/badge/Database-MongoDB-green)
![Razorpay](https://img.shields.io/badge/Payments-Razorpay-blue)
![NextAuth](https://img.shields.io/badge/Auth-NextAuth-purple)
![SaaS](https://img.shields.io/badge/App-SaaS-orange)

Full Stack SaaS Tipping Platform built with Next.js, MongoDB, Razorpay and NextAuth.

---

## Project Links

- 🌐 Live App → [Open CreatorFuel](https://creator-fuel-six.vercel.app/)  
- 💻 Source Code → [GitHub Repository](https://github.com/imjoe77/Creator-Fuel)  
- 📄 Documentation → [Docs Repository](https://github.com/imjoe77/creatorfuel-docs)  
---

## Introduction
CreatorFuel is a full-stack SaaS (Software as a Service) web application that allows creators to receive tips and payments directly from their supporters.

The platform works as a fundraiser / tipping service where creators can create their profile, configure payment settings, and receive payments from fans without any platform charges.

CreatorFuel follows a multi-user SaaS model where each creator can sign up, manage their dashboard, configure Razorpay keys, and use the platform to receive payments securely.

This project was built using Next.js, MongoDB, Razorpay API, Tailwind CSS, and NextAuth.

---

## Problem Statement
Many small creators do not have an easy way to accept payments without building their own payment system.

Existing platforms often charge fees or require complex setup.

CreatorFuel solves this by providing a simple SaaS platform where creators can sign up, configure their payment details, and receive tips directly from fans without hidden charges from the platform.

---

## Application Type

• SaaS (Software as a Service) platform  
• Multi-user system where each creator has their own profile  
• Each creator can configure their own Razorpay payment keys  
• Payments are verified securely per creator  
• Dashboard allows creators to manage profile and stats  
• Public pages allow fans to send tips  

---

## Tech Stack

Framework:
- Next.js (Frontend + Backend API Routes)

Frontend styling:
- Tailwind CSS

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

## Components

### Navbar component
Three separate navbar components are used across the project to show versatile functionality.
One navbar shows default navigation,
one is dedicated for creator pages with search bar,
and another is reused across dashboard and other pages.

### Footer component
Same footer component used across the entire website.
GitHub button redirects to source code repository.

### PaymentPage component

Accepts parameters:
username, payments, profilePic, bannerPic, stats

Functions:

• useEffect  
Shows toast after successful payment and redirects back to creator page

• handleChange  
Handles form input values

• isDisabled  
Checks if form inputs are valid

• pay function  
Main payment logic

- Checks session login
- Validates inputs
- Shows loading toast
- Calls backend initiate()
- Receives Razorpay order
- Opens Razorpay popup
- Prefills user data
- Uses callback URL for verification
- Handles errors

• Top payments logic  
Shows latest 5 payments from database

---

### SearchBar component

• Client-side search using Next.js  
• useState for query and results  
• Calls searchUsers() action  
• Uses map() to display results  
• Link used for navigation  
• useRef used for blur handling  
• Dropdown closes safely  
• Shows fallback message  

---

### SessionWrapper component

Wrapper component used to provide authentication session across the entire application using NextAuth.

---

## Core Features

### Useractions

1. updateProfile  
Updates profile using session email  
Prevents duplicate values  
Maintains data integrity  

2. initiate  
Creates Razorpay order  
Stores payment in DB  
Uses creator key  

3. fetchPayments  
Fetches successful payments  
Sorts latest first  
Limits results  

4. fetchUserStats  
Counts total payments  
Counts total amount  

5. searchUsers  
Regex search  
Case insensitive  
Limit results  
Return plain objects  

6. fetchUser  
Gets logged in user  
Removes secret key  
Sanitizes object  

---

## API Endpoints

### auth
NextAuth login  
Google & GitHub  
Creates user  
Adds username to session  

### razorpay
Called after payment  
Gets FormData  
Finds order  
Gets creator key  
Verifies signature  
Updates DB  
Redirects user  

### user/me
Protected API  
Gets session  
Finds user  
Hides secret  
Returns safe data  

---

## Routes

/[username] → Creator page  
/dashboard → Dashboard  
/about → About  
/creators → Creators list  
/api → API routes  
/models → DB models  
/default → Layout route  

Each route has page.js and layout.js  
Some routes added for structure completeness

---

## Database Connection

Uses Mongoose  
Reads env URI  
Uses global cache  
Prevents multiple connections  
Used in API and actions

---

## Authentication

Login  
Register  
Session handling  

---

## Creator Dashboard

Profile edit  
Payment keys  
Stats  
Supporters list  

---

## Payment Integration

Creator sets keys  
Order created  
Payment verified  
DB updated  
Redirect success  

---

## Flow

Creator signs up  
Sets payment keys  
Gets public page  

User visits page  
Sends tip  
Razorpay popup  
Callback API  
Verify signature  
Update DB  
Redirect success

Platform works as SaaS  
Multiple creators  
Separate keys  
Secure verification

---

## Challenges

Razorpay live keys  
Session issues  
Mongo connection  
Deployment bugs  

---

## What I learned

Full stack flow  
NextAuth  
MongoDB  
Razorpay  
Next.js API  
Production debugging  

---

## Future Improvements

Better UI  
More payment gateways  
Admin panel  
Analytics  
Notifications  

---

## Author

Nathaniel Bandi  
BCA Student  
Aspiring Backend / Cloud Engineer  
Interested in Full Stack, Backend Systems, Cloud
