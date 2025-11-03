# EmailJS Setup Instructions

To enable the contact form to send emails to c.m.odea86@gmail.com, follow these steps:

## 1. Create an EmailJS Account
1. Go to https://www.emailjs.com/
2. Sign up for a free account (allows 200 emails/month)

## 2. Connect Your Gmail Account
1. In EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Select "Gmail"
4. Connect your Gmail account (c.m.odea86@gmail.com)

## 3. Create an Email Template
1. Go to "Email Templates"
2. Click "Create New Template"
3. Use this template structure:
   - **Subject**: New message from {{name}}
   - **Content**:
     ```
     You have received a new message from your portfolio website:

     Name: {{name}}
     Email: {{email}}

     Message:
     {{message}}
     ```
4. Save the template and note the **Template ID**

## 4. Get Your Credentials
1. Go to "Account" → "General"
2. Find your **Public Key**
3. Go to "Email Services" and note your **Service ID**

## 5. Update script.js
Replace the placeholders in `script.js` (around line 114 and 130):
- Replace `YOUR_PUBLIC_KEY` with your actual public key
- Replace `YOUR_SERVICE_ID` with your service ID
- Replace `YOUR_TEMPLATE_ID` with your template ID

## Example:
```javascript
emailjs.init('AbC123dEfG456'); // Your public key
emailjs.sendForm('service_xyz123', 'template_abc456', contactForm)
```

After completing these steps, your contact form will send emails directly to c.m.odea86@gmail.com!
