# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **static HTML website** hosted on GitHub Pages (`erinorth.github.io`). It contains privacy policy, account deletion, and data deletion compliance pages for multiple Flutter mobile apps. There is no build process — files are served directly.

## Architecture

### Page Types (3 per app)
- **Privacy Policy** — comprehensive disclosures covering data collection, storage, and third-party integrations
- **Account Deletion** — step-by-step instructions + HTML form that submits to `formsubmit.co` → `north.affhub@gmail.com`
- **Data Deletion** — similar structure to account deletion, focused on PDPA data subject rights

### Apps Covered
New apps are added over time. The current list can always be derived from the files present in the repository — look for files matching `<prefix>_privacy.html`, `<prefix>_account_deletion.html`, and `<prefix>_data_deletion.html`.

Known apps at the time of writing (not exhaustive):
| App | File Prefix |
|-----|-------------|
| FastPure | `fast_pure_` |
| NightLog | `nightlog_` |
| DebtDone | `debtdone_` |
| NoSpendDay | `nospendday_` |
| MealRecovery | `meal_recovery_` |
| WishPause | `wishpause_` |
| PetSym | `petsym_` |
| JointCast | `jointcast_` |

When adding a new app, **update this table** with the new app name and file prefix.

### File Naming Convention
All files for an app share the same prefix (snake_case): `<app_prefix>_privacy.html`, `<app_prefix>_account_deletion.html`, `<app_prefix>_data_deletion.html`.

### Template Files
`template_privacy.html`, `template_account_deletion.html`, `template_data_deletion.html` — always use these as the base when adding a new app. Substitute the app name and any app-specific data collection details. Do not copy from existing app files, as templates are the canonical starting point.

### Key Design Patterns
- **Self-contained files**: Each HTML page embeds all CSS and JavaScript inline — no external stylesheets or scripts (except Google Fonts: Sarabun)
- **Bilingual (EN/TH)**: Every page has a language toggle. English content is in `.en` elements, Thai in `.th`. JavaScript toggles visibility; default is English.
- **Responsive**: Mobile-first CSS with a 768px breakpoint
- **Form submissions**: Deletion request forms use `formsubmit.co` as the backend; no server-side code needed

### Compliance Notes
- Pages must satisfy both **Google Play** and **Apple App Store** requirements
- Apps that collect health or sensitive data need explicit disclosures in their privacy policies — confirm with the developer what data types the app collects before writing the policy
- Thai law compliance: reference **PDPA** (Personal Data Protection Act) for Thai-language sections
- Standard data retention / deletion timeline stated as **30 days**

## Adding a New App — Checklist
1. Copy the three template files and rename with the new app prefix
2. Replace all placeholder app names in EN and TH sections
3. Update the data collection details to match what the app actually collects
4. Add health/sensitive data disclosures if applicable
5. Update the **Apps Covered** table in this file
