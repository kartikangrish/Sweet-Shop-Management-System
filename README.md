Sweet Shop Management System
This is a full-stack application built to fulfill the requirements of the TDD Kata: Sweet Shop Management System. It features a secure RESTful backend API built with Node.js, Express, and Prisma, and a modern, interactive single-page application frontend built with React and Tailwind CSS.

The project demonstrates a complete development lifecycle, including Test-Driven Development (TDD), clean coding practices, and thoughtful integration of AI as a development partner.

Public Repository Link: https://github.com/YOUR_USERNAME/sweet-shop-kata (Please replace with your actual repository link)

Application Screenshots
Here are the screenshots of the final application in action, showcasing the main user interfaces.

1. Login Page
The clean and simple entry point for all users.
![Login Page]<img width="1068" height="629" alt="Screenshot 2025-09-20 094021" src="https://github.com/user-attachments/assets/df3603bb-96cd-4cce-a5f9-0846d98e52ca" />


2. Standard User Dashboard
This is the view for a regular user. They can browse, search, and purchase sweets.
![Standard User Dashboard]<img width="1060" height="621" alt="Screenshot 2025-09-20 093952" src="https://github.com/user-attachments/assets/a203ff8f-a3d0-43b2-9b53-c963e4ac7446" />


3. Admin Dashboard
The enhanced view for an administrator, which includes additional controls to add, edit, and delete sweets from the inventory.
![Admin Dashboard]<img width="1071" height="650" alt="Screenshot 2025-09-20 093905" src="https://github.com/user-attachments/assets/3d2b98ff-29e2-4df6-ba95-5c1724da5856" />


Setup & Installation
Follow these instructions to set up and run the project locally.

Prerequisites
Node.js (v18+)

PostgreSQL

Git

A terminal or command prompt

Backend Setup
Clone the repository:

git clone [https://github.com/YOUR_USERNAME/sweet-shop-kata.git](https://github.com/YOUR_USERNAME/sweet-shop-kata.git)
cd sweet-shop-kata/backend

Install dependencies:

npm install

Set up environment variables:
Create a .env file in the backend directory and add the following, replacing the placeholder values with your PostgreSQL credentials:

DATABASE_URL="postgresql://USERNAME:PASSWORD@localhost:5432/sweetshop?schema=public"
JWT_SECRET="your_jwt_secret_key_here"

Run database migrations:
This command will set up the necessary tables in your database.

npx prisma migrate dev --name init

Run the backend server:

npm run dev

The backend API will be running on http://localhost:5001.

Frontend Setup
Simply open the frontend/index.html file in your web browser. There are no installation steps required as it uses CDN links for all libraries.

Running the Application & Testing
Creating Users
Create an Admin User (Required): You must create the first admin user directly via the API. Run the following cURL command in your terminal:

curl -X POST http://localhost:5001/api/auth/register \
-H "Content-Type: application/json" \
-d '{"email": "admin@shop.com", "password": "password123", "role": "ADMIN"}'

Create a Regular User: Open the application in your browser, click "Sign Up", and register a new user through the form.

Backend Test Report
To run the backend test suite, navigate to the backend directory and run:

npm test

You will see a report showing the results of the test suite.

Sample Test Output:

PASS  src/__tests__/auth.test.ts
 ✓ should register a new user successfully (125 ms)
 ✓ should not register a user with an existing email (53 ms)
 ✓ should log in a user with correct credentials (97 ms)
 ✓ should not log in a user with incorrect credentials (48 ms)

Test Suites: 1 passed, 1 total
Tests:       4 passed, 4 total
Snapshots:   0 total
Time:        2.815 s
Ran all test suites.

My AI Usage
In this project, I leveraged AI as a pair programmer and productivity tool to accelerate development while focusing on high-level logic and architecture.

AI Tools Used:

Gemini: For generating the initial project structure, writing boilerplate code, creating test cases, and debugging.

How I Used Them:

Project Scaffolding: I used Gemini to generate the initial full-stack project structure, including the Node.js/Express backend setup, the Prisma schema, and the single-file React frontend template. This saved significant time on initial configuration. Commit example: feat: Initialise full-stack project structure Co-authored-by: Gemini <AI@users.noreply.github.com>

TDD Implementation: I prompted Gemini to write the backend tests first for the authentication endpoints. Then, I asked it to write the corresponding controller logic to make the tests pass, following the Red-Green-Refactor pattern.

Frontend Component Generation: I described the required UI components (e.g., "a React component for a sweet card with props for name, price, and quantity") and had Gemini generate the JSX and Tailwind CSS code, which I then refined.

Debugging: I encountered a ReferenceError: jwt_decode is not defined in the frontend. I provided the error and the relevant code to Gemini, which correctly identified the issue and provided the fix to reference the function from the window object.

Reflection on AI's Impact:
Using AI dramatically increased the speed of development. It allowed me to offload repetitive and boilerplate tasks, freeing me up to focus on the core architectural decisions and ensuring all project requirements were met. It acted as an instant-feedback partner, helping to quickly resolve bugs and implement complex features like the role-based admin dashboard. It was crucial to review and understand all AI-generated code to ensure it was secure, efficient, and aligned with the project's goals.
