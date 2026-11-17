# Medical Career UK

Public, no-login prototype for discovering UK healthcare careers and understanding interview and international-registration pathways. Built as a static site on GitHub Pages.

## Preview
- Website: https://nikunjsb.github.io/Medical-Career-UK/
- Development pull request: https://github.com/nikunjsb/Medical-Career-UK/pull/1

GitHub Pages currently targets the development branch. The main branch is not merged by this work.

## Navigation (November 17, 2026 design update)
1. **My Dashboard** — saved jobs, saved-job deadlines, all vacancies closing within seven days, matching records and update preferences. Application tracking has been intentionally removed.
2. **Find Jobs** — doctor/nurse profiles, specialties, multiple cities, radius, saved jobs and preparation shortcuts.
3. **Interview Prep** — topic and level filters, job-context selection, reviewed example questions, answer guidance and helpful/not-helpful feedback.
4. **Moving to the UK** — optional doctor/nurse pathways separating nationality, qualification, institution, internship, practice and registration history, with a general checklist and links to the GMC or NMC.
5. **Medical Updates** — official links for UK professional and immigration information; live news feed not yet connected.
6. **Settings & Privacy** — dashboard update categories and JSON export/import of local browser data.

The dashboard defaults to all three update categories: jobs, deadlines and medical news. Browser notifications **are not implemented** and are not requested. Selecting Follow on a job stores a local preference, **not a delivered alert**. No login or cross-device sync is present.

## Vacancy data and limitations
The existing `data/vacancies.json` is a manually curated, time-sensitive snapshot of a small set of oncology doctor vacancies. Every external employer link must be reconfirmed before applying; a last-checked time does not guarantee that a listing remains open. No automatic daily import, news feed, email or push notifications are running. The interface does not invent vacancies for nursing or other specialties and shows an honest empty state when no matched listings exist. Hospital-coordinate radius checking only works for verified coordinates; otherwise exact city matching is used.

Current question prompts are illustrative educational material, **not official interview questions or clinical treatment advice**. Job-specific preparation uses the selected job's title and role as context; automatic person-specification extraction and curated external video recommendations remain future work. International pathways are organizational checklists, **not GMC, NMC or visa eligibility assessments**.

## Data and privacy
Bookmarks, notifications preferences, application statuses, personal notes and pathway progress are held in `localStorage` on each browser/device. Clearing site data or private browsing may erase them. Use Export/Import to move between devices manually. Never put passport scans, private credentials, API keys or sensitive documentation into the public GitHub repository. Avoid storing sensitive identification details in local browser notes.

## Official starting points
- GMC: https://www.gmc-uk.org/registration-and-licensing
- NMC: https://www.nmc.org.uk/registration/
- UK Health and Care Worker visa: https://www.gov.uk/health-care-worker-visa
- NICE: https://www.nice.org.uk/

## Checks and release
JavaScript syntax and HTML opening/closing tag counts were checked in the connector environment. Full rendered desktop/mobile, keyboard, accessibility, and end-to-end browser testing are **not yet completed**. Review the development branch and live Pages deployment before any merge to main. Do not enable automatic imports or push without confirmed permitted source access and verified back-end delivery.

## Dashboard adjustment
The dashboard shows **all currently included vacancies closing within seven days**, regardless of saved status, alongside a distinct saved-job count. Spacing between dashboard sections is uniform. The former application tracker (status and personal notes) has been removed at the user's request. The data source remains a time-sensitive manually curated snapshot, not a complete UK feed.
