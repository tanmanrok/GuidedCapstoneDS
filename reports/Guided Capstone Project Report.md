
# Big Mountain

Problem statement

Big Mountain Resort is facing a $1,540,000 increase in annual operating costs due to the addition of a new chair lift. To remain profitable while maintaining its premium brand, the resort needs to identify ticket pricing and cost strategies that increase total revenue by at least 5% before the next ski season.

Executive summary

I trained a market-price model on regional resorts and used scenario simulations to test the business options. The model indicates Big Mountain’s facilities are consistent with a higher supported weekend ticket price than its current `AdultWeekend` rate (the modelled prediction exceeded the current price by more than the model MAE). Of the scenarios tested, adding a new run plus a chair lift (Scenario 2) produced the largest modeled uplift in supported price and seasonal revenue. Small changes to snow making or modest run-length adjustments produced negligible modeled benefit.

To put the new operating cost in context: using the season visitor assumption of 350,000 visitors and 5 average tickets per visitor (350,000 × 5 = 1,750,000 tickets), the added operational expenditure of \$1,540,000 is about \$0.88 per ticket (1,540,000 / 1,750,000 ≈ 0.88). That per-ticket operating cost is small relative to ticket price, but capital repayment (annualized capital expenditure) and financing materially change the investment case and must be included in a final decision.

Key evidence

- Price distribution with Big Mountain marked:  
![Price Graph](/images/Adult-Weekend-Ticket-Price.png)
![Price Graph](/images/Adult-Weekend-Ticket-Price-Montana.png)
- Scenario 1 (runs closed → price & revenue):  
![Price Graph](/images/Runs-Close-Revenue-Ticket-Price.png)
- Scenario 2 (add run + lift uplift vs revenue):
![Scenario 2](/images/Scenario-2.png)

Story (what I did and what I found)

When I opened the data, Big Mountain looked like a full-featured resort. But plotted against regional peers, its weekend ticket price was lower than peers with similar vertical and terrain. I trained the model using the rest of the market and asked: "Given Big Mountain’s facilities, what price would the market support?" The answer was a higher price than the resort currently charges.

I then ran the business' shortlisted scenarios. Closing a few runs (scenario 1) showed little benefit and risked harming price and revenue as closures grew. Adding a run and a chair lift (scenario 2) produced the clearest modeled uplift: ticket-support and seasonal revenue both increased, enough that the uplift could absorb a material portion of the $1,540,000 operating increase — once capital expenditure and financing are accounted for. The lift-plus-snow making combinations (scenario 3/4) added little incremental benefit over the lift-alone case.

Recommendation (prioritized, practical)

1) Commission a focused financial feasibility study for Scenario 2 (add run + lift). Inputs needed: capital expenditure, useful life, financing terms, and annualized operational expenditure. Use the modeled uplift as a revenue-side input, but run conservative cases (50% and 75% of modeled uplift) to capture demand uncertainty.  

2) Before any major capital commitment, run small, measurable experiments:  
- Controlled pricing tests (A/B) on specific channels or guest segments to estimate elasticity.  
- Operational pilots: if closing runs is still considered, limit closures to 1–2 low-use runs during off-peak windows and measure operational impacts.  

1) Build a simple scenario tool (Small web app or Streamlit) that allows analysts to adjust capital expenditure, operational expenditure, visitor assumptions, and see modeled revenue/NPV outputs immediately. I can scaffold this quickly.  

2) Update the model and re-run scenarios with real cost inputs and elasticity estimates from experiments before moving to final pricing or capital approvals.

Data and assumptions to collect

- Lift capital expenditure, expected lifetime, and financing assumptions (interest rate, amortization schedule).  
- Annual lift operational expenditure (maintenance, insurance, staffing, energy).  
- Historical bookings by date/channel and any pass-vs-day-guest splits.  
- Any planned marketing/promotional spend tied to the lift opening.  

