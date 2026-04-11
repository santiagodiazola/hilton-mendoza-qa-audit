# 🏨 Hilton Honors - End-to-End Web Audit

## Project Goal
To validate the "Golden Path" of the Hilton Honors user journey, focusing on Account Security, Internationalization (i18n), and Search Engine Resilience.

---

## 📋 Executive Summary
This project represents a full-stack Quality Assurance audit of the Hilton Mendoza digital booking funnel. The objective was to identify technical regressions, validate backend data integrity via API interception, and evaluate the user experience through a psychological and heuristic lens.

---

📊 Audit Execution Metrics

---

## 🛠️ Technical Approach
* **Bug Tracking & Management:** [Trello Project Board](https://trello.com/b/OpY0J1nf/qa-portfolio-bug-tracking)
* **API Testing:** Postman (RESTful GET/POST Validation)
* **Black-Box Testing:** Manual validation of the E2E booking flow.
* **DevTools Auditing:** Used the Chrome Network Tab to analyze XHR/Fetch requests and response headers.
* **Boundary Value Analysis (BVA):** Applied to guest occupancy and date selection calendars.
* **Design Audit:** Heuristic Evaluation (Nielsen’s 10 Usability Principles)
* **Session Security:** Verified cache invalidation and POST-logout state to prevent PII leaks.

---

## 🔍 Key Areas of Testing

### 1. Functional & Logic Testing
* **Boundary Value Analysis (BVA):** Validated date-picker logic to prevent invalid reservation ranges (e.g., past dates or checkout before check-in).
* **Empty State Handling:** Verified "Fail Gracefully" behavior by testing null search results (e.g., "Mars") to ensure proper user feedback instead of system crashes.

### 2. Technical & API Validation
* **Traffic Interception:** Used Chrome DevTools (Network Tab) to identify the `GET /autocomplete` endpoint used for dynamic destination suggestions.
* **Endpoint Analysis:** Validated that the query parameter `input=Mendoz` successfully triggers a `200 OK` response, confirming high-speed data retrieval from the Unbxd search provider.
* **Console Audit:** Identified and documented a critical JavaScript `ReferenceError` (`ttd_dom_ready`) affecting the initialization of page scripts and tracking pixels.

### 3. Psychology-Driven UX Audit
* **Cognitive Load:** Evaluated the visibility and hierarchy of the primary "Find Hotels" Call-to-Action (CTA) across mobile and desktop viewports.
* **Recognition vs. Recall:** Applied psychological principles to analyze search parameter persistence, ensuring users aren't forced to memorize dates and guest counts during the room selection phase.

---

## 🧪 Key Test Scenarios
TC-REG-02: UTF-8 Support in Name Fields (Failed - Bug logged).
TC-AUTH-01: Session Termination & Cache Invalidation (Passed - Security verified).
TC-SRCH-04: Inventory Synchronization (Observation - UX discrepancy).
TC-BOOK-01: Data Persistence during Checkout (Passed).

## 🔴 High-Priority Finding: BUG-001
Vulnerability: UTF-8 Character Encoding Failure during Registration.
The Issue: The system fails to process accented characters (e.g., "í", "ñ"), which are standard in Spanish and European locales.
Technical Analysis: Network Tab (XHR) logs indicate a client-side interceptor error preventing the payload from reaching the server.
Business Risk: High. This is a total blocker for user acquisition in Latin American and European markets.

---

## 📊 Final Quality Status
| Category | Status | Notes |
| :--- | :--- | :--- |
| **Functional** | PASS ✅ | Core booking logic is robust. |
| **API/Backend** | PASS ✅ | Suggestion API is secure and responsive. |
| **Technical Errors** | FAIL ❌ | 1 Critical JS Bug identified in Console. |
| **UX/UI** | IMPROVED ⚠️ | Recommended 2 enhancements for reduced cognitive load. |

---

🚀 How to Review this Audit
View the Test Suite: Check the documentation/ folder for the full Master Test Plan.
Analyze Evidence: Browse the evidence/ folder for annotated screenshots of the UTF-8 registration failure.
Read the Executive Summary: For a high-level overview of release readiness.

---


🚦 Release Recommendation
Search & Booking: PROCEED with minor UX calendar adjustments.
Global Registration: HALT. The registration module requires a fix for UTF-8 encoding to support international growth.

---

## 🔗 Project Resources
* **[Interactive Trello Board](https://trello.com/b/OpY0J1nf/qa-portfolio-bug-tracking)**
* **[Professional Portfolio Website](YOUR_LINK_HERE)**

---
*Created by Santiago Diaz Ola - QA Analyst*
