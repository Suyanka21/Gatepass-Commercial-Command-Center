# PRODUCT TRUTH — GatePass

**Status: fixed commercial reference document. Verified against the live repository,
merged pull requests, and test suite — not against the original plan or intent.**

Last verified: current `main` branch, PRs through `#35` merged. A resident-portal
schema/auth foundation (branch `r1-units-residents`) is in progress and **not yet
merged** — treated throughout this document as unfinished, not complete.

---

## 1. What GatePass currently does

GatePass is a guard-facing visitor and access-control system for a single residential
estate. A guard at a physical gate uses it to admit, verify, and log every person and
vehicle entering the property, with every action attributed to a specific verified
identity and permanently recorded. It replaces a paper visitor logbook with a system
that can verify identity, enforce time-bounded access, flag restricted individuals,
and produce a real audit trail nobody can quietly edit.

## 2. Who uses it

Three roles exist today, each with a completely separate interface — no role ever
sees another role's screen, and this separation is enforced server-side, not just
hidden in the UI:

- **Guard** — the primary daily user. Scans passes, logs entries and exits, records
  notes, verifies vehicles, checks the watchlist.
- **Admin / senior guard** — provisions staff accounts (the only way any account is
  created — there is no public sign-up), reviews shift activity, manages the
  watchlist, views audit logs and reports.
- **Resident** — today, a link-only participant. A resident never logs in; they
  receive a one-time link to approve or deny a specific visitor, and that link
  expires after one use. (This is the piece currently changing — see §6.)

## 3. Current workflows

**Guard-initiated visitor entry:** a walk-in visitor arrives, the guard requests
approval, the resident receives a link (see §5 limitation), approves or denies, the
guard logs the entry either way.

**Staff-issued pre-authorized pass:** an admin or senior guard issues a QR pass (with
a 6-digit PIN backup) ahead of a visitor's arrival; the guard scans it at the gate.
This already works end to end and is the pattern the in-progress resident-issued
pass reuses.

**Entry logging:** every entry captures guard identity, timestamp, plate (with
optional verification against a pre-registered value), and an optional structured
note. Works offline — queued entries persist through a reload and sync automatically
on reconnect.

**Watchlist check:** every arrival is checked against the watchlist; a match warns
the guard and requires supervisor escalation — the system never auto-denies entry on
its own.

**Shift handover and audit review:** admins review shift logs, on-premise lists, and
the full audit trail; a locked pass (from repeated wrong PIN attempts) is shown as
"Locked" on every surface a guard or visitor can see, never as "Valid."

## 4. Completed functionality

Verified directly against code and a passing test suite (currently 41 frontend test
files / 535 tests, 43 server test files / 578 tests, plus a separate real-Postgres
integration suite — all passing):

- Role-based authentication (Supabase-issued JWTs verified server-side via JWKS) with
  no public sign-up; every privileged role is DB-provisioned, never client-chosen.
- Guard console: real signed-in identity, sign-out, shift-safe attribution (the audit
  trail shows the actual signed-in guard, not a placeholder).
- QR pass issuance and scanning, with a rate-limited PIN backup (5 wrong attempts
  locks the pass for 15 minutes; the lock is shown honestly on every surface).
- Vehicle plate verification against a pre-registered value at scan time (soft
  warning, guard decides — never an automatic block).
- Watchlist with mandatory reason, warn-and-escalate behavior (never auto-deny), and
  a 90-day review cycle so entries don't become a permanent, unreviewed blacklist.
- Guard notes: standardized quick tags plus a capped free-text field, attributed to
  the verified guard, deliberately excluded from the audit log to avoid accumulating
  unnecessary personal detail there.
- Pass expiry, enforced server-side at redemption time, not just cosmetically.
- Offline queue that survives a browser reload and a mid-shift connectivity drop
  without losing entries or forcing a guard to re-authenticate.
- Auto-approval matching engine (name/host/unit/plate), already used to
  automatically recognize known visitors and vehicles — this is the same engine the
  in-progress resident portal will let residents feed themselves.
- Transactionally-correct audit logging: an override's audit record cannot exist
  unless the underlying database write it describes actually committed (this was a
  real, confirmed defect, fixed with a failure-injection regression test — not merely
  asserted fixed).
- Production configuration fail-fast checks (missing required env vars prevent
  startup/build rather than failing silently in production).
