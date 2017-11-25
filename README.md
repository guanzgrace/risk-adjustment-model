# Risk-Adjustment-Model

## Background

The primary goal of this project is to make Centers for Medicare & Medicaid Services' (CMS) Medical Loss Ratio (MLR) data regarding the Affordable Care Act (ACA) more easily accessible to the public. We achieve this goal by parsing each individual insurer's reported data and combining that into a large CSV output. 

A secondary goal of this project is to perform a prelimary statistical analysis of the data. Additionally, we attempt to duplicate CMS statistics on this ACA data. We search for statistical outliers and any correlations between premiums and transfers or spending and transfers, and we calculate year to year per person risk adjustment payment.

This project was undertaken as part of ORF 375: Independent Research Project in Fall 2017, under the guidance of [Professor Mark Braverman](https://www.cs.princeton.edu/~mbraverm/). With thanks to [Jeremie Lumbroso](https://www.cs.princeton.edu/people/profile/lumbroso) for helping scrape CMS data from their website.

## Breakdown of Repository

Subfolders represent different facets of the risk transfer formula that we attempted to analyze, as are delineated below.

### 0_Excel-Analysis:

Medical_Loss_Ratio_Data_Analysis is a Python script that does a basic statistical cleaning and analysis of the Excel "Public Use Files" provided online.

We found that the Excel data is not the most accurate because each state's transfers do not add up to 0. Additionally, the Excel data only contained values for 533 companies. The PDF that we cross-checked the results with is more accurate because each state's transfers do sum to 0. The PDF file contained values for 833 companies.

### 1_PDF-Data-ETL: 

Parse_Text_File is a Python script to create CSV files from the accurate PDF data.

Strip_PDF_File is a Python script that removes the '$', ',' and '()' from the PDF data to create data that that is more easily manipulated and comparable.

### 2_PDF-Data-Analysis:

Matching_Datasets is a Python script that attempts to compare Excel data with the data from the PDF file. 

Here, we discover that the PDF file contains values for 833 companies whereas the Excel has data for only 533 companies. Additionally, only some of the companies match up. Because of this discrepancy, we decided to rebuild the PDF from scratch, from the [individual insurer reports that can be found on the CMS website](https://www.cms.gov/apps/mlr/mlr-search.aspx).

### 3_Insurer-Data-ETL:

Read_Insurer_File_2015 is a Python script that reads in the data from an insurer report and can output the HIOS ID, name of the company, state in which the company operates, member months (individual and small group), reinsurance, and risk adjustment (individual and small group).

### 4_Insurer-Data-Analysis:

The goal here is to look at statistical outliers, any correlations between premiums and transfers or spending and transfers, and year to year per person risk adjustment payment.

### 9_Misc folder:

- The AV-Formula folder contains a Python attempt to implement the AV Calculation Macros. While we could not match the results through Python 100%, this is significant in attempting to democratize the AV Calculation to less than a black box.

- The Risk-Transfer-Formula folder contains a Python attempt at implementation of the risk transfer formula in a trial to reverse engineer the formula. This is currently incomplete due to the lack of transparency in calculating basic facets of the transfer formula such as PLRS and Geographic Cost Factor (GCF).

- MMRR2014_004_03_a02.pdf, MMRR2014_004_03_a03.pdf, and MMRR2014_004_03_a04.pdf are government whitepapers discussing the derivation of the Plan Liability Risk Score (PLRS) calculation and the HHS-HCC (Department of Health and Human Services, Hierarchical Condition Categories) risk transfer payment calculation.

## Directions for Future Work

I would eventually like to fully implement the AV Calculations and/or the full Risk Transfer Formula implementation in Python and confirm that the outputs are the same as those calculated by the Excel spreadsheet given by CMS. 

## Milestones Timeline

 Date | Goals | Status 
 --- | --- | ---
11/19/17 | Data cleaning to relevant CSV files | **Completed**
. | Github cleaning | **Completed**
. | Documentation | **Completed**
11/26/17 | Data cleaning II | **Completed**
12/3/17 | Parse individual insurer data | .
. | Introductory statistical analysis | .
. | A few samples of calculated data | .
. | Year to year per person payment | .
12/10/17 | Redo CMS statistics, Correlation analysis | .
12/17/17 | IW talk | .
. | Project site | .
1/XX/2018 | Paper complete | .
. | Poster Presentation complete | .
