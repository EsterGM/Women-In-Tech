# Women-In-Tech

1.- Dataset’s discussion

a) School Level Summary Statistics 2020.xlsx
This file contains information about pupils attending at each level in every school in Scotland. 
There is specific information of both genre boys/girls for the total of each school but not for grades.
Column D of school type is not entirely correct, as some schools offer primary and secondary tuition.
The number of schools listed is 2477.

b) Schools contacts list.xlsx

This file does not contain the independent schools. The number of schools listed is 2467. 

My idea was to join both files, however, due to the difference in the number of lines affected, which does not match between both files, I decided to make a copy of the addresses into the file of the summary statistics using Excel – vlookup function.

Firstly, I moved the column of the Seed Code in the Summary Statistics\2020 file to column A (the same as the contact list file) from column C. I moved the comments written at the end of the table in the Summary Statistics file to the sheet of the Background notes.

Secondly, I inserted the necessary columns in the file of the Summary Statistics after the School name column.

Third, I used a vlookup function to look for the values of the same Seed Code (with the name of the school does not work) and to copy the address in the file of Summary Statistics:

=VLOOKUP(A3,'[2--School+Contacts+List+April+2021.xlsx]Open Schools'!$A$1:$S$2468,5,FALSE)

Column 5 is the first address line in the file of contacts list. This formula can be used with the rest of the columns, modifying the number 5 for 6, 7, 8… until 15.

Checking upon the Sort function for this new created column with addresses, there are 3 cells with =N/A. Their seed codes are:
8244022
8240922
8108625

These 3 schools lacked the contact details. In order to find them, I looked for the name of the school in internet. For the UPRN numbers, I went to https://uprn.uk and used the postcode. Barshare Primary School has 2 indistinguishable numbers, while the others were easily found. The email addresses were not found and in one case, not even the website. I left them highlighted in blue, just in case in the future I needed further working on them.
In total I obtained data on 2477 schools in Scotland, without independent schools and colleges. 

c) Denominations of the schools

If this database is used in the future for further comparisons that are out of scope of this project, I verified the denominations of the schools used in the file of “Schools Contact List” and the “Summary Statistics 2020”. There are discrepancies, highlighted by a comparison made in column BL. The “false” rows are in pink. I believe that the best column to use for denominations should be the one in the contact list file, added in column R.

d) Computer subjects in the datasets

None of the datasets that I checked in the website of the Scottish Government contain data on the subjects taught in schools. There is a pool of information in teachers and pupils, but the numbers are added for the whole country and not specified by school. 

In order to find how many pupils studied CS, I consulted the website of the SQA, https://www.sqa.org.uk/sqa/91419.html. The latest information available is for the year 2018/2019 (this academic year is not yet finished). All data are divided by the type of certification and/or level obtained as per the Curriculum for Excellence. Due to this, I am obliged to collate the data for only CS / Information Technology and similar subjects that appear in each of those files and also for the previous years, in order to obtain historical data. The tables that I need are Table 3 and Table 4 of each file. The numbers are in percentage, so I will need to transform them back to integers, in order to represent them (percentages can be the same for different initial amounts. For example, 5000 students one year can yield 50% women and 50% men, and the next year, 500 students can have the same percentage, however the initial data shows a big decrease from 5000 to 500).

This information is not specified by school, so it would not be included in the maps. Moreover, this can overlap the work of another colleague that is dealing with changes in curriculum during several years. She needs to know how many boys/girls have taken CS every academic year (every year equals to a certification file in the SQA website) and relate it to those changes. In my case, I need that information divided by school, in order to add it to the visualization maps.
