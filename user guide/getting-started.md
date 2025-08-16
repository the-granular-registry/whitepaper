# Getting Started

## **Account Creation and Roles**:

* **Account Types**:
  * **Producer**: Registers projects and submits generation data for GC issuance.
  * **Buyer**: Procures and retires GCs for sustainability or compliance claims.
  * **Storage Operator**: Tracks charge/discharge cycles for time-shifted energy.
  * **Utility/Supplier**: Manages SSS accounts and allocates GCs to customers.
  * **Auditor**: Verifies GC issuance, transfers, and retirements for compliance.
* **Setup Process**:
  * Register via the web portal at https://www.granular-foundation.org or through API endpoints.
  * Provide organizational details, including legal name, contact information, and role-specific metadata (e.g., balancing area for utilities, project IDs for producers).
  * Authenticate using OAuth 2.0 or API tokens; all data transfers use HTTPS encryption.
* **Verification**: Clean Incentive verifies account applications within 48 hours, ensuring compliance with EnergyTag Standard roles (e.g., Issuer, Registrar, Account Holder).

## **System Requirements**:

* **Web Portal**: Compatible with modern browsers (Chrome, Firefox, Edge; latest versions).
* **API Access**: Requires tools like Postman or cURL for REST/GraphQL interactions; supports JSON and CSV payloads.
* **Hardware**: No specific hardware requirements; cloud-based access ensures scalability.

## **Onboarding Process**:

* **Producers**: Submit project metadata (e.g., technology type, installed capacity, geographic coordinates) and a verification report from a qualified third party.
* **Buyers/Suppliers**: Link to existing EAC accounts (e.g., PJM-GATS, M-RETS) for seamless integration.
* **Storage Operators**: Provide storage system specifications (e.g., round-trip efficiency, capacity) and charge/discharge protocols.
* **Existing Registries**: Configure API-based adapters for REC/GO conversion to GCs without disrupting current infrastructure.
* **Initial Setup Checklist**:
  * Create and verify account.
  * Obtain API tokens from the web portal.
  * Review integration guides at https://docs.granular-foundation.org.
  * Test connectivity using sandbox environment (available post-incubation in LF Energy).
