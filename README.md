# AWS CLI Email Management Commands

This README provides a comprehensive list of AWS CLI commands related to creating and managing email templates using Amazon Simple Email Service (SES).

## 1. Create an Email Template
To create a new email template:
```bash
aws ses create-template --cli-input-json file://email_template.json
```

## 2. Update an Existing Email Template
To update an existing email template:
```bash
aws ses update-template --cli-input-json file://email_template.json
```

## 3. Delete an Email Template
To delete an email template:
```bash
aws ses delete-template --template-name "MyNewTemplate"
```

## 4. List All Email Templates
To list all the email templates you have created:
```bash
aws ses list-templates
```

## 5. Get the Details of a Specific Template
To retrieve the details of a specific email template:
```bash
aws ses get-template --template-name "MyNewTemplate"
```

## 6. Send an Email Using a Template
To send an email using a template:
```bash
aws ses send-templated-email --source "your-email@example.com" --destination "ToAddresses=recipient@example.com" --template "MyNewTemplate" --template-data '{"name":"Recipient Name"}'
```

## 7. Verify an Email Address
Before sending emails, you need to verify your email address if you're in the SES sandbox:
```bash
aws ses verify-email-identity --email-address "your-email@example.com"
```

## 8. List Verified Email Addresses
To list all email addresses that are verified in your SES account:
```bash
aws ses list-identities --identity-type EmailAddress
```

## 9. Send a Test Email
To send a simple test email (without using a template):
```bash
aws ses send-email --from "your-email@example.com" --destination "ToAddresses=recipient@example.com" --message "Subject={Data=Test Email},Body={Text={Data=This is a test email}}"
```

## 10. Create a Custom Verification Email Template
If you want to create a custom verification email template:
```bash
aws ses create-custom-verification-email-template --cli-input-json file://custom_verification_template.json
```

## 11. Send a Custom Verification Email
To send a custom verification email:
```bash
aws ses send-custom-verification-email --email-address "recipient@example.com" --template-name "MyCustomVerificationTemplate"
```

## 12. Delete a Custom Verification Email Template
To delete a custom verification email template:
```bash
aws ses delete-custom-verification-email-template --template-name "MyCustomVerificationTemplate"
```

## 13. List Custom Verification Email Templates
To list all custom verification email templates:
```bash
aws ses list-custom-verification-email-templates
```
