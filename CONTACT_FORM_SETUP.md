# Contact Form Setup Guide

This guide will help you set up a functional contact form for your Astro site deployed on Vercel.

## Option 1: Vercel Functions with Resend (Recommended)

### Step 1: Install Dependencies

The necessary dependencies have been added to your `package.json`:

- `@vercel/node` - For Vercel serverless functions
- `resend` - Email service

Run:

```bash
npm install
```

### Step 2: Set up Resend Email Service

1. Go to [resend.com](https://resend.com) and create a free account
2. Get your API key from the dashboard
3. Add the API key to your Vercel environment variables:
   - Go to your Vercel project dashboard
   - Navigate to Settings → Environment Variables
   - Add `RESEND_API_KEY` with your Resend API key

### Step 3: Configure Email Settings

Update the `api/contact.ts` file with your email settings:

```typescript
// Change this to your verified domain
from: 'Contact Form <noreply@yourdomain.com>',

// Change this to your email address
to: ['hello@_troneras.com'],
```

### Step 4: Deploy

Push your changes to GitHub and Vercel will automatically deploy the new API function.

## Option 2: Alternative Email Services

### Using Nodemailer with Gmail

Replace the Resend implementation in `api/contact.ts`:

```typescript
import nodemailer from 'nodemailer';

const transporter = nodemailer.createTransporter({
  service: 'gmail',
  auth: {
    user: process.env.GMAIL_USER,
    pass: process.env.GMAIL_APP_PASSWORD, // Use App Password, not regular password
  },
});

// In the handler function:
await transporter.sendMail({
  from: process.env.GMAIL_USER,
  to: 'hello@_troneras.com',
  subject: `New Contact Form Submission from ${name}`,
  html: `...`,
});
```

Add to your environment variables:

- `GMAIL_USER` - Your Gmail address
- `GMAIL_APP_PASSWORD` - Gmail App Password (enable 2FA first)

### Using SendGrid

```bash
npm install @sendgrid/mail
```

```typescript
import sgMail from '@sendgrid/mail';
sgMail.setApiKey(process.env.SENDGRID_API_KEY);

// In the handler function:
await sgMail.send({
  to: 'hello@_troneras.com',
  from: 'noreply@yourdomain.com',
  subject: `New Contact Form Submission from ${name}`,
  html: `...`,
});
```

## Option 3: Third-party Form Services

### Formspree

Replace the form action in `Form.astro`:

```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST"></form>
```

### Netlify Forms

Add `data-netlify="true"` to your form:

```html
<form data-netlify="true" name="contact"></form>
```

## Security Considerations

1. **Rate Limiting**: Consider adding rate limiting to prevent spam
2. **CAPTCHA**: Add reCAPTCHA or hCaptcha for additional protection
3. **Input Sanitization**: The current implementation includes basic validation
4. **Environment Variables**: Never commit API keys to your repository

## Testing

1. Deploy your changes to Vercel
2. Fill out the contact form on your website
3. Check your email for the submission
4. Verify the success/error messages work correctly

## Troubleshooting

- **CORS Errors**: Vercel functions handle CORS automatically
- **Email Not Sending**: Check your API keys and email configuration
- **Form Not Submitting**: Check browser console for JavaScript errors
- **Environment Variables**: Ensure they're set in Vercel dashboard

## Cost Considerations

- **Resend**: 3,000 emails/month free, then $0.80/1,000 emails
- **SendGrid**: 100 emails/day free, then $14.95/month
- **Gmail**: Free with Gmail account (limited to 500/day)
- **Vercel Functions**: 100GB-hours/month free, then $0.40/GB-hour
