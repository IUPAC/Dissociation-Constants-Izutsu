# Izutsu Digitized pKa Dataset

### Dataset version: v1.0

## Description

This repository includes pKa data measured in select dipolar aprotic solvents digitized and curated from reference data published by IUPAC. The data was originally compiled by Kosuke Izutsu in the IUPAC reference work on acid-base dissociation constants in dipolar aprotic solvents.

With permission from the copyright holder, the International Union of Pure and Applied Chemistry (IUPAC), the reference data was digitized, checked for accuracy, and curated for accessibility, interoperability, and reusability between 14 April 2022 to 1 October 2025 by Jonathan W. Zheng. 

Corrections to some of the data (accounting for inconsistent anchor compounds or "standards") were suggested by Ivo Leito, and Sofja Tshepelevitsh.

## Contributors:

Jonathan W. Zheng

Green Group, Department of Chemical Engineering

Massachusetts Institute of Technology

[jonzheng@mit.edu](mailto:jonzheng@mit.edu)

Ivo Leito

Institute of Chemistry, University of Tartu

Tartu, Estonia

Sofja Tshepelevitsh

Institute of Chemistry, University of Tartu

Tartu, Estonia

William H. Green

Department of Chemical Engineering

Massachusetts Institute of Technology

## License

Copyright &copy; 2026 International Union of Pure and Applied Chemistry.

This material is available for reuse under a [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) license with the following attribution: Reproduced by permission of International Union of Pure and Applied Chemistry.

## Recommended Citation

Zheng, Jonathan W.; Leito, Ivo; Tshepelevitsh, Sofja; Green, William H. (2025) Izutsu Digitized pKa Dataset, v1.0. Copyright &copy; 2026 International Union of Pure and Applied Chemistry (IUPAC), The dataset is reproduced by permission of IUPAC and is licensed under a [CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/). 

References should also include the source, print version of the data:
Izutsu, K. (1990). Acid-Base Dissociation Constants in Dipolar Aprotic Solvents. Blackwell Science.

As references are provided for each entry, a reference to the source of an experimental measurement may also be provided.

This GitHub repository serves as a working copy for the dataset.

## Data & File Overview

**File List**

- `izutsu_data_v1-0.csv` : pKa dataset in dipolar aprotic solvents.
- `code_translations /`  : directory containing optional supporting .csv files that translate from shorthand code to full text labels
  - `references.csv` : translation for bibliographical references 
  - `remarks.csv` : translation for supplementary notes on an entry
  - `standards.csv` : translation for anchoring standards of this entry, e.g. definition of the acidity scale

The dataset includes pKa values measured in the following dipolar aprotic solvents:

- **NM** (Nitromethane)
- **NMPy** (N-Methyl-2-pyrrolidone)
- **DMA** (N,N-Dimethylacetamide)
- **MiBK** (Methyl isobutyl ketone)
- **Sulfolane** (Tetramethylene sulfone)
- **HMPA** (Hexamethylphosphoramide)

Please email [jonzheng@mit.edu](mailto:jonzheng@mit.edu) or post an issue on the GitHub page if any errors are discovered.

## Methodological Information

This dataset was obtained by digitizing reference data from IUPAC publications on acid-base dissociation constants in dipolar aprotic solvents, originally compiled by Kosuke Izutsu. The data was processed to extract information to a convenient form for computational use, and chemical names were translated to SMILES strings and InChI identifiers. The final format was then manually and programmatically checked.

Open-source software used to aid in the data processing: `rdkit`, `pandas`, `pubchempy`, `py2opsin`, and `cirpy` for chemical name translation.

## Quality assurance

Before publication, several programmed checks were performed on the dataset.

- Checking range and distribution of pKa values in various solvents.
- Checking ionic strength and water content values for feasibility.
- Manual review of entries to check the validity of the dissociation type (e.g., pKaH vs. pKa).
- Standardizing formats (e.g., formatting "pk" as "pKa", standardizing pKa type labels, etc.).
- Verification of SMILES and InChI translations.

## Data-specific information

### **Columns**:

