# 📧 Email Sending Program in SAP ABAP

## Overview

This SAP ABAP program is designed to send emails with multiple types of attachments to recipients. It automates the generation and distribution of business documents like Smartforms or Adobe Forms in PDF format and includes dynamic table data directly in the email body.

## ✨ Features

- Sends emails with:
  - 📄 Smartform PDF attachment
  - 🖋️ Adobe Form PDF attachment
  - 📊 Tabular data (as HTML table in the email body)
  - 📌 General business information
- Sends to internal or external SAP users
- Utilizes SAP standard function modules and classes (CL_BCS)

---

## 🛠️ Technical Components

### 1. Email Sending Mechanism

- Uses SAP Business Communication Service (BCS)
- Key classes and interfaces:
  - `CL_BCS`: Main interface for sending email
  - `CL_DOCUMENT_BCS`: To create email content
  - `CL_CAM_ADDRESS_BCS`: To add recipients
  - `SO_NEW_DOCUMENT_ATT_SEND_API1`: Alternative FM

### 2. Generating PDF Attachments

#### a. Smartform to PDF

- Use `SSF_FUNCTION_MODULE_NAME` to get Smartform FM
- Use `SSF_OPEN`, `SSF_CLOSE`, and `CONVERT_OTF` to generate PDF
- Convert OTF to binary using `CONVERT_OTF`

#### b. Adobe Form to PDF

- Call FM `FP_JOB_OPEN` → `FP_FUNCTION_MODULE_NAME` → Adobe Form FM
- Use `FP_JOB_CLOSE`
- Retrieve PDF from `FP_GET_PDF_TABLE`

