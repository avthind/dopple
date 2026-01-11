# Dopple Digital Website Setup Guide

## 1. Setting Up the Contact Form

### Option A: Formspree (Recommended for Quick Setup)

1. **Create a Formspree Account**
   - Go to [https://formspree.io](https://formspree.io)
   - Sign up for a free account (50 submissions/month on free plan)

2. **Create a New Form**
   - After logging in, click "New Form" or "Create Form"
   - Name your form (e.g., "Dopple Digital Contact")
   - Enter the email where you want to receive submissions

3. **Get Your Form ID**
   - You'll see a form endpoint URL like: `https://formspree.io/f/xjvqkrwy`
   - The form ID is the part after `/f/` (e.g., `xjvqkrwy`)

4. **Update contact.html**
   - Open `contact.html`
   - Find line 50: `<form class="form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">`
   - Replace `YOUR_FORM_ID` with your actual form ID
   - Save the file

### Option B: Netlify Forms (If deploying to Netlify)

If you're deploying to Netlify, you can use Netlify Forms instead:

1. Change the form in `contact.html` to:
   ```html
   <form class="form" name="contact" method="POST" data-netlify="true">
   ```

2. Add a hidden input:
   ```html
   <input type="hidden" name="form-name" value="contact">
   ```

3. Netlify will automatically handle form submissions - no form ID needed!

### Option C: EmailJS (Alternative)

You can also use EmailJS or other email services. Check their documentation for setup instructions.

---

## 2. Viewing the Website Locally

### Quick Method (Recommended)

**Using Python (built-in on Mac/Linux):**

Open Terminal in the project folder and run:

```bash
# Python 3
python3 -m http.server 8000

# Or Python 2
python -m SimpleHTTPServer 8000
```

Then open your browser and go to: `http://localhost:8000`

---

**Using Node.js (if you have it installed):**

```bash
npx http-server -p 8000
```

Then open: `http://localhost:8000`

---

### Simple Method (Just Open HTML)

You can also just double-click `index.html` to open it in your browser, but note:
- Some features may not work perfectly (relative paths, animations)
- For best results, use a local server (method above)

---

## 3. Testing the Form

1. Start your local server (see above)
2. Navigate to `http://localhost:8000/contact.html`
3. Fill out and submit the form
4. Check your email (or Formspree dashboard) for the submission

---

## 4. Deployment

Once everything works locally, deploy to:

- **Vercel**: Drag and drop the folder to [vercel.com](https://vercel.com)
- **Netlify**: Drag and drop to [netlify.com](https://netlify.com)
- **GitHub Pages**: Push to GitHub and enable Pages in repository settings

All of these are free for static sites!

