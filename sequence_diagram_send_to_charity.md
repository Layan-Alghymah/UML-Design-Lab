sequenceDiagram
    actor P as Pharmacy
    participant C as CharityOrganization

    P->>P: sendToCharity()
    P->>C: receiveMedicine()
    C-->>P: Medicine received
