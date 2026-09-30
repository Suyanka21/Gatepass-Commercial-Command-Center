# COMMERCIAL STRATEGY DOSSIER: GATEPASS ACCESS CONTROL & SECURITY ECOSYSTEM (KENYA)
**Document Identifier:** 05_Commercial_Strategy.md  
**Date:** September 2026  
**Target Platform:** GatePass Physical Access Intelligence Platform  
**Market Jurisdiction:** Republic of Kenya (Nairobi, Mombasa, Kisumu, Nakuru, Eldoret)  
**Analytical Framework:** Grounded Market Research, Statutory Frameworks (PSRA 2016, DPA 2019, Evidence Act Cap 80), Repository Product Truth, and Competitor Intelligence  

---

## EXECUTIVE SUMMARY & STRATEGIC CONTEXT

This Commercial Strategy Dossier provides an objective, evidence-backed commercial roadmap for **GatePass**, a digital access-management Software-as-a-Service (SaaS) platform operating in Kenya. Grounded in six primary data sources—including repository-verified product truth (`00_GatePass_Product_Truth.md`), private security market research (`01_Kenya_Private_Security_Market.md`), customer discovery (`02_Customer_Discovery.md`), competitive intelligence (`03_Competition_And_Alternatives.md`), and regulatory frameworks (`04_Regulatory_And_Legal_Landscape.md`)—this dossier evaluates GatePass's go-to-market strategy, buyer personas, pricing models, and defensibility.

Specifically, this dossier tests the founding commercial thesis: **"Security firms are the paying customer, not estates."** With the development of resident self-service capabilities (the `r1-units-residents` portal branch), a second potential buyer model—direct sales to Estate Homeowners' Associations (HOAs) and Property Managers—has emerged. 

Every conclusion throughout this dossier is explicitly tagged as **[FACT]**, **[ANALYSIS]**, **[HYPOTHESIS]**, or **[UNKNOWN]** to maintain rigorous commercial credibility.

---

## 1. PROBLEM DEFINITION

### 1.1 Core Operational Breakdown
* **[FACT] Gate Bottlenecks & Congestion:** Legacy gate operations rely on manual paper logbooks, resulting in check-in delays of 3 to 5 minutes per vehicle during peak morning and evening hours (01_Kenya_Private_Security_Market.md [106]; 02_Customer_Discovery.md [3, 20]).
* **[FACT] Caller Intercom Friction:** Unannounced visitors force guards to place manual phone calls or landline intercom calls to residents. Unanswered calls lead to gate traffic backups, tailgating, and verbal altercations between drivers and frontline guards (02_Customer_Discovery.md [3, 10]; 01_Kenya_Private_Security_Market.md [106]).
* **[FACT] Zero Operational Visibility:** Security operations managers lack real-time visibility into field posts, leaving them unable to verify whether guards are awake, on post, or accurately logging visitors without "pencil-whipping" physical Daily Occurrence Books (DOBs) (00_GatePass_Product_Truth.md [121]; 02_Customer_Discovery.md [3, 20]).

### 1.2 Statutory & Financial Pressure Drivers
* **[FACT] PSRA KES 30,000 Minimum Wage Shock:** Legal Notice No. PSRA/005/2023 mandates a statutory gross minimum wage of KES 30,000/month per guard (net KES 26,415.25), upheld by the Employment and Labour Relations Court (ELRC) in February 2025 (01_Kenya_Private_Security_Market.md [99, 103]; 04_Regulatory_And_Legal_Landscape.md [70]). Non-compliance carries corporate fines up to KES 2,000,000 per violation. This has escalated guard payroll by 40% to 80%, squeezing security firm margins and forcing estate clients to demand leaner, tech-enabled guard deployments (01_Kenya_Private_Security_Market.md [104]; 02_Customer_Discovery.md [13]).
* **[FACT] DPA 2019 / ODPC Data Privacy Liabilities:** Paper visitor logbooks expose Personal Identifiable Information (PII)—including visitor names, national ID numbers, phone numbers, vehicle plates, and destination addresses—to public view (01_Kenya_Private_Security_Market.md [99, 109]; 04_Regulatory_And_Legal_Landscape.md [56, 72]). Under the Data Protection Act (DPA) 2019, enforced by the Office of the Data Protection Commissioner (ODPC), open paper registers create severe statutory liabilities, with administrative penalties capped at KES 5,000,000 or 1% of annual turnover (01_Kenya_Private_Security_Market.md [99]; 04_Regulatory_And_Legal_Landscape.md [57, 66]).
* **[FACT] Illegality of Physical ID Card Retention:** The common practice of guards demanding and retaining physical National ID cards or Driver's Licenses at gatehouses is legally indefensible under DPA 2019 and ODPC rulings (04_Regulatory_And_Legal_Landscape.md [72]). Scan-and-verify workflows are legally mandated.

