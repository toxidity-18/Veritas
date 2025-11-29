# Veritas – Automated Evidence & Justice Engine

**Veritas** is a web application designed to help survivors of online abuse turn messy evidence (screenshots, chats, files) into structured, court‑ready case files — and connect them to support resources (helplines, counseling, legal help).  
It aims to make digital justice and support accessible, especially for women and girls online.

---

## 💡 Why Veritas

Online abuse, harassment, doxxing, blackmail and other forms of digital violence are rapidly increasing — especially against women and girls. Survivors often don’t know where to start, don’t have the technical know‑how to organize evidence properly, or don’t know which resources to turn to for help.  

Veritas aims to solve this by offering:

- Easy file upload (images, videos, audio, documents)  
- Automated (or simulated) text extraction and content analysis  
- Structured storage of evidence + metadata in a secure backend  
- A simple case‑file system for organizing evidence by “case”  
- A “SupportBridge” resource directory to connect survivors with help (police, medical, counseling, legal, etc.)  
- A safety‑first design (privacy, optional anonymity, potential “quick hide” / panic features)  

---

## ✅ Features (MVP & Planned)

- Upload evidence files (images, documents, audio/video)  
- Store evidence securely in storage and metadata in database  
- Extract and analyze content (text extraction / OCR simulation + basic threat detection)  
- Maintain “cases” — group evidence under case IDs  
- SupportBridge: list of support resources (police, medical, counseling, legal)  
- Anonymous / optional user mode (no sensitive user data required)  
- Future plans: PDF export of case bundle, better OCR/AI analysis, encryption, user accounts & auth  

---

## 🛠️ Tech Stack

- **Frontend**: React + TypeScript + Vite + Tailwind CSS  
- **Backend / Database**: Supabase (PostgreSQL + Storage + Auth)  
- **Deployment / Hosting**: Supabase + Static frontend (Vite)  
- **Icons / UI**: lucide‑react (for upload / file icons / UI controls)  

---

## 📥 Quick Setup (For Developers / Team Members)

1. Clone the repo:  
   ```bash
   git clone https://github.com/Waitherero-coder/Veritas.git
   cd Veritas
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a .env file (in project folder) with your Supabase config:
   ```bash
   VITE_SUPABASE_URL=https://<YOUR-PROJECT-REF>.supabase.co  
   VITE_SUPABASE_ANON_KEY=<YOUR_ANON_KEY>
   ```
4. Make sure your Supabase project is ready:
* Database tables created (via migrations)
* Storage bucket created (e.g. evidence or evidence-files)
* Row‑Level Security (RLS) policies set appropriately to allow access (for demo / development)

5. Start the dev server:
   ```bash
   npm run dev
   ```
Then open http://localhost:5173 (or as indicated) in your browser.

## 🎯 How to Use (Demo Flow)
* Click “Upload Evidence”
* Select a file (image, doc, video, etc.)
* Submit → file is uploaded to storage, metadata saved, content analyzed (text extraction & threat detection)
* Evidence appears in case file list / dashboard
* Use SupportBridge / Helplines page to view support resources (police, hospitals, counseling)
* (Optional) Repeat for multiple files under a single case to build a full evidence bundle

## 🧑‍🤝‍🧑 Collaboration Instructions (for Team)
* Everyone uses the same Supabase project — same VITE_SUPABASE_URL and VITE_SUPABASE_ANON_KEY
* Each member has their own .env, not committed to GitHub
* To start working: npm install → npm run dev
* When updating migrations / schema: commit to /supabase/migrations/, then run npx supabase db push
* If adding new features (components, UI, pages), create new branches and open Pull Requests

## 🚨 Security & Privacy Notes
* This is a hackathon‑MVP / proof‑of-concept. For real deployment, consider:
* Enforcing authenticated user sessions (via Supabase Auth)
* Proper RLS policies, data encryption, safe data handling
* Secure file / evidence storage, controlled access, PII protection
* Legal / privacy compliance when handling sensitive abuse evidence

## 💡 Future Enhancements (Post‑Hackathon)
* Real OCR + automated text extraction (Tesseract / ML model)
* PDF / ZIP export of full case bundle (evidence + metadata)
* Secure user authentication & role-based access (victim, admin, lawyer)
* Encrypted storage for sensitive files
* Shareable “case summary link” for reporting bodies
* Multi‑country support for helplines / resources
