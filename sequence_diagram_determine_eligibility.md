sequenceDiagram
    actor P as Pharmacy
    participant M as Medicine

    P->>P: scanBarcode()
    P->>P: checkExpiryDate()
    P->>P: checkCondition()
    P->>P: determineDonationEligibility()

    alt Medicine is eligible
        M-->>P: Eligible
    else Medicine is not eligible
        M-->>P: Not Eligible
    end
