
TITLE: Risk Adjustment Dataset
AUTHOR(S): Grace Guan, Professor Mark Braverman

================================================================================

1.0 DATA SET OVERVIEW:

This data covers the 2014 and 2015 benefit years. We provide (1) a combination
of all "Insurer Report" Excel files for each of the 2014 and 2015 Benefit Years 
(BY) in CSV format as well as (2) a parsed CSV format version of the two 
"Summary Report" PDF files for each of the 2014 and 2015 BY.

The "Insurer Report" Excel files have the reported, estimated values of payment
data. The "Summary Report" PDF files have the actual payment data.

(1) We combined 9,265 “Insurer Report” Excel files from the 2014 and 2015 
Benefit Years from the Centers for Medicare and Medicaid Services’ (CMS) website 
to create a new, easier-to-analyze risk adjustment dataset. There are 5059 
insurers for 2014 (including Grand Total reports) and 5260 descriptors. There 
are 4026 insurer reports for 2015 (including Grand Total reports) and 5260 
descriptors. Each insurer report represents an insurer's data for one state that
the insurer operates in. Thus, insurers may be listed multiple times, under
different states. Additionally, each insurer has a Grand Total entry, which
varied by how the insurer chose to fill out the Grand Total file. Some Grand
Total entries sum all of the insurers' states' entries; others show the 
insurers' main state's entries; others are left blank.

(2) We parse the tables within the "Summary Report" PDF files programatically
which allows us to generate a CSV file with the data within. These files contain
the risk adjustment for individual and small group as well as reinsurance
data. No other data (such as member months, nonprofit status, etc.) is given
besides state, company name, and HIOS ID.

"2014-all.csv" contains all Insurer Report Excel files for the 2014 benefit year.
"2015-all.csv" contains all Insurer Report Excel files for the 2015 benefit year.
"2014-Benefit-Year-RI-RA-Updated.csv" contains the "Summary Report" PDF file for the 2014 benefit year.
"2015-Benefit-Year-RI-RA-Updated.csv" contains the "Summary Report" PDF file for the 2015 benefit year.

These files for 2014 and 2015 can be matched on HIOS ID.

================================================================================

2.0 DATA COLLECTION AND PROCESSING:

This data was collected through the CMS. For the Insurer Report Excel files, we 
generated one file each for the 2014 and 2015 benefit years. The 2014 file had 
5260 columns and 5059 rows. The 2015 file had 5260 columns and 4206 rows. We 
named each column in the new Excel spreadsheet by concatenating the row and the 
column names from the original 2014 Excel sheet. Each row represented a 
different Excel file. Some insurers spanned multiple Excel files, since they 
must report separately for every state they operate in.

The PDF file contained values for HIOS ID, company name, company state, reinsurance payment, and individual and small group risk adjustment payments. Each benefit year had two PDF files, one for estimated data that matched the “Insurer Report” Excel files as well as the “Public Use” Excel files, and one with the updated final values of the payments that ended up being made for each benefit year. We used the updated files because we wanted to see how they differed from the estimated files.

================================================================================


3.0 DATA FORMAT:

All files are in the CSV format. Each row represents a company operating in a
state. Each column represents a quantity, such as risk adjustment in the 
individual group, or member months in the small group market.

================================================================================


4.0 DATA REMARKS:

This dataset is limited by the number of companies that decided to report their
estimated risk adjustment values. While the original PDF data sums to zero for
every state, when matched with the Excel data, the actual transfer payments
do not sum to zero.

