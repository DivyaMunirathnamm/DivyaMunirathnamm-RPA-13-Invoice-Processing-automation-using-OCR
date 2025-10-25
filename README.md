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

<img width="1615" height="855" alt="image" src="https://github.com/user-attachments/assets/a6bdc71b-1006-4f69-8ae6-6d507b3b3f51" />

<img width="1619" height="844" alt="image" src="https://github.com/user-attachments/assets/e871a3e7-807b-4cad-a368-c59b9c639293" />

<img width="1620" height="831" alt="image" src="https://github.com/user-attachments/assets/4b1b022b-938b-483f-9c70-4f1c71fc04a1" />



## OUTPUT:
<img width="1082" height="851" alt="image" src="https://github.com/user-attachments/assets/935f8a02-33e2-4ace-87e1-1886d9fcbd5b" />


## RESULT:
The UiPath robot successfully extracted key data from an image-based PDF using OCR and saved it in an Excel file for further use.