- Dependency security: zero high or critical severity findings in production
  dependencies as of the last audit (two moderate findings remain, tied to a
  breaking-change library upgrade, deliberately deferred rather than rushed).
- Public-facing legal/support scaffolding: `/legal/privacy`, `/legal/terms`,
  `/support`, `/support/incident` pages exist, each carrying an explicit,
  unmissable "DRAFT — not reviewed by a lawyer" banner.
- Internal operational documentation: an operations runbook, pilot launch checklist,
  admin/supervisor SOPs, and incident response guidance all exist as written
  documents (not yet exercised against a real incident — see §5).
- Verified access boundaries: audit logs are provably admin/senior-guard only, with
  HTTP-level tests, not just a hidden UI element.

## 5. Partial functionality

Capability exists in code but is not yet usable end to end by a real person:

- **Resident notifications:** the message text and delivery-provider interface are
  built, but no real SMS/WhatsApp provider is connected — the provider is currently
  a default-deny mock. In practice, no resident receives anything today unless a
  staff member manually copies a link to them.
- **Legal and privacy documentation:** structurally present and clearly labeled as
  draft, but not yet reviewed by a lawyer. Adequate for a controlled pilot with an
  informed partner; not adequate for a wider or public rollout.
- **Operational procedures:** documented in full, but untested against a real
  incident, a real device loss, or a real disputed approval. The gap between
  "written down" and "known to work under pressure" is real and unclosed.
- **Production monitoring:** no error tracking or alerting exists. If something
  breaks after deployment, you find out from a person reporting it, not from a
  system telling you.

## 6. Unfinished functionality

- **Resident portal.** Specced and approved (`src/docs/specs/resident-portal.md`);
  the schema-and-authentication foundation is in active development on a branch not
  yet merged to `main`. Three capabilities are planned, in priority order: (1) a
  resident sends a pre-authorized pass to an expected visitor before they arrive —
  reusing the existing pass/scan machinery, not new infrastructure; (2) registering
  household members and workers; (3) registering vehicles — both (2) and (3) feed
  the *already-working* auto-approval engine, they don't duplicate it. Requires a
  new Supabase phone-OTP login path (not used anywhere in the app today) and a paid
  SMS OTP provider, which is a real, billed dependency someone has to own.
- **A live, real-world deployment.** The system has been built and tested
  extensively but has not yet been run by an actual guard at an actual gate.
- **Real SMS/WhatsApp delivery**, independent of and smaller than the resident
  portal — this is worth finishing regardless of the portal's timeline.
- **Multi-tenant / multi-estate architecture.** Not started, not specced. See §9.

## 7. Pilot requirements

*(one real security company, one real estate — the smallest real test)*

Already sufficient: the entire guard-facing operational loop (§4).

