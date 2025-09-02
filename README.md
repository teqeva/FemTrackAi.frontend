# ZiwaAfya Health Access Platform — MVP

ZiwaAfya is a digital health platform designed to improve access to care for women in rural Kenya. This MVP includes both backend and frontend components, enabling Community Health Workers (CHWs) and clinics to register patients, track visits, and retrieve health data using NFC-linked IDs.

---

## 👥 Contributors

- Eva Muthoni— Project Lead & Backend Architect  
  📧 eva@ziwaafya.org

- Sharon Wanjiru — Deployment & API Integration  
  📧 brian.otieno@ziwaafya.org

---

## 🧠 How It Works

ZiwaAfya connects CHWs and clinics to a centralized health database via mobile and web interfaces. Patients are issued NFC bracelets linked to their health records. The backend handles secure data storage and retrieval, while the frontend provides role-based dashboards for field use.

### Core Workflows

1. **CHW/Clinic Registration**  
   Users register via `/register_chw` or `/register_clinic` endpoints.

2. **Patient Onboarding**  
   Patients are linked to NFC IDs and stored in Supabase.

3. **Visit Submission**  
   CHWs submit visit data via `/submit_visit`.

4. **Patient Lookup**  
   NFC ID is used to retrieve patient records via `/get_patient/:id`.

5. **Role-Based Access**  
   RLS policies ensure CHWs and clinics only see relevant data.

---

## 🧱 Tech Stack

- **Backend:** Node.js, Supabase (PostgreSQL), Express or Fastify, dotenv  
- **Frontend:** MGX (Mobile-first UI), React Native or Flutter (optional)  
- **Database:** Supabase with RLS policies  
- **Deployment:** Railway or Replit

---

## ⚙️ Backend Setup

### 1. Clone the Repository
git clone https://github.com/ziwaafya/backend-mvp.git
cd backend-mvp

2. Create .env File
 DATABASE_URL="postgres://postgres:<your_password>@<your-project>.supabase.co:5432/postgres"
PORT=5000

4. Install Dependencies
npm install

6. Push Database Schema (if using Prisma)
npx prisma db push

8. Start Development Server5. Start Development Server
npm run dev


🖥️ Frontend Setup (MGX Integration)
1. Clone Frontend Repo
git clone https://github.com/ziwaafya/frontend-mgx.git
cd frontend-mgx

2. Install Dependencies
npm install

3. Configure API Endpoint
Update config.js or .env with:
API_URL="http://localhost:5000"

4.Run Frontend
npm start

5. Configure API Endpoint
Update config.js or .env with:
API_URL="http://localhost:5000"

7. Run Frontend
npm start

🧪 Testing

Use Postman or cURL to test backend endpoints. Example:
curl -X POST http://localhost:5000/register_chw \
  -H "Content-Type: application/json" \
  -d '{"name": "Amina", "phone": "+254712345678"}'

📦 Deployment Notes

    Supabase handles database, auth, and storage

    Railway or Replit can be used for hosting backend

    MGX frontend can be deployed via Vercel or Netlify

    Ensure .env files are configured before deployment

    RLS policies must be tested before production

📌 License

MIT — open for collaboration and scale.


💡 Future Enhancements

    Offline sync for CHWs in low-connectivity areas

    NFC bracelet provisioning and scanning

    Integration with Kenya's national health system

    Role-based dashboards for clinics and CHWs

    SMS alerts and appointment reminders

