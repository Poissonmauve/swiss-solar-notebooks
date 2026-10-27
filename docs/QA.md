# Likely questions, short answers

The section in brackets says where the answer comes from in `midterm_eda.ipynb` (which starts from the raw files), or on which slide.
Feed-in numbers: Données des tarifs de rétribution: VESE / pvtarif.ch (http://www.vese.ch, http://www.pvtarif.ch).

## Question and data

**Why does this matter?** (slide 2)
Switzerland's target is 35 TWh of new renewable electricity (excluding hydropower) by 2035, set in the Electricity Act accepted in June 2024. A panel pays off through the electricity the household no longer buys and through what it earns for the power it sends to the grid, and the local operator sets both prices. If households respond to these prices, tariffs are a policy lever. 2023 is a rare test: a big, sudden increase (+28% for the median commune, +5.1 ct/kWh) that differed a lot between neighbouring communes.

**What is new compared with the literature?** (slides 3–4)
- Feger et al. (canton of Bern, 165,000 households, structural model): adoption reacts weakly to prices, partly because only about a quarter of households own their home. That is why we look at owner share. Limit for us: prices barely varied in their data.
- Kiso et al. (Japan, prefecture panel around Fukushima): higher prices raised solar on existing homes (elasticity about 1.6) but barely on new builds (about 0.5, not significant). Limit for us: prices rose gradually over three years and came from only ten regional utilities. (Their feed-in tariff and subsidy started in 2009, nationwide, so they are not a confounder there; for us feed-in moves with X, which is worse.)
- Filippini & Garnache (Norway, 2022–23 crisis, working paper): installations surged in the expensive south compared with the north, and buyers put about 70% weight on current prices. Limit for us: all their variation comes from one north–south border (they group five price zones into two regions).
- We found no study of solar adoption that uses the 2023 Swiss tariff jump: one sudden shock, passed on by hundreds of local operators by different amounts, so communes can be compared within cantons. Frings et al. (2024) used the Swiss and German crisis for a survey of energy-efficiency preferences, not solar adoption. Our search was not exhaustive.

**Isn't your shock also "a shock with something else"?** (slide 4)
Yes. Feed-in tariffs moved with it (r = 0.79) and it came during a crisis everyone saw. What is new is the amount of price variation: hundreds of operators, inside cantons. Slide 15 lists the problems.

**How did you clean the data?** (section 1)
1. We kept the 297,633 solar plants commissioned 2015–2025 from the federal register.
2. We placed each plant in a commune with its coordinates (99.3%), or with its postcode if it has none.
3. We mapped every commune to its 2026 version, because communes merge.
4. We counted plants per commune and year.
5. We averaged the H4 tariff over the operators serving each commune.
6. We kept the communes with tariffs for 2022 and 2023: 2,098 of 2,110. The 12 dropped communes (8 in Graubünden, 2 in Aargau, 1 in Fribourg, 1 in Vaud) have no 2022 tariff.
7. We dropped 2026, which is incomplete.

**Why the H4 profile?**
It is ElCom's standard household (5-room flat, 4,500 kWh/year), the usual reference. Measured with other household profiles (H2, H7), the 2023 increase is almost identical (correlation 0.99; checked separately).

**Why the change in the tariff, not its level?**
Each commune is compared with its own past growth, so long-standing level differences drop out; the change is the shock. High-shock communes even had lower 2022 tariffs than low-shock ones (section 4).

**Why the commissioning date?**
It is the only date in the register. It records the grid connection, a few months after the decision. That is why we take 2023 and 2024 together and leave 2022 out.

**Did you remove outliers?** (section 3)
No. The 17 communes with increases above 25 ct are real: they are served by small local utilities. Installations are skewed (cities add hundreds a year, slide 9), so we compare growth rates, not levels.

**Why log(1 + n)?** (section 4)
Y is a skewed count. Logs make growth comparable between small and big communes, and the +1 handles communes with zero installations. Growth is positive in 98% of communes (slide 9). In the final we will use a count model, which handles zeros directly. "0.24 log points ≈ 27%" is approximate because of the +1.

**Z is from 2000. Isn't that outdated?** (slides 5 and 10)
It is the latest tenure data at commune level. Owner shares change slowly, but it is a real limitation. It is missing for 35 communes merged before 2010; they are left out of the Z comparison only.

## Patterns

**What does "74% of the variance is within cantons" mean?** (section 3)
After removing each canton's average, 74% of the variation in X remains. So comparing communes within a canton removes cantonal rules and subsidies but keeps most of the variation. The shock is really set by operators: 495 main operators (section 1), so about 495 independent shocks, not 2,098.

**What does the 0.24 slope mean? Is it significant?** (section 4, slide 13)
We remove the canton average from X and from growth, then fit a straight line. Within the same canton, +10 ct/kWh of increase goes with about 27% faster growth (95% CI 0.20 to 0.28). Before the shock (growth from 2017–18 to 2020–21), the same slope is 0.02 (95% CI −0.03 to 0.07): no detectable relationship. The intervals allow communes served by the same operator to share their errors (495 operators).

**Is that causal?**
No. Slides 15 and 16 explain why it could be misleading and what the final will do about it.

**Isn't the thirds chart just big cities?** (section 4, slide 12)
The index sums installations, so big communes weigh more. That is why we rely on the commune-by-commune slope (slide 13), where every commune counts once.

**Didn't the low-shock communes get their increase later?** (section 4)
Partly: +5.4 ct in 2024, against +1.1 ct for the high-shock communes, so the tariff gap halved (8.6 → 4.3 ct). X measures who was hit first and hardest, and we see a short-run difference between communes. In the final we will look at each year separately.

**More solar, or just earlier?**
We can't tell yet. The final will test whether total installations changed, not just their timing.

**Why index to 2021 = 100?** (section 4)
The groups have different sizes, so we compare how each one grew from its own level. 2021 is the last full year before the shock was announced (August 2022).

**Is the owner gap real?** (section 4, slide 14)
It is descriptive: 308 vs 237 above the median owner-occupier share, 280 vs 241 below. Above the median, the high-shock third already led in 2022 (160 vs 139), when the 2023 tariffs were known but not yet applied: possible anticipation, which the final will test. It is a median split, not owners against tenants. Owner share also moves with house type (r = 0.41) and commune size (r = −0.62), so we will test it as a continuous variable in the final.

## Causality (slides 15–16, section 5)

**Was the shock random?**
No. Operators set tariffs from their own costs. Regional utilities got smaller increases (5.8 vs 8.5 ct), and so did communes with high 2022 tariffs (r = −0.26). That is why we compare within cantons over time, check trends before 2022 (slope 0.02), and will compare neighbouring communes with different operators.

**Couldn't it be the feed-in tariff, not the retail price?**
It could. The same operator sets both, and the two changes move together (r = 0.79). So for now the 0.24 is a response to the operator's whole tariff package. We will try to separate the two in the final, and say clearly what can and cannot be separated.

**Doesn't comparing within cantons miss municipal subsidies?**
Yes. Some communes run their own PV subsidies. Comparing neighbours does not remove them. The final should collect them and check whether X predicts them.

**Is there a comparison group without the shock?**
No. Every commune saw the crisis and the media attention, and the low-shock communes got their increase a year later. We measure a short-run difference between communes, not the total effect of the crisis.

**Installer bottlenecks?**
Possible. Backlogs would delay and cap the response, so 2023 alone may understate it. We will look at 2024–25.

**Reverse causality?**
Unlikely. 2023 tariffs were published by the end of August 2022, before the installations we count, and X is unrelated to how much PV a commune already had (r = 0.03). One channel to know: more self-consumed solar means fewer billed kWh, which can push up grid fees. But 87% of the 2023 increase was the energy part, not grid fees.

**Can you extrapolate?**
Only with care. It was a crisis with heavy media attention, and the tariff gap between communes halved by 2024. We observe commune averages, not households: Z is a commune share, so we cannot say owners themselves reacted more. Y includes farms and firms: 12% of plants are above 30 kW (section 1). The sample drops 12 communes and Z is missing for 35.

**Do you have results yet?**
Not causal ones; the midterm is descriptive. The final adds a regression within cantons over time, tests for pre-trends and anticipation, compares neighbouring communes, uses Z as a continuous variable, and assesses retail against feed-in.

**Spillovers?**
Neighbouring communes share installers and neighbours talk, so a high-shock commune can raise installations next door. That would bias the comparison of neighbours towards zero. We will keep it in mind when comparing neighbours in the final.
