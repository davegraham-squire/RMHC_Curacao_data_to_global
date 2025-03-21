# RMHC_Curacao_data_to_global

This file creates the raw .csv export and codebook of the main (i.e. non-Curacao) study data that we send to globa.l

Input:

* mdta_02_v2024-10-01.rds
* "Variables to send to global...".xlsx with the fields to include  
* the "skeleton file" ../skel/char_child_par_fix_v16.xlsx, with the labels
* A google spreadsheet "Changes needed to LFF quant data to Global", with the manual changes to the data

Key Options:

* None  

Code Overview:

* Load the data from mdta...rds, extract desired variables from "Variables to send to global".xls
* Make any adjustments to the underlying data (only step in this program is to aggregate languages if fewer than 5 per site)
* Create an intitial codebook using the vt() function. If value labels are missing, read them in from the "skel" file. 
** This is particularly helpful for the checkbox fields
* Create a mirror data set with the factors as numeric. This is what we will export.
* Gather the value labels of the original factors. Run vt() on the numeric mirror data set to get values combine that information to get the data description for factor variables.
* Gather the field levels from the character variables.
* Import Manual fixes from Google sheets
* Clean up the code book and export it, and the data as .csv, .rds, .sav

Output:
* code book
* the data as .csv, .rds and .sav files
 
