

- Authenticated web application + backing API as a customer user (primary account: bhakti.pentest, Manager role — widest customer surface; see credentials comment).

- Unauthenticated surfaces: login, 2FA enrollment/verification flows, "Sign in with an email code", public /disclosure form.

- Authorization boundaries between roles where test accounts allow (Manager ↔ Engineer ↔ external supplier portal) — including grant scoping and route isolation.

- Session/auth handling: JWT/refresh flow, logout (note: ATCM-89 — logout button currently broken), 2FA bypass attempts, OTP brute force, "Remember me"/30-day trust.

- File handling: process-document upload (.docx/.pdf), Excel imports, evidence files — upload validation, stored content, download authorization.

- Business-logic controls the product promises: two-person approvals, grant expiry, SHA-256 package integrity, supplier party-match rejection.

- Standard web tiers: OWASP Top 10 (2021) + OWASP WSTG + API Security Top 10.