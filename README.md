🖼️ AltSense: AI Alt-Text Generator
<p align="center">
<img alt="Next.js" src="https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=nextdotjs&logoColor=white">
<img alt="Gemini" src="https://img.shields.io/badge/Google%20Gemini-8E75B7?style=for-the-badge&logo=google-gemini&logoColor=white">
<img alt="Supabase" src="https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white">
<img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white">
<img alt="License" src="https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge">
</p>
<br>
<p align="center">
<!-- It would be fantastic to add a high-quality screenshot or GIF of the dashboard in action here! -->
<img src="https://i.imgur.com/your-screenshot-url.png" alt="AltSense Dashboard Preview" width="800"/>
</p>
<br>
AltSense is a professional, AI-powered platform for generating WCAG 2.2 compliant and SEO-optimized image alt-text in bulk. It's built for e-commerce managers, content creators, and web agencies who need to enhance web accessibility and boost image search rankings without sacrificing efficiency.
✨ Core Features
AltSense transforms the tedious task of writing alt-text into a streamlined, intelligent workflow.
🧠 Dual AI Engine: Uses Google's powerful gemini-2.5-pro for deep visual analysis and gemini-2.5-flash for rapid, context-aware text refinement.
🎯 Precision Control with AI Focus: Direct the AI with two powerful modes:
Contextual: Describes the subject and its relevant surroundings.
Product Only: Ignores backgrounds and packaging for clean, e-commerce-ready descriptions.
🌍 Global Reach: Generate alt-text in over 100 languages with a fast, searchable selector to connect with a worldwide audience.
☁️ Seamless Cloud Integration: Process entire product catalogs by uploading directly from your computer or connecting your Google Drive for large-scale imports.
🚀 High-Volume Batch Processing: The UI is designed to handle hundreds of images in a single session, making large tasks manageable.
👔 Niche-Specific Profiles: Get superior results with presets tuned for E-commerce, Fashion, Automotive, Blogs, and more.
✅ Compliance & SEO Built-In: Automatically generate text that meets modern accessibility standards and incorporates your target keywords for better search ranking.
💸 Pay-As-You-Go Pricing: No monthly subscriptions. Our credit-based system is transparent and cost-effective. Credits never expire.
🛡️ Secure & Private: Your images are your own. We process them and immediately delete them from our servers. We never use your data for training.
🛠️ Tech Stack & Architecture
AltSense is built with a modern, scalable tech stack designed for performance and reliability.
Category	Technology
Frontend	Next.js (React), Tailwind CSS
Backend & API	Next.js API Routes hosted on Vercel
AI Processing	Google Gemini API (gemini-2.5-pro & gemini-2.5-flash)
Database/Auth	Supabase (PostgreSQL, Authentication, Storage)
Payments	PayPal API
Cloud Import	Google Drive API
Architectural Flow (Direct API Model)
The application uses a robust, client-driven processing model that ensures security and immediate feedback.
Authentication: The client authenticates with Supabase Auth. All subsequent API requests include a JWT for verification.
Image Upload: The user uploads image files directly from their browser or selects them via the Google Drive Picker.
API Request: For each image, the client makes a secure POST request to a Next.js API route (/api/altsense-generate).
Backend Processing:
The API route verifies the user's JWT and checks their credit balance in Supabase.
It sends the image data to the Gemini Vision API for analysis.
The raw description is then sent to the Gemini Language API for refinement based on the user's settings (Profile, Keywords, Focus Mode, Language).
The backend deducts one credit and saves the completed job to the PostgreSQL database.
Response: The generated alt-text and job ID are returned to the client for immediate display.
💰 Pricing: Simple & Transparent
AltSense uses a credit-based system where 1 Credit = 1 Image. Credits are purchased via one-time payments and never expire.
Package	Price (USD)	Credits	Cost per Image (Approx)
Starter Pack	$5.00	150	$0.033
Value Pack	$19.00	600	$0.031
Pro Pack	$49.99	2,000	$0.025
Enterprise Pack	$199.96	10,000	$0.020
Agency Pack	$349.99	20,000	$0.017
Bulk Pack	$599.90	50,000	$0.012
New users receive 10 complimentary credits upon sign-up to test the full feature set.
🚀 Getting Started (For Contributors)
Interested in contributing to AltSense? Follow these steps to get your local development environment running.
Clone the Repository
code
Bash
git clone https://github.com/Sinaxbog/GetAltSense.git
cd GetAltSense
Install Dependencies
code
Bash
npm install
Set Up Environment Variables
Create a .env.local file in the root of the project and add the following variables. You can get these from your Supabase, Google Cloud, and PayPal developer dashboards.
code
Env
# Supabase
NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key

# Google Gemini API
API_KEY=your_google_gemini_api_key

# PayPal
NEXT_PUBLIC_PAYPAL_CLIENT_ID=your_paypal_client_id
PAYPAL_CLIENT_SECRET=your_paypal_secret
PAYPAL_ENV=sandbox # or 'production'

# Google Drive Integration (OAuth)
GOOGLE_CLIENT_ID=your_google_oauth_client_id
GOOGLE_CLIENT_SECRET=your_google_oauth_client_secret
NEXT_PUBLIC_BASE_URL=http://localhost:3000
Important: In your Google Cloud Console, make sure to add http://localhost:3000/api/auth/google/callback as an authorized redirect URI for your OAuth client.
Set Up Supabase Database
Log in to your Supabase project.
Go to the SQL Editor and run the SQL scripts found in the /supabase/migrations directory to create the necessary tables (user_credits, image_processing_jobs) and functions.
Run the Development Server
code
Bash
npm run dev
Open http://localhost:3000 in your browser to see the application.
📞 Contact & Support
Official Website: getaltsense.com
Support & Sales: support@getaltsense.com
GitHub Issues: For bugs and feature requests, please open an issue.
📄 License
This project is licensed under the MIT License. See the LICENSE file for details.
