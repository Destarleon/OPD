# OPD Patient Triage (Educational Prototype)

A small web app that scores an adult patient's vital signs with the **Triage Early Warning Score (TEWS)** from the South African Triage Scale (SATS), saves each visit, and shows how a patient's vitals change over time.



> **Important:** this is a student project for learning. It uses fake patients only, it has **not** been clinically validated, and it is **not** a replacement for any hospital records or triage system. Please do not enter real patient information.

## What it does

- Takes vital signs: respiratory rate, heart rate, systolic blood pressure, temperature, mobility, consciousness (AVPU) and trauma in the last 48 hours.
- Adds up the TEWS and gives a colour with a target time to be seen: Green (within 4 hours), Yellow (within 1 hour), Orange (within 10 minutes), Red (immediate). Any emergency sign makes the patient Red.
- Saves each visit under a patient ID, so repeat visits are linked to one patient.
- Searches patients by name or ID.
- Charts one patient's score or vitals across visits.
- Has a doctor's report section for each visit (diagnosis, notes, treatment plan, follow-up). In the full version this section is restricted to doctors and senior staff; in this public demo it is open so anyone can try it.
- Exports all records to CSV.
- Only accepts adult patients (older than 12 years or taller than 150 cm), because it uses the adult chart.

## Scoring table used

| Parameter | Points |
|---|---|
| Mobility | Walking 0, With help 1, Stretcher/immobile 2 |
| Respiratory rate | under 9: 2, 9-14: 0, 15-20: 1, 21-29: 2, over 29: 3 |
| Heart rate | under 41: 2, 41-50: 1, 51-100: 0, 101-110: 1, 111-129: 2, over 129: 3 |
| Systolic BP | under 71: 3, 71-80: 2, 81-100: 1, 101-199: 0, over 199: 2 |
| Temperature | under 35 C: 2, 35-38.4 C: 0, over 38.4 C: 2 |
| AVPU | Alert 0, Confused 1, Voice 1, Pain 2, Unresponsive 3 |
| Trauma | No 0, Yes 1 |

Colour: total 0-2 Green, 3-4 Yellow, 5-6 Orange, 7 or more Red.

The ranges come from the adult TEWS in the SATS training manual. The points per range follow that chart's column layout and **should be checked against the official printed adult SATS chart** before anyone relies on them. The full SATS also uses clinical sign lists and extra checks such as blood glucose, and a senior healthcare professional can override the colour. This app does not include those.

## How it works

It is a single HTML file with plain JavaScript and no build step. In this standalone version, patient records are stored in your own browser (localStorage), so nothing is sent anywhere and other visitors cannot see what you add. The "Reset demo data" link restores the original fake patients.

To run it locally, download `index.html` and open it in a browser.

## Background

It started as a C++ console program for a class exercise, with ad-hoc thresholds. It was then rebuilt as a web app and its scoring was changed to a published triage score. It was built with help from Claude (Anthropic).

## Feedback welcome

If you work in clinical care or health IT in Ghana, I would really like to know:

1. Which triage tool do you actually use today?
2. Does the scoring table above look right?
3. What would make a tool like this useful, or a waste of time, in your day-to-day work?

Open an issue or message me.

## Credits and licence

- Scoring adapted from the **Adult SATS chart, (c) South African Triage Group / Emergency Medicine Society of South Africa (EMSSA)**, used under [CC BY-NC-SA 3.0](https://creativecommons.org/licenses/by-nc-sa/3.0/). Adaptations of that material are shared under the same licence, for non-commercial use.
- [Add a licence for the rest of the code here, for example MIT.]

## Author

Albert Nii Ayikwei Addo-Quaye Jnr, Computer Engineering student, Ghana Communication Technology University (GCTU).