- `Name`: Chemical name of the compound.
- `SMILES`: SMILES string for the chemical species.
- `InChI`: InChI string for the chemical species.
- `Solvent`: The dipolar aprotic solvent in which the pKa was measured (NM, NMPy, DMA, MiBK, Sulfolane, or HMPA).
- `Proton Transfer Type`: Type of proton transfer reaction (proton gain, proton loss, indicator, or autoprotolysis const.).
- `pKa Type`: Original pKa type designation from the source (e.g. pK1, pK2).
- `pKa Type (Standardized)`: Standardized pKa type designation taking into account the degree of proton loss or gain with the proton transfer type (e.g., pKa1, pKa2, pKaH1, pKs).
- `pKa Value (Corrected)`: The pKa value, corrected if necessary for standardization.
- `pKa Value`: The original pKa value as reported.
- `pKa Value Uncertainty`: Uncertainty in the pKa value, if reported.
- `Temperature`: Temperature (deg. C) at which the measurement was made.
- `Temperature Uncertainty`: Uncertainty in the temperature, if reported.
- `Method`: Method used to determine the pKa value (e.g., Potentiometric, Spectrophotometric, Conductometric, Voltammetric).
- `Method (code)`: Abbreviated code for the method.
- `Ionic Strength`: Ionic strength of the solution, if reported.
- `Water Content`: Water content in the solvent, if reported.
- `Homoconjugation and Other Reactions`: Information about homoconjugation or other reactions, if applicable.
- `Indicator type`: Type of indicator used, if applicable.
- `Remarks`: Comments for this specific datapoint.
- `Remarks (code)`: Coded remarks reference.
- `Additional info`: Additional information about the digitization process corresponding to this datapoint.
- `Reference`: Full reference citation for the original source of this datapoint.
- `Reference (code)`: Abbreviated reference code.
- `Standard`: Information about the standard ("anchor") used for calibration.
- `Standard (code)`: Code for the standard classification (e.g., Group A).

### **Rows**:

There are 839 rows corresponding to 513 unique molecules in the dataset (unique on the basis of InChI strings).

### **Solvent Distribution**:

- NM (Nitromethane): 449 entries
- NMPy (N-Methyl-2-pyrrolidone): 204 entries
- DMA (N,N-Dimethylacetamide): 74 entries
- MiBK (Methyl isobutyl ketone): 49 entries
- Sulfolane (Tetramethylene sulfone): 32 entries
- HMPA (Hexamethylphosphoramide): 31 entries

Specialized abbreviations used: 

- `pK`: dissociation constant of any type, e.g. a pKa, pKaH, etc.
- `pKa`: acid dissociation constant
- `pKa1, pKa2, pKa3, ...`: first, second, third (etc.) acid dissociation constants
- `pKaH`: acid dissociation constant of a base's conjugate acid
- `pKs`: autoprotolysis constant of the solvent
- `I`: ionic strength, equal to 1/2 * Sum(ci * zi^2)
- `m`: concentration in mole/1000g of water
- `c`: concentration in mole/L
- `T`: temperature (usually in deg. C)
- `DMA`: N,N-Dimethylacetamide
- `HMPA`: Hexamethylphosphoramide
- `MiBK`: Methyl isobutyl ketone
- `NM`: Nitromethane
- `NMPy`: N-Methyl-2-pyrrolidone

## Acknowledgement

People involved with sample collection, processing, analysis and/or submission: 

- Green Group, Department of Chemical Engineering, MIT
- Institute of Chemistry, University of Tartu
- IUPAC volunteers
- Kosuke Izutsu (original compiler of the reference data)

## Dataset Metadata

The following table is necessary for this dataset to be indexed by 
[Google Dataset Search](https://datasetsearch.research.google.com).


| property    | value                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| name        | `Izutsu Digitized pKa Dataset`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| creator     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| url         | `https://github.com/IUPAC/Dissociation-Constants-Izutsu`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| description | `This repository includes pKa data measured in select dipolar aprotic solvents digitized and curated from reference data published by IUPAC. The data was originally compiled by Kosuke Izutsu in the IUPAC reference work on acid-base dissociation constants in dipolar aprotic solvents. With permission from the copyright holder, the International Union of Pure and Applied Chemistry (IUPAC), the reference data was digitized, checked for accuracy, and curated for accessibility, interoperability, and reusability between 14 April 2022 to 1 October 2025 by Jonathan W. Zheng. Additional corrections are included based on calculations from Ivo Leito and Sofja Tshepelevitsh.` |
| provider    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| license     | `https://creativecommons.org/licenses/by-nc/4.0/`                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |


