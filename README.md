# MNCH Continuum of Care and Data Quality Analysis

## Problem Statement

In counties such as Turkana, Homa Bay, Nairobi, Machakos, and Kilifi, community health teams often record strong initial uptake of antenatal care (ANC), yet many mothers do not complete the fourth ANC visit, deliver without a skilled attendant, or miss postnatal and childhood immunization follow-up. These service drop-offs can slow progress toward Kenya’s maternal and newborn health goals. Kenya has recently renewed its national push to reduce preventable maternal and newborn deaths through the Every Woman Every Newborn Everywhere plan, highlighting the importance of continuity of care across pregnancy, childbirth, and the postnatal period.

A second challenge is data reliability. Monthly facility reports submitted through DHIS2, Kenya’s national health information system, may contain logical inconsistencies, such as reporting more ANC fourth visits than first visits. When such errors are not identified, they can distort attrition patterns and lead to poor targeting of scarce outreach and supervision resources.

**This project addresses two questions:**
1. At which point in the maternal and child health continuum does the greatest drop-off occur, and how does it vary by county or season?
2. Are the facility reports used in this analysis reliable enough to support decision-making, and if not, which facilities should be prioritized for data quality follow-up?

## Key Metrics

- **ANC Retention Rate:** Percentage of women who progress from the first ANC visit to the fourth ANC visit.
- **Skilled Birth Attendance (SBA) Rate:** Percentage of deliveries attended by skilled health personnel.
- **Postnatal Care (PNC) Coverage:** Percentage of mothers and newborns receiving care within 48 hours of delivery.
- **Fully Immunized Child (FIC) Rate:** Percentage of infants fully immunized by 12 months.
- **Data Quality Index (DQI):** Percentage of facility reports that are free from predefined logical errors.

## Stakeholders

- **County health leaders:** Need county-level performance trends and comparison against maternal and newborn health priorities.
- **Monitoring and evaluation (M&E) and DHIS2 officers:** Need automated checks to identify inconsistent or incomplete facility reports.
- **Community Health Promoters (CHPs):** Need clear lists of facilities or catchment areas that require follow-up, since CHPs serve as the link between households and formal health facilities in Kenya’s community health system.

## Data

The analysis uses a synthetic dataset modeled on monthly DHIS2 facility summary reports, including MOH 710 and MOH 711 reporting patterns. It covers 100 facilities across 5 counties, 3 KEPH facility levels, and 12 months in 2025. The dataset includes realistic field challenges such as missing values, reporting gaps, and data-entry anomalies to simulate routine health information system conditions.

## Tools

Python libraries such as pandas and numpy are used for data cleaning, validation, and analysis. Power BI is used to build the dashboard and present findings interactively.

## Scope

This project focuses on the **Maternal, Newborn, and Child Health (MNCH)** segment of the continuum of care: antenatal, delivery, postnatal, and early childhood services. This scope was chosen because it directly captures the ANC-to-immunization attrition pattern under investigation, rather than the broader RMNCAH framework, which also includes reproductive and adolescent health components.

## Limitations

This is a synthetic dataset designed to resemble realistic DHIS2 reporting behavior and common MNCH attrition patterns; it is not based on actual facility-level records. In addition, the dataset is a monthly facility panel rather than a longitudinal patient cohort, so it is intended to show how the health system is performing over time, not to track the journey of individual mothers and children.
