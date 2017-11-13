# Risk-Adjustment-Model

### About

The goal of this project (ORF 375 - Independent Research Project; Fall 2017; under the guidance of Professor Mark Braverman) is to make Centers for Medicare and Medicaid Services' (CMS) medical loss ratio data regarding the Affordable Care Act (ACA) more easily accessible to the public. A secondary goal of this project is to do a prelimary analysis of the data and attempt to duplicate CMS statistics on this ACA data. We search for statistical outliers, any correlations between premiums and transfers or spending and transfers, and we calculate year to year per person risk adjustment payment.

### Breakdown of Repository

In the current folder: 
- MMRR2014_004_03_a02.pdf, MMRR2014_004_03_a03.pdf, and MMRR2014_004_03_a04.pdf are government whitepapers discussing the derivation of the Plan Liability Risk Score (PLRS) calculation and the risk transfer payment calculation.
- Subfolders represent different facets of the risk transfer formula that we attempted to analyze, as are delineated below.

0_Clean_Data folder: 
- The 0_Clean_Data folder contains a Python data analysis of medical loss ratio reported data through Excel. We found that Excel data is not the most accurate, and each state's transfers do not add up to 0. However, the PDF that we cross-checked the results with is more accurate and each state's transfers do sum to 0. Here, we use a Python script to create CSV files from the accurate PDF data begin to analyze that data.

AV_Formula folder: 
- The AV_Formula folder contains a Python attempt to implement the AV Calculation Macros. While we could not match the results through Python 100%, this is significant in attempting to democratize the AV Calculation to less than a black box.

MLR_Analysis folder: 
- The MLR_Analysis folder contains a Python data analysis of medical loss ratio reported data through Excel. We found that Excel data is not the most accurate, and each state's transfers do not add up to 0. However, the PDF that we cross-checked the results with is more accurate and each state's transfers do sum to 0.

Risk_Transfer_Formula folder: 
- The Risk_Transfer_Formula folder contains a Python attempt at implementation of the risk transfer formula in a trial to reverse engineer the formula. This is currently incomplete due to the lack of transparency in calculating basic facets of the transfer formula such as PLRS and Geographic Cost Factor (GCF).

### Directions for Future Work

I would eventually like to fully implement the AV Calculations and/or the full Risk Transfer Formula implementation in Python and confirm that the outputs are the same as those calculated by the Excel spreadsheet given by CMS. Additionally, I would like to analyze the data in the 0_Clean_Data folder further to find more outliers and why they are so, should they exist.