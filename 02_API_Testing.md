# API Testing

## Introduction

After selecting JSONPlaceholder as the target API, I used Postman to send requests to several public endpoints. The purpose of this phase was to observe how the API handled requests, review the returned data, inspect the response headers, and collect evidence for the security assessment.

---

## Tested Endpoints

The following endpoints were tested during this assessment:

| HTTP Method | Endpoint | Status |
|-------------|----------|--------|
| GET | /users | 200 OK |
| GET | /posts | 200 OK |
| GET | /comments | 200 OK |
| GET | /todos | 200 OK |

All requests returned successful responses with a **200 OK** status code.

---

## API Responses

### GET /users

The `/users` endpoint returned a JSON response containing sample user information, including names, email addresses, phone numbers, company information, and addresses.

**Response**

<img width="957" height="500" alt="Users Response" src="https://github.com/user-attachments/assets/86f3f033-8865-49c0-939f-dc50ecb3d634" />

**Response Headers**

<img width="638" height="237" alt="Users Headers" src="https://github.com/user-attachments/assets/609329b5-2262-451c-8f2f-59bd96c8f8e7" />

---

### GET /posts

The `/posts` endpoint returned a collection of sample blog posts in JSON format. Each post contained a user ID, post ID, title, and body.

**Response**

<img width="959" height="468" alt="Posts Response" src="https://github.com/user-attachments/assets/0d044230-d771-40c2-ad3b-6162c159b0da" />

**Response Headers**

<img width="635" height="236" alt="Posts Headers" src="https://github.com/user-attachments/assets/03c1bd2b-a6ed-4829-83e4-7f747f9d483e" />

---

### GET /comments

The `/comments` endpoint returned a list of sample comments, including the commenter's name, email address, and message.

**Response**

<img width="959" height="470" alt="Comments Response" src="https://github.com/user-attachments/assets/ab6847d1-542f-4a33-9ce7-cb50662af8b7" />

**Response Headers**

<img width="641" height="309" alt="Comments Headers" src="https://github.com/user-attachments/assets/18202a4f-cd78-4faf-ba61-65c2a144d0bb" />

---

### GET /todos

The `/todos` endpoint returned a list of sample tasks with user IDs, task descriptions, and completion status.

**Response**

<img width="959" height="470" alt="Todos Response" src="https://github.com/user-attachments/assets/b9f39d15-86ad-4026-95a3-d0268004b27b" />

**Response Headers**

<img width="636" height="292" alt="Todos Headers" src="https://github.com/user-attachments/assets/455b2839-a1ac-489a-8695-dcefdeec1ed2" />

---

## Observations

During testing, I observed the following:

- All tested endpoints were publicly accessible.
- Every request returned a **200 OK** status code.
- The API returned responses in JSON format.
- The API used HTTPS for secure communication.
- Response headers included information such as `Content-Type`, `Content-Length`, `Cache-Control`, and `Content-Encoding`.
- No authentication was required to access the tested endpoints.

---

## Conclusion

The API testing phase confirmed that the selected endpoints were functioning correctly and provided the information required for the security assessment. The observations gathered during testing will be used in the next phase to evaluate authentication, authorization, data exposure, and other potential API security risks.
