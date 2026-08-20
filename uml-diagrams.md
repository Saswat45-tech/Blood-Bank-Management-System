# UML Diagrams — RaktaSetu (Blood Bank Management System)

> These diagrams are written in **Mermaid** syntax, which GitHub renders automatically as visual diagrams when you view this file in the repository. No external image needed — but you can also open this in [draw.io](https://app.diagrams.net/) via the Mermaid import option if you'd like to edit them visually.

## 1. Use Case Diagram

```mermaid
graph LR
    Donor((Donor))
    Recipient((Recipient))
    Admin((Admin/Staff))

    Donor --> UC1[Register as Donor]
    Donor --> UC2[View Donation History]
    Recipient --> UC3[Search Blood by Group/Location]
    Recipient --> UC4[Book Appointment]
    Recipient --> UC5[Receive Notification]
    Admin --> UC6[Login Securely]
    Admin --> UC7[Manage Inventory]
    Admin --> UC8[Approve/Reject Requests]
    Admin --> UC9[Generate Reports]
    UC7 --> UC10[Trigger Low Stock Alert]
```

## 2. Class Diagram

```mermaid
classDiagram
    class Donor {
        +int donorId
        +String name
        +int age
        +String bloodGroup
        +String contact
        +register()
        +viewHistory()
    }
    class Recipient {
        +int recipientId
        +String name
        +String bloodGroupNeeded
        +searchBlood()
        +bookAppointment()
    }
    class Admin {
        +int adminId
        +String username
        +String password
        +login()
        +updateInventory()
        +approveRequest()
    }
    class BloodInventory {
        +String bloodGroup
        +int unitsAvailable
        +updateStock()
        +checkLowStock()
    }
    class Appointment {
        +int appointmentId
        +Date appointmentDate
        +String status
        +confirmAppointment()
    }
    Donor "1" --> "many" BloodInventory : donates
    Recipient "1" --> "many" Appointment : books
    Admin "1" --> "many" BloodInventory : manages
    Admin "1" --> "many" Appointment : approves
```

## 3. Sequence Diagram — Book Appointment (US-04)

```mermaid
sequenceDiagram
    participant R as Recipient
    participant S as System
    participant DB as Inventory Database
    participant A as Admin

    R->>S: Search blood group + location
    S->>DB: Query available units
    DB-->>S: Return matching stock
    S-->>R: Display available options
    R->>S: Select unit & book appointment
    S->>DB: Reserve blood unit
    S->>A: Notify admin of pending request
    A->>S: Approve request
    S->>R: Send appointment confirmation
```

## 4. Activity Diagram — Donation Process (US-01, US-02)

```mermaid
flowchart TD
    Start([Start]) --> A[Donor opens registration form]
    A --> B{Age >= 18?}
    B -- No --> C[Show error: not eligible]
    C --> End([End])
    B -- Yes --> D[Fill personal & medical details]
    D --> E{All mandatory fields filled?}
    E -- No --> F[Show validation error]
    F --> D
    E -- Yes --> G[Submit registration]
    G --> H[System saves donor record]
    H --> I[Update blood inventory count]
    I --> J[Show confirmation to donor]
    J --> End
```
