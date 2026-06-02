# UiPath Invoice Coupon Automation

## Project Overview

This project automates invoice processing using UiPath REFramework and Document Understanding.

The automation performs the following steps:

1. Reads multiple PDF invoices from an input folder.
2. Extracts invoice details using UiPath Document Understanding.
3. Pushes extracted data into an Orchestrator Queue.
4. Processes each queue transaction using REFramework.
5. Validates invoice amount eligibility.
6. Generates a unique coupon code through a custom HTML web application.
7. Sends an email notification to customers.

   * If Grand Total > 1000: Sends coupon code and invoice attachment.
   * If Grand Total <= 1000: Sends a regret email indicating offer eligibility was not met.
8. Marks queue items as successful after processing.

---

## Technologies Used

* UiPath Studio
* UiPath REFramework
* UiPath Document Understanding
* UiPath Intelligent OCR
* UiPath Orchestrator Queue
* SMTP Email Automation
* HTML, CSS, JavaScript
* GitHub

---

## Business Rules

### Eligible Customers

If:

Grand Total > 1000

Then:

* Generate a unique 6-character coupon code
* Send coupon code via email
* Attach invoice PDF

### Non-Eligible Customers

If:

Grand Total <= 1000

Then:

* Send regret email
* No coupon code generated

---

## Project Structure

* Main.xaml
* Framework/
* LoadInvoicesToQueue.xaml
* ExtractInvoiceData.xaml
* Process.xaml
* OpenCouponPage.xaml
* SendCouponMail.xaml
* SendRegretMail.xaml
* invoice_coupon_generator.html

---

## How To Run

1. Configure UiPath Orchestrator Queue.
2. Place invoice PDFs in Input_files folder.
3. Configure Document Understanding API Key.
4. Configure SMTP Email Connection.
5. Run Main.xaml.
6. Monitor queue processing.
7. Verify generated coupon codes and email notifications.

---

## Sample Output

Customer: Arjun Kumar
Invoice Number: INV-2026-003
Grand Total: 2100
Generated Coupon Code: KWUZ8T

Customer: Vikram Singh
Invoice Number: INV-2026-005
Grand Total: 760
Result: Not Eligible

---

## Author

Kaviyanjali

UiPath Developer | Automation Enthusiast
