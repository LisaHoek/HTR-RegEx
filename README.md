# Extracting Entities from Handwritten Civil Records using Handwritten Text Recognition and Regular Expressions
### MSc Thesis - Lisa Hoek

This repository contains scripts to extract entities of death certificates from Curaçao 1831-1950. We suggest reading the thesis for more information and instructions on how to obtain transcriptions from image data with Handwritten Text Recognition in Transkribus.

First, read in the Transkribus XML files:

    folder_name = 
    data_dir = f"dataTranskribus\{folder_name}\{folder_name}\page"
    texts, metadata, regions = read_files(data_dir)

Choose what log info to display:
- All (displays text, match and entity)
- No_matches (displays text of all no matches)
- None (does not display anything)

Then, extract entities with one the following functions:

    df = find_..._in_texts(folder_name, texts, print_log="All")

Using one of the following keywords:

- certificate_number (returns certificate number)
- certificate_date (returns certificate date in (d)d-(m)m-yyyy format)
- certificate_district (not implemented)
- name (returns the name of the deceased person splitted in entities 'first_names' and 'last_name')
- age (returns the age of the deceased person, still in handwritten format)
- profession (returns the profession of the deceased person)
- date_of_death (returns date of death)
- time_of_death (returns time of death)
- place_of_death (returns place of death)
- date_of_birth (returns date of birth of the deceased person in (d)d-(m)m-yyyy format)
- place_of_birth (returns place of birth of the deceased person)
- sex (returns the sex of the deceased person if it can be derived from the certificate)
- marital_status (returns marital status of the deceased person)
- informants (returns two dataframes; name, age and profession of both informants)
- father_info (not implemented yet)
- mother_info (not implemented yet)
- partner_info (not implemented yet)
- parents_deceased (returns whether the father and/or mother have deceased; entities 'father_deceased' and 'mother_deceased')

Each df has columns 'document', 'id', 'text', 'match', and a column of the entity. 
 