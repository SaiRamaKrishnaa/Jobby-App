# Jobby App

Jobby App is a job search application that allows users to search and apply for jobs. The app is built using React and is designed to showcase my ability to create a complete web application, including user authentication, fetching and displaying data from APIs, and handling different states such as loading, success, and failure.

## Table of Contents

- [Jobby App](#jobby-app)
  - [Table of Contents](#table-of-contents)
  - [Features](#features)
  - [Design](#design)
    - [Login Route](#login-route)
    - [Home Route](#home-route)
    - [Jobs Route](#jobs-route)
    - [Job Item Details Route](#job-item-details-route)
    - [Not Found Route](#not-found-route)
  - [Installation](#installation)
  - [API Requests & Responses](#api-requests--responses)
    - [Login API](#login-api)
    - [Profile API](#profile-api)
    - [Jobs API](#jobs-api)
    - [Job Details API](#job-details-api)


## Features

- **Login Route**: Allows users to log in using their credentials.
- **Home Route**: Displays a welcome page with a button to find jobs.
- **Jobs Route**: Displays a list of available jobs with filtering options.
- **Job Item Details Route**: Displays detailed information about a specific job.
- **Not Found Route**: Handles unknown routes by displaying a "Not Found" page.

## Design

### Login Route

- [Login (Small and Extra Small)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-login-sm-outputs.png)
- [Login (Medium, Large, and Extra Large)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-login-lg-output.png)
- [Login Failure (Medium, Large, and Extra Large)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-login-failure-lg-output.png)

### Home Route

- [Home (Small and Extra Small)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-home-sm-output.png)
- [Home (Medium, Large, and Extra Large)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-home-lg-output.png)

### Jobs Route

- [Jobs (Small and Extra Small)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-jobs-sm-outputs.png)
- [Jobs Success (Medium, Large, and Extra Large)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-jobs-success-lg-output-v0.png)
- [No Jobs (Medium, Large, and Extra Large)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-no-jobs-lg-output-v0.png)
- [Profile Failure (Medium, Large, and Extra Large)](https://assets.ccbp.in/frontend/content/react-js/jooby-app-profile-failure-lg-output-v0.png)
- [Jobs Failure (Medium, Large, and Extra Large)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-jobs-failure-lg-output-v0.png)

### Job Item Details Route

- [Job Details Success (Small and Extra Small)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-job-details-success-sm-output-v0.png)
- [Job Details Failure (Small and Extra Small)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-job-details-failure-sm-output.png)
- [Job Details Success (Medium, Large, and Extra Large)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-job-details-success-lg-output-v0.png)
- [Job Details Failure (Medium, Large, and Extra Large)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-job-details-failure-lg-output.png)

### Not Found Route

- [Not Found (Small and Extra Small)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-not-found-sm-output-v0.png)
- [Not Found (Medium, Large, and Extra Large)](https://assets.ccbp.in/frontend/content/react-js/jobby-app-not-found-lg-output-v0.png)

## Installation

To set up the project locally, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/jobby-app.git
   ```
2. Navigate to the project directory:
   ```bash
   cd jobby-app
   ```
3. Install the dependencies:
   ```bash
   npm install
   ```
4. Start the application:
   ```bash
   npm start
   ```

## API Requests & Responses

### Login API

- **API**: `https://apis.ccbp.in/login`
- **Method**: `POST`
- **Request**:
  ```json
  {
    "username": "rahul",
    "password": "rahul@2021"
  }
  ```
- **Success Response**:
  ```json
  {
    "jwt_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6InJhaHVsIiwicm9sZSI6IlBSSU1FX1VTRVIiLCJpYXQiOjE2MTk2Mjg2MTN9.nZDlFsnSWArLKKeF0QbmdVfLgzUbx1BGJsqa2kc_21Y"
  }
  ```
- **Failure Response**:
  ```json
  {
    "status_code": 404,
    "error_msg": "Username is not found"
  }
  ```

### Profile API

- **API**: `https://apis.ccbp.in/profile`
- **Method**: `GET`
- **Response**:
  ```json
  {
    "profile_details": {
      "name": "Rahul Attuluri",
      "profile_image_url": "https://assets.ccbp.in/frontend/react-js/male-avatar-img.png",
      "short_bio": "Lead Software Developer and AI-ML expert"
    }
  }
  ```

### Jobs API

- **API**: `https://apis.ccbp.in/jobs`
- **Method**: `GET`
- **Example**: `https://apis.ccbp.in/jobs?employment_type=FULLTIME,PARTTIME&minimum_package=1000000&search=`
- **Response**:
  ```json
  {
    "jobs": [
      {
        "company_logo_url": "https://assets.ccbp.in/frontend/react-js/jobby-app/facebook-img.png",
        "employment_type": "Full Time",
        "id": "d6019453-f864-4a2f-8230-6a9642a59466",
        "job_description": "We’re in search of a Back-End Software Engineer that specializes in server-side components. In this role, you’ll primarily work in NodeJs, SQL Lite, Python, AWS and GO and will bring a depth of knowledge on basic algorithms and data structures. As a Back-End Engineer, you might be architecting new features for our customers.",
        "location": "Bangalore",
        "package_per_annum": "21 LPA",
        "rating": 4,
        "title": "Backend Engineer"
      }
      ...
    ],
    "total": 25
  }
  ```

### Job Details API

- **API**: `https://apis.ccbp.in/jobs/:id`
- **Method**: `GET`
- **Example**: `https://apis.ccbp.in/jobs/bb95e51b-b1b2-4d97-bee4-1d5ec2b96751`
- **Response**:
  ```json
  {
    "job_details": {
      "company_logo_url": "https://assets.ccbp.in/frontend/react-js/jobby-app/netflix-img.png",
      "employment_type": "Full Time",
      "job_description": "We’re looking for a Front-End Engineer to join our dynamic team. You’ll be working primarily with React.js, CSS, and HTML. We value a solid understanding of UI/UX principles and a passion for creating beautiful, responsive designs.",
      "location": "Hyderabad",
      "package_per_annum": "18 LPA",
      "rating": 4.5,
      "title": "Frontend Engineer"
    },
    "similar_jobs": [
      {
        "id": "similar-job-1",
        "title": "UI/UX Designer",
        "company_logo_url": "https://assets.ccbp.in/frontend/react-js/jobby-app/google-img.png",
        "location": "Pune",
        "rating": 4.2,
        "employment_type": "Part Time"
      },
      ...
    ]
  }
  ```

