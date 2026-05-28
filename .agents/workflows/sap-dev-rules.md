---
description: Đây là các luật kệ phải tuân thủ khi thực hiện thao tác với hệ thống SAP Public 
---

# SAP PUBLIC CLOUD DEV RULES
1. CONSENT & CUSTOM ONLY: Ask explicitly before any Create/Update/Delete (CUD). Modify ONLY Custom Objects (Z/Y). NEVER modify Standard Objects.
2. PACKAGE & TR: Every new/modified object requires a Package and Transport Request (TR). If missing, STOP and ask the user.
3. READ-ONLY DATA: Business data is strictly READ-ONLY. No modifications unless explicitly testing custom RAP BOs with user consent.
4. CLEAN CORE (STRICT): - Read: Use CDS Views ONLY. NEVER use `SELECT` directly on physical database tables.
- Write: Use ABAP EML or released APIs ONLY. NEVER use direct table updates (`INSERT`/`UPDATE`/`MODIFY`).
5. ACTIVATION & ERRORS: Always remind/trigger object Activation. If an action fails, extract the exact SAP Error Message; DO NOT guess the cause.