# Plan: Vision and Features (Section 3.i)

Draft for section 3.i of the report. We will move the final version into the Word document.

**Working name:** NutriScan (not final).

## Vision statement

NutriScan helps shoppers and people who manage their diet make healthier food choices. The user scans or types a product barcode and immediately sees the product's nutrition facts, allergen warnings and a clear health score, and can then log the food in a diary that tracks daily intake against personal goals. Dietitians can follow their clients' diaries and give advice, and all data can be saved, exported and shared as reports.

## User roles

| Role | What the role can do |
|---|---|
| **Consumer** | Scans products, keeps a food diary, sets goals, sees reports, exports data. |
| **Dietitian** | Does everything a consumer does. Also sees the diaries and reports of assigned clients, and writes notes for them. |
| **Admin** | Manages user accounts and roles, and manages the built-in product list. |

## Page and menu structure

```
Login
└── (after login) Main menu
    ├── Dashboard
    │   ├── Today's totals against goals
    │   ├── Average health score for today
    │   └── Recent scans
    ├── Scan
    │   ├── Camera scan
    │   ├── Scan from photo
    │   ├── Enter barcode
    │   └── Search by product name
    ├── Product page (opens from Scan, Diary, Favourites or History)
    │   ├── Nutrition facts (per 100 g and per serving)
    │   ├── Health score and score breakdown
    │   ├── Nutri-Score, NOVA group, "High in" check
    │   ├── Ingredients, allergens and alerts
    │   ├── Healthier alternatives
    │   └── Actions: add to diary, add to favourites, compare
    ├── Diary
    │   ├── Day view by meal (breakfast, lunch, dinner, snacks)
    │   ├── Add, edit and delete entries
    │   └── Add a custom food
    ├── Compare
    ├── Reports
    │   ├── Weekly and monthly charts
    │   ├── Top foods and average health score
    │   └── Export (CSV, print or PDF)
    ├── My Foods
    │   ├── Favourites
    │   └── Scan history
    ├── Profile and Goals
    │   ├── Personal details
    │   ├── Daily targets (calculated or custom)
    │   └── Allergies and diet preferences
    ├── Clients (dietitian only)
    │   ├── Client list
    │   ├── Client diary and reports
    │   └── Notes to client
    ├── Admin (admin only)
    │   ├── Users and roles
    │   └── Product list
    ├── Data
    │   ├── Export backup (JSON)
    │   ├── Import backup
    │   └── Reset demo data
    ├── Settings (units, dark mode)
    └── Help (user guide)
```

## Feature list

**Core** features are the minimum for a complete app. **Extra** features are for extra credit, and we can cut them if we are short of time.

### Pass 1: Foundation

| ID | Feature | Description | Type |
|---|---|---|---|
| F1.1 | App layout | A responsive layout with a header, a main menu and page areas that works on phones and computers. | Core |
| F1.2 | Login and logout | Users sign in with a user ID and password from a list of test accounts. | Core |
| F1.3 | Roles | The menu shows only the pages that the user's role (consumer, dietitian or admin) can use. | Core |
| F1.4 | Local data storage | The app saves all data in the browser, so it stays after the page is closed. | Core |
| F1.5 | Built-in product list | About 20 sample products are included, so the app works without internet. | Core |
| F1.6 | Settings | The user chooses metric or imperial units and a light or dark theme. | Extra |

### Pass 2: Product lookup and scanning

| ID | Feature | Description | Type |
|---|---|---|---|
| F2.1 | Enter barcode | The user types a barcode and the app finds the product. | Core |
| F2.2 | Online lookup | The app gets product data from the Open Food Facts database, and uses the built-in list when there is no internet. | Core |
| F2.3 | Camera scan | The user scans a barcode or QR code with the device camera. | Core |
| F2.4 | Scan from photo | The user uploads a photo of a barcode and the app reads it. | Core |
| F2.5 | Search by name | The user searches for a product by name when there is no barcode. | Core |
| F2.6 | Product page | The app shows the product's name, image, brand and nutrition facts per 100 g and per serving. | Core |
| F2.7 | Scan history | The app keeps a list of recently scanned products. | Core |

### Pass 3: Health score and alerts

| ID | Feature | Description | Type |
|---|---|---|---|
| F3.1 | Health score | The app gives each product a score from 0 to 100, based on sugar, salt, saturated fat, fibre, protein and calories. | Core |
| F3.2 | Score breakdown | The app shows how much each nutrient added to or took away from the score. | Core |
| F3.3 | Nutri-Score and NOVA | The app shows the official Nutri-Score grade (A to E) and the NOVA processing group when they are available. | Core |
| F3.4 | Allergen alerts | The app warns the user when a product contains one of their allergens. | Core |
| F3.5 | Diet alerts | The app warns the user when a product does not match their diet (for example vegan or low sodium). | Extra |
| F3.6 | "High in" check | The app shows whether the product is high in saturated fat, sugars or sodium, based on Health Canada's front-of-package labelling rules. | Extra |
| F3.7 | Healthier alternatives | The app suggests similar products with a better health score. | Extra |