---

## 2. CUSTOMER / BUYER MAP & STAKEHOLDER ANALYSIS

```
+----------------------------------------------------------------------------------------------------+
|                                    GATEPASS STAKEHOLDER & BUYER MAP                                |
+-------------------+-----------------------------------+--------------------------------------------+
| STAKEHOLDER ROLE  | PRIMARY GOALS & INCENTIVES        | CORE PAIN POINTS & STATUTORY RISKS         |
+-------------------+-----------------------------------+--------------------------------------------+
| Security Firm     | - Protect operating margins       | - PSRA KES 30,000 minimum wage inflation   |
| Owner / MD        | - Differentiate via "Digital SLA" | - Client churn to low-cost competitors     |
| (Buyer Route A)   | - Win multi-site estate tenders   | - Statutory PSRA license cancellation risk |
+-------------------+-----------------------------------+--------------------------------------------+
| Estate / HOA      | - Estate safety & access control  | - ODPC data privacy lawsuits & KES 5M fine |
| Board Committee   | - Service charge collection       | - Resident gate congestion complaints      |
| (Buyer Route B)   | - Enhance property rental yields  | - Uncollected estate dues & arrears        |
+-------------------+-----------------------------------+--------------------------------------------+
| Security Ops      | - Real-time multi-site visibility | - Guards sleeping or "pencil-whipping"     |
| Manager (User)    | - Prove SLA guard attendance      | - Gate altercations & missing logs         |
+-------------------+-----------------------------------+--------------------------------------------+
| Frontline Security| - Fast gate clearance (<30s)      | - Verbal abuse from frustrated drivers     |
| Guard (User)      | - Simple tablet interface         | - Internet drops / power blackout freezes  |
+-------------------+-----------------------------------+--------------------------------------------+
| Resident / Host   | - Fast guest clearance            | - Frequent phone calls from gatehouse      |
| (Participant)     | - Maintain personal privacy       | - Illegal exposure of contact details      |
+-------------------+-----------------------------------+--------------------------------------------+
```

* **[FACT] User Separation:** GatePass separates operational roles server-side via Supabase JWKS JWT validation: Guards operate the gate console; Admins provision staff accounts and review audit logs; Residents participate via link approvals or pre-authorized pass generation (00_GatePass_Product_Truth.md [122]; 03_Competition_And_Alternatives.md [45]).

---

## 3. STRATEGIC VALUE PROPOSITION

### 3.1 For Security Companies (Channel Buyers)
* **[ANALYSIS] Margin Protection & Contract Retention:** Enables security firms to justify higher client billing rates (KES 35,000–45,000/post) necessary to cover PSRA minimum wages by bundling "Tech-Enabled Guarding" and auditable digital SLAs (01_Kenya_Private_Security_Market.md [104]; 02_Customer_Discovery.md [13]).
* **[ANALYSIS] Multi-Site Operational Control:** Provides real-time field visibility and transactionally correct audit logs, eliminating guard sleeping and falsified paper logs across dozens of client gates (00_GatePass_Product_Truth.md [124, 125]; 02_Customer_Discovery.md [14]).

### 3.2 For Estates & Property Managers (Direct Buyers)
* **[ANALYSIS] Turnkey ODPC Compliance:** Eliminates open paper registers, enforcing data minimization, encrypted access logs, and automated 6-month data scrubbing pipelines to insulate estates from KES 5M ODPC fines (04_Regulatory_And_Legal_Landscape.md [57, 82-84]).
* **[ANALYSIS] Frictionless Access & Dues Enforcement:** Delivers pre-authorized visitor access via WhatsApp/SMS in under 30 seconds, while providing HOAs with leverage to enforce monthly service charge collections by linking payment status to gate pass privileges (02_Customer_Discovery.md [10, 15]; 01_Kenya_Private_Security_Market.md [106]).

