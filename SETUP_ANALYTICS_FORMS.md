# Setup Guide: Google Analytics & Forms

## ✅ What's Been Done

- ✅ Google Analytics snippet added to all 26 pages
- ✅ Scheduling form updated to use Formspree
- ✅ All pages ready for tracking & form submissions

---

## 📊 Google Analytics Setup (5 minutes)

### Step 1: Create Google Analytics Account
1. Go to [google.com/analytics](https://google.com/analytics)
2. Click "Start measuring"
3. Create an account (Business name: "Double R Roofing")
4. Create a property (Website: "double-r-roofing.com")
5. Select Web as the data stream
6. Accept terms

### Step 2: Get Your Tracking ID
1. In Google Analytics, go to Admin → Property → Data Streams
2. Click on your web stream
3. Copy the **Measurement ID** (looks like: `G-XXXXXXXXXX`)

### Step 3: Update Your Site
1. Open `/public/httpsdouble-r-roofing.com/index.html`
2. Find: `G-XXXXXXXXXX` (appears 2 times)
3. Replace with your Measurement ID
4. Repeat for all pages in `/pages/` folder OR run this command:

```bash
# From repository root:
sed -i 's/G-XXXXXXXXXX/YOUR_ACTUAL_ID/g' public/httpsdouble-r-roofing.com/*.html
sed -i 's/G-XXXXXXXXXX/YOUR_ACTUAL_ID/g' public/httpsdouble-r-roofing.com/pages/*.html
```

### Step 4: Verify
- Deploy site
- Visit your site
- In Google Analytics, check "Realtime" tab
- You should see live visitor data within seconds

---

## 📧 Forms Setup with Formspree (5 minutes)

### Step 1: Create Formspree Account
1. Go to [formspree.io](https://formspree.io)
2. Sign up with your email
3. Verify your email

### Step 2: Create a Form
1. Click "+ New Project"
2. Name it: "Double R Roofing"
3. Click "+ Add Form"
4. Configure form:
   - **Form email:** Your email (where submissions go)
   - **Form name:** "Appointment Requests"
5. Copy the **Form ID** (shown after creation)

### Step 3: Update Scheduling Form
1. Open `/public/httpsdouble-r-roofing.com/pages/scheduling.html`
2. Find: `action="https://formspree.io/f/YOUR_FORM_ID"`
3. Replace `YOUR_FORM_ID` with your actual Form ID from Formspree

### Step 4: Test It
1. Visit your site
2. Fill out the appointment form
3. Submit
4. Check your email for the form submission!

---

## 📱 Optional: Add to Other Pages

If you want form submissions on other pages, create more Formspree forms and update:

- `/pages/calculator-roofing-solutions.html` - Cost calculator
- `/pages/premium-roofing-solutions.html` - Service inquiry
- `/pages/contact.html` - General contact (if needed)

---

## 🔑 Quick Command Reference

**Replace Google Analytics ID everywhere:**
```bash
cd /workspaces/Double-R-Roofing-RiseabovetheRest
sed -i 's/G-XXXXXXXXXX/YOUR_REAL_GA_ID/g' public/httpsdouble-r-roofing.com/**/*.html
```

**Replace Formspree ID in scheduling:**
```bash
sed -i 's/YOUR_FORM_ID/YOUR_REAL_FORMSPREE_ID/g' public/httpsdouble-r-roofing.com/pages/scheduling.html
```

---

## ✨ What You'll Get

✅ Real-time visitor tracking
✅ Traffic source analysis
✅ Visitor behavior insights
✅ Form submission emails
✅ Conversion tracking for bookings

---

**Questions?** Check Formspree and Google Analytics documentation or reach out!
