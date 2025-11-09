# 🖼️ AltSense: AI Alt-Text Generator

<p align="center">
  <img alt="Next.js" src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white">
  <img alt="Gemini" src="https://img.shields.io/badge/Google%20Gemini-8E75B7?style=for-the-badge&logo=google-gemini&logoColor=white">
  <img alt="Supabase" src="https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white">
  <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white">
  <img alt="License" src="https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge">
</p>

<br>

<p align="center">
  <!-- Replace with your real screenshot or demo GIF -->
  <img src="https://imgur.com/a/2OFMUQl" alt="AltSense Dashboard Preview" width="800"/>
</p>

---

AltSense is a professional, AI-powered platform for generating **WCAG 2.2 compliant** and **SEO-optimized** image alt-text in bulk.  
It’s built for e-commerce managers, content creators, and web agencies who need to enhance accessibility and improve image search rankings *without wasting hours writing descriptions manually*.

---

## ✨ Core Features

AltSense transforms the tedious task of writing alt-text into a streamlined, intelligent workflow.

### 🧠 Dual AI Engine  
- **gemini-2.5-pro** for deep visual analysis  
- **gemini-2.5-flash** for lightning-fast contextual refinement  

### 🎯 AI Focus Modes  
Control how the AI thinks:  
- **Contextual Mode:** Includes background + surrounding details  
- **Product-Only Mode:** Clean descriptions for e-commerce products  

### 🌍 100+ Supported Languages  
Generate alt text globally, with a searchable language selector.

### ☁️ Cloud Integration  
Import images from:  
- Local device  
- **Google Drive** (built-in picker)

### 🚀 Bulk Processing  
Upload **hundreds of product photos** in one workflow. Perfect for marketplaces.

### 👔 Niche Profiles  
Optimized presets for:  
- E-commerce  
- Automotive  
- Fashion  
- Blogs  
- Marketplace sellers  

### ✅ SEO & Accessibility Built-In  
- WCAG 2.2 compliant output  
- Optional keyword injection  
- Perfect for improving product rankings

### 💸 Pay-As-You-Go Pricing  
No subscriptions.  
Credits never expire.

### 🛡️ Privacy & Security  
Your images are processed once and immediately deleted.  
No data is used for training. Ever.

---

## 🛠️ Tech Stack & Architecture

| Category           | Technology |
|-------------------|------------|
| **Frontend**      | Next.js (React), Tailwind CSS |
| **Backend/API**   | Next.js API Routes (Vercel) |
| **AI Engine**     | Google Gemini (Pro & Flash) |
| **Database/Auth** | Supabase - PostgreSQL, Auth, Storage |
| **Payments**      | PayPal API |
| **Cloud Import**  | Google Drive API |

---

## 🏗️ Architectural Flow (Direct API Model)

1. **Authentication**  
   - User logs in via Supabase Auth  
   - Client receives a JWT for secure API access  

2. **Image Upload**  
   - User uploads files or chooses from Google Drive  

3. **API Request** (`/api/altsense-generate`)  
   - Client sends secure POST request with JWT  

4. **Backend Processing**  
   - Verifies JWT  
   - Checks user credit balance  
   - Sends image → Gemini Vision  
   - Sends refined result → Gemini Text  
   - Deducts one credit in Supabase  
   - Stores the result in database  

5. **Response**  
   - Returns generated alt text + job ID  
   - Client displays results instantly  

---

## 💰 Pricing: Simple & Transparent

| Package            | Price | Credits | Cost per Image |
|-------------------|-------|---------|----------------|
| Starter Pack      | $5.00  | 150     | ~$0.033 |
| Value Pack        | $19.00 | 600     | ~$0.031 |
| Pro Pack          | $49.99 | 2,000   | ~$0.025 |
| Enterprise Pack   | $199.96 | 10,000 | ~$0.020 |
| Agency Pack       | $349.99 | 20,000 | ~$0.017 |
| Bulk Pack         | $599.90 | 50,000 | **$0.012** |

✅ New users receive **10 free credits** at signup.

---

📞 Contact & Support

Website: https://getaltsense.com

Support: support@getaltsense.com

Issues: Open a GitHub Issue anytime.

📄 License

This project is licensed under the MIT License.
See the LICENSE file for details.
