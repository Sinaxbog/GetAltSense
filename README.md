# 🖼️ AltSense: The AI Alt-Text Generator for Enterprise Scale and WCAG Compliance

[![Made with Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)](https://nextjs.org/)
[![Powered by Gemini API](https://img.shields.io/badge/Google_Gemini-1473E6?style=for-the-badge&logo=google&logoColor=white)](https://ai.google.dev/models/gemini)
[![Database: Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white)](https://supabase.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

**AltSense** is a professional, AI-powered platform designed for **reliable, high-volume** generation of **WCAG 2.2 compliant** and **SEO-optimized** image alt-text. We provide e-commerce managers, content teams, and web agencies with a scalable solution to automate accessibility and image search ranking.

---

## ✨ Problem Solved: Scalability & Compliance

Manual alt-text writing fails at scale, leading to inconsistent quality and legal risk. AltSense eliminates this bottleneck by combining best-in-class vision processing with a resilient queuing system.

### Core Value Proposition

* **⚡ Guaranteed Reliability:** Our **Server-Side Queuing Architecture** (using Supabase Edge Functions) ensures reliable processing of large image batches (1,000s of images) without timing out, failing, or hitting external API rate limits.
* **🧠 Contextual Accuracy:** The two-step AI refinement uses **Niche Profiles** (e.g., E-commerce SEO, Art Curator) to generate output that is not just descriptive, but **functionally useful** for specific industry needs.
* **🛡️ Risk Mitigation:** Every generated alt-text is guaranteed to meet **WCAG 2.2** criteria, providing an essential layer of legal compliance and better user experience.

---

## 🛠️ Architectural Blueprint (Tech Deep Dive)

AltSense is built as a **Next.js Hybrid Application** leveraging the power of two distinct serverless platforms for maximum efficiency and security.

| Component | Technology | Role |
| :--- | :--- | :--- |
| **Monetization & API** | **Vercel Serverless (Next.js)** | Handles secure PayPal payment capture and the front-facing API routes for job submission. |
| **AI Processing** | **Google Gemini API** | Uses `gemini-2.5-pro` for initial vision analysis and `gemini-2.5-flash` for final text refinement. |
| **Database & Queue** | **Supabase (PostgreSQL)** | Manages `user_credits` and acts as the central **`image_processing_jobs` queue** for reliable, asynchronous job handling. |
| **Background Worker** | **Supabase Edge Functions** | The scheduled worker runs the queue. It handles image download, API call retries, job status updates, and **critical file deletion** (the "Delete on Complete" policy). |
| **Realtime** | **Supabase Realtime** | Instantly streams job status updates to the client, providing a smooth user experience without polling. |

---

## 💰 Pricing and Usage Model

AltSense operates on a simple **Credit System** (**1 Credit = 1 Image Alt-Text Generated**). This system provides transparent, scalable usage for agencies and large content teams.

| Package | Price (USD) | Credits Granted | Cost per Image (Approx) |
| :--- | :--- | :--- | :--- |
| **Starter Pack** | $5.00 | 150 | $0.033 |
| **Value Pack** | $19.00 | 600 | $0.031 |
| **Pro Pack** | $49.99 | 2,000 | $0.025 |
| **Enterprise Pack** | $199.96 | 10,000 | $0.020 |
| **Agency Pack** | $349.99 | 20,000 | $0.017 |
| **Bulk Pack** | $599.90 | 50,000 | $0.012 |

New users receive **10 complimentary credits** upon sign-up to test the full feature set.

---

## 🚀 Getting Started (For Contributors/Partners)

1.  **Clone the Repository:** `git clone [Your Repo URL]`
2.  **Configure Environment:** Set up required environment variables: `NEXT_PUBLIC_PAYPAL_CLIENT_ID`, `PAYPAL_CLIENT_SECRET`, `SUPABASE_URL`, `SUPABASE_ANON_KEY`, and `API_KEY` (for Gemini).
3.  **Run Migrations:** Execute the provided SQL for the `image_processing_jobs` table and `process_job_and_deduct_credits` function.
4.  **Deploy Edge Worker:** Deploy the `alt-text-worker` function to your Supabase instance and schedule its execution.

### Contact and Support

* **Official Website & Documentation:** https://getaltsense.com/
* **Support/Sales:** support@getaltsense.com
* **License:** This project is licensed under the MIT License.
