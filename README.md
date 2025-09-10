# <!-- Title -->
<div align="center" style="padding:18px;border:2px solid #38BDF8;border-radius:14px;">
  <h1 style="margin:0;font-size:34px;line-height:1.2;">🧪 SQA Test Suite — E-commerce Web App (KaBuM!)</h1>
  <p style="margin:6px 0 0 0;font-size:15px;opacity:.92;">Functional • API • UI • Performance • Compatibility • Accessibility</p>
  <p style="margin:10px 0 0 0;">
    <img alt="Made with Postman" src="https://img.shields.io/badge/Postman-API%20Tests-orange">
    <img alt="Perf: JMeter" src="https://img.shields.io/badge/JMeter-Performance-blue">
    <img alt="UI: Selenium/Playwright" src="https://img.shields.io/badge/UI-Selenium%2FPlaywright-purple">
    <img alt="License" src="https://img.shields.io/badge/License-MIT-green">
  </p>
</div>

<p align="center" style="margin-top:12px;">
  <b>বাংলা Quick Start নিচে আছে — keep scrolling.</b>
</p>

---

## 📜 Overview

<div style="border-left:6px solid #38BDF8;padding:10px 14px;border-radius:8px;background:#f8fbff;">
This repository provides a complete, reproducible <b>SQA testing toolkit</b> for a retail e-commerce site (tested with KaBuM! as a real-world case).
It includes <b>API collections (Postman/Newman)</b>, <b>UI test stubs (Selenium/Playwright)</b>, <b>performance plans (JMeter)</b>, data-driven test assets, and automated <b>HTML reports</b>.
</div>

> 🔴 <span style="color:#F87171"><b>Disclaimer:</b></span> All tests target <b>public pages/endpoints</b> for learning purposes. Do not attack, overload, or break TOS/rate limits. Use staging/mocks wherever possible.

---

