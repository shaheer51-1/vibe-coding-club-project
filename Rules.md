# AI Development Rules (Rules.md)
## VibeForge 2.0 — Coding Standards, Operational Constraints & Agent Rules

**Document Version:** 1.0.0  
**Phase:** Phase 1 (Foundation & UI)  
**Author:** Antigravity Senior Software Engineer & Governance Lead  

---

### 1. Fundamental Operational Rules

1. **Rule R-001 (Zero-Runtime Constraint):** Never instruct the user to install Node.js, run `npm install`, or execute mandatory terminal commands. The application must run cleanly in any modern browser via standalone/CDN technologies or standard web file protocols (`file:///` or lightweight preview).
2. **Rule R-002 (Honesty in Implementation):** Never pretend that an unimplemented feature (such as live LLM generation, cloud database sync, or zip exporting) is functioning. Mark simulated behaviors explicitly with `"Demo Mode"` or `"Planned for Phase X"`.
3. **Rule R-003 (Preserve & Respect Existing Work):** Never perform destructive file rewrites without verifying existing code. Do not introduce breaking dependencies.
4. **Rule R-004 (Single Source of Truth):** All requirements are defined in `PRD.md`, technical architecture in `TRD.md` / `Architecture.md`, and task roadmaps in `phases.md`. Changes to functionality must be reflected across these documents.

---

### 2. Frontend & Coding Standards

1. **Rule R-005 (Component Modularity):** Keep components focused, single-responsibility, and under 300 lines where practical. Decouple UI rendering from data mock definitions.
2. **Rule R-006 (Strict Iframe Sandboxing):** All live website previews must be rendered within an isolated `<iframe>` containing `sandbox="allow-scripts allow-forms allow-same-origin"`. Never evaluate or inject arbitrary code into the parent application DOM.
3. **Rule R-007 (Accessible Interactivity):** Every interactive element (button, link, input, tab) must have:
   - Meaningful accessible names or `aria-label`.
   - Visible focus indicator (`focus:ring-2 focus:ring-violet-500`).
   - Clear hover and disabled states.
   - Genuine functional behavior (no dead/inert buttons).
4. **Rule R-008 (Design Integrity):** Strictly adhere to the VibeForge color palette:
   - Charcoal background (`#0b0d13`)
   - Surface cards (`#121622`, `#181e2e`)
   - Violet accent (`#8b5cf6`)
   - Electric Blue accent (`#3b82f6`)
   - White text with high contrast (`#f8fafc`, `#94a3b8`)
5. **Rule R-009 (Error Handling & Fallbacks):** All async operations (e.g., simulated delays, future fetch calls, clipboard copies) must incorporate comprehensive `try...catch` blocks and user-friendly visual toast notifications.

---

### 3. Supabase Integration Rules (Future Phase 3)

1. **Rule R-010 (No Blind Classification of Fetch Errors):** When connecting Supabase, never catch all exceptions and label them `RLS_OR_SCHEMA_ERROR`. Differentiate between network-level failures (`TypeError: Failed to fetch`) and PostgreSQL HTTP error codes (`42501` for RLS, `42P01` for undefined table).
2. **Rule R-011 (Mandatory RLS Verification):** Never create a table in Supabase without enabling Row Level Security (`ALTER TABLE ... ENABLE ROW LEVEL SECURITY;`) and supplying explicit `INSERT` and `SELECT` policies.
3. **Rule R-012 (Zero Secret Exposure):** Never commit or hardcode Supabase Service Role keys or database passwords in client-side code. Only the public `anon` key is permitted in browser contexts.
