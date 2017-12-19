# Risk-Adjustment-Model

## Table of Contents
1. [Background](#a1)
2. [Breakdown of Repository](#a2)

    1. [Excel Analysis](#b0)
    2. [PDF Data ETL](#b1)
    3. [PDF Data Analysis](#b2)
    4. [Insurer Data ETL](#b3)
    5. [Insurer Data Analysis](#b4)
    6. [Miscellaneous](#b9)
3. [Directions for Future Work](#a3)
4. [Milestones](#a4)

<a name="a1"></a>
## 1. Background

The primary goal of this project is to make Centers for Medicare & Medicaid Services' (CMS) Medical Loss Ratio (MLR) data regarding the Affordable Care Act (ACA) more easily accessible to the public. We achieve this goal by parsing each individual insurer's reported data and combining that into a large CSV output. 

A secondary goal of this project is to perform a prelimary statistical analysis of the data. Additionally, we attempt to duplicate CMS statistics on this ACA data. We search for statistical outliers and any correlations between premiums and transfers or spending and transfers, and we calculate year to year per person risk adjustment payment.

This project was undertaken as part of ORF 375: Independent Research Project in Fall 2017, under the guidance of [Professor Mark Braverman](https://www.cs.princeton.edu/~mbraverm/). With thanks to [Jeremie Lumbroso](https://www.cs.princeton.edu/people/profile/lumbroso) for helping scrape CMS data from their website.

<a name="a2"></a>
## 2. Breakdown of Repository

Subfolders represent different facets of the risk transfer formula that we attempted to analyze, as are delineated below.

<a name="b0"></a>
### i. 1_Excel-Analysis:

Medical_Loss_Ratio_Data_Analysis is a Python script that does a basic statistical cleaning and analysis of the Excel "Public Use Files" provided online.

We found that the Excel data is not the most accurate because each state's transfers do not add up to 0. Additionally, the Excel data only contained values for 533 companies. The PDF that we cross-checked the results with is more accurate because each state's transfers do sum to 0. The PDF file contained values for 833 companies.

<a name="b1"></a>
### ii. 2_PDF-Data-ETL: 

Parse_Text_File is a Python script to create CSV files from the accurate PDF data.

Strip_PDF_File is a Python script that removes the '$', ',' and '()' from the PDF data to create data that that is more easily manipulated and comparable.

<a name="b2"></a>
### iii. 3_PDF-Data-Analysis:

Matching_Datasets is a Python script that attempts to compare Excel data with the data from the PDF file. 

Here, we discover that the PDF file contains values for 833 companies whereas the Excel has data for only 533 companies. Additionally, only some of the companies match up. Because of this discrepancy, we decided to rebuild the PDF from scratch, from the [individual insurer reports that can be found on the CMS website](https://www.cms.gov/apps/mlr/mlr-search.aspx).

<a name="b3"></a>
### iv. 4_Insurer-Data-ETL:

Read_Insurer_File_2015 is a Python script that reads in the data from an insurer report and can output the HIOS ID, name of the company, state in which the company operates, member months (individual and small group), reinsurance, and risk adjustment (individual and small group). We expanded this to Read_Insurer_File_More_Data-FINAL, which is a Python script that scrapes every field from sheets 0, 1, and 2 from the Excel file.

<a name="b4"></a>
### v. 5_Insurer-Data-Analysis:

The goal here is to look at statistical outliers, any correlations between premiums and transfers or spending and transfers, and year to year per person risk adjustment payment. 

<a name="b9"></a>
### vi. 6_Misc folder:

- The AV-Formula folder contains a Python attempt to implement the AV Calculation Macros. While we could not match the results through Python 100%, this is significant in attempting to democratize the AV Calculation to less than a black box.

- The Risk-Transfer-Formula folder contains a Python attempt at implementation of the risk transfer formula in a trial to reverse engineer the formula. This is currently incomplete due to the lack of transparency in calculating basic facets of the transfer formula such as PLRS and Geographic Cost Factor (GCF).

- MMRR2014_004_03_a02.pdf, MMRR2014_004_03_a03.pdf, and MMRR2014_004_03_a04.pdf are government whitepapers discussing the derivation of the Plan Liability Risk Score (PLRS) calculation and the HHS-HCC (Department of Health and Human Services, Hierarchical Condition Categories) risk transfer payment calculation.

<a name="a3"></a>
## 3. Directions for Future Work

I would eventually like to fully implement the AV Calculations and/or the full Risk Transfer Formula implementation in Python and confirm that the outputs are the same as those calculated by the Excel spreadsheet given by CMS. 

<a name="a4"></a>
## 4. Milestones Timeline

 Date | Goals | Status 
 --- | --- | ---
11/19/17 | Data cleaning to relevant CSV files | **Completed**
. | Github cleaning | **Completed**
. | Documentation | **Completed**
11/26/17 | Data cleaning II | **Completed**
12/3/17 | Parse individual insurer data | **Completed**
. | Download all Excel data from CMS | **Completed**
. | Merge all Excel data into one CSV | **Completed**
. | Manually adjust Excel data to be parseable | **Completed**
12/10/17 | Introductory statistical analysis | **Completed**
. | Final data cleaning: delete duplicates, merge PDF data | **Completed**
. | A few samples of calculated data | **Completed**
. | Year to year per person payment | **Completed**
. | Redo CMS statistics, Correlation analysis | **Completed**
12/14/17 | IW talk | **Completed**
Jan 2018 | Project site | .
. | Semester 1 Paper complete | .
. | Final GitHub repo | .