---

## 4. EVALUATION OF ORIGINAL THESIS VS. EMERGING DUAL-BUYER MODEL

### 4.1 Testing the Original Thesis: "Security firms are the paying customer, not estates"
* **[FACT] Evidence Supporting Security Firms as the Buyer:**
  1. *PSRA Wage Crisis:* Security firms face court-mandated KES 30,000 guard wages, forcing them to adopt technology to justify higher client billing or deploy leaner guard forces (01_Kenya_Private_Security_Market.md [103, 104]).
  2. *Sales Velocity & Scale:* Security owners control portfolios of 20 to 100+ gates. Winning one security firm deploys GatePass across dozens of sites simultaneously with a fast 2-to-4-week sales cycle (02_Customer_Discovery.md [14, 15]).
  3. *Product Truth Alignment:* GatePass's core architecture emphasizes guard shift attribution, fail-closed security, offline resilience, and transactionally correct audit logs—features designed specifically for guard force accountability (00_GatePass_Product_Truth.md [121, 125, 136]).
* **[FACT] Evidence Supporting Estates / Property Managers as the Buyer:**
  1. *Direct ODPC Legal Liability:* Property managers and HOAs act as Data Controllers under DPA 2019 Section 2 and face direct statutory liability for privacy breaches (04_Regulatory_And_Legal_Landscape.md [64, 66]).
  2. *Emergence of Resident Self-Service:* The resident portal branch (`r1-units-residents`) introduces proactive pass generation, household registration, and vehicle management, transforming GatePass from a guard-only tool into a resident-facing estate management platform (00_GatePass_Product_Truth.md [127]).
  3. *Service Charge Monetization:* Estates actively seek digital tools to streamline monthly service charge collection and gate convenience (02_Customer_Discovery.md [15]; 01_Kenya_Private_Security_Market.md [106]).

### 4.2 Synthesis: The Dual-Buyer / Channel Hybrid Model
* **[ANALYSIS] Dual Commercial Viability:** Both buyer models are commercially viable, but address different market triggers and sales velocities:
  * **Route A (B2B Channel Partner Model):** Security firms license GatePass as operational infrastructure, re-billing clients or bundling it as "Tech-Enabled Guarding." This serves as the primary high-velocity distribution engine.
  * **Route B (Direct B2B SaaS Model):** Estate HOAs and Property Developers purchase GatePass directly, mandating its usage by their contracted security agency.
  * **Route C (Co-Sponsored Hybrid):** Estate HOAs pay for resident-facing portal capabilities (per-unit subscription), while the security firm pays for or co-sponsors guard console terminals.

---

## 5. DETAILED ANALYSIS OF THE 16 CORE STRATEGY QUESTIONS

1. **What problem is GatePass actually solving?**  
   * **[ANALYSIS]** Solves operational gate friction, security guard accountability gaps, and severe statutory liabilities (PSRA minimum wage inflation and ODPC data privacy fines) by replacing paper registers with an auditable, offline-resilient digital access platform (01_Kenya_Private_Security_Market.md [99]; 04_Regulatory_And_Legal_Landscape.md [56, 57]).
2. **Who has the strongest pain?**  
   * **[ANALYSIS]** Security firm owners (facing 40–80% wage cost increases and contract churn) and Estate HOAs (facing KES 5M ODPC fine risks and resident gate congestion complaints) (01_Kenya_Private_Security_Market.md [104]; 02_Customer_Discovery.md [20]).
3. **Who uses GatePass?**  
   * **[FACT]** Primary user: Frontline Security Guards. Administrative user: Security Supervisors and Estate Admins. Secondary participants: Residents and Visitors (00_GatePass_Product_Truth.md [122]; 02_Customer_Discovery.md [4]).
4. **Who benefits?**  
   * **[ANALYSIS]** Frontline guards (reduced gate abuse/queues), Security owners (SLA compliance & margin expansion), Estate managers (ODPC compliance & service charge leverage), and Residents (fast, private access) (02_Customer_Discovery.md [5, 18]).
