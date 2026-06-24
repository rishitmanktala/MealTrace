# 🍽️ MealTrace

**AI-powered nutrition tracker** — snap a photo of your meal and get instant calorie & macro breakdowns.

MealTrace is a static frontend application backed by **Supabase** for authentication, database storage, and edge functions. It uses the **Groq API** (via a Supabase Edge Function) to analyze meal photos and extract detailed nutritional data.

---

## ✨ Features

- 📸 **Photo-Based Meal Logging** — Upload or capture a meal photo to auto-detect calories, macros (protein, carbs, fat, fiber), vitamins, and minerals
- 🔒 **User Authentication** — Email/password sign-in and sign-up via Supabase Auth
- 📊 **Dashboard & Charts** — Visualize daily nutrition intake with interactive Chart.js graphs
- 📅 **Meal History** — Browse and review past logged meals
- 🎯 **Goal Tracking** — Set daily calorie and macro targets
- ⚡ **Serverless Backend** — No traditional server; Supabase handles auth, storage, and API calls

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML/CSS/JS, Inter font |
| Charts | Chart.js 4 |
| Auth & Database | Supabase (PostgreSQL) |
| AI Analysis | Groq API via Supabase Edge Function (Deno) |
| Deployment | GitHub Pages |

---

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) v18+
- A [Supabase](https://supabase.com/) project
- A [Groq](https://console.groq.com/) API key

### Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/rishitmanktala/mealtrace.git
   cd mealtrace
   ```

2. **Configure environment:**
   ```bash
   cp .env.example .env
   ```
   Add your `GROQ_API_KEY` in the Supabase Dashboard under **Edge Functions → Secrets**.

3. **Run the Supabase migration:**
   ```bash
   npx supabase db push
   ```

4. **Deploy the Edge Function:**
   ```bash
   npx supabase functions deploy analyze-meal
   ```

5. **Open `index.html`** in a browser or deploy to GitHub Pages.

---

## 📁 Project Structure

```
mealtrace/
├── index.html              # Main app UI
├── app.js                  # Client-side logic
├── style.css               # Styles
├── supabase/
│   ├── functions/
│   │   └── analyze-meal/   # Deno edge function for AI analysis
│   └── migrations/         # Database schema
└── .env.example            # Environment variable template
```

---

## 📄 License

This project is open source.
