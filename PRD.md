# Product Requirements Document (PRD)
## VibeForge 2.0 — AI-Powered Website Builder

**Document Version:** 1.0.0  
**Status:** Approved for Phase 1 (Foundation & UI)  
**Author:** Antigravity Senior Software Engineer & Product Architect  
**Target Audience:** Engineering, Product, UI/UX, QA  

---

### 1. Executive Summary & Problem Statement

#### 1.1 Product Overview
VibeForge is an intelligent, accessible web application designed to empower creators, developers, entrepreneurs, and students to generate, preview, customize, and export modern, responsive multi-page websites using natural language prompts.

#### 1.2 The Problem
Building web applications or landing pages currently demands extensive boilerplate setup, knowledge of HTML/CSS/JS, responsive grid systems, and hosting deployment pipelines. Existing AI builders are frequently locked behind expensive paywalls, produce rigid single-page templates, hide source code, or suffer from fragile database integrations (such as silent schema mismatches and RLS policy failures).

#### 1.3 The Solution
VibeForge provides a transparent, code-first yet no-code-friendly environment:
1. **Prompt-to-Website Workflow:** Natural language input automatically maps to semantic multi-page website code.
2. **Transparent Code & File Access:** Full visibility and editing capabilities for generated HTML, CSS, and JS files.
3. **Live Multi-Viewport Preview:** Real-time responsive testing across desktop, tablet, and mobile views.
4. **Reliable Database & Form Integration:** Dedicated, validated Supabase integration with proper Row Level Security (RLS) for contact forms and user data.
5. **Zero-Setup Accessibility:** Runs directly in modern browsers without requiring local runtime installations (e.g., Node.js) for initial exploration.

---

### 2. Goals & Non-Goals

#### 2.1 Goals (Phase 1)
- **G-001:** Deliver a modular, production-ready frontend interface with dark SaaS aesthetics.
- **G-002:** Provide an interactive Dashboard with searchable demo projects, project metadata, and empty states.
- **G-003:** Deliver a validated Website Creation workflow with prompt entry, preset pills, category selection, and explicit Demo Mode notices.
- **G-004:** Implement a complete Builder Workspace featuring a top toolbar, file explorer, responsive preview canvas (desktop/tablet/mobile), code viewer, and AI chat assistant panel.
- **G-005:** Render a realistic, multi-section sample website inside an isolated sandbox iframe.
- **G-006:** Ensure zero dependency on Node.js runtimes or terminal commands on the host machine.
- **G-007:** Establish complete architectural and technical documentation (`PRD`, `TRD`, `Architecture`, `appFlow`, `database`, `design`, `Rules`, `phases`).

#### 2.2 Non-Goals (Phase 1)
- **NG-001:** Connecting live OpenAI/Gemini/Anthropic API keys (strictly simulated/demo mode in Phase 1).
- **NG-002:** Persisting projects to Supabase Cloud or user authentication (planned for Phase 3).
- **NG-003:** Generating actual downloadable ZIP archives via client-side zip libraries (planned for Phase 4).
- **NG-004:** Live code compilation or arbitrary code execution in the parent DOM.

---

### 3. Target Personas

| Persona | Role | Primary Need | Key Constraint |
| :--- | :--- | :--- | :--- |
| **Alex (Student)** | BSCS Student / Beginner Developer | Wants to see how websites are structured (HTML/CSS/JS) and experiment with ideas without setting up heavy dev environments. | No Node.js installed; zero-budget requirement. |
| **Samantha (Founder)** | Solopreneur / Marketer | Needs high-converting landing pages generated in minutes with custom branding. | Lacks technical coding skills; needs visual refinement. |
| **David (Freelancer)** | Web Designer / Developer | Wants an AI foundation to scaffold multi-page client sites quickly with full code export. | Demands clean, readable code and ZIP export. |

---

### 4. Functional Requirements

#### 4.1 Dashboard & Project Management
- **FR-001 (Dashboard Layout):** System shall display the VibeForge logo, navigation bar, project counter, and a prominent "Create New Website" action.
- **FR-002 (Project Listing):** System shall render project cards containing project title, description, category tag, thumbnail preview placeholder, and relative timestamp.
- **FR-003 (Search & Filter):** System shall provide a real-time search input and category filter (All, Landing Page, Portfolio, E-Commerce, SaaS).
- **FR-004 (Empty State):** System shall render a dedicated empty state graphic and CTA when search queries return zero results.
- **FR-005 (Demo Data Badge):** All sample projects shall be explicitly labeled with a "Demo Project" badge.

