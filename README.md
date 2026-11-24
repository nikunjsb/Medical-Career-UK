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
5. **Medical Updates** — a dated, curated three-month official-source news archive covering doctors, nursing and immigration, with labels for enacted rules, future changes, consultations, policy announcements and reports. It is not an automated live news feed.
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

## Closing-soon dashboard (17 November 2026)
The dashboard's seven-day deadline count and compact list now respect the visitor's existing browser-stored profession, role, oncology specialty, selected UK cities and radius (subject to verified employer coordinates). It includes unsaved vacancies. Only three matches appear initially; **Show more/Show fewer** expands the list, while **Explore closing jobs** opens Find Jobs with a seven-day filter. The saved-deadlines number remains separate. Search preferences are not re-requested on the dashboard. This feature only filters the current curated vacancy snapshot; it does not provide comprehensive automatic UK-wide updates.

## Curated vacancy expansion — 17 November 2026
Eight further official Trac adverts were added to `data/vacancies.json`, bringing the manually curated set from 12 to **20**. The expansion includes oncology/cancer nursing jobs in Cambridge, Bristol, London, Bournemouth, Luton and Nuneaton, plus a London head-and-neck oncology surgical fellowship. The added cities and profession-specific role filters are included in the browser interface. Previously selected whole-UK locations are migrated to include the new cities.

These adverts are employer snapshots, not a continuously updated service. Closing dates may change or posts may close early. The 17 November Nuneaton vacancy is particularly time-sensitive. Records are removed from the current open view when expired or when the dataset becomes stale. Do not infer nationwide completeness or ongoing eligibility from the count of 20. The compact dashboard change may require GitHub Pages to publish the development branch before it becomes visible.

## Earlier oncology shortlist reconciliation — 17 November 2026
Compared previously discussed oncology openings against existing records. Added four unique employer-linked Trac adverts: Royal Marsden Post CCT Sarcoma Surgery Fellowship (18 Nov), London North West Locum Consultant Clinical Oncology — Urological / Lower GI (22 Nov), London North West Consultant Medical Oncologist in Breast (22 Nov), and Royal Wolverhampton Consultant Medical Oncologist — Colorectal & Breast (17 Nov). This brings the curated dataset from 20 to **24 records**. The Wolverhampton vacancy has a same-day deadline and may expire soon.

Do **not** import previously shortlisted Oxford Gynae Oncology, Bristol Haematology / Oncology Fellow, Wolverhampton Senior Clinical Fellow, or Wolverhampton Gynae Oncology Fellow simply from stale search summaries: their Trac application pages report closure or earlier cut-offs despite inconsistent indexed NHS job pages. Verify employer status before adding them.

Removed the obsolete **Original five** city shortcut; users still have multi-city selection and All UK / Clear cities controls. Existing browser-stored city preferences are retained. The site displays filtered matches, not all records simultaneously.

## Three-month UK medical career news — 17 November 2026
Added `data/medical-updates.json` with **nine** manually researched official-source items published within 17 August–17 November 2026. The Medical Updates tab displays date, source, UK scope, audience, status, summary, career implications and official source URL. Visitors can filter by Doctors, Nursing or Immigration; records outside the rolling three-month window are hidden. The homepage shows the latest news item when the medical-updates setting is enabled. These summaries are an editorial selection, not an exhaustive roundup. Published law with a future commencement date is distinguished from current rules; government policy announcements and consultations are not represented as final enacted requirements.

News freshness is **not automated**. The `curatedAt` field records the review date, and new items must be sourced, reviewed, and committed in future. Avoid promising daily updates until a verified ingestion and review process is implemented.

## Contract details and filters — 18 November 2026
Job cards now display contract type and duration. Separate contract-type and duration filters are saved with browser preferences, restored by backup import, cleared by Reset filters and applied to dashboard matching/deadlines. Duration choices are generated from the dataset, preserving weeks/months/years rather than guessing a month equivalent for display or matching. Permanent has its own duration option. Missing details display **Not stated**, meaning not captured in the curated record, not necessarily absent from the employer advert.

Vacancy records accept optional `contractType` (`permanent`, `fixed-term`, `locum`, `bank`, `not-stated`) and `contractDuration` (`{"value":12,"unit":"months"}` with positive numeric value and weeks/months/years, otherwise null). Older records remain compatible. Populate these from the advertised contract field and term; locum, training, experience requirements, CCT windows and weekly hours do not establish contract length. Permanent roles use null duration and display Permanent. This change backfills only 16 explicit terms already recorded in existing curated summaries; the other 35 records remain Not stated pending employer-advert review. It does not refresh vacancy status or last-checked timestamps.
