# Standard Supply Service (SSS) Module

**Overview**: The SSS module enables utilities to allocate and retire GCs for standard supply service (e.g., RPS-eligible energy) and provide customers with auditable, hourly-matched data.

## **Supplier Setup**:

* **Master Accounts**: Create via portal/API with metadata:
  * **Balancing Area**: E.g., ERCOT, CAISO.
  * **Regulatory Context**: E.g., RPS, Clean Energy Standard (CES).
  * **Resource Type**: E.g., hydro, solar, nuclear.
* **Retirement**: Suppliers retire RPS-eligible GCs into master accounts, reflecting clean energy in standard supply.

## **Customer Subaccounts**:

* **Allocation**: Pro rata based on customer load share (hourly or monthly).
* **Claiming**: Customers receive invitations to claim subaccounts via email or portal; verified via secure link.
* **Merging**: Subaccounts can be linked with PPA, trading, or green tariff accounts for unified reporting.
* **Example**: A utility allocates 10% of its 1,000 MWh solar GCs to a customer with 100 MWh monthly load.

## **Green Tariff Integration**:

* **Overlay Tariffs**: Offer additional GC retirements for unmatched hours to achieve 24/7 CFE.
* **Process**: Customers opt into tariffs via portal; suppliers retire incremental GCs to cover gaps.
* **Example**: A customer with 50% SSS coverage purchases a green tariff to retire GCs for the remaining 50% of their load.

## **Communication**:

* **Notifications**: Automated alerts for new GC retirements, subaccount updates, or tariff opportunities.
* **Permissioned Access**: Customers view allocations via portal or API; suppliers control communication settings.
