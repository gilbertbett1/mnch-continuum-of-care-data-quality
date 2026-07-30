# MCH Continuum of Care & Data Quality Analysis

---

## Problem Statement

In counties such as Turkana, Homa Bay, Nairobi, Machakos, and Kilifi, community health teams often record strong initial uptake of antenatal care (ANC) at the first visit, but many mothers do not return for the fourth ANC contact, deliver without a skilled attendant, or miss postnatal and childhood immunization follow-up. These drop-offs directly threaten progress toward Kenya’s maternal and child health targets.

The challenge is compounded by monthly facility reports submitted into DHIS2, Kenya’s national health information system, which can contain logical errors. For example, some facilities may report more ANC fourth visits than ANC first visits, creating misleading results that can mask true attrition and misdirect limited outreach resources if left unchecked.

**This project asks two questions:**
1. Where in the maternal-to-child health (MCH) continuum is the greatest drop-off occurring, and does it vary by county or season?
2. Are the facility reports feeding into this analysis reliable enough to trust, and if not, which facilities should be prioritized for data-quality follow-up?

---

## Key Metrics Tracked

- **ANC Retention Rate** — Percentage of women who complete ANC visits from the first through the fourth contact.
- **Skilled Birth Attendance (SBA) Rate** — Percentage of deliveries attended by a skilled provider.
- **Postnatal Care (PNC) Coverage** — Percentage receiving care within 48 hours of delivery.
- **Fully Immunized Child (FIC) Rate** — Percentage of infants fully vaccinated by 12 months.
- **Data Quality Index (DQI)** — Percentage of facility reports free from logical errors.

---

## Stakeholders

- **County health leadership** — Needs a county-level view of coverage and performance against national targets.
- **M&E / DHIS2 officers** — Need automated flags for incomplete or unreliable facility data.
- **Community health promoters (CHPs)** — Need a prioritized list of facilities and areas for follow-up.

---

## Data

The analysis uses a synthetic dataset modeled on DHIS2 monthly facility summary reports (MOH 710/711). It covers 100 facilities across five counties and three KEPH facility levels: Level 2 dispensary, Level 3 health center, and Level 4 hospital. The data spans 12 months in 2025 and includes realistic imperfections such as missing values, reporting gaps, and data-entry anomalies to reflect routine field conditions.

---

## Tools

- **Python** (pandas, numpy) for cleaning and analysis.
- **Power BI** for dashboard development and presentation.

---

## Scope Note

This project focuses specifically on the **Maternal and Child Health (MCH)** segment of the continuum of care: antenatal, delivery, postnatal, and early childhood services. It does not cover the full RMNCAH framework, which also includes reproductive health and adolescent health. MCH was selected because it captures the specific ANC-to-immunization attrition problem investigated in this project.

---

## Methodology

1. **Data Generation** — A synthetic 12-month DHIS2-style facility-month extract was created with realistic reporting gaps, seasonal access effects in flood-prone counties, and data-entry anomalies.
2. **Data Cleaning and Quality Validation** — Schema standardization, deduplication, tier-aware median imputation within County and Facility Level, logic-based validation rules, and a Data Quality Index were applied.
3. **Diagnostic Analysis** — The analysis focused on three questions: where the largest drop-off occurs, whether coverage varies seasonally, and whether data quality is associated with service attrition.
4. **Dashboard Development** — A single-page Power BI dashboard was built to present KPI cards and four supporting visuals.

---

## Key Insights

**1. The largest drop in the continuum happens early.**  
Nearly 40% of women who attend a first ANC visit do not return for the fourth visit, making ANC 1 to ANC 4 the biggest single drop in the continuum. Losses after ANC 4 are comparatively smaller. This suggests that retention efforts should focus first on improving follow-up after the initial ANC contact.

**2. Seasonal access barriers appear to explain part of the gap.**  
Counties with poorer road infrastructure and flood exposure, such as Turkana, Homa Bay, and Kilifi, show a recurring decline in ANC 1 coverage during the long and short rains. Coverage drops from roughly the low 90s to the low 70s during these periods, while other counties remain relatively stable. This points to an access and logistics challenge that is strongly seasonal.

**3. Data quality problems are separate from service drop-off.**  
An early analysis suggested that poor data quality and worse attrition were linked, but that relationship was driven by a calculation issue in one of the flags. Once that dependency was removed, the relationship was minimal. This means attrition and reporting quality should be managed through separate response tracks.

**4. Reporting is incomplete by design.**  
About 95% of expected facility-month reports were submitted, which reflects realistic reporting completeness rather than perfect compliance. Among submitted reports, roughly 81% were free of logical errors, while the remainder contained issues such as implausible ANC or PNC values. Modeling this imperfection makes the analysis closer to real DHIS2 conditions.

---

## Recommendations

**1. Target ANC retention directly.**  
Since the largest loss occurs between ANC 1 and ANC 4, community health promoters should prioritize follow-up shortly after the first ANC contact rather than spreading limited outreach evenly across all care stages.  
*Owner: Sub-County Public Health Nurses / CHPs*

**2. Time outreach before the rainy seasons.**  
Turkana, Homa Bay, and Kilifi should receive seasonal outreach support before and during the long rains and short rains. This can include mobile clinics, transport support, and pre-positioned community health services.  
*Owner: County Executive Committee for Health / Sub-County Medical Officers*

**3. Separate data-quality supervision from attrition response.**  
Facilities with repeated logic errors should be flagged for supportive supervision and retraining through a dedicated M&E workflow. These should not be mixed with the list of facilities flagged for high attrition.  
*Owner: M&E Officers / DHIS2 Focal Persons*

**4. Set a short-term performance target.**  
Reduce ANC 1 to ANC 4 attrition from about 39% to below 30% within two quarters, and track progress monthly using the dashboard’s attrition and data-quality indicators.  
*Owner: County Executive and Sub-County Medical Officers*

---

## Limitations

- This is a **synthetic dataset** built to reflect realistic DHIS2 reporting patterns and common MCH attrition dynamics, not real facility data.
- It is a **cross-sectional monthly panel**, not a longitudinal patient cohort, so it shows system performance rather than the journey of specific mothers and infants.
- **PNC coverage** is measured against skilled-facility deliveries only; home deliveries are excluded from the denominator.
- Tier-aware imputation by County and Facility Level improves on county-only imputation, but some county-level combinations still contain few facilities, which can reduce the stability of imputed values.

---

## Future Work

- Add cohort-level tracking of mothers and infants across the full continuum of care.
- Extend the analysis with predictive risk scoring once a larger and more feature-rich dataset is available.

---

## Repository Contents

- `raw_mch_data.csv` — Synthetic raw facility-month extract.
- `cleaned_mch_data.csv` — Cleaned, validated, indicator-enriched dataset.
- `finding1_cascade_summary.csv`, `finding2_seasonality_summary.csv`, `finding3_facility_summary.csv` — Supporting tables for the diagnostic findings.
- `MCH_dashboard.pdf` / Power BI file — Final dashboard output.
- Analysis notebook — Full cleaning, validation, and diagnostic code.