### Pass 4: Diary, goals and dashboard

| ID | Feature | Description | Type |
|---|---|---|---|
| F4.1 | Profile | The user enters age, sex, height, weight and activity level. | Core |
| F4.2 | Daily targets | The app calculates daily targets for calories and nutrients, and the user can change them. | Core |
| F4.3 | Food diary | The user adds a product to a meal with a portion size, and can edit or delete the entry. | Core |
| F4.4 | Custom food | The user adds a food that has no barcode by typing its nutrition facts. | Core |
| F4.5 | Daily totals | The diary shows the day's totals against the targets, with progress bars. | Core |
| F4.6 | Date navigation | The user moves between days to see or change past entries. | Core |
| F4.7 | Dashboard | The home page shows today's progress, the average health score and the recent scans. | Core |

### Pass 5: Reports, comparison and data

| ID | Feature | Description | Type |
|---|---|---|---|
| F5.1 | Charts | The app shows charts of calories and nutrients over a week or a month. | Core |
| F5.2 | Report summary | The app shows averages, the average health score and the most-eaten foods for a period. | Core |
| F5.3 | Compare products | The user compares two or three products side by side. | Core |
| F5.4 | Favourites | The user saves products to a favourites list for quick use. | Core |
| F5.5 | Export CSV | The user downloads the diary as a CSV file for a spreadsheet. | Core |
| F5.6 | Print report | The user prints a report or saves it as a PDF. | Core |
| F5.7 | Backup and restore | The user exports all data as a JSON file and imports it again later. | Core |

### Pass 6: Roles, help and polish

| ID | Feature | Description | Type |
|---|---|---|---|
| F6.1 | Client list | A dietitian sees a list of assigned clients and their recent progress. | Core |
| F6.2 | Client view | A dietitian opens a client's diary and reports (read only). | Core |
| F6.3 | Client notes | A dietitian writes notes that the client sees on their dashboard. | Extra |
| F6.4 | User management | An admin creates, edits and deletes users and changes their roles. | Core |
| F6.5 | Product management | An admin adds and edits products in the built-in product list. | Extra |
| F6.6 | Help page | A user guide inside the app explains each page. | Core |
| F6.7 | Accessibility | The app works with the keyboard, has good colour contrast and labels all controls. | Extra |

## Technical approach

The whole app is **one self-contained HTML file**. It uses plain JavaScript, or React loaded from a CDN, with no build step and no server.

| Part | Choice |
|---|---|
| Code | One `.html` file. The `.txt` copy for deliverable 4 is the same file, renamed. |
| Data storage | The browser's `localStorage`. Users can export all data as a JSON file and import it again (F5.7). |
| Login | Test accounts and roles are written into the app (F1.2, F1.3). There is no real authentication. |
| Product data | The Open Food Facts API. It needs no API key and allows requests from a local file. The built-in product list is the fallback when there is no internet (F1.5, F2.2). |
| Barcode scanning | A scanner library loaded from a CDN, for example `html5-qrcode`. Manual entry and scan from photo are fallbacks when the camera is not available (F2.1, F2.4). |
| Companion site | The same file hosted on Vercel or GitHub Pages. This gives a live HTTPS link, where the camera works best. |

**Why not Next.js with a Supabase database?** We first considered this option, but it does not fit the assignment:

1. **Deliverable 4 needs the code as one `.html` file** that any user can open and use with all functions. A Next.js app has many files and needs a build step and a server.
2. **Free Supabase projects pause after about a week without activity.** Marking happens some weeks after the deadline, so the marker could see a broken app.
3. **The app must not depend on an outside service** that can stop, change or need keys. With a single file, only the product lookup needs the internet, and the built-in list covers that.

**Limitations.** Each browser keeps its own data, so data does not move between devices unless the user exports and imports it. The login protects nothing, because all data is on the user's device. These limits are acceptable for a prototype, and we will state them in the user instructions.

## Open decisions

1. **App name.** "NutriScan" is a placeholder. Check that the final name is not an existing product.
2. **Target users.** Do we focus on Canadian shoppers? This fits the Health Canada "High in" feature and the executive summary evidence.
3. **Scope.** Do we keep the dietitian and admin roles? They add marks for comprehensiveness, but they also add a full pass.
4. **Tool for the passes.** Claude Code or a chat interface (see the notes on recording).
