---
title: Delve — Privacy Policy
---

# Privacy Policy

**Last updated:** May 6, 2026

Delve is a mobile app that scans bookshelves and recommends books based on your reading taste. This policy explains what data Delve collects, how it's used, and the choices you have.

If anything here is unclear, email **orthanc.bct@gmail.com**.

---

## Who we are

Delve is built and operated by Adam Keller as an independent project. There is no company behind it.

---

## What we collect

### Account data
When you first open the app, Delve creates an anonymous Firebase account so your library follows you across sessions on the same device. If you sign in with Google, Delve also receives:

- Your Google account email address
- Your display name
- Your profile photo URL

### Library data
Anything you add to your in-app library is stored against your account:

- Books on your *Read*, *To Read*, and *Currently Reading* shelves (title, author, ISBN, cover image URL, publication year)
- Your ratings (1–5 stars)
- Reviews and private notes you write
- The date you read a book and the date you added it
- Where the entry came from (manually added, Goodreads import, or saved from a scan recommendation)

### Goodreads imports
If you import a Goodreads CSV, Delve reads every row in the file and stores the same fields listed above. The CSV file itself is not retained after import — only the parsed data lands in your library.

### Reading preferences
- Genre interests you select during onboarding (e.g. "Sci-Fi", "Memoir & Biography")
- Optional free-text description of favorite authors or themes (up to 500 characters)
- Adventure level (1–5), which controls how far recommendations stray from your established taste

### Scan data
Each time you scan a shelf:

- The photo is uploaded to Delve's API and forwarded to Anthropic's Claude API for book identification. **Delve does not save the image on its own servers** — it streams through the request and is discarded.
- The most recent 3 scans are cached **locally on your device** (image file + identified books + recommendations) so the home screen can show thumbnails. These never leave your phone unless you re-scan.
- A scan record is kept on the server with: scan ID, timestamp, image size in bytes, the AI model used, token counts, latency, number of books identified, status (success / quota-denied / error), and any error code. **The image bytes themselves are not stored.**

### Recommendation data
When recommendations are generated, Delve sends Anthropic a condensed summary of your taste profile (loved books, disliked books, want-to-read list, genre interests, adventure level). The full recommendation result is logged against your account along with token usage and the AI model used.

### Usage analytics
Delve records a small set of named behavioral events to understand how the app is used: onboarding step viewed, interests saved, Goodreads import started/succeeded/failed, scan started/succeeded/failed, scan quota denied, recommendation card tapped, recent scan tapped, Pro upgrade prompt shown/tapped, Google sign-in completed, anonymous account upgraded, screen viewed, book search performed, book added/removed, book shelf changed, book rating changed. Each event includes the event name, a small JSON properties bag (capped at 4 KB), a session ID, and timestamps.

### Error reports
If the app or backend crashes, anonymized stack traces and contextual metadata are sent to Sentry to help fix the bug. Reports are tagged with your Firebase user ID so a single failure can be debugged across multiple events. No request bodies, scan images, or library content are included in error reports.

---

## How we use your data

- To run the app's core feature: scanning shelves and producing recommendations.
- To enforce monthly scan quotas (so the app's AI costs stay manageable).
- To improve the app — analytics show which features users actually use and where they get stuck.
- To debug crashes and errors.

Delve does not sell your data, share it with advertisers, or use it for marketing.

---

## Who else processes your data

Delve relies on a small set of third-party services. Each has its own privacy policy:

| Service | What it processes | Why |
|---|---|---|
| **Firebase Authentication** (Google) | Account identity, email, name, photo | Sign-in and account management |
| **Google Cloud SQL** (Google) | All server-side data | Database hosting |
| **Google Cloud Run** (Google) | All API requests | Backend hosting |
| **Anthropic (Claude API)** | Scan images, taste-profile summaries | Book identification and recommendations |
| **Google Books API** (Google) | Search queries you type when adding books | Finding cover images and metadata |
| **Sentry** | Error stack traces, request metadata, your user ID | Crash reporting |
| **Google Sign-In** (Google) | Your Google account credentials | Optional sign-in upgrade |

Anthropic's data handling is governed by their commercial terms — they do not train on data submitted via the API.

---

## How long we keep it

- **Account, library, ratings, interests:** kept until you delete your account.
- **Scan records (metadata, no images):** currently kept indefinitely. A 180-day retention window is planned.
- **Analytics events:** currently kept indefinitely. A 180-day retention window is planned.
- **Locally cached scans on your device:** the most recent 3 only; older ones are deleted as new scans replace them.
- **Error reports:** retained per Sentry's default retention (~90 days).

---

## Your choices

- **Edit or delete individual books:** Library tab → tap any book.
- **Update your interests or adventure level:** Settings tab.
- **Re-import or replace your Goodreads library:** Settings → Re-import Goodreads CSV.
- **Delete your account and all associated data:** Settings → Delete account. This permanently removes your profile, library, ratings, scan records, and analytics events from Delve's servers, and removes your Firebase account. Locally cached scans on your device are also cleared.

If you can't access the app and need data deleted, email **orthanc.bct@gmail.com** with your account email and we'll handle it manually.

---

## Children

Delve is not directed at children under 13 and does not knowingly collect personal information from them. If you believe a child has created an account, email **orthanc.bct@gmail.com** and we'll delete it.

---

## Changes to this policy

If this policy changes in a way that affects how your data is handled, the **Last updated** date at the top will change. Material changes will also be flagged in-app on next launch.

---

## Contact

Questions, concerns, or data requests: **orthanc.bct@gmail.com**
