# 🏨 Hilton Honors - End-to-End Web Quality Audit

## 🎯 Project Mission
To execute a high-rigor functional and technical audit of the **Hilton Honors** user conversion funnel. This audit prioritizes **Internationalization (i18n)** resilience, **Session Integrity**, and **Search Engine UX**, ensuring the platform is ready for global market expansion.

---

## 📋 Executive Overview
This project represents a full-stack Quality Assurance audit of the Hilton digital booking engine. Beyond standard functional validation, this audit utilizes **API interception** to verify backend data integrity and a **Psychological/Heuristic lens** to evaluate user friction and cognitive load.

---

## 📊 Quality Metrics at a Glance

| Category | Metric | Status |
| :--- | :--- | :--- |
| **Total Test Cases** | 11 | 100% Executed |
| **Pass Rate** | 91% | Stable Core |
| **Critical Defects** | 1 | i18n Blocker (BUG-001) |
| **JS Console Errors** | 1 | ReferenceError identified |
| **Release Status** | **CONDITIONAL** | Halt for Spanish/EU locales |

---

## 🛠️ Technical Toolkit
* **Project Management:** [Interactive Trello Board](https://trello.com/b/OpY0J1nf/qa-portfolio-bug-tracking)
* **API Auditing:** Postman (RESTful Validation) & Chrome DevTools (XHR/Fetch Interception)
* **Testing Methodologies:** Black-Box, Boundary Value Analysis (BVA), Negative Testing
* **UX Framework:** Nielsen’s 10 Usability Heuristics & Cognitive Load Theory
* **Environment:** macOS Sonoma | Chrome v122 | Safari v17.2 (WebKit)

---

## 🔍 Key Audit Domains

### 1. Technical & API Integrity
* **Traffic Interception:** Monitored the `GET /autocomplete` endpoint via the Network Tab to validate dynamic destination mapping.
* **Endpoint Resilience:** Verified that query parameters (e.g., `input=Mendoz`) trigger efficient `200 OK` responses from the **Unbxd** search provider.
* **Console Stability:** Documented a critical `ReferenceError` (`ttd_dom_ready`) affecting tracking pixels and page initialization scripts.

### 2. Internationalization (i18n) & Logic
* **Encoding Audit:** Targeted testing of the registration module using **UTF-8 characters** (e.g., "Díaz Ola").
* **Boundary Analysis:** Validated the $T+0$ date-picker logic to prevent historical reservations and malformed search queries.

### 3. Psychology-Driven UX (Heuristic Audit)
* **Recognition vs. Recall:** Analyzed search parameter persistence to ensure the system retains user intent (dates/guests) throughout the funnel.
* **Friction Analysis:** Evaluated the Call-to-Action (CTA) hierarchy to minimize "Decision Paralysis" during the property selection phase.

---

## 🧪 Highlighted Test Scenarios

| ID | Scenario | Result | Key Finding |
| :--- | :--- | :--- | :--- |
| **TC-REG-02** | UTF-8 Character Support | ❌ **FAIL** | Registration blocks accented characters (Blocker). |
| **TC-AUTH-01** | Session Termination | ✅ **PASS** | Cache invalidated; no PII leaks post-logout. |
| **TC-SRCH-04** | Inventory Synchronization | ⚠️ **OBS** | UI allows 24-month selection; API capped at 12. |
| **TC-BOOK-01** | Data Persistence | ✅ **PASS** | Profile data successfully maps to checkout form. |

---

## 🔴 High-Priority Finding: BUG-001
**Vulnerability:** UTF-8 Character Encoding Failure during Registration.
* **The Issue:** The registration module fails to process accented characters common in Spanish and European locales.
* **Technical Analysis:** XHR logs indicate a client-side interceptor error preventing the payload from reaching the server.
* **Business Impact:** **Market Blocker.** This represents a total barrier to user acquisition in LATAM and EU markets.

---

## 🚀 How to Review this Audit
1.  **[Master Test Plan](https://github.com/YOUR_USERNAME/hilton-audit/tree/main/documentation):** View the full TP-001 strategy and methodology.
2.  **[Evidence Vault](https://github.com/YOUR_USERNAME/hilton-audit/tree/main/evidence):** Annotated screenshots of bugs and successful validation states.
3.  **[Defect Log](https://github.com/YOUR_USERNAME/hilton-audit/tree/main/defects):** Detailed technical breakdown of BUG-001.

---

## 🚦 Final Release Recommendation
* **Domestic (US/ASCII):** **PROCEED.** Core booking logic is highly stable.
* **Global (i18n/UTF-8):** **HALT.** Immediate remediation of the registration encoding gate is required for international expansion.

---
**Created by [Santiago Diaz Ola](https://github.com/YOUR_USERNAME) - QA Analyst & Clinical Psychologist**
