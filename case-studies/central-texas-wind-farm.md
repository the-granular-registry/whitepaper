# Central Texas Wind Farm

## Project Information

* Capacity: 200MW
* Dataset: Primary Substation Meter
* Year: 2023
* Location: Comanche County, Texas
* Grid Operator: ERCOT

## Data Overview

### Generation Meter Data

The graphs below show a typical generation profile.&#x20;

<figure><img src="../.gitbook/assets/image (84).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (85).png" alt=""><figcaption></figcaption></figure>

### Marginal Emissions

Locational Marginal Emissions (LME) data shows a tail with periods of low LME values. These are hours when renewables are on the margin due to curtailment.&#x20;

{% hint style="info" %}
[What are Power Grid Marginal Emissions?](../faq/what-are-power-grid-marginal-emissions.md)
{% endhint %}

<figure><img src="../.gitbook/assets/image (86).png" alt=""><figcaption><p>LME distribution with values less than 0 in Red</p></figcaption></figure>

Force LME values less than 0 to zero. This avoids positive emissions for energy generation.

{% content-ref url="../faq/how-can-renewable-generators-create-positive-emissions-negative-lmes.md" %}
[how-can-renewable-generators-create-positive-emissions-negative-lmes.md](../faq/how-can-renewable-generators-create-positive-emissions-negative-lmes.md)
{% endcontent-ref %}

<figure><img src="../.gitbook/assets/image (87).png" alt=""><figcaption><p>Adjusted LME Values</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (88).png" alt=""><figcaption><p>LME vs. Time</p></figcaption></figure>

## Impact Assessment

When assigning avoided emissions to energy generation, periods of high generation and low carbon impact become clear. This is further shown in the correlation scatter plot

<figure><img src="../.gitbook/assets/image (98).png" alt=""><figcaption><p>Plot showing the variation in avoided emissions with generation</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (99).png" alt=""><figcaption></figcaption></figure>

## PEC Issuance

To be an electricity attribute certificate, the number of PECs must match the number is issued RECs and be denominated in tons CO2e per MWh.

<figure><img src="../.gitbook/assets/image (100).png" alt=""><figcaption></figcaption></figure>

The issued PECs are backed by RECs, the additional timestamp, and avoided emissions.&#x20;

### Fractional RECs

Every hour of generation does not end in a round number of megawatt-hours for easy REC assignment. In these cases, the REC is split across multiple PECs. This has the following benefits:

* Ensures each REC\_ID equals one megawatt-hour.
* The avoided emissions calculation for each hour remains accurate.&#x20;
* Most PECs are backed by one REC representing one megawatt-hour of generation. Some PECs will be less and can be purchased by smaller buyers or battery operators.&#x20;

<figure><img src="../.gitbook/assets/image (91).png" alt=""><figcaption><p>The REC split, highlighted in yellow, shows how PECs can ensure accurate hourly carbon impact.</p></figcaption></figure>

### Variations in PEC Carbon Impact

The resulting distribution of avoided emissions across the issued PECs shows Low, Mid, and High-impact PECs.&#x20;

* PECs can be valued according to carbon impact.
* Buyers can avoid low-impact PECs to enhance claims.&#x20;

<figure><img src="../.gitbook/assets/image (102).png" alt=""><figcaption></figcaption></figure>

## Conclusion

This case study describes how the addition of the hourly timestamp and marginal avoided emissions can enhance REC procurement.&#x20;