5. **Who is most likely to pay?**  
   * **[ANALYSIS]** Security companies seeking multi-site contract differentiation (Route A) and premium Estate HOAs seeking resident convenience and privacy compliance (Route B) (02_Customer_Discovery.md [6, 14, 15]).
6. **What evidence supports security firms as the buyer?**  
   * **[FACT]** Court-enforced PSRA KES 30,000 minimum wage mandate, 2-to-4-week sales cycles, multi-site contract scale (20–100+ gates per client), and GatePass's guard-accountability codebase focus (01_Kenya_Private_Security_Market.md [103, 104]; 02_Customer_Discovery.md [14, 15]).
7. **What evidence supports estates/property managers as the buyer?**  
   * **[FACT]** ODPC Data Controller liability (KES 5M fine exposure), active ODPC audits, and the development of resident portal features (pre-authorized passes, household/vehicle registration) (04_Regulatory_And_Legal_Landscape.md [64, 66]; 00_GatePass_Product_Truth.md [127]).
8. **Could both be viable?**  
   * **[ANALYSIS]** Yes. A hybrid strategy leverages security firms for rapid multi-gate distribution while monetizing estate HOAs for premium resident self-service features (02_Customer_Discovery.md [14, 15]; 01_Kenya_Private_Security_Market.md [115]).
9. **What are the different sales motions?**  
   * **[ANALYSIS]** Security Firm Route: Direct B2B executive sales to MDs/COOs (2–4 week cycle, top-down multi-site deployment). Estate Route: Committee consultative selling to HOA Boards/Property Managers (2–6 month cycle, AGM budget approval) (02_Customer_Discovery.md [15]).
10. **What are the different pricing structures?**  
    * **[ANALYSIS]** Security Firm: Fixed monthly subscription per active gate terminal (e.g., KES 5,000–15,000/terminal/month). Estate HOA: Per-housing-unit monthly SaaS fee (e.g., KES 50–150/unit/month) + transactional communication charges (KES 0.60–3.00/pass) (01_Kenya_Private_Security_Market.md [110]).
11. **What does GatePass replace?**  
    * **[FACT]** Paper visitor logbooks, physical Daily Occurrence Books (DOBs), analog intercoms, unstructured WhatsApp gate groups, and manual push-button boom barrier operations (02_Customer_Discovery.md [8]; 03_Competition_And_Alternatives.md [39]).
12. **What is genuinely differentiated?**  
    * **[FACT]** Verified server-side privilege enforcement (Supabase JWKS JWTs), fail-closed security design, transactionally correct audit logging, reload-resistant offline guard queue, guard-attributed notes excluded from audit logs, and human-in-the-loop watchlist escalation (00_GatePass_Product_Truth.md [125, 136]; 03_Competition_And_Alternatives.md [45, 52]).
13. **What is commoditised?**  
    * **[FACT]** Basic QR code pass generation/scanning, 6-digit PIN backups, time-bounded pass expiration, visitor entry/exit timestamp logging, and link-based approval requests (03_Competition_And_Alternatives.md [46, 53]).
14. **What must be validated before choosing a commercial model?**  
    * **[UNKNOWN]** Live gate guard adoption under peak congestion, production SMS/WhatsApp OTP delivery costs over Kenyan (+254) networks, security firm willingness to re-bill SaaS, and HOA willingness-to-pay ceilings for standalone VMS vs. financial PMS (00_GatePass_Product_Truth.md [137]; 01_Kenya_Private_Security_Market.md [117]).
15. **What business model appears most consistent with the evidence?**  
    * **[HYPOTHESIS]** B2B Channel Partner Model with Security Companies as primary distribution nodes, combined with a Direct Estate SaaS add-on for resident self-service (01_Kenya_Private_Security_Market.md [115]).
16. **What assumptions remain unproven?**  
    * **[UNKNOWN]** Real-world field guard compliance, Twilio (+254) SMS unit economics, resident adoption rates of digital guest invites, and multi-tenant schema scalability (00_GatePass_Product_Truth.md [132, 137]).

---

## 6. BUSINESS MODEL & BUYER HYPOTHESES

