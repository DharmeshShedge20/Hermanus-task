# Hermanus-task

Project Overview
This is the backend for the online prescription platform, built using Spring Boot and MongoDB. The application facilitates consultations between doctors and patients. It allows patients to fill out a consultation form, view doctor profiles, and manage their personal information. Doctors can sign up, sign in, and update their profile.

Technologies Used
Java 17
Spring Boot
MongoDB
Spring Data MongoDB
Lombok


Features
Doctor Registration: Doctors can sign up and sign in using their email and phone number.
Patient Registration: Patients can sign up and sign in using their email or phone number.
Consultation Forms: Patients can submit consultation forms which store their medical history and current illness details.
Doctor Profile: Doctors can view their profile based on their name.

API Endpoints
1. Consultation Form Endpoints
POST /consultation
Create a new consultation form.
Request Body:

json
{
  "currentIllnessHistory": "string",
  "recentSurgery": "string",
  "surgeryTimeSpan": "string",
  "isDiabetic": true,
  "allergies": "string",
  "otherFamilyConditions": "string"
}
Response: 201 Created

GET /consultation/{id}
Get a consultation form by ID.
Response:

200 OK (ConsultationForm)
404 Not Found (if form does not exist)
GET /consultation
Get all consultation forms.
Response:

200 OK (List of ConsultationForms)
2. Doctor Endpoints
POST /api/doctor/signup
Register a new doctor.
Request Body:

json
{
  "profilePicture": "string",
  "name": "string",
  "specialty": "string",
  "email": "string",
  "phoneNumber": "string",
  "experience": 5
}
Response: 200 OK (Doctor)

POST /api/doctor/signin
Doctor sign in using email and phone number.
Request Body:

json
{
  "email": "string",
  "phoneNumber": "string"
}
Response: 200 OK (Doctor)

401 Unauthorized (if credentials are invalid)
GET /api/doctor/{name}/profile
Get doctor profile by name.

Response:
200 OK (Doctor Profile)
404 Not Found (if doctor not found)
3. Patient Endpoints
POST /api/patient/signup
Register a new patient.
Request Body:

json
{
  "profilePicture": "string",
  "name": "string",
  "age": 30,
  "email": "string",
  "phoneNumber": "string"
}
Response: 200 OK (Patient)

POST /api/patient/signin
Patient sign in using email or phone number.
Request Parameters:

email (optional)
phoneNumber (optional)
Response: 200 OK (Patient)
GET /api/patient/doctors
Get a list of doctor names.
Response:

200 OK (List of Doctor Names)
Project Setup
Requirements
Java 17
Spring Boot
MongoDB
Maven
