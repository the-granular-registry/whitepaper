# DG Solar + Battery Storage Project

## Project Information

* Power Capacity @POI (MW):&#x20;
* BESS Duration (HR):&#x20;
* Dataset:&#x20;
* Year: 2023
* Location:&#x20;
* ISO: PJM

<figure><img src="../.gitbook/assets/image (104).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (103).png" alt=""><figcaption></figcaption></figure>

## Data Overview

### Metered Electricity Overview

The graphs below shows the metered energy for this battery. The sample data was extended to cover the entire year. &#x20;

<figure><img src="../.gitbook/assets/image (59).png" alt=""><figcaption></figcaption></figure>

### Marginal Emissions

Locational Marginal Emissions (LME) data shows a bimodal distribution with periods of low LME values. These are hours when renewables are on the margin due to curtailment.&#x20;

<figure><img src="../.gitbook/assets/image (60).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (61).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (62).png" alt=""><figcaption></figcaption></figure>

By combining the generation and emissions datasets, we can calculate hourly avoided emissions.&#x20;



<figure><img src="../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

## Charging Analytics

The battery operator must neutralize the induced emissions and power consumption from the grid. Below is the sum of energy and emissions for each hour.&#x20;

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

### Power Emissions Proof (PEP)

Once the operator retires the required PECs to match hourly consumption and induced carbon emissions, a Power Emissions Proof (PEP) is created. This PEP is embedded in all issued PECs for this battery asset during this audit period.&#x20;

## Discharge Analytics

Now that the charging impact has been neutralized and documented, the methodology is applied to the discharge activity to issue PECs.

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>

### REC Split

Since each hour does not end with an even number of energy produced, PECs are issued with split REC\_IDs for accuracy.&#x20;

The charts below show how the split REC\_ID across two hours sums to 1 MWh.

<figure><img src="../.gitbook/assets/image (94).png" alt=""><figcaption><p>Showing fractional REC at the end of hour 17</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (95).png" alt=""><figcaption><p>Showing fractional REC at the start of hour 18. Together they sum to 1 MWh.</p></figcaption></figure>

## PEC Issuance

Since all charging activity is neutralized along with a published PEP, all discharged energy can be used to create PECs. This process is the same as renewable generation except there is no directly issued RECs.&#x20;

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

## Conclusion

For carbon arbitrage, the registry shifts activity from low-demand hours and low-impact PECs to periods of high-demand hours and high-impact PECs. The results is a clear way for a battery operator to monetize this activity along with a direct use of PECs in corporate carbon accounting.&#x20;
