# interac-e-transfer-auto-receipt
Automated Professional Receipts for Interac E-Transfers

## Overview
This automation has three parts:
1. a gmail filter that applies a label to e-transfer confirmations
2. a google apps script that handles everything, which is attached to a google sheet to store the collected information
3. a customizable receipt template, which the apps script generates the pdf receipt from using the info from the e-transfer confirmation

## Requirements
- You must have Auto Deposit enabled for your e-transfer email. Receipts will also be sent from this email.
- You must use a gmail or google workspace account and keep the program files in your associated google drive.

## Setup
1. Make copies of the files from [this folder](https://drive.google.com/drive/folders/1KkNlziUiJ6i6nDEXu3-JFBe2wl1qSJh5?usp=sharing). Save the files in a folder somewhere in your google drive.
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
