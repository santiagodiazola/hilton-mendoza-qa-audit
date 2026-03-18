# 🏨 QA Audit: Hilton Mendoza Booking Engine

## 📋 Executive Summary
This project represents a full-stack Quality Assurance audit of the Hilton Mendoza digital booking funnel. The goal was to identify technical regressions, validate data integrity via API testing, and evaluate the user experience through a psychological lens.

---

## 🛠️ Technical Stack
* **Bug Tracking:** [Trello Board](https://trello.com/b/OpY0J1nf/qa-portfolio-bug-tracking)
* **API Testing:** Postman (RESTful GET/POST Validation)
* **Diagnostics:** Chrome DevTools (Console, Network, Elements)
* **Design Audit:** Heuristic Evaluation (Nielsen’s Principles)

---

## 🔍 Key Areas of Testing

### 1. Functional & Logic Testing
* **Boundary Value Analysis:** Validated date-picker logic to prevent invalid reservation ranges.
* **Empty State Handling:** Verified system "Fail Gracefully" behavior during null search results.

### 2. Technical & API Validation
* **API Integrity:** Used Postman to verify `200 OK` status codes and JSON schema accuracy for content delivery.
* **Console Audit:** Identified a critical `ReferenceError` (`ttd_dom_ready`) affecting script execution.

### 3. Psychology-Driven UX Audit
* **Cognitive Load:** Evaluated the booking CTA visibility on mobile viewports.
* **Recognition vs. Recall:** Analyzed search parameter persistence to reduce user mental effort.

---

## 📊 Final Status
| Category | Status |
| :--- | :--- |
| **Functional** | PASS ✅ |
| **API/Backend** | PASS ✅ |
| **Technical Errors** | FAIL ❌ (1 Critical JS Bug) |
| **UX/UI** | IMPROVEMENTS SUGGESTED ⚠️ |

---

## 🔗 Project Links
* **[Interactive Bug Tracking Board (Trello)](https://trello.com/b/OpY0J1nf/qa-portfolio-bug-tracking)**
* **[Portfolio Website](YOUR_WEBSITE_LINK_HERE)**
