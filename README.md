<!-- README.md (KaBuM-Web-App-Testing) — generated September 18, 2025 -->
<!-- All content below is plain Markdown + HTML (inline CSS) so it renders nicely on GitHub -->

<!-- ====== Title Card ====== -->
<div align="center" style="font-family: ui-sans-serif, system-ui, 'Segoe UI', Roboto; line-height:1.55; color:#e5e7eb; background:#0b1220; padding:24px; border-radius:16px; border:1px solid #1f2a44;">
  <h1 style="margin:0 0 6px; font-size:34px;">🧪 KaBuM! Web App — SQA Test Repository</h1>
  <p style="margin:0; opacity:.9;">Functional · API · UI · Performance · Traceability</p>
  <p style="margin:12px 0 0 0;">
    <img alt="Status" src="https://img.shields.io/badge/Repo-Audit%20Complete-22C55E" />
    <img alt="Tests" src="https://img.shields.io/badge/API-Postman%20Collection-38BDF8" />
    <img alt="Artifacts" src="https://img.shields.io/badge/Docs-Test%20Plan%20%26%20Cases-8B5CF6" />
    <img alt="License" src="https://img.shields.io/badge/License-MIT-10B981" />
  </p>
</div>

<!-- ====== Inline Color Legend (per your scheme) ====== -->
<div align="center" style="margin-top:10px; font-size:13px;">
  <b style="color:#FB923C;">📊 Step</b> ·
  <b style="color:#38BDF8;">🎯 Result</b> ·
  <b style="color:#F472B6;">⚡ Decision</b> ·
  <b style="color:#FACC15;">🟨 Metrics</b> ·
  <b style="color:#A78BFA;">🟪 Transform</b> ·
  <b style="color:#22C55E;">🟩 Success</b> ·
  <b style="color:#F87171;">🟥 Risk</b>
</div>

---

## 📌 Overview

This repository contains a **curated SQA test suite** for the Brazilian e-commerce site <a href="https://www.kabum.com.br/">KaBuM!</a>. It currently focuses on **API sanity checks** and **test documentation** (Test Plan & Test Cases). Sections for UI automation and JMeter performance tests are scaffolded for future work.

> <b style="color:#22C55E;">🟩 Current status</b>: Repository files verified and documented (1:1) as of <b>September 18, 2025</b>.<br>
> <b style="color:#F87171;">🟥 Note</b>: A few CI/automation scripts contain placeholder ellipses (<code>...</code>) and need completion before use.

---

## 🧭 Table of Contents
- <a href="#-repository-structure">Repository Structure</a>
- <a href="#-artifacts--what-you-can-open-now">Artifacts — What you can open now</a>
- <a href="#-api-tests-postman--newman">API Tests (Postman / Newman)</a>
- <a href="#-ui--performance-scaffolds">UI & Performance (Scaffolds)</a>
<!-- - <a href="#-cicd-sync-google-sheet-to-excel">CI/CD — Sync Google Sheet to Excel</a> -->
<!-- - <a href="#-audit--1%3a1-match-with-files">Audit — 1:1 Match with Files</a> -->
- <a href="#-missing-items--fix-checklist">Missing Items / Fix Checklist</a>
- <a href="#-license">License</a>

---

## 📂 Repository Structure

```text
├─ .github/
│  ├─ workflows/
│  │  ├─ sheet-to-excel.yml
├─ API Testing/
│  ├─ KaBuM API Testing.postman_collection.json
├─ Load Testing/
│  └─ (empty)
├─ scripts/
│  ├─ export_to_xlsx.py
├─ Test Cases/
│  ├─ KaBuM Web Testing.pdf
│  ├─ KaBuM Web Testing.xlsx
├─ Test Plan/
│  ├─ KaBuM Test Plan.docx
│  ├─ KaBuM Test Plan.pdf
├─ LICENSE
├─ README.md
```
<!-- ====== README snippet (HTML+CSS inline; GitHub-compatible) ====== -->
<!-- Copy-paste directly into your README.md -->

