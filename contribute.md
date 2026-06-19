# Contributing to Ender

Welcome! We are excited that you want to contribute to Ender. This guide will walk you through setting up your development environment and making your first contribution.

## 🚀 Step-by-Step Setup for First-Time Contributors

### 1. Fork the Repository
Click the **Fork** button in the upper-right corner of the GitHub repository to create a copy of the repo under your own GitHub account.

### 2. Clone Your Fork
Clone your fork to your local machine:
```bash
git clone https://github.com/<YOUR_USERNAME>/Ender.git
cd Ender
```

### 3. Install Dependencies
This project uses **pnpm** as its primary package manager. Run the following to install all dependencies:
```bash
pnpm install
```
*(If you do not have pnpm installed, you can install it via `npm install -g pnpm` or use `npm install`)*

### 4. Configure Environment Variables
Copy the `.env.example` file to `.env.local`:
```bash
cp .env.example .env.local
```
Open `.env.local` in your editor and configure the necessary keys:
* Configure at least one **AI Provider** (`ANTHROPIC_API_KEY`, `OPENAI_API_KEY`, `GEMINI_API_KEY`, or `GROQ_API_KEY`).
* Configure at least one **Scraping Provider** (`FIRECRAWL_API_KEY` is default and recommended).
* Select and configure a **Sandbox Provider** (`vercel` or `e2b`).

### 5. Setup Local Database
Ender uses MongoDB. Make sure you have a MongoDB instance running:
* **Option A**: Run MongoDB locally (default connection URI is `mongodb://localhost:27017`).
* **Option B**: Run via Docker:
  ```bash
  docker run -d -p 27017:27017 --name ender-mongo mongo:latest
  ```

### 6. Run the Development Server
Start the local server in development mode:
```bash
pnpm dev
```
Open [http://localhost:3000](http://localhost:3000) in your browser to verify it runs.

---

## 🛠️ Making Changes & Code Quality Checks

Before you commit and submit your Pull Request, ensure that your code aligns with the repository quality standards:

### 1. Run Linter
We use ESLint to maintain clean code formatting. Run the linter locally:
```bash
pnpm lint
```

### 2. Build Check
Ensure that the TypeScript types compile and the Next.js production build succeeds:
```bash
pnpm build
```

---

## 📬 Submitting a Pull Request (PR)

1. Create a branch for your changes:
   ```bash
   git checkout -b feature/your-feature-name
   ```
2. Commit your code changes with a descriptive message:
   ```bash
   git commit -m "feat: add support for stellar wallet connection"
   ```
3. Push your branch to your GitHub fork:
   ```bash
   git push origin feature/your-feature-name
   ```
4. Open a **Pull Request** on the main repository, describing what the change accomplishes and linking any open issues.
