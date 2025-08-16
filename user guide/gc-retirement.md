# GC Retirement

## **Retirement Process**:

* **Steps**:
  1. Select GCs in the portal or via API (/retire endpoint).
  2. Specify beneficiary and purpose (e.g., Scope 2 reporting, 45V compliance).
  3. Confirm retirement; registry marks GCs as “Retired” with a permanent audit log.
* **One-Time Retirement**: Ensures no double counting; retired GCs cannot be transferred or reused.

## **Use Cases**:

* **Corporate Sustainability**: Retire GCs to claim 24/7 CFE or zero-emission Scope 2 under GHG Protocol.
* **Regulatory Compliance**: Meet EU RED III sub-hourly GO requirements or U.S. 45V hydrogen tax credit rules.
* **Green Tariffs**: Utilities retire GCs for customer green tariff programs.

## **Reporting Tools**:

* Generate retirement statements (PDF/JSON) with GC IDs, timestamps, and MERs.
* Integrate with ESG platforms for automated Scope 2 reporting.
* Example: A corporation retires 500 GCs to cover 500 MWh of hourly load, producing a report for CDP submission.

## **Public Retirement Table**:

* **Access**: Available at https://www.granular-foundation.org/retirements; displays retired GCs with timestamps, IDs, and beneficiaries.
* **Purpose**: Ensures transparency, prevents double-counting, and supports auditability for sustainability claims.
* **Verification**: Stakeholders can query GC status to confirm retirement for compliance (e.g., CDP, SEC disclosures).
* **Interoperability**:
  * **EAC Integration**: Converts RECs/GOs/I-RECs into GCs via EnergyTag Configurations 1-3 (direct issuance, unbundled RECs, canceled EACs).
  * **API Endpoints**: Supports REST/GraphQL for seamless data exchange with PJM-GATS, M-RETS, or Evident.
  * **Example**: A producer transfers 100 GCs from PJM-GATS to the Granular Registry, which issues hourly GCs with embedded MERs.
