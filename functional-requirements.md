# Functional Requirements — RaktaSetu (Blood Bank Management System)

## 1. Requirements Elicitation Technique
Requirements were gathered using **stakeholder interviews (simulated)**, review of similar blood bank systems, and a **survey-based technique** where common donor/recipient pain points (long search times, lack of stock visibility) were identified and translated into user stories.

## 2. Functional Requirements

| ID | Requirement | Related User Story |
|----|-------------|---------------------|
| FR-01 | The system shall allow donors to register with name, age, contact number, blood group, and address. | US-01 |
| FR-02 | The system shall validate that a registering donor is at least 18 years old. | US-01 |
| FR-03 | The system shall allow donors to view their donation history. | US-02 |
| FR-04 | The system shall allow recipients to search available blood units by blood group and location. | US-03 |
| FR-05 | The system shall allow recipients to book an appointment to receive a specific blood unit. | US-04 |
| FR-06 | The system shall require admin/staff to log in with a username and password before accessing management features. | US-05 |
| FR-07 | The system shall allow admins to add, update, or remove blood inventory records. | US-06 |
| FR-08 | The system shall automatically generate a low-stock alert when any blood group falls below a defined threshold (e.g., 5 units). | US-07 |
| FR-09 | The system shall allow admins to approve or reject pending donor and recipient requests. | US-08 |
| FR-10 | The system shall notify recipients when their blood request has been approved. | US-09 |
| FR-11 | The system shall allow staff to generate a report of monthly donations and requests. | US-10 |

## 3. Stakeholders (Summary)
See `stakeholder-analysis.md` for full details.
- Donors
- Recipients / Patients
- Hospital Administrative Staff
- System Administrator
- Course Instructor (project sponsor)
