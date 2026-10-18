cd "C:/temp/claude/d--Rubiks-portfolio/d752e13d-d5c1-4074-80b7-7bdad1c1b368/scratchpad" && cat > readme-fix.mjs <<'EOF'
import fs from "fs";
const p = "github-profile-README.md";
let s = fs.readFileSync(p, "utf8");
const rep = (a, b) => { if (!s.includes(a)) throw new Error("missing: " + a.slice(0, 70)); s = s.replace(a, b); };

// Header + typing: full-stack first
rep("desc=Full%20Stack%20AI%20Developer%20%E2%80%A2%20AI%20Agents%20%E2%80%A2%20Automation", "desc=Full-Stack%20Engineer%20%E2%80%A2%20AI%20Developer");
rep("lines=%24+whoami+%E2%86%92+Full+Stack+AI+Developer+%40+GAC;Next.js+%C2%B7+NestJS+%C2%B7+Node.js+%C2%B7+Python;LLM+agents+%C2%B7+RAG+%C2%B7+function+calling;GoHighLevel+%C2%B7+n8n+%C2%B7+Make+%C2%B7+Zapier;",
    "lines=%24+whoami+%E2%86%92+Full+Stack+AI+Developer+%40+GAC;Next.js+%C2%B7+React+%C2%B7+NestJS+%C2%B7+Node.js+%C2%B7+TypeScript;Production+APIs%2C+real-time+apps+%26+Stripe+billing;LLM+apps+%C2%B7+RAG+%C2%B7+AI+agents;");

rep(`→ Building LLM-powered AI agents & automation workflows at Get AI Chatbots (GAC)
→ Shipping with Next.js, Node.js/Python, GoHighLevel and n8n
→ Deploying on Azure, AWS and Replit`, `→ Full Stack AI Developer at Get AI Chatbots (GAC)
→ Building full-stack apps with Next.js, Node.js and Python, with AI built in
→ Deploying on Azure, AWS and Replit`);
rep("AI agents · RAG · function calling · GHL & n8n automation · Stripe billing · real-time apps",
    "Next.js & NestJS · API design · real-time apps · Stripe billing · LLM apps & RAG · GHL & n8n");

rep("I build **full-stack products, AI agents and business automations that ship**: from Next.js and NestJS apps to GoHighLevel and n8n workflows that capture, qualify and follow up with leads.",
    "I'm a **full-stack engineer who builds AI into real products**. Most of my work is end-to-end web apps (Next.js and React on the front, NestJS and Node.js on the back, Postgres or MongoDB underneath) with LLM features, payments and integrations where they add value.");

rep(`- LLM agents for lead handling, booking and support
- RAG systems and LLM function calling
- GHL / n8n / Make / Zapier automations, plus custom code where no-code stops
- Production full-stack apps with Next.js + NestJS`, `- Production full-stack apps with Next.js + NestJS
- Clean APIs, real-time features and payments
- AI features: LLM agents, RAG and function calling
- Integrations & automation (GHL, n8n) when a project needs them`);

// Replace AI-flow diagram with a full-stack architecture view
const a = s.indexOf("## 🔁 How I build an AI automation");
const b = s.indexOf("## 🛠️ Tech stack");
s = s.slice(0, a) + `## 🏗️ How I usually build

\`\`\`mermaid
flowchart LR
    U([User]) --> FE[Next.js / React<br/>frontend]
    FE --> API[NestJS / Node.js<br/>API]
    API --> DB[(PostgreSQL · MongoDB<br/>via Prisma)]
    API --> RT[WebSockets<br/>real-time]
    API --> PAY[Stripe<br/>billing]
    API --> AI[LLM services<br/>agents · RAG]
    API --> INT[Integrations<br/>GHL · n8n · email]
\`\`\`

` + s.slice(b);

// Stats on separate lines + working contribution chart
const c = s.indexOf("## 📈 GitHub activity");
const d = s.indexOf("## 🎤 Beyond the code");
s = s.slice(0, c) + `## 📈 GitHub activity

<p align="center">
  <img width="560" src="https://streak-stats.demolab.com/?user=anasfazalawan&theme=tokyonight&hide_border=true&background=0d1117&ring=a78bfa&fire=f0abfc&currStreakNum=a78bfa" />
</p>

<p align="center">
  <img width="560" src="https://github-readme-stats.vercel.app/api/top-langs/?username=anasfazalawan&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=a78bfa&card_width=560" />
</p>

<p align="center">
  <img width="100%" src="https://ghchart.rshah.org/a78bfa/anasfazalawan" alt="GitHub contribution chart" />
</p>

` + s.slice(d);

rep("**AI agents · GHL & n8n automation · full-stack web apps · talks & workshops**",
    "**Full-stack web apps · AI development · automation (GHL & n8n) · talks & workshops**");
rep("I also give **talks and hands-on workshops** on AI agents, automation and building with LLMs.",
    "I also give **talks and hands-on workshops** on full-stack development and building with AI.");
fs.writeFileSync(p, s);
EOF
node readme-fix.mjs && grep -n "AI automation\|activity-graph\|AI agents · GHL" github-profile-README.md; echo "---ok"
