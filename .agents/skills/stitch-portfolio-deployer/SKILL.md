---
name: stitch-portfolio-deployer
description: Comprehensive end-to-end skill to build, customize, and deploy executive professional portfolios using Google Stitch via Model Context Protocol (MCP), localhost live preview, and 1-click GitHub Pages deployment.
metadata:
  icon: rocket_launch
---

# Stitch-to-GitHub Portfolio Engineering Skill

This skill captures the end-to-end methodology for transforming raw career credentials, resumes, and Google Stitch UI designs into a live, production-grade personal website hosted for free on GitHub Pages.

---

## 🎯 The 6-Phase Engineering Pipeline

```
┌────────────────────────┐      ┌────────────────────────┐      ┌────────────────────────┐
│ Phase 1: Positioning   │ ──>  │ Phase 2: Stitch MCP    │ ──>  │ Phase 3: Customization │
│ Resume & Superpower    │      │ Connect & Pull Design  │      │ Photo, Links, Branding │
└────────────────────────┘      └────────────────────────┘      └────────────────────────┘
            │                                                                │
            ▼                                                                ▼
┌────────────────────────┐      ┌────────────────────────┐      ┌────────────────────────┐
│ Phase 6: LinkedIn Live │ <──  │ Phase 5: GitHub Pages  │ <──  │ Phase 4: Localhost     │
│ Add Link to Profile    │      │ Zero-Cost SSL Launch   │      │ Live Inspection (3000) │
└────────────────────────┘      └────────────────────────┘      └────────────────────────┘
```

---

## Phase 1: Career Discovery & Functional Positioning

1. **Extract Authentic Experience:**
   - Ingest raw LinkedIn profile, CV, and actual project backlog items.
   - Map exact organizational hierarchy (e.g., Groups of companies, Partner culture, corporate conglomerates).
2. **Define the Candidate's True Superpower (Avoid Title Inflation):**
   - Differentiate official designations (e.g., *Functional Consultant*) from technical ecosystem roles (e.g., *Solution Architect*).
   - Frame the candidate's superpower honestly: e.g., *"Business Model & Calculation Designer who bridges business stakeholders and developers by structuring airtight functional logic without guesswork."*
3. **Catalog Interconnected Functional Domains:**
   - Group competencies into 10 enterprise modules: Commercial (O2C), Logistics (Distribution), Inventory (Costing/Valuation), Procurement (P2P), Financials (Posting Groups/GL), HRM (Portal Integration), Trade (LC/Import), Production (BOMs), Fleet (Transportation), and Approval Governance.

---

## Phase 2: Google Stitch Connection via MCP

1. **Configure MCP Server (`mcp_config.json`):**
   - Obtain the Google Stitch MCP configuration with API key:
     ```json
     {
       "mcpServers": {
         "stitch": {
           "url": "https://stitch.googleapis.com/mcp",
           "serverUrl": "https://stitch.googleapis.com/mcp",
           "headers": {
             "X-Goog-Api-Key": "<STITCH_API_KEY>"
           }
         }
       }
     }
     ```
   - Store in `~/.gemini/config/mcp_config.json`.
2. **Query Stitch Tools via JSON-RPC:**
   - `list_screens` with `projectId: "<STITCH_PROJECT_ID>"`.
   - Identify the exact desktop/responsive target screen resource ID.
3. **Download HTML Source:**
   - Call `download_file` with the screen's `html_code.name` resource path.
   - Extract raw HTML into `index.html`.

---

## Phase 3: Asset & Content Customization

1. **Profile Media Optimization:**
   - Copy real uploaded profile photograph into `assets/profile.jpg`.
   - Embed at **medium size** (`w-20 h-20` to `w-24 h-24` in hero, `w-10 h-10` in header) with status ring.
2. **Copywriting & Positioning Rewrites:**
   - Replace generic template text with exact real-world project artifacts:
     - Android SFA Mobility Engine (TSO/DSM/RSM dashboards, offline SQLite sync, GPS arrow tracking).
     - HRM Portal Integration (Leave balance, penalty omission request form, notice-period salary automation, G/L manpower budget limits).
   - Replace any unearned architectural buzzwords with accurate functional consultant language.
3. **Interactive Utilities:**
   - Implement 1-click clipboard copy for email with visual feedback.
   - Hook up direct LinkedIn URL, telephone, and `mailto:` action triggers.

---

## Phase 4: Localhost Live Preview Testing

1. **Start Non-Blocking Preview Server:**
   - Execute:
     ```powershell
     python -m http.server 3000
     ```
   - Verify HTTP status:
     ```powershell
     Invoke-WebRequest -Uri "http://localhost:3000" -UseBasicParsing
     ```
2. **Quality Checklist:**
   - [ ] Profile photo renders sharply without distortion.
   - [ ] All anchor jump links (`#overview`, `#core-erp`, `#mobility-sfa`, `#artifacts`) scroll smoothly.
   - [ ] Mobile responsive layout collapses cleanly on narrow viewports.
   - [ ] Clipboard copy function works on all devices.

---

## Phase 5: GitHub Pages 1-Click Deployment

1. **Unified Brand Naming Rule:**
   - Ensure the GitHub username matches the LinkedIn handle (e.g., `mohammadabidmiah`).
   - The repository name MUST be:  
     👉 **`<username>.github.io`**  
     *(This ensures the root URL `https://<username>.github.io` with no trailing directory paths).*
2. **Git Initialization:**
   ```powershell
   git init
   git branch -M main
   git add .
   git commit -m "Launch official enterprise portfolio"
   git remote add origin https://github.com/<username>/<username>.github.io.git
   ```
3. **Interactive Push Automation (`push_to_github.bat`):**
   - Provide a double-clickable batch file to trigger the native Git Credential Manager browser login on Windows without command-line authentication hurdles.
4. **GitHub Pages Activation:**
   - In GitHub: **Repository Settings** &rarr; **Pages**.
   - Under **Build and deployment**, set Source to **Deploy from a branch** &rarr; Branch: **`main`** / `/(root)`.
   - Click **Save**.

---

## Phase 6: Production Verification & LinkedIn Showcasing

1. **Live Production HTTP Probe:**
   ```powershell
   Invoke-WebRequest -Uri "https://<username>.github.io" -UseBasicParsing
   Invoke-WebRequest -Uri "https://<username>.github.io/assets/profile.jpg" -UseBasicParsing
   ```
2. **LinkedIn Profile Integration:**
   - Edit Intro &rarr; **Custom Website Link**.
   - URL: `https://<username>.github.io`
   - Link Text: **`ERP Implementation Portfolio`** or **`Official Portfolio`**.
