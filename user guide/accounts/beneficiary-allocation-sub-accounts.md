# Beneficiary Allocation Sub-Accounts

## Overview

Beneficiary allocation sub-accounts, often referred to as external sub-accounts, extend The Granular Registry's hierarchical framework to enable secure, pro-rata sharing of retired Granular Certificate (GC) attributes with external parties such as tenants, suppliers, or retail customers. Unlike internal organizational sub-accounts (which focus on intra-org segmentation), beneficiary allocations facilitate "on-behalf-of" retirements, granting read-only visibility into a master account's retired GCs without transferring ownership or altering the ledger. This design preserves chain-of-custody integrity under EnergyTag v2 (e.g., Configuration 3 requirements for post-retirement enhancements) and aligns with GHG Protocol Scope 2 market-based guidance, where intermediaries (e.g., landlords or utilities) retire GCs centrally but allocate claims to end-users reporting the consumption.

In the renewable power market, where corporate buyers increasingly demand verifiable, granular data for Scope 2 zero-emissions claims and Scope 3 reductions, beneficiary allocations address key challenges: fragmented value chains, opaque utility tariffs, and the need for auditable insets (internal offsets within supply chains). By referencing retired GC attributes (e.g., hourly timestamps from metered production, combined marginal emissions rates \[OM from REsurety + BM from ClimateTRACE], and technology metadata), these sub-accounts enable precise avoided-emissions calculations without risking double-counting—critical for compliance with SEC climate-risk disclosures, EU RED III sub-hourly Guarantees of Origin (GOs), and SBTi validations.

Beneficiary allocations operate as "linked views" or "pro-rata designations," tied to the master account's retirement as the immutable source of truth. They support invitation-based claiming, allowing external parties to import allocations into their own organizational master accounts for unified reporting. This positions the registry as a neutral hub for multi-stakeholder ecosystems, reducing integration costs with legacy EAC systems (e.g., APX or Grexel) and accelerating adoption of impact-based procurement strategies.

### Key Features and Functionality

Beneficiary allocation sub-accounts are initiated by master account holders (e.g., utilities or buyers) and claimed by external beneficiaries, emphasizing transparency and compliance in distributed carbon accounting.

#### Creation and Configuration

* **Creation Process**: Master holders create sub-accounts via UI or API (e.g., POST /accounts/{master\_id}/beneficiary-sub-accounts), specifying metadata like beneficiary ID (e.g., tenant/supplier EIN), consumption profile (e.g., hourly MWh from AMI meters or Scope 3 estimates), and pro-rata rules (e.g., share based on leased capacity or attributable emissions). Supports bulk creation for high-volume scenarios (e.g., utilities allocating to 1M+ customers).
* **Pro-Rata Allocation**: Automated engine divides retired GC attributes (e.g., avoided emissions = share \* (OM + BM)/2 per GC) based on uploaded or integrated data (e.g., CSV from building management systems or EPA Scope 3 tools). Enforces conservation (sum of shares ≤ 1) with dynamic recalcs for variable loads (e.g., monthly updates).
* **Invitation Mechanism**: Generate secure, expirable tokens (e.g., JWTs) for beneficiaries to claim; includes verification (e.g., domain matching or shared secrets) to prevent unauthorized access.

#### Management and Access

* **Claiming and Linking**: Beneficiaries redeem tokens to activate the sub-account, importing it as a "linked allocation" in their org's master (e.g., API POST /orgs/{org\_id}/claim-allocation?token=...). Post-claim, it appears as a virtual sub-account for aggregation with direct procurements (e.g., PPAs or unbundled GCs).
* **Read-Only Visibility**: Beneficiaries access dashboards showing pro-rata GC details (e.g., source project COD, marginal rates, tech type), with filters for time/location matching. No modifications allowed; changes (e.g., revocations) are master-initiated with notifications.
* **Beneficiary Statements**: Auto-generated upon claim (PDF/JSON format), certifying the allocation (e.g., "Pro-rata share of 200 MWh from Master's retired GCs: 150 MT CO2e avoided via 24/7 matching"). Includes audit-proof references (e.g., master GC hashes) for defensibility.
* **Revocation and Expiry**: Masters can revoke (e.g., on contract end), auto-expiring allocations and notifying beneficiaries; logs ensure traceability.

### Use Cases in Renewable Power and Carbon Accounting

Beneficiary allocations unlock value in interconnected markets, where intermediaries hold GCs but end-users report emissions.

* **Landlord-Tenant Scope 2 Sharing**: A data center operator retires GCs from a facility-wide PPA; allocates pro-rata to tenants based on rackspace power draw. Tenants claim for market-based zeroing, supporting 24/7 CFE claims without custom transfers—ideal for multi-tenant facilities under net leases.
* **Supply Chain Scope 3 Insetting**: A buyer like Meta retires GCs for upstream suppliers' estimated load (e.g., semiconductor manufacturing); allocates via sub-accounts. Suppliers claim for their Scope 2, while Meta reports Scope 3 reductions (avoided emissions per Category 3/4), aligning with CSRD value chain mandates.
* **Utility SSS and Green Tariffs**: Retail suppliers retire RPS GCs; allocate to customers for default supply visibility. Customers claim to overlay with voluntary procurements, enabling granular residual mix calculations and compliance with California/New York clean energy policies.
* **Broker/PPAs "On-Behalf-Of" Retirements**: Brokers retire bundled GCs; allocate to clients for verifiable claims, streamlining audits in volatile markets where marginal rates vary (e.g., high-impact evening wind in ERCOT).

These cases enhance corporate decarbonization by directing procurements to high-impact assets (e.g., using registry's impact rankings) and providing evidence for SBTi/Scope 3 insets.

### Technical and Compliance Considerations

* **Architecture**: Leverages TimescaleDB for scalable pro-rata queries (<500ms on 10k+ allocations); uses foreign keys to reference master GCs (no duplication). API endpoints extend SSS module (e.g., bulk invites for utilities).
* **Integration Points**: API for consumption ingestion (e.g., from Scope 3 databases like ecoinvent); aligns with EAC adapters for seamless REC-to-GC conversion.
* **Compliance Alignment**: Prevents double-claiming by flagging allocated shares in master reports (e.g., exclude from intermediary Scope 2); supports GHG Protocol Scope 3 (upstream/downstream chaining) and EnergyTag unique claims. Generates immutable logs for audits (e.g., SEC 13a-15 controls).
* **Limitations and Best Practices**: Post-retirement only; cap allocations at 100% to avoid over-claims. For experts: Use with marginal APIs for simulations (e.g., prioritize allocations to high-BM hours); pair with SSS for utility-scale rollouts.

Beneficiary allocation sub-accounts empower intermediaries to foster transparent, impactful ecosystems—driving renewable adoption while simplifying Scope 2/3 reporting. For internal accounts or SSS specifics, refer to related sections. Contact Clean Incentive for API docs or pilot opportunities.
