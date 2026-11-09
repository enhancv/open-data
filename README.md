# The Data Behind Enhancv's Research

Enhancv runs surveys and interviews on hiring, job searching, and the tools people use to write resumes. This repository publishes the data behind those studies, from survey responses and results tables to recruiter interviews and full transcripts of the head-to-head resume builder sessions.

Use the data to check a figure from one of these studies against the answers behind it, or to run your own analysis.

## Which studies are here?

Newest first:

| Study | Folder | People | Fieldwork | Collected through | What's included |
| :---- | :----- | -----: | :-------- | :---------------- | :-------------- |
| Enhancv vs. Competitors: Head-to-Head Resume Builder Study, 2026 | `us_resume_builder_head_to_head_2026/` | 210 | Feb–Oct 2026 | Respondent.io | participant profiles, results, transcripts |
| US Leadership Journey Survey, 2026 | `us_leadership_journey_2026/` | 500 | Sep 2026 | Pollfish | responses, results |
| US Recruiter Survey on Hiring Seasonality, 2026 | `us_recruiter_hiring_seasonality_2026/` | 500 | Sep 2026 | Pollfish | responses, results |
| US Remote Work and Social Skills Survey, 2026 | `us_remote_work_social_skills_2026/` | 1,000 | Jun 2026 | Pollfish | responses, results |
| AI in Hiring: Candidate Experience Survey, 2026 | `ai_in_hiring_candidate_experience_2026/` | 1,066 | Apr 2026 | Google Forms | responses, results |
| US Overemployment and Multiple Jobs Survey, 2026 | `us_overemployment_2026/` | 1,000 | Apr 2026 | Pollfish | responses, results |
| US Ghost Jobs and Phantom Listings Survey, 2026 | `us_ghost_jobs_2026/` | 1,005 | Feb–Mar 2026 | SurveyMonkey | responses, results |
| US Return-to-Office Mandates Survey, 2026 | `us_return_to_office_2026/` | 1,000 | Mar 2026 | Pollfish | responses, results |
| Recruiter Interviews on ATS Rejections | `recruiter_ats_interviews/` | 25 | Sep–Oct 2025 | Enhancv | interview summaries, results |

## What does each folder contain?

- `survey_meta.json` describes the study: who took part, how many people, when, through which vendor, and how Enhancv protected their privacy.
- `questions.json` lists the questions exactly as asked, with their answer options.
- `respondents.json` (surveys), `participants.json` (head-to-head study) or `interviews.json` (recruiter study) holds one de-identified record per person.
- `results/combined.json` has the answer counts and percentages for every question. Survey results also break down by gender, age, household income, education, and US region, and `results/questions/` splits the same numbers into one file per question.
- `transcripts/` appears in the head-to-head study only, with one anonymized transcript per participant and an `index.json` of all of them.

In the results files, any group of fewer than 10 people shows `"suppressed": true` instead of numbers. A percentage from a handful of people misleads, and small groups are the easiest to re-identify.

## How do the transcripts work?

Each transcript file matches a participant ID in `participants.json`, for example `TL-01.json`. The `final_choice` field records the builder the participant picked at the end, which is their answer to question F1 in `questions.json`.

Speakers appear as Interviewer or Participant. Tags such as `[name redacted]` and `[company name redacted]` replace names, employers, schools, places, contact details, and login details, while the names of the resume builders under test stay in. Apart from the tags, the wording is the raw automatic transcription, errors and all.

## What did Enhancv remove to protect people?

Enhancv applied these rules before publishing:

- No names, email addresses, phone numbers, IP addresses, vendor IDs, or response timestamps appear anywhere.
- Location stops at the US state for surveys and the US Census region for interviews. ZIP codes, counties, metro areas, and media markets are gone.
- Ages and household incomes show as ranges.
- Ethnicity, race, languages spoken, and anything about respondents' children are out.
- Written-in answers to open questions stay private, since free text can reveal who wrote them. Each `survey_meta.json` lists those questions.
- In the interview studies, a broad profession, seniority level, industry, and company-size band stand in for job titles and employers.

## Where does the data come from?

The surveys ran on Pollfish, SurveyMonkey, and Google Forms. For the head-to-head study, Respondent.io recruited experienced US professionals, and an independent moderator ran every session. Enhancv interviewed the recruiters directly.

Each `survey_meta.json` gives the population, method, and fieldwork dates. Survey files also state the weighting.

## Can I use the data?

Yes, for any purpose, commercial work included, as long as you credit Enhancv. Enhancv releases the data under the [Creative Commons Attribution 4.0 International license (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/), and [`LICENSE`](LICENSE) has the full legal text.

### How to credit Enhancv

Name Enhancv and link to the article that reported the study, or to this repository if there's no article:

> Source: Enhancv, "[Study title]," [link]

For example:

> Source: Enhancv, "Enhancv vs. Competitors: Head-to-Head Resume Builder Study, 2026," https://enhancv.com/blog/best-resume-builders/

Online, link the study title to the source page.

## Who can I ask about a dataset?

Email monika@enhancv.com with questions about any dataset or for press requests.
