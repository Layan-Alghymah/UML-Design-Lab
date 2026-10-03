sequenceDiagram
    actor D as Donor
    participant M as Medicine
    participant P as Pharmacy
    participant C as CharityOrganization
    participant W as WasteDisposalFacility

    D->>M: registerMedicine()

    P->>M: getBarcode()
    M-->>P: barcode
    P->>P: scanBarcode()

    P->>M: getExpiryDate()
    M-->>P: expiryDate
    P->>P: checkExpiryDate()

    P->>M: getCondition()
    M-->>P: condition
    P->>P: checkCondition()

    P->>P: determineDonationEligibility()
    P->>M: setEligibility()

    alt Medicine is eligible
        P->>C: sendToCharity()
        C->>C: receiveMedicine()
        P->>M: updateStatus()
    else Medicine is not eligible
        P->>W: sendToDisposal()
        W->>W: disposeMedicine()
        P->>M: updateStatus()
    end
