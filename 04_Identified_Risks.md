# Identified Risks

## Introduction

Based on the API testing and authentication review, I identified several security observations that could present risks if implemented in a production environment. Although JSONPlaceholder is intentionally designed as a public testing API, the following findings demonstrate common API security issues that organizations should address when developing real-world applications.

---

## Risk 1: No Authentication Required

**Severity:** Medium

### Observation

All tested endpoints were accessible without requiring any authentication. No API key, Bearer token, OAuth, or user login was required to retrieve data.

### Potential Impact

If a production API exposed sensitive information without authentication, unauthorized users could access confidential business or customer data.

### Recommendation

Implement strong authentication mechanisms such as API keys, OAuth 2.0, or JWT Bearer tokens to ensure that only authorized users can access protected resources.

---

## Risk 2: Publicly Accessible Endpoints

**Severity:** Medium

### Observation

The `/users`, `/posts`, `/comments`, and `/todos` endpoints were publicly accessible and returned data successfully with a **200 OK** response.

### Potential Impact

Publicly accessible endpoints increase the likelihood of automated data collection, API scraping, and unauthorized information gathering.

### Recommendation

Limit public access to only the endpoints that must be publicly available and require authentication for resources containing sensitive information.

---

## Risk 3: Excessive Data Exposure

**Severity:** Medium

### Observation

The `/users` endpoint returned multiple pieces of information, including:

- Name
- Username
- Email address
- Phone number
- Website
- Company details
- Address

### Potential Impact

Returning more information than necessary increases the amount of data exposed if the API is accessed by unauthorized users. This can also increase privacy and security risks.

### Recommendation

Return only the data required for each request and avoid exposing unnecessary fields in API responses.

---

## Risk 4: No Visible Authorization Controls

**Severity:** High

### Observation

During testing, all requested resources could be accessed without any visible authorization checks or user-specific access restrictions.

### Potential Impact

If this behavior existed in a production API, users could potentially access resources that should only be available to other authenticated users, resulting in unauthorized data exposure.

### Recommendation

Implement proper authorization controls to ensure users can only access resources they are permitted to view or modify.

---

## Risk 5: No Visible Rate Limiting

**Severity:** Medium

### Observation

During testing, there was no visible indication that rate limiting was being enforced on the tested endpoints.

### Potential Impact

Without rate limiting, attackers could send a large number of requests to scrape data or overload API resources.

### Recommendation

Implement rate limiting to restrict excessive requests from the same client and reduce the risk of abuse.

---

## Summary

| Risk | Severity |
|------|----------|
| No Authentication Required | Medium |
| Publicly Accessible Endpoints | Medium |
| Excessive Data Exposure | Medium |
| No Visible Authorization Controls | High |
| No Visible Rate Limiting | Medium |

---

## Conclusion

The identified findings are based on observations made during API testing and are intended to demonstrate common API security risks. While these behaviors are acceptable for a public demonstration API such as JSONPlaceholder, similar configurations in a production environment could expose organizations to unauthorized access, excessive data exposure, and API abuse. Implementing appropriate authentication, authorization, and access control mechanisms would significantly improve the overall security posture of a production API.
