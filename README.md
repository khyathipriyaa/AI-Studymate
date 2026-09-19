# 🎓 AI StudyMate - Your Personal AI Study Assistant

> **“Learn smarter. Prepare better. Score higher.”**

**AI StudyMate** is a full-featured, modern AI-powered academic assistant web application designed specifically for college, university, and engineering students. It equips students with the tools to master complex coursework, format high-scoring exam answers, drill interactive MCQs, structure personalized study plans, study directly from uploaded lecture PDFs, and solve lab coding assignments.

---

## 🚀 Key Features

### 1. 💬 AI Academic Chatbot
- **ChatGPT-Style Experience**: Clean conversational interface with user and tutor message bubbles, smooth typing indicators, and formatted responses.
- **Student-Friendly Explanations**: Breaks down complex engineering and science topics with intuitive real-world analogies.
- **Follow-up Continuity**: Maintains conversation context and suggests smart follow-up questions.
- **One-Click Actions**: Quick copy-to-clipboard for note-taking and chat reset.

### 2. 📝 Exam Mode (2, 5 & 10 Marks)
- **Targeted University Grading**: Generates answers tailored specifically to university evaluation schemes:
  - **2 Marks**: Crisp 3-4 line definitions, core formulas, and key points without filler.
  - **5 Marks**: Structured 4-5 numbered points, brief example, and conclusions.
  - **10 Marks**: Full university exam structure with title, intro, architecture breakdown, **ASCII Block Diagram**, step-by-step working principle, real-world case study, comparison table, and conclusion.
- **Export Ready**: One-click Copy Model Answer and Print/PDF export buttons.

### 3. 🎯 Interactive Quiz Mode
- **Topic-Based MCQ Generation**: Generates 3, 5, or 10 multiple-choice questions on any subject (e.g. Operating Systems Deadlocks, Binary Search Trees, DBMS Normalization).
- **Step-by-Step Flow**: Shows one question at a time to prevent cognitive overload.
- **Instant Explanations**: Highlights correct/incorrect choices immediately with detailed conceptual explanations.
- **Celebration & Scorecard**: Confetti celebration, performance rating, and complete post-quiz review.

### 4. 📅 Smart Study Planner
- **Personalized Timetable**: Input your subjects, upcoming exam dates, and daily available study hours (2-10 hrs).
- **Intelligent Spacing**: Balances difficult subjects with revision buffers and mock test days.
- **Actionable Advice**: Daily time slots, Pomodoro revision tips, and high-score exam strategies.

### 5. 📄 Notes & PDF Assistant
- **Document Upload & Text Extraction**: Upload lecture slides, professor notes, or syllabus PDFs.
- **Server-Side PDF Parsing**: Extracts text cleanly using Node `pdf-parse`.
- **Grounded Q&A**: Answers questions strictly referencing the uploaded material.
- **Explicit Source Citations**: Clearly displays the citation tag:
  👉 `[From Uploaded Notes]` whenever the answer originates from your document.

### 6. 🌐 Multilingual Support
- Switch seamlessly between:
  - 🇬🇧 **English**
  - 🇮🇳 **Telugu (తెలుగు)**
  - 🇮🇳 **Hindi (हिन्दी)**
- All AI system prompts dynamically adapt to generate natural, academic responses in the selected language.

### 7. 💻 Coding Helper (C, Java, Python, C++, JS)
- **Language Support**: Specialized assistance for C, Java, Python, C++, and JavaScript.
- **4 Action Modes**: Explain Concept, Debug Error, Write Code, and Optimize Complexity.
- **Student-Centric Output**: Complete runnable code with syntax styling, step-by-step logic, Big-O Time/Space complexity badge, and **Common Exam & Lab Mistakes** to watch out for.

### 8. 🎨 UI/UX & Themes
- **Modern Student Dashboard**: Sleek responsive design for mobile, tablet, and desktop.
- **Dark & Light Mode**: Instant theme switching with persistent localStorage memory.
- **Landing Page**: Engaging hero section, feature cards, and "Start Learning" button.

---

## 🛠️ Technology Stack

