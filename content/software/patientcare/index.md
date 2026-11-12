---
title: PatientCare
tagline: An electronic health and care record, in constant use in the NHS since 2008.
description: PatientCare is an electronic health and care record built on structured, standards-based data and integrated with health service systems.
featured: true
weight: 1
build:
  publishResources: false  # publish only the resized screenshots, not the original PNGs
screens:
  - src: screens/neuroinflammatory.png
    title: Neuroinflammatory summary
    caption: Diagnosis, severity scores, relapses and disease-modifying treatments on one page. The patient is invented.
    alt: Neuroinflammatory summary for an invented patient with relapsing remitting multiple sclerosis, showing severity scores, disease events and disease-modifying therapies
  - src: screens/edss-chart.png
    title: EDSS over time
    caption: The EDSS from every clinic visit, with relapses marked, plotted against centiles for the same disease duration.
    alt: Chart of EDSS scores from 2009 to 2026 with relapses marked and severity centiles shown as lines
  - src: screens/medication-chart.png
    title: Medication chart
    caption: Every treatment on one timeline, including changes of dose. Point at a bar for its dose, or click it to edit.
    alt: Timeline of an invented patient's medications from 2011 to 2026, including four disease-modifying therapies in turn
highlights:
  - title: Industry standards
    text: Built on SNOMED CT, the NHS dictionary of medicines and devices (dm+d) and HL7 FHIR, so data can be counted, compared and shared.
  - title: Highly interoperable
    text: Connects to the systems a health service already runs, such as staff directories, patient indexes, patient administration systems and document repositories. In NHS Wales, for example, staff sign in with their NHS Wales accounts and find patients through national and local indexes, such as the eMPI, and across multiple patient administration systems.
  - title: Built for long-term conditions
    text: Records that follow patients over years, supporting services for long-term conditions such as multiple sclerosis, motor neurone disease, Parkinson's disease and epilepsy.
  - title: Outcome measures
    text: Integrates patient-reported and clinician-reported outcome measures into the record, for use in clinic and in research.
---

## Modules

- **[Medicines risk acknowledgement](/software/araf/)**: annual risk acknowledgement forms (ARAF) for valproate and topiramate, with online acknowledgement for patients.

## Integrations

- SNOMED CT, through [hermes](https://github.com/wardle/hermes)
- The NHS dictionary of medicines and devices, through [dmd](https://github.com/wardle/dmd)
- UK organisational data, through [clods](https://github.com/wardle/clods)
- UK indices of deprivation, through [deprivare](https://github.com/wardle/deprivare)
- Staff directories, patient indexes, patient administration systems and document repositories, including those used across NHS Wales

## How it is built

PatientCare is a set of loosely coupled modules. Applications are lightweight and focused on workflow: they ask for data in the shape they need, and a graph API brings it together from separate services. Data is written as events and read back in whichever form each application needs, including HL7 FHIR.
