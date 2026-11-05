<div align="center">

# 🎓 EduSphere: University ERP System

**A Next-Generation, Multi-Tenant Educational ERP Built on ServiceNow**

[![ServiceNow Application](https://img.shields.io/badge/Platform-ServiceNow-293e40?style=for-the-badge&logo=servicenow&logoColor=white)](https://www.servicenow.com/)
[![Architecture](https://img.shields.io/badge/Architecture-Multi--Tenant-005571?style=for-the-badge)](https://github.com/)
[![Payments](https://img.shields.io/badge/Gateway-Razorpay-02042b?style=for-the-badge&logo=razorpay&logoColor=white)](https://razorpay.com/)
[![Security](https://img.shields.io/badge/Security-SSO%20%7C%20RBAC%20%7C%20MFA-10a37f?style=for-the-badge)](https://github.com/)
[![Delivery](https://img.shields.io/badge/Delivery-Agile%2FScrum-f06529?style=for-the-badge)](https://github.com/)

<p align="center">
  <em>Digitizing and automating major academic, administrative, financial, and operational processes for affiliated universities and their member colleges through a single integrated solution.</em>
</p>

</div>

---

## 📖 Overview

**EduSphere** is a centralized College ERP Management System designed to operate entirely on the ServiceNow platform. Built as a custom scoped application (`x_erp`), EduSphere transitions institutions away from fragmented spreadsheets, paper-based forms, emails, and standalone applications into a unified, real-time ecosystem.

---

## 🚧 The Challenge vs. 🚀 The Solution

| The Legacy Problem ❌ | The EduSphere Solution ✅ |
| :--- | :--- |
| **Data Silos:** Duplicate data entry across fragmented apps. | **Single Source of Truth:** One unified ServiceNow platform. |
| **Manual Bottlenecks:** Delays in multi-level approvals. | **Dynamic Routing:** Automated, hierarchy-driven workflows. |
| **Scalability Issues:** New colleges required new software. | **Tenant Isolation:** Add new colleges simply via configuration. |
| **Poor Visibility:** Blind spots across college departments. | **Real-Time Analytics:** Dashboards for Deans, HODs, and Admin. |

---

## 🏗️ Architectural Highlights

*   🏢 **Multi-College Tenancy:** The University acts as the top-level owner (defining programs, courses, and the academic calendar), while individual affiliated colleges act as tenants.
*   🔐 **Role-Based Access Control (RBAC):** Every transactional record utilizes a `College` key for tenant isolation. College-level roles only see their own data, while University-level roles (e.g., Head Dean) are granted cross-college visibility.
*   🔀 **Dynamic Approval Routing:** Approvals are not hard-coded; they resolve dynamically at runtime using institutional hierarchy data *(Head Dean ➔ Deans ➔ Directors/Principals ➔ HODs ➔ Faculty)*.
*   📱 **Mobile-First Integrations:** Supports a mobile app for event entry via QR code, faculty attendance check-ins, and student self-service.

---

## 🧩 Core Modules & Capabilities

<details>
<summary><b>🏫 Institutional & Academic Management</b></summary>
<br>

*   **University & Affiliation:** Manages member colleges, onboarding workflows, and yearly affiliation renewals.
*   **Academic Structure:** Centralized definition of academic years, programs (B.Tech, MBA, BCA, etc.), courses, semesters, sections, and elective quotas.
*   **Timetable Engine:** Conflict-checking timetable builder supporting dynamic lab/tutorial splits, integrated with event and exam schedules.

</details>

<details>
<summary><b>🎓 Student Lifecycle & Operations</b></summary>
<br>

*   **Admissions & Registrations:** Portal-based application process with automated document verification and merit-based seat allocation tracking 10th, 12th, and JEE scores.
*   **Points-Based Attendance:** Tracks faculty and student attendance. Uses a weighted points system (e.g., lectures = 1.0, labs = 1.1) to calculate exam eligibility, triggering automated warnings at 80% and 75%.
*   **Examinations:** Manages exam schedules, dynamic seating plans, hall ticket approvals (gated by attendance/fees), grading (60% internal / 40% external), backlogs, and re-evaluations.

</details>

<details>
<summary><b>👥 Faculty & Employee Management</b></summary>
<br>

*   **People & Hierarchy:** Manages employee profiles, department mapping, and dynamic `AuthorityAssignment`.
*   **Leave Management:** Multi-tier approval routing for Casual, Sick, Earned, and long-term leave (maternity, sabbatical), directly feeding Loss of Pay (LOP) calculations to payroll.
*   **Proxy Faculty Engine:** Handles planned and emergency proxy assignments, auto-ranking available faculty by subject eligibility and teaching load.

</details>

<details>
<summary><b>💳 Financial & Support Services</b></summary>
<br>

*   **Payments & Payroll:** Centralized fee structures, scholarship waivers, and payroll processing. Includes a fully integrated online payment gateway with automated receipts and nightly reconciliation.
*   **Events & QR Entry:** Manages internal/external events, venue booking, and budget approvals. Generates signed, single-use QR passes for secure mobile-app scanning at event gates.
*   **Placement Cell:** Manages company drives, dynamic eligibility criteria, interview rounds, and escalations for student no-shows.
*   **Help Desk & Campus Assets:** SLA-driven service ticketing for IT, hostels, and academics, plus full lifecycle management for technical and sports assets.

</details>

---

## 🔗 Technical Integrations

*   💳 **Payment Gateway:** Integration with **Razorpay** (Orders API, Webhooks, Refunds API) using HTTPS REST and HMAC signature verification for secure, idempotent payment processing.
*   🛡️ **Identity & Access (SSO):** SAML 2.0 or OIDC integration with the institution's Identity Provider, enforcing MFA for privileged roles.
*   📲 **Mobile App Framework:** ServiceNow mobile REST APIs supporting QR scanning, push notifications, and offline-tolerant manual fallbacks.
*   ✉️ **Communications:** Automated Email and Push notification engine supporting immediate alerts, scheduled reminders, and daily digests.

---

## 🔒 Security & Data Compliance

> **EduSphere is built with a zero-trust mindset tailored for the education sector.**

- **Data Isolation:** Strict row-level ACLs enforce college boundaries. A user in College A cannot view College B's transactional data.
- **Data Immutability:** Published exam marks, confirmed fee payments, and submitted student documents are strictly locked against unauthorized edits.
- **Comprehensive Auditability:** Detailed audit logging for all approvals, attendance corrections, fee modifications, and role changes.

---
<div align="center">
  <p><i>Developed for ServiceNow deployment utilizing Agile/Scrum methodologies.</i></p>
</div>