- **Framework**: [Next.js 14](https://nextjs.org/) (App Router, Server Components & Route Handlers)
- **Language**: [TypeScript](https://www.typescriptlang.org/)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/)
- **Icons**: [Lucide React](https://lucide.dev/)
- **PDF Engine**: [pdf-parse](https://www.npmjs.com/package/pdf-parse)
- **AI SDK**: [@google/generative-ai](https://www.npmjs.com/package/@google/generative-ai) (Google Gemini 1.5 Flash)
- **Celebration FX**: [canvas-confetti](https://www.npmjs.com/package/canvas-confetti)

---

## 📦 Getting Started Locally

### Prerequisites
- Node.js 18.x or 20.x or higher
- npm or yarn or pnpm

### Installation

1. **Clone or navigate to the project directory**:
   ```bash
   cd "AI studymate"
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Configure Environment Variables (Optional)**:
   Copy `.env.example` to `.env.local`:
   ```bash
   cp .env.example .env.local
   ```
   Open `.env.local` and add your Gemini API key:
   ```env
   GEMINI_API_KEY=your_gemini_api_key_here
   ```

   > [!TIP]
   > **No API Key? No Problem!**
   > AI StudyMate includes a built-in **Smart Academic Engine**. If no key is configured, all 6 study modules still work immediately with realistic university-level responses, MCQs, and exam answers!
   > You can also paste your Gemini API key anytime directly inside the app using the **"Academic Engine / Live Gemini"** button in the top navbar.

4. **Start the development server**:
   ```bash
   npm run dev
   ```

5. **Open your browser**:
   Navigate to [http://localhost:3000](http://localhost:3000).

---

## 🔑 How to Get a Free Gemini API Key

1. Go to [Google AI Studio](https://aistudio.google.com/app/apikey).
2. Sign in with your Google account.
3. Click **"Create API Key"**.
4. Copy your key and:
   - Paste it into the in-app **API Key Settings** modal (top-right button in the app header), OR
   - Paste it into `.env.local` as `GEMINI_API_KEY=your_key`.

---

## 🚀 Building for Production & Deployment

### Build the Application
```bash
npm run build
```

### Run Production Server
```bash
npm start
```

### Deploying to Vercel (Recommended)
1. Push your repository to GitHub:
   ```bash
   git init
   git add .
   git commit -m "Initial commit of AI StudyMate"
   git branch -M main
   git remote add origin https://github.com/your-username/ai-studymate.git
   git push -u origin main
   ```
2. Go to [Vercel](https://vercel.com/) and click **"Add New Project"**.
3. Import your GitHub repository.
4. Under **Environment Variables**, add `GEMINI_API_KEY` with your API key value.
5. Click **Deploy**. Your app will be live on a custom `.vercel.app` domain in seconds!

---

## 📂 Project Architecture

```text
ai-studymate/
├── public/                     # Static assets & icons
├── src/
│   ├── app/
│   │   ├── api/
│   │   │   ├── chat/           # /api/chat - Conversation endpoint
│   │   │   ├── exam/           # /api/exam - 2/5/10 marks answer generator
│   │   │   ├── quiz/           # /api/quiz - MCQ generator
│   │   │   ├── planner/        # /api/planner - Timetable generator
│   │   │   ├── code/           # /api/code - Code mentor & debugger
│   │   │   └── pdf/
│   │   │       ├── extract/    # /api/pdf/extract - PDF parser
│   │   │       └── qa/         # /api/pdf/qa - Grounded document QA
│   │   ├── globals.css         # Tailwind & custom styles
│   │   ├── layout.tsx          # Root HTML & Metadata
│   │   └── page.tsx            # Main application coordinator
│   ├── components/
│   │   ├── chat/               # ChatView.tsx
│   │   ├── exam/               # ExamModeView.tsx
│   │   ├── quiz/               # QuizModeView.tsx
│   │   ├── planner/            # StudyPlannerView.tsx
│   │   ├── pdf/                # NotesAssistantView.tsx
│   │   ├── code/               # CodingHelperView.tsx
│   │   ├── landing/            # LandingPage.tsx
│   │   ├── layout/             # Navbar.tsx, Sidebar.tsx, ApiKeyModal.tsx
│   │   └── ui/                 # ThemeToggle.tsx, LanguageSelector.tsx
│   └── lib/
│       ├── types.ts            # Data models & interfaces
│       ├── utils.ts            # Utility helpers
│       └── ai/
│           ├── provider.ts     # Gemini SDK + Router + Fallbacks
│           ├── prompts.ts      # Specialized academic prompts
│           └── fallback-data.ts# Offline university academic engine
├── next.config.mjs             # Next.js configuration
├── tailwind.config.ts          # Tailwind styling rules
├── tsconfig.json               # TypeScript configuration
└── package.json                # Project dependencies & scripts
```

---

## 🎓 Designed for Students, Built for Performance

AI StudyMate was created to empower college students everywhere to study with confidence, retain difficult concepts faster, and achieve top grades in their academic journey.
