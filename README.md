# Risk-Adjustment-Model

## Background

The primary goal of this project is to make Centers for Medicare & Medicaid Services' (CMS) Medical Loss Ratio (MLR) data regarding the Affordable Care Act (ACA) more easily accessible to the public. A secondary goal of this project is to do a prelimary analysis of the data and attempt to duplicate CMS statistics on this ACA data. We search for statistical outliers and any correlations between premiums and transfers or spending and transfers, and we calculate year to year per person risk adjustment payment.

This project was undertaken as part of ORF 375: Independent Research Project in Fall 2017, under the guidance of Professor Mark Braverman.

## Breakdown of Repository

Subfolders represent different facets of the risk transfer formula that we attempted to analyze, as are delineated below.

### 0_Data-ETL folder: 

The 0_Data-ETL folder contains a Python data analysis of medical loss ratio reported data through Excel. We found that Excel data is not the most accurate, and each state's transfers do not add up to 0. However, the PDF that we cross-checked the results with is more accurate and each state's transfers do sum to 0. Here, we use a Python script to create CSV files from the accurate PDF data begin to analyze that data.

### 1_Data-Analysis folder:

MLR-Analysis folder: 

- The MLR-Analysis folder contains a Python data analysis of medical loss ratio reported data through Excel. We found that Excel data is not the most accurate, and each state's transfers do not add up to 0. However, the PDF that we cross-checked the results with is more accurate and each state's transfers do sum to 0, so we analyze that in the 0_Data-ETL folder.

Updated-Analysis folder: 

- The Updated-Analysis folder has the core of what my independent work will show as results. It takes data from the PDFs from 0_Data-ETL and from the Excel spreadsheets of MLR-Analysis and ties them together to look at statistical outliers, any correlations between premiums and transfers or spending and transfers, and year to year per person risk adjustment payment.

### 9_Misc folder:

AV-Formula folder: 

- The AV-Formula folder contains a Python attempt to implement the AV Calculation Macros. While we could not match the results through Python 100%, this is significant in attempting to democratize the AV Calculation to less than a black box.

Risk-Transfer-Formula folder: 

- The Risk-Transfer-Formula folder contains a Python attempt at implementation of the risk transfer formula in a trial to reverse engineer the formula. This is currently incomplete due to the lack of transparency in calculating basic facets of the transfer formula such as PLRS and Geographic Cost Factor (GCF).

Whitepapers folder: 

- MMRR2014_004_03_a02.pdf, MMRR2014_004_03_a03.pdf, and MMRR2014_004_03_a04.pdf are government whitepapers discussing the derivation of the Plan Liability Risk Score (PLRS) calculation and the HHS-HCC (Department of Health and Human Services, Hierarchical Condition Categories) risk transfer payment calculation.

## Directions for Future Work

I would eventually like to fully implement the AV Calculations and/or the full Risk Transfer Formula implementation in Python and confirm that the outputs are the same as those calculated by the Excel spreadsheet given by CMS. Additionally, I would like to further analyze the data in the 0_Data-ETL folder.

## Milestones Timeline

 Date | Goals | Status 
 --- | --- | ---
11/19/17 | Data cleaning to relevant CSV files | **Completed**
. | Github cleaning | **Completed**
. | Documentation | **Completed**
11/26/17 | Data cleaning II | **In Progress**
. | A few samples of calculated data | **In Progress**
12/3/17 | Statistical Analysis | .
. | Year to year per person payment | .
12/10/17 | Redo CMS statistics, Correlation analysis | .
12/17/17 | IW talk | .
. | Project site | .
1/XX/2018 | Paper complete | .
. | Poster Presentation complete | .
