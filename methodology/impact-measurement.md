# Impact Measurement

## **Data Collection**

* **Project Metadata:** such as nameplate capacity, substation ID, project location, etc.
* **Meter Data:** showing charging and discharging activity at the hourly or sub-hourly granularity. Ensure all metering equipment is calibrated regularly for accuracy. Maintain records of calibration.
* **Downtime:** Scheduled and unscheduled downtime.&#x20;
* **Operational Mode:** Document the operational mode of the battery (e.g., peak shaving, load shifting, emergency backup, renewable integration).
* **State of Charge:** Regularly record the state of charge (SoC) of the battery to understand the usage patterns and efficiency.
* **Data Accessibility for Verification:** Provide access to relevant data to authorized parties, including auditors and verifiers, while maintaining confidentiality where necessary.
* **Data Storage and Backup:** Implement secure and reliable data storage solutions with appropriate backup mechanisms to prevent data loss.
* **Remote Monitoring and IoT Integration:** Where feasible, integrate Internet of Things (IoT) technology for real-time monitoring and data transmission.
* **Compliance with Data Protection Regulations: A**dhere to relevant data protection and privacy regulations in the jurisdiction of operation, ensuring that all data collection and transmission is compliant with legal requirements.

## **Emission Factor Determination**

The following hierarchy is established to determine the most appropriate emission factor for a given time and location. This hierarchy moves from broader to more granular data sources:

| TYPE                                          | DESCRIPTION                                                                                                                                                                 | SOURCE                                                                                                          |
| --------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| **Hourly Nodal Marginal Emissions - Public**  | Provide the most accurate reflection of the impact of emissions at specific nodes within the grid.                                                                          | Grid Operator                                                                                                   |
| **Hourly Nodal Marginal Emissions - Private** | Proprietary models                                                                                                                                                          | REsurety                                                                                                        |
| **Hourly Zonal Marginal Emissions - Public**  | Reflect the specific emissions associated with electricity generation in a defined grid zone.                                                                               | Grid Operator                                                                                                   |
| **Hourly Zonal Marginal Emissions - Private** | Proprietary models                                                                                                                                                          | WattTime                                                                                                        |
| **Hourly Average Emissions**                  | Utilize average grid emission factors as the baseline data. These are generally available and provide a broad overview of emissions associated with electricity generation. | National grid operator databases, environmental agencies, or global emission factor databases (e.g., IEA, EPA). |
