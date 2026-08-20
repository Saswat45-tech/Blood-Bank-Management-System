# Non-Functional Requirements — RaktaSetu (Blood Bank Management System)

| ID | Category | Requirement |
|----|----------|-------------|
| NFR-01 | **Performance** | The system shall return blood search results within 2 seconds under normal load. |
| NFR-02 | **Usability** | A first-time user shall be able to complete donor registration without external help within 3 minutes. |
| NFR-03 | **Security** | All admin accounts shall require password-based authentication; passwords shall be stored in hashed form. |
| NFR-04 | **Availability** | The system shall be available 99% of the time during hospital operating hours (6 AM – 10 PM). |
| NFR-05 | **Reliability** | The system shall not allow duplicate donor registrations using the same contact number. |
| NFR-06 | **Scalability** | The system shall support at least 500 concurrent donor/recipient records without performance degradation. |
| NFR-07 | **Maintainability** | The codebase shall follow a modular structure so new features (e.g., SMS alerts) can be added without major rework. |
| NFR-08 | **Data Privacy** | Donor medical information shall only be visible to authorized admin accounts, in line with basic health-data privacy principles. |
| NFR-09 | **Portability** | The system's web interface shall be accessible from any modern browser (Chrome, Firefox, Edge) without additional plugins. |

## Techniques Used to Derive Non-Functional Requirements
Non-functional requirements were derived through **quality attribute analysis**, considering how real hospital and blood bank systems are expected to behave (fast search, secure access, high availability), combined with constraints reasonable for an academic simulation project.
