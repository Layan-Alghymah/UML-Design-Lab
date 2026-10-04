sequenceDiagram
    actor P as Pharmacy
    participant W as WasteDisposalFacility

    P->>P: sendToDisposal()
    P->>W: disposeMedicine()
    W-->>P: Disposal completed