## 🧭 Table of Contents
- [Features](#-features)
- [Repository Structure](#-repository-structure)
- [Quick Start](#-quick-start)
- [Configuration & Environments](#-configuration--environments)
- [Test Coverage](#-test-coverage)
- [Run Guides](#-run-guides)
  - [API (Postman/Newman)](#api-postmannewman)
  - [Performance (JMeter)](#performance-jmeter)
  - [UI (Selenium-or-Playwright)](#ui-selenium-or-playwright)
- [Reporting](#-reporting)
- [Traceability Matrix](#-traceability-matrix)
- [CI/CD (GitHub Actions)](#cicd-github-actions)
- [Screenshots](#-screenshots)
- [Contributing](#-contributing)
- [License](#-license)
- [Bangla Quick Start](#-bangla-quick-start)

---

## 🌟 Features

<ul style="list-style:none;padding-left:0;margin-left:0;">
  <li>✅ <b>Functional UI & API flows</b>: Registration, Login, Search, PDP, Cart, Checkout.</li>
  <li>✅ <b>Data-driven tests</b> with CSV/JSON datasets.</li>
  <li>✅ <b>Performance tests</b> with realistic ramp-up, assertions, and HTML dashboards.</li>
  <li>✅ <b>Structured reports</b> (Newman HTML, JMeter dashboard) saved per run.</li>
  <li>✅ <b>Traceability</b> from Requirements → Test Cases → Results.</li>
  <li>✅ <b>Extensible</b> UI stubs for Selenium/Playwright.</li>
</ul>

---

## 📂 Repository Structure

<pre>
.
|-- 📁 Test Cases
|   |-- 📄 KaBuM Web Testing.xlsx
|   |-- 📄 KaBuM Web Testing.pdf
|-- 📁 Test Plan
|-- 📁 API Testing
|   |-- 📄 KaBuM API Testing.postman_collection.json
|-- 📁 Load Testing
|-- 📄 README.md
</pre>

---

## ⚙️ Quick Start

<div style="border:2px dashed #FB923C;border-radius:12px;padding:12px;">
  <div style="font-weight:700;color:#FB923C;">📊 Step 1 — Prerequisites</div>
  <ul>
    <li>Node.js (18+), <code>npm</code>, <code>newman</code>, <code>newman-reporter-htmlextra</code></li>
    <li>Apache JMeter (5.6+)</li>
    <li>Java 11+ (for JMeter) • Optional: Python 3.10+ (helpers)</li>
  </ul>

  <div style="font-weight:700;color:#FB923C;">📊 Step 2 — Install CLI Tools</div>
  <pre><code>npm i -g newman newman-reporter-htmlextra</code></pre>

  <div style="font-weight:700;color:#FB923C;">📊 Step 3 — First API Run</div>
  <pre><code>newman run postman/ecommerce_collection.json \
  -e postman/ecommerce_environment.json \
  -r htmlextra --reporter-htmlextra-export "reports/$(date +%F_%H-%M)/newman.html"</code></pre>

  <div style="font-weight:700;color:#22C55E;">✅ Expected</div>
  <div>HTML report at <code>reports/&lt;timestamp&gt;/newman.html</code> with pass % ≥ 95%.</div>
</div>

---

## 🔐 Configuration & Environments

- <b>Base URL</b> (public site): <code>https://www.kabum.com.br/</code> (read-only browsing/search only)
- <b>Environment Vars (Postman)</b>:
  ```json
  {
    "baseUrl": "https://www.kabum.com.br",
    "searchTerm": "ssd",
    "timeoutMs": 10000
  }
  ```
- <b>Rate Limits</b>: add delays for pagination; avoid tight loops.
- <b>Sensitive Data</b>: never commit real credentials/tokens.

<div style="margin-top:8px;padding:10px;border-left:6px solid #FACC15;background:#fffbea;border-radius:8px;">
  <b style="color:#FACC15;">🟨 Tip:</b> For dynamic search terms, use a pre-request script to randomize <code>q</code>.
</div>

---

## 🧪 Test Coverage

### Scope & Modules
- <b>Registration & Login</b>, <b>Search & Filters</b>, <b>Product Detail (PDP)</b>, <b>Cart</b>, <b>Checkout</b>, <b>Order Summary</b>
- <b>Non-functional:</b> Performance (load), Compatibility (Chrome/Firefox/Brave), Accessibility (basic checks)

### Types of Testing
- <b>Functional (UI/API)</b>, <b>Integration (chained API flows)</b>, <b>Performance (JMeter)</b>, <b>Smoke/Regression</b>, <b>Usability & A11y (basic)</b>

### Entry/Exit Criteria
- <span style="color:#22C55E;font-weight:700;">Entry</span>: environment reachable, datasets loaded, smoke suite ≥ 90% pass
- <span style="color:#22C55E;font-weight:700;">Exit</span>: critical defects = 0, overall pass ≥ 95%, P95 < 2.5s (search), error% < 1%

---

## ▶️ Run Guides

### API (Postman/Newman)

<b>Chained user flow (Search → PDP → Cart):</b>
1. <code>GET /?q={{searchTerm}}</code> capture SKU
2. <code>GET /produto/{{sku}}</code> assert 200 & title contains brand
3. <code>POST /cart/add</code> mock call or UI step (avoid real purchase)

<b>Run with HTML report:</b>
```bash
newman run postman/ecommerce_collection.json \
  -e postman/ecommerce_environment.json \
  -r htmlextra --reporter-htmlextra-export "reports/$(date +%F_%H-%M)/newman.html" \
  --delay-request 250
```

<b>CSV data run:</b>
```bash
newman run postman/ecommerce_collection.json \
  -e postman/ecommerce_environment.json \
  --iteration-data data/products.csv \
  -r htmlextra --reporter-htmlextra-export "reports/$(date +%F_%H-%M)/newman.html"
```

---

### Performance (JMeter)

<b>Plan</b>: <code>kabum_testplan.jmx</code>
- Thread Group: ramp 10 → 300 (15 min), hold 10 min
- Assertions: P95 < 2500 ms; Error% < 1%
- Think Time: 500–1500 ms

<b>Run & generate dashboard:</b>
```bash
jmeter -n -t jmeter/kabum_testplan.jmx \
  -l reports/$(date +%F_%H-%M)/results.jtl \
  -e -o reports/$(date +%F_%H-%M)/jmeter-dashboard
```

---

### UI (Selenium or Playwright)

<b>Playwright quickstart (TypeScript):</b>
```bash
cd ui-tests/playwright
npm i
npx playwright test --reporter=list,html --output=../../reports/$(date +%F_%H-%M)/playwright
```

<b>Selenium (Python) skeleton:</b>
```bash
cd ui-tests/selenium
python -m venv venv && source venv/bin/activate
pip install -r requirements.txt
pytest -q --html=../../reports/$(date +%F_%H-%M)/selenium.html
```

> 🔴 <span style="color:#F87171">Never automate real payments.</span> Use mocks/stubs or stop at order review.

---

## 🎯 Reporting

<div style="border-left:6px solid #38BDF8;padding:10px 14px;border-radius:8px;background:#f8fbff;">
<b>Artifacts per run (timestamped):</b><br>
• <b>Newman:</b> <code>reports/&lt;ts&gt;/newman.html</code><br>
• <b>JMeter:</b> <code>reports/&lt;ts&gt;/jmeter-dashboard/index.html</code><br>
• <b>UI:</b> <code>reports/&lt;ts&gt;/playwright</code> or <code>selenium.html</code>
</div>

<b>🎯 Outcome (Blue):</b>
- Pass% ≥ 95% overall
- No critical/sev-1 defects open
- Performance targets met on P95/P99

<b>⚡ Decision (Pink):</b>
- Promote to regression baseline if all targets are met
- Else: create bug tickets, re-run focused suites

---

## 🧩 Traceability Matrix

<table style="width:100%;border-collapse:collapse;">
  <thead>
    <tr style="background:#f1f5ff;">
      <th style="border:1px solid #e5e7eb;padding:8px;">Requirement</th>
      <th style="border:1px solid #e5e7eb;padding:8px;">Test Case(s)</th>
      <th style="border:1px solid #e5e7eb;padding:8px;">Type</th>
      <th style="border:1px solid #e5e7eb;padding:8px;">Status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="border:1px solid #e5e7eb;padding:8px;">R-001 Search results show relevant items</td>
      <td style="border:1px solid #e5e7eb;padding:8px;">TC-001, TC-002</td>
      <td style="border:1px solid #e5e7eb;padding:8px;">API + UI</td>
      <td style="border:1px solid #e5e7eb;padding:8px;color:#22C55E;"><b>Passed</b></td>
    </tr>
    <tr>
      <td style="border:1px solid #e5e7eb;padding:8px;">R-004 Add to Cart from PDP</td>
      <td style="border:1px solid #e5e7eb;padding:8px;">TC-010</td>
      <td style="border:1px solid #e5e7eb;padding:8px;">UI</td>
      <td style="border:1px solid #e5e7eb;padding:8px;color:#22C55E;"><b>Passed</b></td>
    </tr>
    <tr>
      <td style="border:1px solid #e5e7eb;padding:8px;">R-007 Performance: P95 &lt; 2.5s (search)</td>
      <td style="border:1px solid #e5e7eb;padding:8px;">PT-003</td>
      <td style="border:1px solid #e5e7eb;padding:8px;">Perf</td>
      <td style="border:1px solid #e5e7eb;padding:8px;color:#F87171;"><b>At Risk</b></td>
    </tr>
  </tbody>
</table>

---

## 🛠 Example Test Case (Concise Format)

<div style="border:1px solid #e5e7eb;border-radius:12px;padding:12px;">
<b>TC_ID:</b> TC-010
<b>Module:</b> Registration
<b>Type of Testing:</b> Functional
<b>Feature:</b> Signup
<b>Description:</b> Verify that the Signup user information form accepts valid data
<b>Expected Result:</b> Account created and confirmation shown (no PII stored)
<b>Test Data:</b> (use <code>data/users.csv</code>)
<b>Steps:</b> Open signup → fill valid fields → submit → verify success message
</div>

> 🟪 <span style="color:#A78BFA">Preprocessing (Purple):</span> randomize emails like <code>user+{{timestamp}}@example.com</code> to avoid duplicates.

---

## 🤖 CI/CD (GitHub Actions)

```yaml
name: sqa-ci
on: [push, pull_request]
jobs:
  api_and_perf:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: '20' }
      - run: npm i -g newman newman-reporter-htmlextra
      - name: Run Newman
        run: |
          mkdir -p reports/ci
          newman run postman/ecommerce_collection.json \
            -e postman/ecommerce_environment.json \
            -r htmlextra --reporter-htmlextra-export "reports/ci/newman.html" \
            --delay-request 250
      - name: Setup JMeter
        run: sudo apt-get update && sudo apt-get install -y openjdk-11-jre-headless
      - name: Run JMeter
        run: |
          JMETER_VERSION=5.6.3
          curl -L -o jmeter.tgz https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-$JMETER_VERSION.tgz
          tar -xzf jmeter.tgz
          ./apache-jmeter-$JMETER_VERSION/bin/jmeter -n -t jmeter/kabum_testplan.jmx \
            -l reports/ci/results.jtl -e -o reports/ci/jmeter-dashboard
      - uses: actions/upload-artifact@v4
        with:
          name: sqa-reports
          path: reports/ci
```

---

## 🖼 Screenshots

> Add images to <code>docs/</code> and reference here:

- <b>Search results</b>
  <code><img src="docs/search.png" alt="Search results" width="850"></code>

- <b>Newman HTML report</b>
  <code><img src="reports/&lt;timestamp&gt;/newman.html.png" alt="Newman report" width="850"></code>

- <b>JMeter dashboard</b>
  <code><img src="reports/&lt;timestamp&gt;/jmeter-dashboard/summary.png" alt="JMeter dashboard" width="850"></code>

---

## 🤝 Contributing

1. Fork → create feature branch → commit with your preferred convention
2. Add/Update tests & data; keep reports out of PRs (or squash them)
3. Open PR with screenshots + pass/fail summary

---

## 📄 License

MIT — see <code>LICENSE</code>.

---


## ✅ Release Checklist

- [ ] <span style="color:#22C55E">Smoke</span> suite pass ≥ 90%
- [ ] <span style="color:#38BDF8">Newman</span> HTML report attached
- [ ] <span style="color:#38BDF8">JMeter</span> dashboard generated
- [ ] <span style="color:#A78BFA">Data</span> files validated (no real PII)
- [ ] <span style="color:#F472B6">Decisions</span> documented (go/no-go)
- [ ] <span style="color:#F87171">Risks</span> + mitigations logged

---

### Notes on Real-World KaBuM! Usage
- Prefer read-only flows (search, PDP).
- Throttle requests & add realistic delays.
- For checkout, stop at <b>review</b> page or use <b>sandbox</b> mocks.
