# Does the Granular Registry qualify as an "EAC Issuer" under US Hydrogen 45V rules?

The Granular Registry can satisfy Treasury/IRS § 1.45V-4(d)(2)(v) and therefore qualify as a “qualified EAC registry” for 45 V hydrogen claims, **provided that it is operated in the U S., implements a public generator API, and can demonstrate those capabilities to a 45 V qualified verifier**. A hydrogen producer could then match every MWh of electricity it uses with a “qualifying EAC” issued by the Granular Registry and retire those certificates inside the same platform.

***

### 1. What does 45 V require from an EAC registry

The proposed 45 V regulations (Fed. Reg. 26 Dec 2023) define a **“qualified EAC registry or accounting system”** as one that [Federal Register](https://www.federalregister.gov/documents/2023/12/26/2023-28359/section-45v-credit-for-production-of-clean-hydrogen-section-48a15-election-to-treat-clean-hydrogen).

| Requirement               | 45 V text                                                                            | Practical meaning for registries                 |
| ------------------------- | ------------------------------------------------------------------------------------ | ------------------------------------------------ |
| (A) Unique ID             | “Assigns a unique identification number to each EAC”                                 | serial-number per MWh                            |
| (B) One-to-one            | “Enables verification that only one EAC is associated with each unit of electricity” | prevents double issuing                          |
| (C) One-time retirement   | “Verifies that each EAC is claimed and retired only once”                            | locking/retirement function                      |
| (D) Ownership             | “Identifies the owner of each EAC”                                                   | account structure, audit log                     |
| (E) Public generator view | “Provides a publicly accessible view … of all currently registered generators”       | open list or API to stop duplicate registrations |

After 1 Jan 2028 a _qualifying_ EAC must also carry an **hourly timestamp** and fulfil incrementality + deliverability rules (same DOE “region”, new-build or uprate, etc.) [Federal Register](https://www.federalregister.gov/documents/2023/12/26/2023-28359/section-45v-credit-for-production-of-clean-hydrogen-section-48a15-election-to-treat-clean-hydrogen)

***

### 2. How the Granular Registry stacks up

| 45 V criterion                   | Evidence from Granular Registry design                                                                                                                                                                 | Meets?                                                |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------- |
| Unique ID                        | EnergyTag Standard § 1.4: “GCs shall have a unique identification number, received at issuance and maintained over the full certificate lifetime.” Granular-Certificate-Sc…                            | ✔                                                     |
| One-to-one & one-time retirement | Standard assigns GC Issuer the duty to avoid double issuance and double cancellation; the GC Registry Operator “shall record the Accounts and the Certificates held in them”. Granular-Certificate-Sc… | ✔                                                     |
| Ownership                        | Account-holder model identical to existing North-American EAC systems; owner changes are logged. Granular-Certificate-Sc…                                                                              | ✔                                                     |
| Public generator list            | GC Registry White-Paper recommends “public, API-based generator database for duplicate-check & transparency.” GC Registry White Paper…                                                                 | **Mostly** (must actually be implemented and exposed) |
| Hourly data                      | GCs record “production/storage discharge interval … maximum of one hour”. Granular-Certificate-Sc…                                                                                                     | ✔                                                     |
| Incrementality / new-build flag  | EnergyTag Config-2 & 3 workflows allow COD and uprate data tags; Granular Registry data model already stores COD, fuel, capacity, etc. Granular-Certificate-Sc…                                        | ✔                                                     |
| Deliverability (DOE region)      | Registry stores GPS or nodal ID; matching engine can filter by DOE regions.                                                                                                                            | ✔ (requires region mapping table)                     |

**Gap to close:** Treasury insists on (E) _public_ generator disclosure “through an API”. The Granular Registry design anticipates such an API, but will need to:

* expose the generator table (ID, fuel, COD, location, capacity) publicly or via an unauthenticated endpoint;
* document it for verifiers; and
* Keep duplication checks automated.

If that API is launched, the Registry meets every listed element of § 1.45V-4(d)(2)(v). No additional federal “pre-approval” list is foreseen—the hydrogen producer has to demonstrate to its _qualified verifier_ that the registry it used satisfies the five bullets.

***

### 3. Practical implications for hydrogen producers

| Item                                    | Impact / action                                                                                                                                    |
| --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Hour-matching from 2028**             | Producers will need hourly (not annual) GCs. Granular Registry’s sub-hour tagging is already compliant.                                            |
| **Incrementality rule (≤36-month COD)** | Registry must surface COD metadata so verifiers can filter out non-incremental GCs.                                                                |
| **Regional deliverability**             | Build a lookup that maps each generator’s balancing-authority or NERC region to the DOE 2023 “Transmission Needs Study” regions used by 45 V.      |
| **Verification workflow**               | Add export function so the _qualified verifier_ can pull a signed retirement report (certificate IDs, hour, owner, region) to attach to Form 7210. |
| **Engagement with Treasury/DOE**        | Publish a technical memo showing how the platform satisfies § 1.45V-4(d)(2)(v) and offer sandbox access to verifiers.                              |

***

### 4. Bottom line

_Technically,_ the Granular Registry already checks every box that § 1.45V-4 sets out for a qualified EAC registry—unique certificate IDs, double-count protection, ownership tracking, hourly data, and (once the public API is live) a transparent generator list.

That means hydrogen producers could retire Granular Certificates within the Registry to meet the power-matching requirements of 45 V, as long as those certificates themselves meet the **incrementality, temporal-matching, and regional deliverability** tests and a _qualified verifier_ attests to it.