#### 4.2 Website Creation Modal
- **FR-006 (Prompt Input):** System shall provide a multi-line natural language prompt input with character counter and clear guidance.
- **FR-007 (Prompt Validation):** System shall enforce a minimum prompt length of 10 characters before allowing creation.
- **FR-008 (Prompt Presets):** System shall offer one-click prompt pills for common types: Portfolio, SaaS Landing Page, E-Commerce, and Agency.
- **FR-009 (Type Selector):** System shall provide a website category dropdown selector.
- **FR-010 (Demo Mode Notice):** Creation interface shall explicitly inform the user: *"Demo Mode: Live AI generation will be connected in Phase 2."*
- **FR-011 (Loading State):** When creating, the button shall exhibit an animated loading spinner for 1.2 seconds before transitioning to the builder workspace.

#### 4.3 Builder Workspace
- **FR-012 (Header Toolbar):** Toolbar shall display back-to-dashboard navigation, project title, a "Saved (Demo)" status pill, viewport controls, view switcher, and an export action.
- **FR-013 (Viewport Switcher):** System shall support switching between Desktop (100% / 1200px max), Tablet (768px), and Mobile (375px) preview modes with smooth animated transitions.
- **FR-014 (View Switcher):** System shall support toggling between **Preview**, **Code**, and **Files** views, plus side-by-side mode on wide screens.
- **FR-015 (File Explorer):** System shall display a hierarchical file tree showing sample project files (`index.html`, `styles.css`, `main.js`, `about.html`, `contact.html`).
- **FR-016 (File Selection):** Clicking a file in the explorer shall switch the active file and display its corresponding sample source code in the code viewer.
- **FR-017 (Code Viewer):** System shall render line numbers, syntax highlighting cues, file metadata (size, lines), and a "Copy Code" action with clipboard confirmation.
- **FR-018 (Preview Canvas):** System shall render the active website preview inside an isolated `iframe` utilizing `srcdoc` or Blob URL for security.
- **FR-019 (AI Chat Panel):** System shall provide a collapsible right-hand AI assistant panel featuring conversation history, simulated AI responses, and quick action suggestion pills.
- **FR-020 (Export Action):** Clicking "Export" shall trigger a clear informational modal indicating that ZIP export is scheduled for Phase 4.

---

### 5. Non-Functional Requirements

- **NFR-001 (Performance):** Initial application bundle and UI shall render within 1.5 seconds in modern browsers.
- **NFR-002 (Zero Local Runtime):** Application must operate entirely in standard web browsers without requiring Node.js, npm, or CLI dependencies on the user's host machine.
- **NFR-003 (Security & Isolation):** Previews must run within an isolated `<iframe>` with `sandbox="allow-scripts allow-forms allow-same-origin"` to avoid polluting parent application state.
- **NFR-004 (Accessibility):** Color contrast shall meet WCAG 2.1 AA standards (minimum 4.5:1 for normal text). Interactive elements must support keyboard tab navigation and focus rings.
- **NFR-005 (Responsiveness):** UI shall adapt fluidly across screen widths from 320px to 2560px.
- **NFR-006 (Visual Excellence):** Interface shall follow a dark theme with `#0b0d13` background, `#121622` card containers, violet `#8b5cf6`, electric blue `#3b82f6` accents, and subtle borders.

---

### 6. Scope Boundaries & Traceability Matrix

| Feature | Phase 1 (Current) | Phase 2 | Phase 3 | Phase 4 |
| :--- | :--- | :--- | :--- | :--- |
| **UI & Layout** | Complete & Functional | Iterated | Iterated | Iterated |
| **Search & Filtering** | Complete (Local State) | Persisted | Persisted | Persisted |
| **Sample Website Preview** | Complete (Multi-section) | Dynamic AI generated | Cloud loaded | Exportable |
| **Viewport Switching** | Complete (Desktop/Tablet/Mobile) | Maintained | Maintained | Maintained |
| **File Tree & Code Viewer** | Complete (Interactive Sample Files) | Editable | Sync to DB | Included in ZIP |
| **AI Generation Engine** | Demo Mode / Simulated | Live LLM API | Custom Agents | Fine-tuned prompts |
| **Supabase Cloud DB & Auth** | Out of Scope | Out of Scope | Active & Validated | Production RLS |
| **ZIP Export** | Informational Modal | Out of Scope | Out of Scope | JSZip Engine |
