# 🏨 QA Audit: Hilton Mendoza Digital Booking Engine

## 📋 Executive Summary
This project represents a full-stack Quality Assurance audit of the Hilton Mendoza digital booking funnel. The objective was to identify technical regressions, validate backend data integrity via API interception, and evaluate the user experience through a psychological and heuristic lens.

---

## 🛠️ Technical Stack
* **Bug Tracking & Management:** [Trello Project Board](https://trello.com/b/OpY0J1nf/qa-portfolio-bug-tracking)
* **API Testing:** Postman (RESTful GET/POST Validation)
* **Diagnostics:** Chrome DevTools (Network Interception, Console, Elements)
* **Design Audit:** Heuristic Evaluation (Nielsen’s 10 Usability Principles)

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

## 📊 Final Quality Status
| Category | Status | Notes |
| :--- | :--- | :--- |
| **Functional** | PASS ✅ | Core booking logic is robust. |
| **API/Backend** | PASS ✅ | Suggestion API is secure and responsive. |
| **Technical Errors** | FAIL ❌ | 1 Critical JS Bug identified in Console. |
| **UX/UI** | IMPROVED ⚠️ | Recommended 2 enhancements for reduced cognitive load. |

---

## 🔗 Project Resources
* **[Interactive Trello Board](https://trello.com/b/OpY0J1nf/qa-portfolio-bug-tracking)**
* **[Professional Portfolio Website](YOUR_LINK_HERE)**

---
*Created by Santiago Diaz Ola - QA Analyst*