### 6.1 Primary Hypothesis: B2B Security Firm Channel Model
* **[HYPOTHESIS]** GatePass should target Tier-1 and Tier-2 Private Security Companies (PSCs) as its primary channel partners. PSCs bundle GatePass into their client proposals as "Tech-Enabled Guarding," allowing them to justify higher client bill rates (KES 35,000–45,000/guard) while paying GatePass a wholesale SaaS fee per gate terminal (01_Kenya_Private_Security_Market.md [104, 115]).

### 6.2 Secondary Hypothesis: Direct Estate HOA SaaS Model
* **[HYPOTHESIS]** For high-end gated estates (>50 units) where HOAs manage their own security procurement, GatePass can sell directly to the HOA board on a per-unit subscription basis, mandating that whichever security firm wins the guarding contract must operate the GatePass console (02_Customer_Discovery.md [6, 15]).

---

## 7. PRICING HYPOTHESES & UNIT ECONOMICS

```
========================================================================================
                          GATEPASS PRICING STRUCTURE HYPOTHESES
========================================================================================
[MODEL A: SECURITY FIRM WHOLESALE TERMINAL FEE]
  * Target Buyer: Private Security Companies (Tier 1 / Tier 2)
  * Pricing: KES 7,500 - KES 12,000 / active gate terminal / month
  * Included Volume: Unlimited guard check-ins, offline queue sync, audit logs
  * Margin Impact: Security firm markups terminal fee by 25-40% when billing estate client.

[MODEL B: ESTATE HOA PER-UNIT SUBSCRIPTION]
  * Target Buyer: Estate Homeowners Associations / Property Managers
  * Pricing: KES 80 - KES 120 / residential unit / month (Min KES 5,000/mo per estate)
  * Value Driver: Includes resident portal access, WhatsApp guest passes, M-Pesa billing alerts.

[MODEL C: TRANSACTIONAL COMMUNICATION PASS-THROUGH]
  * Target Buyer: All Subscribing Estates
  * Pricing: KES 1.50 - KES 2.50 / SMS/WhatsApp OTP pass delivered
  * Unit Economics: Twilio / Infobip wholesale cost (~KES 0.80 - 1.20) yields ~50% gross margin.
========================================================================================
```

---

## 8. COMPETITIVE POSITIONING & DIFFERENTIATION MATRIX

| Capability / Dimension | GatePass (gatepass.io) | SOJA VMS (Robisearch) | EstateIQ / Mygate | Nyumba Zetu | TrackTik |
| ------ | ------ | ------ | ------ | ------ | ------ |
| **Primary Domain** | Access Operations & Truth | Access Operations & VMS | Residential ERP | Property Financial PMS | Guard Force Workforce |
| **Target Geography** | Kenya / East Africa | Kenya / Uganda / SA | Nigeria / India / UAE | Kenya | Global |
| **Server Privilege Control** | Server-Side JWKS JWT | Client / Server | UI-Level | Server-Side | Enterprise RBAC |
| **Fail-Closed Security** | Verified Fail-Closed | Unverified | Unverified | Unverified | Verified |
| **Offline Guard Queue** | Reload-Resistant Queue | Local Caching | App Caching | N/A | Offline Sync |
| **Audit Log Integrity** | Transactionally Correct | Standard Logs | Standard Logs | Financial Logs Only | GPS Audit Trails |
| **ALPR / Hardware Control** | No (Manual Guard Scan) | Native ALPR & Booms | Minimal | None | Patrol Checkpoints |
| **Gov ID Database Sync** | No | Yes (Kenyan IPRS) | No | No | No |
| **Estate Dues Billing** | No (Deliberate Exclusion) | No | Native Ledgers | Native M-Pesa Ledgers | Client Billing Only |

### 8.1 Genuinely Differentiated Capabilities (Product Truth)
* **[FACT] Verified Server-Side Authorization:** Role privileges are enforced strictly server-side via Supabase JWTs verified through JWKS—never trusted from the client (00_GatePass_Product_Truth.md [125, 134, 136]).
* **[FACT] Fail-Closed Architecture:** Locked passes (from 5 failed PIN attempts) display as "Locked" across all guard and visitor surfaces, explicitly failing closed during ambiguous states (00_GatePass_Product_Truth.md [124, 125, 136]).
* **[FACT] Transactionally Correct Audit Logs:** Override audit records cannot exist unless the underlying database write commits (verified via failure-injection regression tests) (00_GatePass_Product_Truth.md [125, 134]).
* **[FACT] Reload-Resistant Offline Queue:** Guard entry queue survives mid-shift network drops and browser reloads without losing data or forcing re-authentication (00_GatePass_Product_Truth.md [123, 125]).
* **[FACT] Guard Note Privacy Boundaries:** Guard notes feature standardized quick tags plus free text attributed to verified guards, deliberately excluded from audit logs to avoid PII bloat (00_GatePass_Product_Truth.md [125]).
* **[FACT] Human-in-the-Loop Escalation:** Watchlist matches generate soft warnings requiring supervisor escalation rather than automated system blocks (00_GatePass_Product_Truth.md [124, 125, 135]).