<!-- ====== Artifacts — What you can open now ====== -->
<section id="artifacts" style="font-family: ui-sans-serif, system-ui, 'Segoe UI', Roboto; line-height:1.55;">
  <h2 id="-artifacts--what-you-can-open-now" style="margin:0 0 10px; font-size:22px; color:#111827;">
    📦 Artifacts — <span style="font-weight:600;">What you can open now</span>
  </h2>
  <ul style="margin:0 0 14px 18px; padding:0;">
    <li style="margin:6px 0;">
      <b>Test Plan</b>:
      <code>Test Plan/KaBuM Test Plan.pdf</code>
      <span style="color:#374151;">(authoritative project scope, approach, risks, schedule). The <code>.docx</code> source is included for edits.</span>
    </li>
    <li style="margin:6px 0;">
      <b>Test Cases</b>:
      <code>Test Cases/KaBuM Web Testing.xlsx</code>
      <span style="color:#374151;">(with a matching PDF for quick viewing).</span>
    </li>
    <li style="margin:6px 0;">
      <b>API Collection</b>:
      <code>API Testing/KaBuM API Testing.postman_collection.json</code>
      <span style="color:#374151;">(3 requests; see below).</span>
    </li>
    <li style="margin:6px 0;">
      <b>License</b>:
      <span style="color:#374151;">MIT (see bottom of this README).</span>
    </li>
  </ul>

  <div style="background:#0b1220; color:#e5e7eb; padding:10px 12px; border-radius:10px; border:1px solid #1f2a44;">
    <b style="color:#22C55E;">🟩 Tip</b>:
    <span>You can import the Postman collection directly or run it headless via <code>newman</code>.</span>
  </div>
</section>

<hr style="border:none; border-top:1px solid #e5e7eb; margin:18px 0 14px;" />

<!-- ====== API Tests (Postman / Newman) ====== -->
<section id="-api-tests-postman--newman" style="font-family: ui-sans-serif, system-ui, 'Segoe UI', Roboto; line-height:1.55;">
  <h2 style="margin:0 0 10px; font-size:22px; color:#111827;">🧪 API Tests (Postman / Newman)</h2>

  <p style="margin:0 0 6px;">
    <b>Collection name:</b>
    <code>KaBuM API Testing</code><br />
    <b>Requests (3):</b>
  </p>
  <ul style="margin:0 12px 12px 18px; padding:0;">
    <li style="margin:4px 0;">User/Get authenticated user</li>
    <li style="margin:4px 0;">Collections/Search items</li>
    <li style="margin:4px 0;">LandingPage – Availability – 200 OK</li>
  </ul>

  <h3 style="margin:12px 0 8px; font-size:18px; color:#111827;">Run with Postman (GUI)</h3>

  <p style="margin:6px 0;">
    <b style="color:#FB923C;">📊 Step:</b>
    <span>Import the JSON file from <code>API Testing/</code> → run folder/single requests.</span><br />
    <b style="color:#38BDF8;">🎯 Result:</b>
    <span>Validate availability of landing page and core search/user endpoints.</span>
  </p>
</section>

<h3 style="margin:12px 0 8px; font-size:18px; color:#111827;">Run with Newman (CLI)</h3>

  #### Install
  ```bash
    npm install -g newman
  ```
  #### Run collection (basic)
  ```bash
    newman run "API Testing/KaBuM API Testing.postman_collection.json" --reporters cli,htmlextra
  ```
  #### Save HTML report
  ```bash
    newman run "API Testing/KaBuM API Testing.postman_collection.json" -r htmlextra --reporter-htmlextra-export
  ```
  ```bash
    reports/api-run.html
  ```

  <!-- ====== README Sections (HTML+CSS inline; GitHub-compatible) ====== -->
<!-- Copy-paste directly into your README.md -->

<!-- ========== UI & Performance (Scaffolds) ========== -->
<section id="-ui--performance-scaffolds" style="font-family: ui-sans-serif, system-ui, 'Segoe UI', Roboto; line-height:1.6; color:#111827;">
  <h2 style="display:flex; align-items:center; gap:.6rem; margin:0 0 10px; font-size:22px;">
    <span style="font-size:22px;">🧭</span>
    <span>UI &amp; Performance (Scaffolds)</span>
  </h2>

  <ul style="margin:0 0 12px 18px; padding:0;">
    <li style="margin:6px 0;">
      <b>UI Automation</b>:
      <span style="color:#374151;">Not yet committed. Recommended stacks:
        <b>Playwright</b> or <b>Selenium + PyTest</b>. Keep specs under <code>ui-tests/</code>.</span>
    </li>
    <li style="margin:6px 0;">
      <b>Performance (JMeter)</b>:
      <span style="color:#374151;"><code>Load Testing/</code> is currently empty. Add <code>.jmx</code> test plans and save HTML dashboard under <code>Load Testing/reports/</code>.</span>
    </li>
  </ul>

  <div style="margin-top:10px; background:#0b1220; color:#e5e7eb; padding:12px 14px; border-radius:10px; border:1px solid #1f2a44;">
    <b style="color:#F472B6;">⚡ Decision</b>:
    <span>Start with smoke-level UI flows (search, PDP open, add-to-cart) and a single JMeter smoke (landing page) before expanding.</span>
  </div>
