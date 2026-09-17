# 🏨 Hilton Honors - Exploratory QA & Functional Audit

## 📈 Executive Overview
A structured, self-directed quality assurance audit evaluating the user registration funnel, input sanitization, and internationalization (i18n) handling on the Hilton platform. 

This project was executed as a portfolio artifact to demonstrate professional test planning, execution, and defect reporting standards.

---

## 📊 Scope & Methodology
- **Focus Areas:** User registration flow, UTF-8 multi-byte character handling, and form validation using Boundary Value Analysis (BVA).
- **Techniques:** Exploratory testing, negative scenario validation, and network layer inspection via browser dev tools.
- **Artifacts Managed:** Test Plan, Traceability Matrix (11 test cases), Defect Log, and structured evidence screenshots (managed via TestRail and Trello workflows).

---

## 🎯 Key Finding: UTF-8 Character Handling Defect (BUG-001)

During multi-byte character validation testing (using names containing accented characters common in Spanish and European locales), a registration-blocking functional defect was isolated.

* **Summary:** The registration form fails to process or serialize special characters correctly, resulting in an unhandled response error during account creation.
* **Impact:** Blocks account creation for users with standard internationalized characters in their names.
* **Evidence:** Local browser inspection and network payload tracking confirm form-submission rejection.

![Bug Evidence](https://github.com/santiagodiazola/hilton-mendoza-qa-audit/blob/main/evidence/Evidence%20BUG-001.png)
*Console evidence showing a JavaScript execution failure in the registration module when processing non-standard UTF-8 characters (e.g., "í").*

---

## 🛠️ Tools & Ecosystem
* **Test Management:** TestRail, Trello. [Interactive Trello Board](https://trello.com/b/OpY0J1nf/qa-portfolio-bug-tracking)
* **Techniques:** Risk-Based Testing (RBT), Boundary Value Analysis, Negative Testing
* **Inspection:** Chrome DevTools (Network & Console inspection)

---

## 🚀 How to Review this Audit
1.  **[Test Plan](https://github.com/santiagodiazola/hilton-mendoza-qa-audit/blob/main/documentation/test-plan/Hilton_Test_Plan_v1.pdf):** View the full TP-001 strategy and methodology.
2.  **[Evidence Vault](https://github.com/santiagodiazola/hilton-mendoza-qa-audit/tree/main/evidence):** Annotated screenshots of bugs and successful validation states.
3.  **[Defect Log](https://github.com/santiagodiazola/hilton-mendoza-qa-audit/blob/main/documentation/bug-report/BUG-001%20Registration%20Failure.pdf):** Detailed technical breakdown of BUG-001.
4.  **[Quality Summary Report](https://github.com/santiagodiazola/hilton-mendoza-qa-audit/blob/main/documentation/TestRail/Hilton_Honors_QA_Audit_Summary_Report_Santiago_Diaz.pdf):** An executive TestRail export summarizing coverage across 11+ test cases and module-specific pass rates.