Still required: a connected SMS/WhatsApp provider (a pilot where approval links
never arrive isn't a real pilot); the resident-portal's first capability at minimum
(send-a-pass), so the pilot demonstrates proactive visitor management, not just
reactive approval; an actual production deployment with real environment
configuration; and basic error monitoring so failures are visible.

Not required for a pilot, and shouldn't be treated as a blocker: full legal sign-off
(a controlled pilot with one informed, consenting partner and clearly-marked draft
policy is a defensible position); the remaining two resident-portal capabilities
(household/vehicle registration can reasonably follow after send-a-pass);
multi-tenant architecture.

## 8. Investor-demo requirements

A meaningfully different, lighter bar than a pilot. Does not require: a live SMS
provider (a test number is sufficient), production monitoring, or finished legal
review.

Does require: a rehearsed, reliable, end-to-end narrative — guard scans a pass,
resident approves via link, a watchlist match is caught and escalated, a locked pass
correctly refuses entry, an admin views the audit trail. The resident-portal
send-a-pass capability is genuinely worth prioritizing for this audience
specifically: "a resident sends a visitor's pass before they even arrive" is a
stronger, more intuitive demo beat than the current guard-only, reactive-only flow.

## 9. Commercialisation requirements

*(multiple paying customers — a different scale of work than a pilot, not an
extension of it)*

The current schema and architecture implicitly assume a single estate. Serving
several customers means choosing between one deployment per customer (operationally
simple, doesn't scale past a handful of customers) or building genuine
multi-tenancy — a top-level organization/estate entity with enforced data isolation
between tenants. That is a dedicated design-and-review effort on the same order as
the resident portal, not a small addition on top of what exists.

Also required, and not yet begun: billing, self-service customer onboarding (today,
provisioning the very first admin account is a manual script someone runs by hand —
this does not scale past a small number of manually-onboarded customers), real
customer support infrastructure, and completed (not draft) legal review.

## 10. Known limitations

- No resident has ever logged into the app in production — the resident-facing side
  of the system is the least field-tested part of it.
- The provisioning of a new customer's very first admin account is a manual,
  operator-run process, not self-service.
- No production error monitoring exists.
- Notification delivery is entirely unproven outside manual link-copying.
- Ops documentation is untested against a real incident.
- The system assumes one estate; nothing about multi-tenant isolation has been
  designed, let alone built.

## 11. Current deployment state

Built, tested, and continuously verified in CI (lint, both test suites, build, a
real-Postgres integration suite, dependency audit) against a version-controlled
repository. **Not currently running in a live production environment serving real
guards, residents, or visitors.** All verification to date has been in development
and test environments.

## 12. Technical evidence relevant to commercial credibility

- 535 frontend tests and 578 server tests currently passing, plus a separate
  integration suite that runs against a real Postgres database rather than mocks
  only — override-audit correctness specifically has a failure-injection regression
  test, not just a happy-path test.
- A documented history of real defects found and fixed through direct, evidence-based
  verification rather than self-reported completion — including a transactional
  audit-logging bug, an onboarding-state synchronization bug, and a data-loss bug in
  the offline queue. This is a system that has been genuinely adversarially tested
  during its own construction, not just built and assumed correct.
- Zero high/critical severity vulnerabilities in production dependencies.
- Every role-based access boundary (guard cannot reach admin surfaces, audit logs are
  admin-only, resident writes cannot affect another unit — the last of these is part
  of the in-progress resident-portal spec, explicitly tested for in its test plan)
  is enforced server-side and verified by tests, not by hiding UI elements.

## 13. What GatePass explicitly does NOT do

By deliberate, repeated decision — not oversight:

- No payments, billing, rent, or service-charge handling.
- No maintenance ticketing.
- No community chat, marketplace, or noticeboard.
- No general resident dashboard, notification inbox, or visit-history browser beyond
  the three scoped resident-portal capabilities.
- No real-time push notifications (polling is sufficient at this scale).
- No offline/PWA support for the resident portal (residents are online-only by
  design; only the guard console needs offline resilience).
- No multi-property or multi-tenant support today.
- No automatic entry denial based on the watchlist — a human always makes the final
  call.

This list is a feature, not a gap. This discipline — a consistent willingness to say
"not now" — is a material part of why what has been built is solid rather than
half-finished across a dozen directions.

## 14. Product philosophy

Every design decision in this system has favored the same things, consistently,
across six months of development: fail closed rather than fail open (an uncertain
state blocks an action rather than silently permitting it); tell the truth to the
person in front of the screen (a locked pass says "Locked," not "Valid"; a refusal
says why, in language a non-technical person can read); never let the client decide
its own privilege (every role, every unit-scope, every authorization check is
resolved server-side, never trusted from the browser); and a human makes the final
call on anything consequential (watchlist matches warn, they don't block; guards
decide on a plate mismatch, the system doesn't decide for them). This is a system
built around accountability as the product, not merely as a compliance afterthought.

## 15. Current assumptions requiring commercial validation

These are working assumptions the engineering work has been built on — none have
been tested against a real paying customer yet:

- That a security company, not the estate itself, is the primary buyer — worth
  re-examining now that resident self-service (portal, household/vehicle
  registration) has become a near-term priority. It's plausible there are now two
  distinct buyers with different needs — the security company (paying for
  operational accountability) and the estate or property manager (paying for
  resident convenience) — rather than one. This affects pricing, sales motion, and
  competitive positioning, and hasn't been deliberately resolved.
- That guards will actually adopt a QR/PIN system over informal, ad hoc methods —
  unvalidated by any real guard's actual use.
- That the 48-hour resident pass window, the 10-open-passes-per-unit cap, and the
  90-day household-registration renewal cycle are the right numbers — these are
  reasonable starting defaults, not numbers derived from real usage data.
- That a security-firm customer will accept a resident self-service login (a real
  change to the "residents never sign in" model this system started with) rather
  than preferring that all resident-facing data entry stay staff-mediated.
- That Twilio Verify (or an equivalent) reliably delivers OTP and notification SMS
  to Kenyan (+254) numbers at acceptable cost and speed — not yet confirmed.
