# Internal Accounts Subaccounts

### Overview

Internal accounts, also referred to as organizational sub-accounts, represent a hierarchical extension of a master account within The Granular Registry. Designed for intra-organizational segmentation, these accounts enable renewable energy developers, corporate buyers, utilities, and other entities to partition retired Granular Certificates (GCs) based on internal criteria such as regions, projects, trading markets, or business units. Unlike beneficiary allocation accounts (which facilitate external claims), internal accounts are strictly inward-facing, providing structured visibility and management without involving third-party claiming or attribute sharing.

This feature aligns with the evolving demands of corporate carbon accounting under the GHG Protocol Scope 2 market-based method, where entities must aggregate and report granular, time-stamped attributes (e.g., hourly production matches, combined marginal emissions rates via Operating Margin \[OM] + Build Margin \[BM]) across complex portfolios. By leveraging a tree-like hierarchy, internal accounts prevent ledger fragmentation while supporting precise avoided-emissions calculations—critical for Science-Based Targets initiative (SBTi) validations, SEC climate disclosures, and EU Corporate Sustainability Reporting Directive (CSRD) requirements.

Internal accounts operate exclusively on _retired_ GCs, ensuring compliance with EnergyTag v2 standards (e.g., Configuration 3 for post-retirement enhancement) and avoiding double-counting risks. They function as "nested views" rather than independent ledgers, inheriting the master account's retirement as the single source of truth.

### Key Features and Functionality

Internal accounts are created and managed directly within an organization's master account, offering flexibility for large-scale operations in the renewable power market.

#### Creation and Configuration

* **Creation Process**: Master account holders (e.g., a sustainability manager or portfolio administrator) can create unlimited internal accounts via the registry's UI or API (e.g., POST /accounts/{master\_id}/internal-sub-accounts). Required metadata includes:
  * Name/Label: Descriptive tags (e.g., "ERCOT Wind Portfolio 2024" or "EU Compliance Market").
  * Filters/Rules: Automated assignment criteria, such as technology type (e.g., solar, wind), vintage (e.g., COD > 2023), or geography (e.g., nodal/zonal codes per ISO/RTO boundaries like PJM or CAISO).
  * Pro-Rata Shares (Optional): Decimal allocations (0-1) based on internal consumption estimates or divisional budgets, enforced to sum ≤ 1 across siblings.
* **Hierarchy Support**: Accounts can be nested (e.g., "US Operations" → "West Region" → "CAISO Solar"), with depth limits (e.g., 5 levels) to maintain query performance. Use PostgreSQL's ltree extension for efficient traversal.
* **Assignment of Retired GCs**: Post-retirement, GCs are assigned via rules or manual selection (e.g., API PATCH /internal-sub-accounts/{id}/assign?gc\_ids=\[...]). Supports bulk operations for high-volume portfolios (e.g., 10k+ GCs from a multi-project PPA).

#### Management and Access

* **Permissions**: Role-based access control (RBAC) integrates with organizational roles—e.g., "portfolio\_manager" can reassign GCs between internal accounts for optimization, while "analyst" has read-only views. No external access; all operations are scoped to the org's master.
* **Dynamic Updates**: Recalculate allocations on-demand (e.g., monthly for variable internal loads) using the pro-rata engine, which ingests data from internal sources (e.g., ERP systems or Scope 2 estimates via API integrations).
* **Views and Reporting**: Aggregated dashboards show metrics like total retired MWh, avoided emissions (computed as share \* (OM + BM)/2 per GC), and residual mix for unallocated shares. Export formats include CSV for CDP submissions or JSON for ESG software (e.g., Watershed or Persefoni integrations).
* **Audit Trails**: Immutable logs track all assignments/reassignments (e.g., via signed events), ensuring traceability for internal audits or regulatory reviews (e.g., under SEC Rule 13a-15 for climate-related financial controls).

### Use Cases in Renewable Power and Carbon Accounting

Internal accounts address common pain points for experts managing diverse portfolios:

* **Regional Segmentation**: A multinational developer like Pattern Energy creates sub-accounts for ISO-specific GCs (e.g., "PJM Region" for East Coast wind), facilitating location-based matching and compliance with state RPS mandates.
* **Project-Level Tracking**: Corporate buyers (e.g., Meta) organize GCs by PPA vintage or technology (e.g., "Offshore Wind 2025"), enabling granular 24/7 CFE claims and SBTi-aligned avoided-emissions reporting.
* **Market Differentiation**: Trading desks separate voluntary (e.g., high-impact unbundled GCs) from compliance markets (e.g., RPS-eligible), streamlining portfolio risk assessments and derivative pricing based on marginal emissions volatility.
* **Divisional Allocation**: Utilities or large corporates allocate retired GCs pro-rata to business units (e.g., data centers vs. manufacturing), supporting internal carbon pricing and Scope 2 sub-site reporting without duplicating retirements.

These use cases enhance precision in corporate disclosures, where granular data (e.g., hourly OM from REsurety and BM from ClimateTRACE) must be segmented for auditability.

### Technical and Compliance Considerations

* **Architecture**: Built on TimescaleDB for time-series efficiency (e.g., querying hourly allocations across 1M+ GCs in <500ms). Pro-rata engine uses vectorized computations (e.g., NumPy) for scalability.
* **Integration Points**: API endpoints align with existing EAC adapters (e.g., import retired RECs from APX or Grexel); extend SSS module logic for optional pro-rata.
* **Compliance Alignment**: Ensures unique claims per EnergyTag (no transfers); supports GHG Protocol Scope 2 (market-based zeroing via aggregated retirements) and Scope 3 (internal insets). Prevents over-allocation with database constraints; generates Beneficiary-like Statements for internal use (e.g., divisional claims).
* **Limitations and Best Practices**: Not for active trading (use master for transfers); cap nesting to avoid performance hits. For experts: Pair with marginal rate APIs for real-time impact simulations during assignments.

Internal accounts empower organizations to navigate the complexities of the renewable market with structured, verifiable data—paving the way for more impactful decarbonization strategies. For external beneficiary allocations, refer to forthcoming documentation. Contact Clean Incentive support for implementation guidance or API sandbox access.
