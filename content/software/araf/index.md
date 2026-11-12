---
title: Medicines risk acknowledgement
tagline: Annual risk acknowledgement forms (ARAF) for valproate and topiramate, from evaluation to signed report.
description: Manage MHRA annual risk acknowledgement forms (ARAF) for the valproate and topiramate pregnancy prevention programmes, with online patient acknowledgement and a signed report for the record.
badge: Follows the MHRA forms
part_of: /software/patientcare
cta_title: Manage risk acknowledgement in your service
featured: true
weight: 10
build:
  publishResources: false  # publish only the resized screenshots, not the original PNGs
steps:
  - title: Evaluate
    text: The prescriber records whether the programme applies, with any permanent or temporary reason for exclusion. The patient can confirm an exclusion online or in clinic.
  - title: Decide
    text: The prescriber records the treatment decision, and a second clinician countersigns it.
  - title: Explain risks
    text: The prescriber records that the risks have been explained to the patient.
  - title: Acknowledge
    text: The patient acknowledges the risks on their own phone or computer, from a QR code or an SMS link, or on paper in clinic.
screens:
  - src: screens/cohort.png
    title: Every patient in the service
    caption: Each patient's status and when their form expires, with a filter for each step still to do.
  - src: screens/patient-record.png
    title: In the patient record
    caption: The patient's programme, its status and expiry date, under Treatment in their record.
  - src: screens/recording.png
    title: Recording the steps
    caption: Each step is recorded in turn. Here the treatment decision waits for a second clinician to countersign it.
  - src: screens/portal.png
    device: phone
    title: The patient's view
    caption: Patients open the link from an SMS or QR code and acknowledge each statement on their own phone.
  - src: screens/report.png
    device: document
    file: screens/araf-valproate-sample.pdf
    file_title: Download the sample report
    title: The signed report
    caption: The completed MHRA form, filled in from the record and signed by the prescriber. The patient's acknowledgement and signature come from her phone. This sample is for an invented patient.
    alt: Step 4 of a completed valproate annual risk acknowledgement form, initialled and signed by the patient
outcome:
  title: Signed report
  text: The completed form is produced as a filled-in copy of the MHRA form and published to the patient's record as a signed report.
---

## Programmes

- Valproate
- Topiramate, for epilepsy
- Topiramate, for migraine

Each programme follows the MHRA form for that drug. A patient can be in more than one.

## For the service

- **Every patient at a glance.** Each service has a list of its patients showing each patient's status, when their form expires and the next step due.
- **Part of the patient record.** Record valproate or topiramate as a medication and the patient's annual risk forms appear in their record. Drugs are identified using SNOMED CT, so every product and brand is covered.
- **Gaps flagged.** Warnings show when a patient taking the drug is not registered to a programme, when a registered patient is no longer recorded as taking it, and when a patient is registered to two services at once.
- **The right people act.** Only clinicians in the service responsible for the patient can record or request forms. Everyone else sees a read-only view.

## For patients

Patients respond from a link sent by SMS or a QR code given in clinic, on their own phone or computer. Paper remains available.

## Security

The patient-facing service runs separately from the clinical record, with its own database. Requests sent to patients are signed by the clinical system.
