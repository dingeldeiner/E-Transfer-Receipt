# interac-e-transfer-auto-receipt
Automatically send customers a receipt when you receive an Interac E-Transfer auto-deposit confirmation email.

## Overview
This automation has three parts:
1. a gmail filter that applies a label to e-transfer confirmations
2. a google apps script that handles everything, which is attached to a google sheet to store the collected information
3. a customizable receipt template, which the apps script generates the pdf receipt from using the info from the e-transfer confirmation

## Setup
1. Make copies of the files from [this folder](https://drive.google.com/drive/folders/1KkNlziUiJ6i6nDEXu3-JFBe2wl1qSJh5?usp=sharing)
2. In your gmail:
  - Go to settings > all settings > filters and blocked > import filters
  - Upload the 'mailFilters.xml' file
  - Click 'open' then 'create filter'
3. In your copy of the 'AUTORECEIPT' sheet:
  - Go to extensions > apps script and open the apps script
  - In the editor, update RECEIPT_FILE_ID and DATA_FILE_ID to the google drive ID of your receipt template and AUTORECEIPT sheet
  - Go to the triggers tab and create a time-driven trigger that runs 'mainFunction()' every minute
4. In your copy of the 'Receipt' google sheet, update the template with your info
  - Upload a logo if you want
  - If you want to really change up the template, make sure you update the cell references in the apps script
