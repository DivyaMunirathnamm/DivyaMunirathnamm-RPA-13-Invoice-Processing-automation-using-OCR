 # RPA-13-Invoice-Processing-automation-using-OCR
## NAME:DIVYA M
## REGISTER NUMBER:212223040043
## AIM:
To automate the extraction of key information (Invoice Number, Date, and Total Amount) from a scanned invoice PDF using OCR technology in UiPath and store the extracted data into an Excel file.

## ALGORITHM:
### Step 1: 
Prepare the Project Create a new project in UiPath Studio called InvoiceOCRBot.
Place your Invoice PDF in the project folder for easy access. 
### Step 2: 
Read the Invoice using OCR Use the Read PDF with OCR activity (from UiPath.PDF.Activities).
Set the file path to your invoice PDF.
Use Tesseract OCR or Microsoft OCR engine.
Output: ocrText (String variable)
### Step 3:
Extract Data Using Regex Use Assign activities to extract data: invoiceNumber = System.Text.RegularExpressions.Regex.Match(ocrText, "Invoice Number[:\s]([A-Za-z0-9-]+)").Groups(1).Value
invoiceDate = System.Text.RegularExpressions.Regex.Match(ocrText, "Date[:\s]([0-9/-]+)").Groups(1).Value
totalAmount = System.Text.RegularExpressions.Regex.Match(ocrText, "Total Amount[:\s]*([\d,]+.\d{2})").Groups(1).Value 
### Step 4: 
Create and Write to Excel Use a Build Data Table activity to create a table with columns: Invoice Number, Date, Total Amount
Use Add Data Row to insert extracted values.
Use Write Range activity to save the data to Invoice.xlsx. 
### Step 5:
Run and Verify Run the bot.
Open the Invoice.xlsx file to check if the data is entered correctly.

## PROGRAM:
<img width="692" height="641" alt="image" src="https://github.com/user-attachments/assets/d21e7eae-1b55-4012-811e-abe728c0f560" />
<img width="508" height="670" alt="image" src="https://github.com/user-attachments/assets/b9f3d60f-22f4-4b19-bd43-929aff7e53c2" />
<img width="563" height="534" alt="image" src="https://github.com/user-attachments/assets/cf5fc559-b6b3-4cd0-9d7a-59644ef93852" />

<img width="1333" height="690" alt="image" src="https://github.com/user-attachments/assets/347feb06-380f-46e6-b3f1-799a9ca1a312" />
<img width="1331" height="705" alt="image" src="https://github.com/user-attachments/assets/e1933e7c-2bb1-4665-855b-3f98d51f611b" />
<img width="1328" height="673" alt="image" src="https://github.com/user-attachments/assets/f08c4c28-4a70-438f-b23b-7dc2a477896c" />


## OUTPUT:
<img width="1082" height="851" alt="image" src="https://github.com/user-attachments/assets/935f8a02-33e2-4ace-87e1-1886d9fcbd5b" />


## RESULT:
The UiPath robot successfully extracted key data from an image-based PDF using OCR and saved it in an Excel file for further use.
