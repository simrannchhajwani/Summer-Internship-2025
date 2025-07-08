# NutriCare - A Hospital Nutrition Tracking System  

The Hospital Nutrition Tracking System is a comprehensive full-stack web application designed to streamline the nutritional care process within a clinical setting. It provides a centralized, role-based platform for patients, doctors, and administrators to collaboratively manage dietary intake, monitor key health metrics, and facilitate personalized nutritional guidance.

This system was developed to address the real-world challenge of manual and fragmented diet tracking in healthcare. By leveraging modern web technologies, it aims to improve patient engagement, provide clinicians with actionable data, and enhance the overall efficiency of diet-based treatment plans.

---

## Table of Contents

- [Core Features](#core-features)
- [Live Demo](#live-demo)
- [Screenshots](#screenshots)
- [Technical Architecture](#technical-architecture)
- [Getting Started](#getting-started)
- [Folder Structure](#folder-structure)
- [Environment Configuration](#environment-configuration)
- [Future Enhancements](#future-enhancements)
- [Author](#author)
- [License](#license)

---

## Core Features

The application's functionality is securely segregated based on user roles to ensure data privacy and operational integrity.

### For the Patient
- **Secure Onboarding:** A seamless registration and login process secured with JSON Web Tokens.
- **Health Profile Management:** The ability to create and update a detailed personal health profile, including biometrics (height, weight), age, and relevant health conditions.
- **Intuitive Meal Logging:** A simple interface to log daily meals, integrated with a comprehensive Indian food database to provide nutritional information (calories, protein, carbs, fat) automatically.
- **Health Metric Insights:** An auto-calculating Body Mass Index (BMI) tool that provides immediate feedback based on profile data.
- **Personalized Feedback:** A dedicated section to view personalized notes and recommendations from their assigned doctor or dietician.
- **Appointment Scheduling:** Functionality to request, view, and manage follow-up appointments.

### For the Doctor / Dietician
- **Patient Roster Management:** A dashboard to view all assigned patients and quickly access their profiles.
- **In-Depth Patient Analysis:** Access to complete patient meal logs, nutritional data summaries, and BMI history to identify trends and assess progress.
- **Personalized Diet Plans:** Tools to create and send customized diet recommendations and feedback directly to the patient.
- **Appointment Coordination:** The ability to schedule and confirm follow-up appointments in response to patient requests.

### For the Administrator
- **Credential Verification:** A secure portal to review and approve new registrations for doctors and dieticians, ensuring only qualified professionals gain access.
- **User Account Oversight:** Full control over managing user accounts across all roles, including activation, deactivation, and role assignment.
- **System Integrity:** The capability to manage and update the core Indian food database to maintain accuracy and relevance.

---

## Live Demo

- **Frontend Application (Vercel):** `[Your Deployed Frontend URL Here]`
- **Backend API (Render):** `[Your Deployed Backend URL Here]`

---

## Screenshots

*coming soon*

**Example:**
`![Patient Dashboard](assets/patient-dashboard.png)`
`![Doctor's View of Patient Logs](assets/doctor-view.png)`
`![Meal Logging Interface](assets/meal-logger.png)`

---

## Technical Architecture

This project is built on the MERN stack, chosen for its robustness, scalability, and rich ecosystem.

- **Frontend:**
  - **React.js (v18):** A declarative library for building dynamic and responsive user interfaces.
  - **React Router:** For client-side routing and navigation between pages and protected views.
  - **Material UI v5:** – Component library for sleek, responsive, accessible UI.
  - **Axios:** A promise-based HTTP client for making reliable requests to the backend API.
  - **React Context API:** For efficient global state management, particularly for user authentication status.

- **Backend:**
  - **Node.js & Express.js:** A non-blocking runtime and web framework for building a fast, scalable, and secure RESTful API.
  - **MongoDB with Mongoose:** A NoSQL database and Object Data Modeling (ODM) library, providing flexibility for storing complex health data.
  - **JSON Web Tokens (JWT):** For implementing stateless, secure authentication and authorization for all user roles.
  - **Bcrypt.js:** For industry-standard hashing and salting of user passwords before database storage.
  - **CORS:** Middleware configured to ensure secure communication between the frontend and backend domains.

---

## Getting Started

To run this project locally, please follow the steps below.

### Prerequisites
- Node.js (v16 or later)
- npm (or yarn)
- Git
- A MongoDB Atlas account or a local MongoDB instance.

### Installation & Setup

1.  **Clone the Repository**
    ```bash
    git clone https://github.com/your-username/health-nutrition-system.git
    cd health-nutrition-system
    ```

2.  **Configure the Backend**
    ```bash
    cd backend
    npm install
    
    # Create the environment file from the example template
    cp ../.env.example .env 
    
    # Update the .env file with your credentials (see Environment Configuration)
    
    # Start the development server
    npm run dev 
    ```
    The backend API will now be running on `http://localhost:5000`.

3.  **Configure the Frontend**
    ```bash
    cd ../frontend
    npm install
    
    # The frontend is configured to connect to the backend URL automatically.
    
    # Start the development server
    npm run dev
    ```
    The React application will now be available at `http://localhost:5173`.

---

## Folder Structure

The project maintains a clean, separated monorepo structure for scalability and maintainability.

```
/health-nutrition-system
├── backend/
│   ├── controllers/    # Request handling logic
│   ├── models/         # Mongoose database schemas
│   ├── routes/         # API endpoint definitions
│   ├── middleware/     # Custom middleware (e.g., auth)
│   ├── config/         # Database connection config
│   └── server.js       # Main backend entry point
├── frontend/
│   ├── src/
│   │   ├── components/ # Reusable React components
│   │   ├── pages/      # Page-level components
│   │   ├── context/    # Global state management
│   │   ├── services/   # API request handlers (axios)
│   │   ├── App.jsx     # Main application component with routing
│   │   └── index.js    # Frontend entry point
├── assets/             # For project screenshots
├── .env.example        # Environment variable template
└── README.md
```

---

## Environment Configuration

The backend requires the following environment variables, which should be placed in a `.env` file within the `/backend` directory.

```ini
# MongoDB Atlas connection string
MONGO_URI=mongodb+srv://<user>:<password>@<cluster-url>/<database-name>

# Secret key for signing JSON Web Tokens
JWT_SECRET=a_very_strong_and_long_secret_key_for_production

# The URL of the deployed frontend application (for CORS)
FRONTEND_URL=http://localhost:5173
```
For production, `FRONTEND_URL` should be updated to the Vercel/Netlify URL.

---

## Future Enhancements

This project has a solid foundation that can be extended with several high-impact features:

- **Advanced Data Visualization:** Integrating libraries like Chart.js or D3.js to create graphs for tracking weight, BMI, and macronutrient trends over time.
- **Real-Time Notifications:** Implementing WebSockets to provide instant alerts for new doctor feedback or appointment confirmations.
- **Automated Reporting:** A feature to generate and download PDF summaries of nutritional intake and health progress for a given period.
- **Third-Party Integrations:** Connecting with health-tracking APIs like Google Fit or Apple HealthKit to automatically sync activity and biometric data.

---

## Author

- **Simran Chhajwani** - https://www.linkedin.com/in/simranchhajwani/ - https://github.com/simrannchhajwani

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
