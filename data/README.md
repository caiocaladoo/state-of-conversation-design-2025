# State of Conversation Design 2025: public dataset

286 respondents. Free text translated to English and anonymized.

**Version:** 1.0 (edition 2025/26) · **Date:** 2026-11-26 · **Source:** State of Conversation Design survey (SoCD26), 286 responses.

## The simple way: `SoCD26_public.xlsx`

| Sheet | What it is |
|---|---|
| `responses` | **Start here for your own analysis.** One row per person and one column per survey question, in the order of the questionnaire, with the answers written out, open answers included. Multiple choices are joined with "; ". Ratings are 1–5 (Q35 shows how often, from Never to Daily). |
| `highlights` | Headline findings, one line each. |
| `results` | All aggregate results in one table. Filter by `section` (choices, ratings, geography, region flow, platforms/tools/communities, themes, responses over time) and `question_id`. |
| `compare_groups` | Salary, remote work and rating averages by region, level, gender, experience and company size. Groups under 10 people are combined into one group, "Other groups (fewer than 10 people each)". |
| `respondents` | One row per person (random ID). Multiple-choice answers are joined with "; ". Ratings are numbers. Experience and salary bands also come as numeric min/max. Geography: world region and country; countries with fewer than 10 people are shown as "Other (region)". |
| `open_answers` | Every open-ended answer in English, with the themes assigned so far. Filter by `question`. |
| `dictionary` | What each column in `respondents` means and its allowed values. |
| `clusters` | Cluster dictionary for the 16 classified open questions: description, "not this", 4 real examples, size of each cluster. |

This folder holds the public download: this README, the workbook, and the same data as a normalized database.

- `SoCD26_public.xlsx`: the workbook, described above.
- `SoCD26_public.sqlite`: normalized tables for analysis (`responses` and `responses_columns`, the same one-row-per-person table with short column names and their full questions, `respondents`, `respondents_wide`, `answers_choice`, `answers_scale`, `answers_text`, `answers_entity`, `entities`, `answers_theme`, `themes`, `clusters`, `questions`, `options`, `dictionary`, `results`, `compare_groups`, `open_answers`). Each person is a random id (`R001`..`R286`), the same in every table. Choice labels: `answers_choice.(question_id, option_id)` → `options`. Clusters: `answers_theme.(question_id, theme_id)` → `themes`.

## Open-answer clusters (round 2)

- 16 open questions are classified against a closed set of clusters per question (6-10 clusters plus "Other"): Q17, Q18, Q19, Q22, Q23, Q24, Q25, Q28, Q31, Q34, Q36, Q37, Q40, Q41, Q42, Q48.
- Q18 (job title) is single-label. All the others are multi-label: an answer gets up to 3 clusters.
- "Other" is exclusive: an answer in Other has no other cluster. Clusters with fewer than 3 answers were merged into Other.
- `answers_theme` has one row per answer and cluster, with an `evidence` snippet and a `method` (`rules` = keyword pass, `review` = checked by hand). The definitions, "not this" and examples are in `clusters`.
- Method: keyword pass over the English text, then a manual review of every answer left in Other and of samples of the rest. It is a first classification, not a gold standard: the `method` column lets a later model re-check or replace it.
- Platforms, channels, tools and communities (Q28, Q31, Q34) are extracted by name matching into canonical names with a type.

## What was removed from the free text

- Empty placeholders and keyboard filler in required fields ("-", ".", "N/A", "n/a", "Na", "Nil", "aaaa", "ssss", etc.) are treated as no answer.
- "I don't know"-type answers ("idk", "no sé", "não sei") are kept as answers.
- One answer with a personal name and email, and one off-topic political statement about named public figures, were removed.

## Privacy

- Removed: names, emails, IPs, submission IDs and dates, timers, consent flag, referral names, and all other survey-platform data. IDs are random.
- Responses over time are shown only as weekly totals.
- Employers, clients, universities and individual names (including authors and speakers people recommend) in free text became `[company]`, `[client]`, `[university]`, `[expert]`. Platforms, tools, training providers, communities, events and book titles are kept.
- Open answers where a respondent described their own age, country, employer or team size were made generic. Mentions of a country as a topic, and names of communities and events, are kept.
- "Middle East and North Africa" and "Sub-Saharan Africa" are shown together as "Middle East, North Africa and Sub-Saharan Africa", because one of them had fewer than 10 people.
- Geography in `respondents` is world region and country, with countries under 10 people grouped as "Other (region)". Aggregate results (`results`, `compare_groups`) are computed on the full data and keep their own grouping: groups under 10 people are combined.

## What was removed or generalized in the respondent table (and why)

| Change | What | Why |
|---|---|---|
| Small countries | `origin_country` and `residence_country` keep countries with 10 or more people; the others are shown as "Other (region)". ISO codes removed. | A country with very few people, plus level or salary, can single out a person. |
| Age | `age`, `age_min`, `age_max` removed. | Age is a strong identifier combined with region and level. |
| Company size | `company_size`, `company_size_min`, `company_size_max` removed. | Narrows down the employer and so the person. |
| Design team size | `design_team_size`, `design_team_size_min`, `design_team_size_max` removed. | A small team size points to a specific team. |
| Underrepresented groups | `underrepresented_groups` removed. | Sensitive personal information. |
| Normalized database | In `answers_choice`, the per-person rows of q06, q04 (age), q13 (company size) and q14 (design team size) are removed. | So the removed answers cannot be rebuilt from the long table. |

The respondent tables have all 286 people. The `dictionary` sheet describes every column that is kept.

Respondent-level data can never be made impossible to recognise: many people have a unique combination of answers. Please do not try to identify anyone.

## Notes

- Ratings 1–5 are agreement. Collaboration frequency maps Never=1 … Daily=5.
- Percentages use the people who answered that question (open-answer themes: people who wrote an answer).