### 8.2 What GatePass Must NOT Claim
* **[FACT] Explicit Exclusions:** To maintain commercial credibility, GatePass must **NEVER** claim: live production deployment, native ALPR scanning, government IPRS database sync, integrated rent/service charge collection, multi-tenant enterprise architecture, active SMS/WhatsApp in production, or guard GPS patrol tracking (03_Competition_And_Alternatives.md [51]; 00_GatePass_Product_Truth.md [133, 135]).

---

## 9. MARKET OPPORTUNITY & TAM / SAM / SOM ESTIMATION

```
========================================================================================
                     MARKET SIZE ESTIMATION FOR GATEPASS IN KENYA
========================================================================================
[TOTAL ADDRESSABLE MARKET (TAM)]
  * Basis: ~2,172 registered PSCs + ~15,000 formal residential gated estates/apartments
    in Nairobi Metropolitan Area + ~3,000 commercial towers.
  * TAM Value: Estimated at ~KES 3.6 Billion ($27M USD) annually in access control SaaS.

[SERVICEABLE ADDRESSABLE MARKET (SAM)]
  * Basis: Mid-to-High Tier Residential Estates (>30 units) + Top 500 Commercial
    Office Towers + Tier-1 & Tier-2 Security Companies (~500 active PSCs).
  * SAM Value: Estimated at ~KES 850 Million ($6.5M USD) annually.

[SERVICEABLE OBTAINABLE MARKET (SOM - 3-Year Target)]
  * Basis: 200 Residential Estates (100 units @ KES 100/unit/mo = KES 24M/yr) +
    50 Commercial Buildings (2 gates @ KES 10,000/gate/mo = KES 12M/yr) + 15 Partner PSCs.
  * SOM Value: Estimated at ~KES 45 Million to KES 60 Million ($350k - $460k USD) ARR.
========================================================================================
```

---

## 10. RISKS & COMMERCIAL UNKNOWNS

### 10.1 High-Priority Commercial Risks
* **[ANALYSIS] Guard Resistance & Device Damage:** Guards earning low wages may resist digital logging or damage gate tablets (02_Customer_Discovery.md [12, 26]). *Mitigation:* Deploy ruggedized IP65 cases, lock tablets into kiosk mode, and enforce GFN shift attribution (02_Customer_Discovery.md [26]; 04_Regulatory_And_Legal_Landscape.md [76]).
* **[ANALYSIS] SMS / WhatsApp Overage Inflation:** Excessive guest pass generation could cause messaging costs to exceed subscription revenue (02_Customer_Discovery.md [26]). *Mitigation:* Use WhatsApp-first routing and cap free monthly passes per unit.
* **[ANALYSIS] Unreviewed Draft Legal Terms:** Operating commercially with draft legal banners (`/legal/privacy`, `/legal/terms`) creates immediate legal liability under DPA 2019 Section 42 (04_Regulatory_And_Legal_Landscape.md [88, 89]).

### 10.2 Core Commercial Unknowns
1. **[UNKNOWN] Guard Scanning Latency Under Peak Congestion:** Empirical scanning speed and error rates when Tier-3 guards operate tablets during 6:30 PM gate traffic (01_Kenya_Private_Security_Market.md [117]).
2. **[UNKNOWN] Twilio (+254) Delivery Reliability & Unit Economics:** Real-world SMS/WhatsApp OTP delivery rates across Safaricom/Airtel networks (00_GatePass_Product_Truth.md [137]).
3. **[UNKNOWN] PSC Willingness to Re-Bill SaaS:** Whether security firm owners prefer licensing third-party SaaS or building in-house apps (01_Kenya_Private_Security_Market.md [117]).
4. **[UNKNOWN] HOA Willingness-to-Pay Ceilings:** Price elasticity for standalone access control vs. bundled financial property management software (01_Kenya_Private_Security_Market.md [117]).

