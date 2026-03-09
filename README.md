# Google Sheets Payment Reminder Email Sender

This Google Apps Script automatically sends **payment reminder emails** to customers using data stored in a Google Sheet.

## 📋 Sheet Structure
![Project Preview](https://github.com/mishraaniruddha2987-cmyk/Email-Automation-Projects-in-google-sheet./blob/main/Capture2.PNG)
![Project Preview](https://github.com/mishraaniruddha2987-cmyk/Email-Automation-Projects-in-google-sheet./blob/main/Capture1.PNG)
![Project Preview](https://github.com/mishraaniruddha2987-cmyk/Email-Automation-Projects-in-google-sheet./blob/main/Screenshot_2026-03-09-11-26-45-58_e307a3f9df9f380ebaf106e1dc980bb6.jpg)
This Google Apps Script automatically sends **payment reminder emails** to customers using data stored in a Google Sheet.

## 📋 Sheet Structure

Create a sheet named **Sheet1** with the following headers:

| Sr.No. | Name     | Email                                   | Due Amount | Due Date   |
| ------ | -------- | --------------------------------------- | ---------- | ---------- |
| 1      | John Doe | [john@email.com](mailto:john@email.com) | 5000       | 10-03-2026 |

## ✉️ Email Template

**Subject**

```
Payment Reminder
```

**Body**

```
Dear <Name>,

Your installment of Rs.<Due Amount> is pending till date <Due Date>. 
Please pay your installment ASAP to avoid unwanted charges.

Regards  
Aniruddha Mishra
```

## ⚙️ Setup Instructions

1. Open your **Google Sheet**
2. Go to **Extensions → Apps Script**
3. Delete the default code
4. Paste the script below
5. Click **Save**
6. Run the function **sendPaymentReminders()**
7. Authorize the script when prompted

## 💻 Google Apps Script

```javascript
function sendPaymentReminders() {

  var sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Sheet1");
  var data = sheet.getDataRange().getValues();

  for (var i = 1; i < data.length; i++) {

    var name = data[i][1];
    var email = data[i][2];
    var dueAmount = data[i][3];
    var dueDate = data[i][4];

    var subject = "Payment Reminder";

    var body = "Dear " + name + ",\n\n" +
      "Your installment of Rs." + dueAmount +
      " is pending till date " + dueDate +
      ". Please pay your installment ASAP to avoid unwanted charges.\n\n" +
      "Regards\n" +
      "Aniruddha Mishra";

    MailApp.sendEmail(email, subject, body);
  }
}
```

## ▶️ Running the Script

Run the function:

```
sendPaymentReminders()
```

This will send reminder emails to all customers listed in **Sheet1**.

## 📌 Optional: Add a Button in Google Sheets

1. Go to **Insert → Drawing**
2. Create a button (e.g., *Send Reminders*)
3. Click **Assign Script**
4. Enter:

```
sendPaymentReminders
```

Now you can send all emails with **one click**.

## ⚠️ Gmail Sending Limits

| Account Type     | Daily Limit      |
| ---------------- | ---------------- |
| Gmail (Free)     | ~100 emails/day  |
| Google Workspace | ~1500 emails/day |

## 🚀 Features

* Reads customer data directly from Google Sheets
* Sends personalized emails
* Works with a single command
* Easy to customize

## 📜 License

MIT License


Create a sheet named **Sheet1** with the following headers:

| Sr.No. | Name     | Email                                   | Due Amount | Due Date   |
| ------ | -------- | --------------------------------------- | ---------- | ---------- |
| 1      | John Doe | [john@email.com](mailto:john@email.com) | 5000       | 10-03-2026 |

## ✉️ Email Template

**Subject**

```
Payment Reminder
```

**Body**

```
Dear <Name>,

Your installment of Rs.<Due Amount> is pending till date <Due Date>. 
Please pay your installment ASAP to avoid unwanted charges.

Regards  
Aniruddha Mishra
```

## ⚙️ Setup Instructions

1. Open your **Google Sheet**
2. Go to **Extensions → Apps Script**
3. Delete the default code
4. Paste the script below
5. Click **Save**
6. Run the function **sendPaymentReminders()**
7. Authorize the script when prompted

## 💻 Google Apps Script

```javascript
function sendPaymentReminders() {

  var sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName("Sheet1");
  var data = sheet.getDataRange().getValues();

  for (var i = 1; i < data.length; i++) {

    var name = data[i][1];
    var email = data[i][2];
    var dueAmount = data[i][3];
    var dueDate = data[i][4];

    var subject = "Payment Reminder";

    var body = "Dear " + name + ",\n\n" +
      "Your installment of Rs." + dueAmount +
      " is pending till date " + dueDate +
      ". Please pay your installment ASAP to avoid unwanted charges.\n\n" +
      "Regards\n" +
      "Aniruddha Mishra";

    MailApp.sendEmail(email, subject, body);
  }
}
```

## ▶️ Running the Script

Run the function:

```
sendPaymentReminders()
```

This will send reminder emails to all customers listed in **Sheet1**.

## 📌 Optional: Add a Button in Google Sheets

1. Go to **Insert → Drawing**
2. Create a button (e.g., *Send Reminders*)
3. Click **Assign Script**
4. Enter:

```
sendPaymentReminders
```

Now you can send all emails with **one click**.

## ⚠️ Gmail Sending Limits

| Account Type     | Daily Limit      |
| ---------------- | ---------------- |
| Gmail (Free)     | ~100 emails/day  |
| Google Workspace | ~1500 emails/day |

## 🚀 Features

* Reads customer data directly from Google Sheets
* Sends personalized emails
* Works with a single command
* Easy to customize

## 📜 License

MIT License
