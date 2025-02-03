# Storage

## **Standardized Reporting Format**

Develop a standardized reporting format that details all relevant information, including operational data of the battery, emission reductions achieved, and methodologies used for calculations.

PECs have unique identification data coded into them, and supplementary data is accessible through the registry. This includes:

* Audit Period
* Identity, location (GPS reference), and country of provenance
* Type and capacity of the production facility
* Whether and to what extent the installation has benefited from outside support
* Date when the installation became operational

## **Calculating Net Emissions**

1. **Data Quality Assessment:** Conduct an initial assessment to determine the availability and reliability of project meter data and emission factor data. Check for missing data.
2. **Temporal Alignment:** Ensure hourly alignment between the emission factors used and the actual operational data of the project.
3. **Calculate Induced Emissions:** Emissions from Charging = Total Electricity Used for Charging × EF during Charging Period
4. **Calculate Avoided Emissions:** Emissions Avoided by Discharging = Total Electricity Discharged × EF during Discharging Period
5. **Calculate Net Emissions:** Subtract Avoided Emissions from Induced Emissions.&#x20;

<figure><img src="../../.gitbook/assets/image (67).png" alt=""><figcaption></figcaption></figure>

$$
Avoided Emissions = Hourly Discharge * Hourly EF
$$

$$
Net Emissions Impact = Charging Induced Emissions - Discharging Avoided Emissions
$$