---

## 11. VALIDATION PLAN & FIELD RESEARCH ROADMAP

```
+----------------------------------------------------------------------------------------------------+
|                                    CUSTOMER-VALIDATION SCORECARD                                   |
+-----------------------------------+-------------------+--------------------+-----------------------+
| VALIDATION METRIC                 | TARGET THRESHOLD  | PASS / FAIL CRITERIA| MEASUREMENT METHOD    |
+-----------------------------------+-------------------+--------------------+-----------------------+
| 1. Gate Clearance Speed           | < 30 Seconds      | Pass: <= 30s       | Field stopwatch timing|
|                                   | per visitor       | Fail: > 45s        | during peak hours     |
+-----------------------------------+-------------------+--------------------+-----------------------+
| 2. Resident Pre-Clearance Adoption| > 70% of visits   | Pass: >= 70%       | Server log analytics  |
|                                   | pre-authorized    | Fail: < 50%        | of pre-issued QR codes|
+-----------------------------------+-------------------+--------------------+-----------------------+
| 3. WhatsApp Approval Rate         | > 85% response    | Pass: >= 85%       | WhatsApp Business API |
|                                   | within 45 seconds | Fail: < 65%        | message delivery logs |
+-----------------------------------+-------------------+--------------------+-----------------------+
| 4. Offline Queue Sync Integrity   | 100% data recovery| Pass: 100% zero-loss| Simulated network drop|
|                                   | post-reconnect    | Fail: Any lost log | test on guard tablet  |
+-----------------------------------+-------------------+--------------------+-----------------------+
| 5. Security Firm Margin Expansion | > 15% SaaS re-bill| Pass: Net positive | Financial audit of B2B|
|                                   | margin            | margin expansion   | security partner deals|
+-----------------------------------+-------------------+--------------------+-----------------------+
```

---

## 12. RECOMMENDED NEXT EVIDENCE TO COLLECT & PRE-COMMERCIAL PREREQUISITES

### 12.1 Pre-Commercial Rollout Prerequisites (Mandatory Blockers)
1. **[FACT] Finalize Legal Terms:** Remove "DRAFT" banners from `/legal/privacy` and `/legal/terms` following formal sign-off by qualified Kenyan legal counsel (04_Regulatory_And_Legal_Landscape.md [91, 92]).
2. **[FACT] Secure ODPC Data Processor Registration:** Submit formal registration via the ODPC portal and obtain a Data Processor Certificate (04_Regulatory_And_Legal_Landscape.md [65, 92]).
3. **[FACT] Connect Real SMS/WhatsApp Provider:** Replace default-deny mock provider with a live Twilio/Infobip integration for +254 numbers (00_GatePass_Product_Truth.md [126, 129]).
4. **[FACT] Merge Resident Portal Branch (`r1-units-residents`):** Complete and merge proactive pass issuance capabilities to enable resident self-service (00_GatePass_Product_Truth.md [127, 129]).
5. **[FACT] Deploy Automated 6-Month Data Purge Pipeline:** Build and test the background job enforcing the 180-day raw log window followed by permanent anonymization to comply with PSRA and DPA Section 39 (04_Regulatory_And_Legal_Landscape.md [82-84, 92]).
6. **[FACT] PSRA License & GFN Input Validation:** Add mandatory PSRA corporate license fields to admin onboarding and Guard Force Number (GFN) validation fields to guard profiles (04_Regulatory_And_Legal_Landscape.md [71, 76, 92]).

### 12.2 Single-Estate Pilot Execution
* **[ANALYSIS] Controlled Pilot Scope:** Conduct a single-estate pilot involving one consenting property partner and one licensed security firm to collect empirical field data on guard scanning latency, tablet durability, offline queue recovery, and resident approval response times (00_GatePass_Product_Truth.md [128, 129]; 04_Regulatory_And_Legal_Landscape.md [93]).

---
*Dossier Compiled for GatePass Commercial Strategy.*  
*Saved as:* `/workspace/out/05_Commercial_Strategy.md`
