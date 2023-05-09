# Technical Specifications for RMI Plastics PCF Data Exchange
## Updated 9 May 2023

-------------------------
## 1. Introduction
This document contains the necessary technical foundation for a plastics data model extension to the [Pathfinder Network,](https://wbcsd.github.io/data-exchange-protocol/v2/#pathfinder-network) developed by [RMI.](https://rmi.org/) For full documentation of the Pathfinder Network, refer to the link above.

The goal of this document is to enable the interoperable exchange of plastics Product Carbon Footprints, in accordance with the RMI's [Plastic Modling Accounting Guidance], across conforming host systems.

## 2. Terminology
For a full list of terminology, please refer to the [Terminology](https://wbcsd.github.io/data-exchange-protocol/v2/#terminology) section of the Pathfinder techical specification.

### Credits
  Avoided emissions outside the fixed systems boundary. Credits are required to be seperately reported from the total emissions intensity.
  
## 3. Conformance
For conformance with the Pathfinder Network, please refer to the [Conformance](https://wbcsd.github.io/data-exchange-protocol/v2/#conformance) section of the Pathfinder technical specification.

## 4. Data Model Extension
This section specifices a [data model extension](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-datamodelextension) for plastics product footprints conforming with the [Pathfinder Network.](https://wbcsd.github.io/data-exchange-protocol/v2/#pathfinder-network)

The data model extension contains additional information for plastics products, beyond what is specified in the [Pathfinder Data Model.](https://wbcsd.github.io/data-exchange-protocol/v2/#data-model)

The data model extension consists of the following:

### Data Type 4.14. Credits
See [Terminology](https://github.com/RMI/plastics-guidance/blob/main/technical_specification.md#credits).

#### 4.14.1. Properties
The properties of a Credits object are listed in the table below.

| **Property**                | **Type** | **Req** | **Specification**                                                |
|-----------------------------|----------|---------|------------------------------------------------------------------|
| creditEmissions:<br>Decimal | Number   | M       | GHG Emissions for a credit, <br>corresponding to processNamesSet |
| creditName                  | String   | M       | The name of the credit                                           |
| creditDescription           | String   | O       | A description of a given credit                                  |

### Data Type 4.15. CreditsSet
A set of Credits values.

#### Data Type 4.15.1 Properties
As an array of Credits, with each object conforming to the JSON representation of Credits.