</section>

<hr style="border:none; border-top:1px solid #e5e7eb; margin:18px 0 14px;" />

<!-- ====== README sections (HTML+CSS inline; GitHub-compatible) ====== -->
<!-- Paste directly into README.md -->

<!-- ✅ Missing Items / Fix Checklist -->
<section id="-missing-items--fix-checklist" style="font-family: ui-sans-serif, system-ui, 'Segoe UI', Roboto; line-height:1.55; margin-top:8px;">
  <h2 style="display:flex; align-items:center; gap:10px; margin:0 0 12px; font-size:22px; color:#111827;">
    <span style="display:inline-flex; width:22px; height:22px; border-radius:6px; background:#22C55E; box-shadow: inset 0 0 0 2px rgba(0,0,0,.12);"></span>
    <span>Missing Items / Fix Checklist</span>
  </h2>
  <ul style="list-style:none; padding:0; margin:0 0 8px 0;">
    <li style="margin:8px 0; display:flex; gap:10px;">
      <input type="checkbox" disabled style="accent-color:#111827; margin-top:3px;" />
      <div>
        <b>Complete CI code</b>: Replace <code>...</code> in both workflow and script with working versions (Appendix A/B).
      </div>
    </li>
    <li style="margin:8px 0; display:flex; gap:10px;">
      <input type="checkbox" disabled style="accent-color:#111827; margin-top:3px;" />
      <div>
        <b>Newman report</b>: Add <code>reports/api-run.html</code> from a sample run.
      </div>
    </li>
    <li style="margin:8px 0; display:flex; gap:10px;">
      <input type="checkbox" disabled style="accent-color:#111827; margin-top:3px;" />
      <div>
        <b>UI tests</b>: Add Playwright tests under <code>ui-tests/</code> (smoke flows first).
      </div>
    </li>
    <li style="margin:8px 0; display:flex; gap:10px;">
      <input type="checkbox" disabled style="accent-color:#111827; margin-top:3px;" />
      <div>
        <b>JMeter</b>: Add <code>Load Testing/main.jmx</code> and a sample HTML dashboard under <code>Load Testing/reports/</code>.
      </div>
    </li>
    <li style="margin:8px 0; display:flex; gap:10px;">
      <input type="checkbox" disabled style="accent-color:#111827; margin-top:3px;" />
      <div>
        <b>Traceability</b>: Add <code>docs/traceability-matrix.xlsx</code> mapping Test Plan ↔ Test Cases ↔ Runs.
      </div>
    </li>
    <li style="margin:8px 0; display:flex; gap:10px;">
      <input type="checkbox" disabled style="accent-color:#111827; margin-top:3px;" />
      <div>
        <b>Badges</b>: Optionally add CI status + report badges after CI is green.
      </div>
    </li>
  </ul>

  <div style="margin-top:10px; padding:10px 12px; border-radius:10px; background:#0b1220; color:#e5e7eb; border:1px solid #1f2a44;">
    <b style="color:#22C55E;">🟩 When these are done</b>, the repo will be fully demonstrable to recruiters: docs, runnable API checks, and CI artifacts.
  </div>

  <hr style="border:none; border-top:1px solid #e5e7eb; margin:18px 0 12px;" />

  <!-- 📄 License -->
  <h2 id="-license" style="margin:0 0 10px; font-size:22px; color:#111827;">📄 License</h2>
  <p style="margin:0;">
    This project is licensed under the <b style="color:#111827;">MIT License</b> — see <code><a href="LICENSE">LICENSE</a></code> for details.
  </p>
</section>
