# GC Issuance

## **Overview**

GC issuance converts raw meter data or existing EACs into timestamped GCs, embedding long-run MERs to reflect carbon impact. The process adheres to the EnergyTag Standard, ensuring unique IDs and hourly granularity.

## **Eligibility Criteria**:

* **Supported Technologies**: Wind, solar (PV/CSP), geothermal, bioenergy (biomass, biogas, waste-to-energy), nuclear, marine/tidal, and storage-integrated projects.
* **Data Requirements**: Hourly generation data in UTC, verified by ISO settlement feeds or qualified reporting entities.
* **Compliance**: Projects must retire associated RECs/GOs per EnergyTag configurations (1-3) and minimize environmental/social impacts (e.g., wildlife conservation, community engagement).

## **Data Submission**:

* **Format**: Submit CSV or JSON files with:
  * **Timestamp**: ISO 8601 (e.g., 2025-07-22T13:00:00Z).
  * **Generation (MWh)**: Positive for generation, zero for consumption (negative values replaced).
  * **Meter\_ID**: Unique meter identifier.
  * **PEC\_Project\_ID**: Unique project identifier from onboarding.
* **Methods**:
  * **Web Portal**: Upload files via secure interface; supports drag-and-drop.
  * **API**: Submit via POST requests to /data/submit endpoint; tokens provided during onboarding.
* **Frequency**: Monthly or quarterly, aligned with EAC issuance cycles.
* **Purpose**: Allows end-users to split parent GCs into smaller child GCs (down to watt-hours) for precise load matching.
* **Process**:
  1. Request split via portal/API, specifying child GC energy amounts (e.g., split 0.75 MWh into 0.5 MWh and 0.25 MWh).
  2. Registry validates total energy conservation.
  3. Parent GC is canceled; child GCs are issued with new GC IDs (e.g., GC101-20250722T130000Z-200003-0500000).
  4. Audit trail logs split details.
* **Example**:
  * Parent GC: GC101-20250722T130000Z-200003-0750000 (0.75 MWh).
  * Child GC 1: GC101-20250722T130000Z-200003-0500000 (0.5 MWh).
  * Child GC 2: GC101-20250722T130000Z-200003-0250000 (0.25 MWh).

## **Quality Control**:

* **Automated Checks**:
  * **Time Interval Consistency**: No missing or duplicate timestamps; uniform hourly intervals.
  * **Data Completeness**: All required fields populated.
  * **Format Validation**: Correct timestamp and numeric formats.
  * **Outlier Detection**: Flags values outside expected ranges (e.g., negative generation, excessive MWh).
* **Manual Review**: Flagged data triggers producer notification for correction or documentation.
* **Consumption Handling**: Negative values (consumption) are set to zero for CFE projects.
