# MNCH Continuum-of-Care & Data Quality Analysis

## Problem Statement

In counties like Turkana, Homa Bay, Nairobi, Machakos, and Kilifi, community
health teams record strong initial contact for Antenatal Care (ANC 1st
visit), but a large share of mothers never return for their 4th ANC
contact, deliver without a skilled attendant, or miss postnatal and
childhood immunization follow-up. This drop-off directly threatens progress
against Kenya's maternal and child mortality targets.

Adding to the problem: monthly facility reports submitted into DHIS2
(Kenya's national health information system) sometimes contain logical
errors -- for example, more women recorded at ANC visit 4 than at ANC visit
1 -- which can mask true attrition and misdirect limited outreach resources
if left unvalidated.

**This project asks two questions:**
1. Where in the maternal-to-child health (MCH) continuum is the biggest
   drop-off occurring, and does it vary by county or season?
2. Are the facility reports feeding into this analysis reliable enough to
   trust, and if not, which facilities need a data-quality follow-up?

## Key Metrics Tracked
- **ANC Retention Rate** -- % of women who complete ANC 1st through 4th visit
- **Skilled Birth Attendance (SBA) Rate** -- % of deliveries under skilled care
- **Postnatal Care (PNC) Coverage** -- % receiving care within 48 hours of delivery
- **Fully Immunized Child (FIC) Rate** -- % of infants fully vaccinated by 12 months
- **Data Quality Index (DQI)** -- % of facility reports free of logical errors

## Stakeholders
- **County health leadership** -- needs macro-level coverage vs. national targets
- **M&E / DHIS2 officers** -- need automated flags for unreliable facility data
- **Community health promoters** -- need a list of facilities/areas to prioritize for follow-up

## Data
Synthetic dataset modeled on DHIS2 monthly facility summary reports
(MOH 710/711), covering 100 facilities across 5 counties and 3 KEPH
facility levels (Level 2 dispensary, Level 3 health center, Level 4
hospital) over 12 months (2025). Data includes realistic imperfections:
missing values, reporting gaps, and data-entry anomalies, to reflect
genuine field conditions.

## Tools
Python (pandas, numpy) for cleaning and analysis · Power BI for the
dashboard

## Scope Note
This project focuses specifically on the **Maternal & Child Health (MCH)**
segment of the continuum -- antenatal, delivery, postnatal, and early
childhood care -- rather than the full RMNCAH framework (which also
includes reproductive health and adolescent health). MCH was chosen as the
scope because it captures the specific ANC-to-immunization attrition
problem this project investigates.

## Limitations
This is a synthetic dataset built to reflect realistic DHIS2 reporting
patterns and known MCH attrition dynamics, not real facility data. It is a
cross-sectional monthly panel (each row is a facility's monthly count), not
a tracked patient cohort -- so it answers "how is the system performing"
rather than "what happened to a specific group of mothers."