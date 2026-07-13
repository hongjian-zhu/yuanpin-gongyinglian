# Inquiry Backend Setup

This site no longer uses `mailto:` for the RFQ form.

Current form status:

- The form markup is ready.
- The JavaScript submit handler is ready.
- The backend endpoint is not configured yet.
- The placeholder is `REPLACE_WITH_BACKEND_ENDPOINT`.

## What The Backend Should Receive

The backend should accept a JSON POST request from the RFQ form and store:

- name
- company
- country
- email
- buyer_type
- quantity
- products
- message
- submitted_at
- source_page
- customer IP, collected by the backend
- inquiry status, created by the backend

## Recommended Implementation Options

### Option 1: Netlify Forms

Good for a simple first version. It can collect form submissions in Netlify and send email notifications.

Best if the site is deployed on Netlify.

### Option 2: Formspree / Basin / Getform

Good if the site stays on GitHub Pages and you want a fast form backend.

Replace `REPLACE_WITH_BACKEND_ENDPOINT` with the form endpoint URL.

### Option 3: Custom Backend

Best long term.

Suggested flow:

1. Buyer submits RFQ form.
2. `/api/inquiries` receives JSON.
3. Server validates fields.
4. Server saves inquiry to a database.
5. Server sends an email to `hongjianzhu14@gmail.com`.
6. Admin can view inquiries in a small dashboard.

Suggested stack:

- Cloudflare Pages + Workers + D1
- Netlify Functions + Netlify Forms
- Vercel + Serverless Function + database
- Node.js backend + MySQL/PostgreSQL

## Files To Update Later

Update these form attributes when the backend is ready:

- `index.html`: `data-endpoint="REPLACE_WITH_BACKEND_ENDPOINT"`
- `contact.html`: `data-endpoint="REPLACE_WITH_BACKEND_ENDPOINT"`

