# Authentication and Authorization

## Introduction

In this phase, I reviewed how the JSONPlaceholder API handles authentication and authorization. The objective was to determine whether the API requires users to verify their identity before accessing resources and whether any access controls are enforced to restrict access to specific data.

---

## Authentication Assessment

During testing, I observed that the API does not require any form of authentication to access the public endpoints.

The tested endpoints were:

- GET /users
- GET /posts
- GET /comments
- GET /todos

Each request was completed successfully without requiring:

- Username and password
- API Key
- Bearer Token
- OAuth authentication

Every request returned a **200 OK** response, indicating that the resources are publicly accessible.

---

## Authorization Assessment

I also reviewed whether the API enforced authorization controls on the tested endpoints.

Based on the testing performed, all requested resources were accessible without any user-specific permissions or authorization checks.

Since JSONPlaceholder is a public demonstration API designed for learning and testing, this behavior is expected. However, in a real production environment, sensitive resources should only be accessible to authenticated and authorized users.

---

## Security Observation

The assessment identified the following observations:

- No authentication mechanism was required.
- No authorization checks were observed on the tested endpoints.
- Public data could be accessed without user verification.
- The API is intentionally designed to provide open access for educational purposes.

Although this behavior is acceptable for a public testing API, the same implementation would present security risks if used in a production application containing sensitive information.

---

## Conclusion

The authentication and authorization review confirmed that the tested endpoints are publicly accessible without requiring user authentication or access permissions. While this is appropriate for a demonstration API, production APIs should implement strong authentication and authorization mechanisms to protect sensitive resources from unauthorized access.
