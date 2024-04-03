# Technical Specifications for RMI Plastics PCF Data Exchange
## Updated 23 May 2023

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
1. HighestIntensityPlastic
2. LowestIntensityPlastic
3. MethaneLeakIntensity
4. VirginPlastic
5. MechanicalPcr
6. ChemicalPcr
7. BioBasedPlastic
8. AltBioBasedPlastic
9. CcuBasedPlastic
10. PemReEmissionsScore
11. RecyclabilityScore
12. EndOfLifeIntensity
13. EndofLifePrimaryDataShare
14. UseIntensity
15. Credits

### 4.1. Data Type: HighestIntensityPlastic
HighestIntensityPlastic refers to the resin type that makes up the highest fraction of fossil ghg emissions of the final product.
Valid values are:
**virginPlasti**
**mechanicalPcr**
**chemicalPcr**
**bioBasedPlastic**
**altBioBasedPlastic**
**ccuBasedPlastic**

#### 4.1.1. JSON Representation
Each HighestIntenistyPlastic MUST be encoded as a JSON String.

### 4.2. Data Type: LowestIntensityPlastic
LowestIntensityPlastic refers to the resin type that makes up the lowest fraction of fossil ghg emissions of the final product.
Valid values are:
**virginPlastic**
**mechanicalPcr**
**chemicalPcr**
**bioBasedPlastic**
**altBioBasedPlastic**
**ccuBasedPlastic**

#### 4.2.1. JSON Representation
Each LowestIntenistyPlastic MUST be encoded as a JSON String.

### 4.3. Data Type: MethaneLeakIntensity

#### 4.3.1. JSON Representation
Each MethaneLeakIntensity MUST be encoded as a JSON number.

### 4.4. Data Type: ResinDetail

#### 4.4.1. Properties
The properties of a ResinDetail object are listed in the table below.

| **Property**                        | **Type** | **Req** | **Specification**                                                     |
|-------------------------------------|----------|---------|-----------------------------------------------------------------------|
| massPercentage:<br>Percent          | Number   | M       | The mass percentage of the final product for a particular resin type  |
| emissionsIntensity                  | Number   | M       | The emissions intensity for a particular resin type                   |
| primaryDataShare:<br>Percent        | Number   | M       | The primary data share percentage for a particular resin type         |
| methaneLeakIntensity                | Number   | M       | The methane leak instensity for a particular resin type               |

#### 4.4.2. JSON Representation
Each ResinDetail MUST be encoded as a JSON object

### 4.5. Data Type RenewableEnergyRating
RenewableEnergyRating is defined in Appendix B of RMI's Plastics Emissions Reporting Guidance.

#### 4.5.1. JSON Representation
Each RenewableEnergyRating MUST be encoded as a JSON String.

### 4.6. Data Type RecyclabilityRating
RecyclabilityRating is defined in Appendix B of RMI's Plastics Emissions Reporting Guidance.

#### 4.6.1. JSON Representation
Each RecyclabilityRating MUST be encoded as a JSON String.

### 4.7. Data Type EndOfLifeIntensity
Emissions instensity of a product's final end-of-life disposal method, as defined by Appendix B of RMI's Plastics Emissions Reporting Guidance.

#### 4.7.1. JSON Representation
Each EndOfLifeIntensity MUST be encoded as a JSON number.

### 4.8. Data Type EndOfLifePrimaryDataShare
Primary Data Share of a products end-of-life disposal method, as defined by Appendix B of RMI's Plastics Emissions Reporting Guidance.

#### 4.8.1. JSON Representation
Each EndOfLifePrimaryDataShare MUST be encoded as a JSON number.

### 4.9. Data Type UseIntensity
A metric intended to provide a view of the intended service life of a product, as defined by Appendix B of RMI's Plastics Emissions Reporting Guidance.

#### 4.9.1. JSON Representation
Each UseIntensity MUST be encoded as a JSON number.

### Data Type 4.10. Credits
See [Terminology](https://github.com/RMI/plastics-guidance/blob/main/technical_specification.md#credits).

#### 4.10.1. Properties
The properties of a Credits object are listed in the table below.

| **Property**                | **Type** | **Req** | **Specification**                                                |
|-----------------------------|----------|---------|------------------------------------------------------------------|
| creditEmissions:<br>Decimal | Number   | M       | GHG Emissions for a credit, <br>corresponding to processNamesSet |
| creditName                  | String   | M       | The name of the credit                                           |
| creditDescription           | String   | O       | A description of a given credit                                  |

### Data Type 4.11. CreditsSet
A set of Credits values.

#### Data Type 4.11.1 Properties
As an array of Credits, with each object conforming to the JSON representation of Credits.
