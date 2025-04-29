# Can GCs be issued for carbon‑free generators that do not receive EACs?

**Yes.**\
Many grids only issue Energy Attribute Certificates (EACs) for _renewable_ technologies, leaving out other carbon-free generators—e.g., nuclear, large-scale hydro, geothermal or emerging zero-carbon fuels. The Granular Registry can still track, trade and retire hourly certificates for those assets by operating under **EnergyTag Configuration #2 (“GC scheme supplements the EAC scheme”)**.

***

**How Configuration #2 works in practice**

| Step                     | What happens                                                                                                                                               | Who is responsible            |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------- |
| 1 — Meter data           | The plant’s revenue-grade meters (or ISO/utility telemetry) send hourly generation data to the Granular Registry.                                          | Measurement Body / ISO        |
| 2 — Certificate issuance | The Registry issues one Granular Certificate (GC) for every net-MWh, stamped with the hour, location, technology, emissions factor, etc.                   | GC Issuer (Granular Registry) |
| 3 — No double counting   | The asset owner attests that no other EAC or claim will be created for the same MWh. The Registry periodically reconciles issued GCs with settlement data. | GC Issuer + Asset Owner       |
| 4 — Trading & retirement | GCs can be transferred, bundled into tariffs, or retired to support 24/7 CFE reporting and market-based Scope 2 accounting.                                | Market participants           |

Because there is **no pre-existing EAC** for these MWh, the GC becomes _the_ sole environmental-attribute instrument for that electricity. All claims—Scope 2 disclosures, 24/7 matching, carbon-free power tariffs—flow from the retirement of that GC.

***

**What if the local EAC programme expands later?**

If the grid operator or regulator someday starts issuing conventional EACs for these carbon-free sources, the pathway simply migrates to **EnergyTag Configuration #1**:

1. The local registry mints the new EACs.
2. The Granular Registry converts (or “fractionalises”) them into hourly GCs at issuance.
3. The underlying EACs are cancelled, keeping a single chain of custody.

No certificates are duplicated and market participants keep the same hourly-level data they already rely on.

***

**Key safeguards**

* **Single source of truth** – Only the Granular Registry can issue certificates for the covered asset until an official EAC scheme is in place.
* **Independent meter data** – Hourly generation is verified via ISO settlement feeds or a qualified reporting entity.
* **Full EnergyTag compliance** – All roles (Issuer, Registrar, Measurement Body, Account Holders) follow the EnergyTag Standard, maintaining auditability and interoperability with other GC systems.

***

Whether a plant is renewable **or** simply carbon-free, the Granular Registry can provide the complete certificate lifecycle—issuance, transfer, retirement—needed for credible 24/7 and Scope 2 claims, even when the local market has no traditional EAC mechanism in place.

## **Can these stand‑alone GCs be used under the GHG Protocol’s Scope 2&#x20;**_**market‑based**_**&#x20;method?**

**Yes – provided the GC scheme meets the eight Scope 2 Quality Criteria.**\
A Granular Certificate that follows the EnergyTag Standard already meets those criteria even without an underlying REC/GO:

| GHG Protocol quality criterion | How a GC‑only scheme complies                                                             |
| ------------------------------ | ----------------------------------------------------------------------------------------- |
| Legal validity                 | Scheme documented; accepted by local regulator or contractual law.                        |
| Registry & tracking            | Independent, auditable registry prevents double issue/transfer/use.                       |
| Exclusive ownership            | Retirement cancels the GC permanently for a single beneficiary.                           |
| Auditable                      | Third‑party or registry audit of issuance, transfer, cancellation.                        |
| Vintage                        | Hour‑stamped; falls within the reporting year (or stricter if desired).                   |
| Geographic relevance           | Certificate generated in the same balancing area as consumption (or per programme rules). |
| Emission factor                | GC records technology‑specific or zero‑emission factor.                                   |
| Transparency                   | Scheme rules and retirement evidence available for assurance.                             |

Maintaining the retirement certificates and audit trail allows the reporting entity to enter these GCs in the Scope 2 market‑based column with a **zero** or specified emission factor, exactly as it would for standard RECs/Guarantees of Origin.

**Key takeaway:** Hour‑level GCs created under EnergyTag Configuration #2 _can_ be counted toward Scope 2 targets—even when no traditional REC or GO exists for that generator—so long as the scheme continues to meet the GHG Protocol quality criteria above.
