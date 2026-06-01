# Workbook Glossary

This glossary gives the AI assistant context on what each tab represents in the SNAP onboarding workbook.

## Section 01 — Bank Structure

### 01A Branches
Physical locations where customers can open accounts. Each row is one branch with branch ID, address, type (full / drive-through / ATM-only), and key flags.

### 01B Region Usage
A decision: does this bank use SNAP's "region" concept to group branches (by state, by city, by line of business)? If no, no further config in this tab.

### 01C Officers
Individuals authorized to approve account openings or specific account types.

### 01D Sales Associates
Customer-facing employees who originate accounts. May be tied to specific branches.

### 01E Core Cleanup
Tasks to ensure the core banking system data is consistent before SNAP imports it.

## Section 02 — CIF Configuration

### 02A Individual CIF Data
Fields collected from individual customers (name, DOB, SSN, address, contact). Configures which fields are required/optional/hidden.

### 02D State Codes
ISO state/province codes accepted as customer addresses.

### 02E Address Types
Which address types are valid (HOME, MAIL, WORK, PREV). Affects what shows in dropdowns elsewhere.

### 02F Country Codes
Which countries can appear as customer country-of-residence / country-of-citizenship. Some are excluded by OFAC.

### 02G Business Types
Legal entity types for business accounts (LLC, S-Corp, Sole Prop, ...).

### 02H ID Types
Government-issued IDs accepted for CIP (Driver License, Passport, State ID, ...). Each has its own validation matrix (expiry required, photo required, etc.).

## Workflow

- Bank-side users at this bank fill in one issue per tab.
- Data-heavy tabs (Branches, Officers, Country Codes, Business Types, Sales Associates) ship with a CSV template. Download, fill in Excel, paste back as a comment on the issue.
- Conceptual tabs (Region Usage, Address Types, ID Types) get answered as comments directly.
- ZAP team reviews comments and updates issue status (`status:needs-review` → `status:complete`).

## Conventions

- Section ordering: numerical from the `section:NN` label.
- Tab ordering inside a section: alphabetical by tab code (01A, 01B, 01C, ...).
- Pinned issues mark the current focus area.
