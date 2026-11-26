---
name: socd-open-data
description: Explore the State of Conversation Design 2025/26 open survey data (286 conversation designers): download it from GitHub, draw charts in the report's style, and answer questions with n and caveats, linking to the published report (edition 2025/26).
---

# State of Conversation Design open data

When the user asks about the State of Conversation Design data, help them explore the open data of the "State of Conversation Design 2025/26" survey: 286 respondents, a self-selected sample reached through communities, collected January to April 2025.

Repository: https://github.com/caiocaladoo/state-of-conversation-design-2025
Data notes (read first): https://raw.githubusercontent.com/caiocaladoo/state-of-conversation-design-2025/main/data/README.md
CSV files (one per table): https://raw.githubusercontent.com/caiocaladoo/state-of-conversation-design-2025/main/data/csv/<table>.csv
Main tables: responses (one row per person, one column per survey question, answers written out; column names and full questions in responses_columns), results (all aggregate results), compare_groups (pay, remote work and ratings by region, level, gender, experience and company size), respondents_wide (one row per person, random id, with world region and country), open_answers (open answers in English, with themes), questions, options, dictionary.
If you cannot open the links, ask me to attach data/SoCD26_public.xlsx.
Report map: https://raw.githubusercontent.com/caiocaladoo/state-of-conversation-design-2025/main/report/REPORT_MAP.md (also report/report_index.json). It lists every page of the published report (https://stateofconversationdesign.com/2025/): the 60 numbered findings (F01–F60), the charts, chapters and archetypes, each with a summary and a link. The site itself is built with JavaScript, so read the map instead of fetching the site pages.

Step 1. Download results.csv and compare_groups.csv and build ONE interactive artifact (a single page) with these three starter charts:
  a. "Where respondents live": share of respondents by world region (results, section "Geography", question "Residence region").
     In the report: https://stateofconversationdesign.com/2025/chart/1.03 (finding F02).
  b. "Median yearly pay by level": median_salary_usd by level from compare_groups, dimension "Level", ordered Entry-level, Mid-level, Senior-level, Principal, Manager, Director/VP/C-level; leave out the "Other groups" row.
     In the report: https://stateofconversationdesign.com/2025/chart/9.15 (pay by level inside each place) and finding F12.
  c. "What people expect for 2025": share who agree (pct) for question q45 in results.
     In the report: https://stateofconversationdesign.com/2025/chart/7.45
  Show the value and n on every bar.
  Under each chart, a source line with two links: "Source: State of Conversation Design 2025/26 survey (n = 286), open data" (linking to the repository) and "See it in the report" (linking to that chart's report page).
  At the top of the page, one line: "Built from the open data of the State of Conversation Design 2025/26 report", with a link to https://stateofconversationdesign.com/2025/. At the bottom, links to the report and to the repository.

Step 2. Then tell me in two or three sentences what the charts show, say where the data comes from (the State of Conversation Design 2025/26 survey, January to April 2025, 286 respondents, open data in the repository above) and give the link to the official report (https://stateofconversationdesign.com/2025/) and to the matching report pages. Suggest three questions I could explore next. Wait for my question.

Connecting the data with the report:
- When the report already covers my question, say so and link the finding or chart from the report map (for example "F12" with its link), then add what the data shows beyond it.
- When your own calculation differs from a number in the report, say so. The report was computed on the full data before anonymization. The public data has world region and country, but countries with fewer than 10 people are grouped as "Other (region)", and age, company size and team size per person were removed.
- Always name the edition: "State of Conversation Design 2025/26", survey of January to April 2025.

Style (the report's brand), for every chart you make:
- Read the brand guide first: https://raw.githubusercontent.com/caiocaladoo/state-of-conversation-design-2025/main/brand/BRAND.md . Look at the report's own chart exports and copy their structure: https://raw.githubusercontent.com/caiocaladoo/state-of-conversation-design-2025/main/images/report-chart-7-45.png (also report-chart-1-03.png and report-chart-9-15.png).
- Layout of each chart card: header with the "SoCD" logo (white on indigo #4D49FC, the "o" in green #24CB71, font Dela Gothic One) and "State of Conversation Design 2025/26"; an indigo left panel with the chart number, the title, the question as asked and a one-sentence takeaway with the key numbers in yellow #FFC700; a light right panel with the chart; a footer with "n = … · Edition 2025/26" and the report link.
- Fonts: "Dela Gothic One" for titles, "IBM Plex Sans" for text, "IBM Plex Mono" for numbers such as n (Google Fonts).
- Colors: background #F5F5FD, text #0E0D2E, secondary text #3A3965 and #5A5984, lines #DAD9F0, main bars #4D49FC. Extra series, in this order: #0391D6, #D92A2A, #B93FC4, #B88600, #0F9C55. Grey #8A8AA8 for "other" groups.
- Never use color alone to tell things apart: label bars and lines directly, and add patterns, outlines or markers when there is more than one series. Horizontal bars for long labels.
- Footer of the page: "State of Conversation Design 2025/26 · open data", with the report and repository links.

Rules for every answer:
1. Use only this data. If it cannot answer my question, say so.
2. For every number, say how many people are behind it (n) and which question or table it comes from.
3. Do not draw conclusions about groups with fewer than 10 people; say the group is too small.
4. A correlation is not a cause: say "is associated with", not "causes".
5. Say the results describe the people who answered, not the whole field.
6. Ratings are 1 to 5 (agreement). Percentages use the people who answered that question.
7. Never try to identify or describe a single person, and do not quote an open answer in a way that could point to who wrote it.
8. Show your calculation or code so I can check it, and give a short, plain-language summary first.
9. End every answer with its sources: the data table(s) used and, when relevant, the report page links, with the edition (2025/26).

How to install: zip the `socd-open-data` folder and upload it in the Skills area of your Claude settings. Then ask, for example, "Show me pay by level from the State of Conversation Design data".
