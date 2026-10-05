# Medicine Waste Management System

## Project Overview

The **Medicine Waste Management System** is a software design project for managing donated medicines from registration to their final destination.

The system allows **public patients and hospitals** to register medicines. A **pharmacy** then checks the medicine's barcode, expiry date, and condition to determine whether it is eligible for donation.

* Eligible medicines are sent to a **Charity Organization**.
* Medicines that are not eligible are sent to a **Waste Disposal Facility**.
* An **Administrator** tracks medicine status and generates confirmations and reports.

The project focuses on designing the system using **UML class diagrams, use cases, and sequence diagrams**.

---

## Problem Statement

Unused medicines may still be useful to others, while expired or unsuitable medicines need to be safely disposed of.

Without an organized system, it can be difficult to:

* Register donated medicines.
* Track medicine information.
* Check expiry dates and conditions.
* Determine donation eligibility.
* Send medicines to the correct destination.
* Track the status of donated medicines.
* Generate reports and confirmations.

This system provides a structured workflow for managing the medicine donation and disposal process.

---

## System Actors

The main actors in the system are:

| Actor                       | Responsibility                               |
| --------------------------- | -------------------------------------------- |
| **Donor**                   | Registers donated medicine                   |
| **Public Patient**          | Donates medicine as a type of Donor          |
| **Hospital**                | Donates medicine as a type of Donor          |
| **Pharmacy**                | Checks and processes donated medicine        |
| **Charity Organization**    | Receives eligible medicine                   |
| **Waste Disposal Facility** | Disposes of unsuitable medicine              |
| **Administrator**           | Tracks medicine status and generates reports |

---

## Main Workflow

```text
Donor
   |
   v
Register Medicine
   |
   v
Medicine
   |
   v
Pharmacy
   |
   +--> Scan Barcode
   |
   +--> Check Expiry Date
   |
   +--> Check Condition
   |
   +--> Determine Donation Eligibility
   |
   +----------------------+
   |                      |
   v                      v
Eligible              Not Suitable
   |                      |
   v                      v
Charity              Disposal Facility
   |                      |
   +----------+-----------+
              |
              v
     Medicine Status Updated
              |
              v
     Administrator Tracks Status
```

---

## Medicine Status

A medicine can have one of the following statuses:

* `Registered`
* `Under Review`
* `Sent to Charity`
* `Sent to Disposal`

The `eligibility` attribute is kept separate from `status`.

* `eligibility` indicates whether the medicine can be donated.
* `status` indicates the current stage of the medicine in the workflow.
---
