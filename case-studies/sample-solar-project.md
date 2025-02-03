# Sample Solar Project

## Project Information

* Capacity: 100MW
* Dataset: MERRA-2
* Year: 2022
* Location: Amarillo, Texas
* System Loss: 10%
* Tracking: Single axis (azimuth)
* Tilt: 35 deg
* Azimuth: 180 deg

{% hint style="info" %}
Sample dataset generated using [Renewables.ninja](https://www.renewables.ninja/)
{% endhint %}

## Data Overview

### Solar Generation

The graphs below show a typical generation profile for a solar plant.&#x20;

<figure><img src="../.gitbook/assets/image (50).png" alt=""><figcaption><p>Time series of Hourly Solar Generation - One year</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (52).png" alt=""><figcaption><p>Time series of Hourly Solar Generation - Few weeks</p></figcaption></figure>

### Marginal Emissions

Locational Marginal Emissions (LME) data shows a bimodal distribution with periods of low LME values. These are hours when renewables are on the margin due to curtailment.&#x20;

{% hint style="info" %}
[What are Power Grid Marginal Emissions?](../faq/what-are-power-grid-marginal-emissions.md)
{% endhint %}

<figure><img src="../.gitbook/assets/image (53).png" alt=""><figcaption><p>Timeseries of Hourly LME Values</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (54).png" alt=""><figcaption><p>Distribution of Hourly LME Values</p></figcaption></figure>

## Analytics

By combining the generation and emissions datasets, we can calculate hourly avoided emissions.&#x20;

<figure><img src="../.gitbook/assets/image (55).png" alt=""><figcaption></figcaption></figure>

The distribution of hourly avoided emissions varies widely with a very flat distribution. It would be interesting to create certificates at diff

<figure><img src="../.gitbook/assets/image (56).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (57).png" alt=""><figcaption></figcaption></figure>

## PEC Issuance

To be an electricity attribute certificate, the number of PECs must match the number is issued RECs and be denominated in tonnes CO2e per MWh.

### Option 1: The Proportional Allocation Method

This method allocates avoided emissions across the issued RECs proportional to the hourly avoided emissions.&#x20;

<figure><img src="../.gitbook/assets/image (58).png" alt=""><figcaption></figcaption></figure>

The resulting distribution of avoided emissions across the issued RECs now matches the hourly distribution.&#x20;
