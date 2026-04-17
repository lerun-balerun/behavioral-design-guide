# Behavioral Design Skill — Validation Cases

Nine published behavioral design cases from Irrational Labs, academic RCTs, and applied practitioner work. Each case contains only the **user-facing context** — what a product manager, researcher, or practitioner would tell the skill when starting a new session. Ground truth (what the published teams actually found, diagnosed, designed, and measured) lives in a separate file and is not used during solving.

The solver should read one case at a time, treat the context as a first-person user input, and walk the skill through all 8 stages (DEFINE → MAP → EVIDENCE CHECK → DIAGNOSE → DESIGN → OPTIMIZE → TEST → ANALYZE → SCALE), producing a structured output at each stage.

---

## Case 01: RecoveryOne — Virtual Physical Therapy Enrollment

> "I'm a product designer at RecoveryOne, a virtual physical therapy platform offered through employer health benefits. Our problem: patients are referred by their employer health plan, land on our website, but most don't complete enrollment. Current enrollment rate is around 34%. We have analytics showing where people drop off in the enrollment flow, and we've done some qualitative research with people who dropped off. Team: 1 PM, 2 designers, 1 data analyst. We have about 500 new referrals per month."

---

## Case 02: Marvin — Virtual Therapy Platform for Healthcare Workers

> "I'm a product manager at Marvin, a virtual therapy platform available through employer health benefits for hospital workers. Nearly half of medical professionals report burnout, but very few seek therapy. Our landing page converts at about 10% — people visit but don't enroll. We have website analytics (traffic, bounce rates, funnel drop-off) and some NPS data from existing users. We don't have direct qualitative research with people who didn't enroll. Team: 1 PM, 1 designer. About 200 new page visitors per month from employer referrals."

---

## Case 03: AdmitHub — FAFSA Application via SMS

> "I work at AdmitHub, an AI-powered mobile messaging platform for student success. We're partnering with West Texas A&M University. The problem: many eligible students fail to submit the FAFSA (Free Application for Federal Student Aid), leaving billions in financial aid unclaimed. The school's FAFSA submission rate has been declining year-over-year. We have access to student records (who is eligible, who submitted), and we can send SMS messages through our platform. Students are already receiving some generic reminders. Team: 2 product people, access to university data. Student population: ~2000 eligible students."

---

## Case 04: Steady — Bank Account Linkage for Gig Workers

> "I'm a product manager at Steady, a mobile app that helps gig workers find jobs and maximize their earnings. We have an Income Tracker feature that lets users see earnings from all their gig jobs in one place, and we can pay bonuses directly into their bank account. But both features require bank account linkage via Plaid.
>
> The problem: 92.9% of users who reach the bank-linking step during onboarding don't complete it. They just tap past it. We currently show a screen explaining the benefits with a 'Continue' button and a 'Maybe Later' option. We want to try re-engaging users who skipped — we can target people who created an account in the last 7 days but didn't link. We have about 15,000 eligible users per cohort and can run a randomized experiment with an in-app pop-up."

---

## Case 05: Credit Karma Money — Recurring Transfers

> "I'm on the product team at Credit Karma. We recently launched Credit Karma Money Spend, a new checking account. Users can fund it either by manually transferring money from their other bank or by setting up direct deposit. The problem: when users make a manual transfer, the funds can take several days to become available. Users sometimes forget to transfer until the last minute and then don't have access to their money when they need it. We've been getting complaints about this delay.
>
> We want to increase the number of users who set up recurring transfers or direct deposit so their account stays funded automatically. We have a product team (PM, designer, researcher, analytics), full funnel data, and enough volume to run multi-condition A/B tests. We're open to intervening at any point in the user journey."

---

## Case 06: EarnUp — Mortgage Overpayment

> "I'm a product manager at EarnUp, a fintech platform that helps homeowners pay back their mortgage faster by timing payments with their paydays. We want to get more of our existing users to increase their monthly mortgage payment above the required minimum — even a small increase saves thousands in interest over the life of the loan.
>
> We have access to our users' payment history data and can see exactly what amounts people are currently paying. We can reach users via email during the sign-up flow or after they're already set up. We have enough users for a randomized experiment. Our team has a PM, a data analyst, and partnership with a behavioral science research lab."

---

## Case 07: Mumbai Suburban Railways — Reducing Trespassing Fatalities

> "I work for a behavioral science consultancy. We've been hired by the Mumbai suburban railway authorities to reduce pedestrian fatalities from track trespassing. About 3,000 people die annually crossing the railway tracks — roughly 8-10 per day. The railway runs at ground level through extremely dense urban areas, and trains pass every minute or so at 60+ mph. There are foot-over bridges at stations, but they're steep and hard to climb, so many people take the shortcut of crossing the tracks directly.
>
> The authorities have already tried many things: warning signs posted at tracks, daily print and radio ads about the dangers, building walls and fences, and enforcement drives to catch and fine trespassers. None of it has worked.
>
> We have no app or digital product. Our interventions would be physical changes to the railway environment. We can observe trespassing behavior, analyze fatality records, and pilot interventions at specific high-risk trespassing points. One pilot site averages about 40 fatalities per year. Multiple languages are spoken in the city and some residents are illiterate."

---

## Case 08: Truancy Notifications — School Absence Letter Redesign

> "I'm an administrator at a large urban public school district. State law requires us to send truancy notification letters to parents when their child accumulates three or more unexcused absences. We send these letters monthly via mail in five languages.
>
> The problem: our current letters don't seem to be doing much. Students who receive them continue to miss school at roughly the same rate. The letters are written by our legal team — they're about 380 words, written at a 10th-grade reading level, and include seven bullet points of legally mandated language about parental liability, fines, prosecution, and potential jail time.
>
> We can't stop sending the letters (it's legally required), and we must include the mandated legal language somewhere. But we want to know if changing HOW we write the letter could reduce subsequent absences. We have about 150,000 truant students per year across all grade levels. 84% qualify for free/reduced lunch, ~50% are Spanish-speaking, 12% are Black/African-American. We have full attendance data from our student information system and can randomize at the household level."

---

## Case 09: School Cafeteria — Healthy Food Selection

> "I'm the food services director for a large urban school district. We serve lunch to about 3,000 students daily across 14 elementary and middle schools. Federal regulations require us to offer fruits, vegetables, whole grains, and lean protein at every meal — so the healthy food IS available. But students aren't choosing it or eating it. They walk past the fruit and grab cookies. They take the required vegetables but throw them away.
>
> We can't remove unhealthy options entirely (students can buy à la carte items, and we need the revenue). We can't change the menu dramatically (federal requirements, budget constraints, existing kitchen equipment). What we CAN change is how the cafeteria is set up: where foods are placed, how they're displayed, what students see first, signage, verbal prompts from staff, and the flow of the lunch line.
>
> We have plate waste data (we can measure what students select and what they actually eat), enrollment and participation data, and we can pilot changes in some schools while keeping others as controls. Team: me, 2 nutrition coordinators, and cafeteria managers at each school. Budget for changes is very small — maybe $50-100 per school for materials."

---

*End of cases file. Do not consult the ground truth file while solving.*
