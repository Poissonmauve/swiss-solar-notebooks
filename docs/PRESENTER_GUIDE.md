# Presenter guide: script, the whole study explained, and Q&A

For the deck `midterm_E4S_v2_fixed.pptx` (16 slides, 10 minutes). Speak, don't read: the script is what to say, not what to memorise word for word.

---

## Part 1. The script

Times are targets. Total about 9 minutes, which leaves a minute for pauses and clicks.

### Daoud: slides 1–4 (about 2 minutes 10)

**Slide 1: the question (20 s)**
> Good morning. We're Daoud, Marie and Jieyu. Our question: when electricity got much more expensive in 2023, did Swiss households put more solar panels on their roofs?
> We measure three things for every commune. Y, the outcome, is the number of new solar installations per year. X is how much the household electricity tariff went up in 2023. Z is the share of homes lived in by their owner. Tenants usually can't install panels themselves, so we expect communes with more owners to react more.

**Slide 2: why it matters (35 s)**
> Switzerland has a legal target: 35 terawatt-hours of renewable electricity, not counting hydropower, by 2035. So it matters whether households respond to prices.
> A rooftop panel pays off in two ways: you buy less electricity, and the grid pays you for what you send back. In Switzerland, your local grid operator sets both prices, and there are hundreds of them. In our communes, 495 are the main operator.
> In 2023 the tariff of the median commune went up 28 percent, about 5 centimes per kilowatt-hour. But some communes barely moved and others jumped by more than 20 centimes. That variation is what we use.

**Slide 3: three studies (50 s)**
> Feger and co-authors build a model of solar adoption for about 165,000 Swiss households, customers of utilities in the canton of Bern, from 2008 to 2014. They find that higher electricity prices do raise adoption, and that prices are a cheaper way to encourage solar than installation subsidies. They also show that adopters are mostly richer homeowners, which is why we look at Z. Their limit for us: prices barely changed in their data.
> Kiso and co-authors use Fukushima. After Japan shut its nuclear plants, electricity prices rose, and that raised solar on existing homes, but barely on new builds. Their limit: the rise was slow, over about three years, and came from only ten regional utilities.
> Filippini and Garnache, a 2026 ETH working paper, look at the same 2022 crisis in Norway. They compare the expensive south with the cheaper north: installations surged in the south, and buyers seemed to put a lot of weight on current prices. Their limit: all the price variation comes from one north–south border.

**Slide 4: our gap (25 s)**
> So each study had one narrow source of price variation: almost none in Bern, ten utilities in Japan, one border in Norway.
> We found no solar study that uses the 2023 Swiss tariff jump. It was sudden, and hundreds of local operators passed it on by very different amounts. So we can compare communes inside the same canton, under the same cantonal rules. This shock has problems of its own, and we come back to them at the end. Marie will now show you the data.

### Marie: slides 5–10 (about 2 minutes 40)

**Slide 5: ingredients (40 s)**
> Y comes from the federal register of power plants. We keep the solar plants and place each one in a commune using its coordinates. It is a count, very skewed, with zeros, so later we use growth in the log of one plus the count. Its limit: the register gives the date the plant was connected, a few months after the decision.
> X comes from ElCom, the federal electricity regulator. We take the standard household tariff, called H4, and compute 2023 minus 2022. It is continuous, in centimes per kilowatt-hour. We keep it in levels, because some communes even had small decreases, and we keep the 17 communes above 25 centimes: they are real small utilities, not errors.
> Z comes from the 2000 census: owner-occupied dwellings divided by all occupied dwellings. We split it at its median. Its limit: it is 26 years old.
> Communes merge every year, so we mapped every source to the 2026 communes.

**Slide 6: the sample (15 s)**
> After cleaning we have 297,633 solar plants, in 2,098 of Switzerland's 2,110 communes, from 2015 to 2025. The 12 communes we drop have no 2022 tariff, and most are in Graubünden.

**Slide 7: summary statistics (15 s)**
> One row per commune. The median commune went from about 5 new installations a year before the shock to 18.5 after. The tariff increase has a median of 5 centimes and goes up to 43.

**Slide 8: Y over time (20 s)**
> Installations rose slowly, jumped 165 percent between 2021 and 2023, stayed high in 2024 and fell in 2025. Many things changed in 2023, so this national line can't tell us why. That's why we compare communes.

**Slide 9: Y across communes and space (30 s)**
> Y is very skewed: most communes add a handful of systems a year, a few cities add hundreds. The last bar is everything above 95. That's why we use growth in logs, which treats a city and a village alike. The map shows growth was positive in 98 percent of communes.

**Slide 10: Z (25 s)**
> Most communes have 40 to 70 percent owner-occupiers, with a median of 56. Cities have fewer owners, rural communes more. Z comes from one census, so it doesn't change over time in our data, and 35 communes have no value because they merged before 2010.

### Jieyu: slides 11–15 (about 3 minutes 20)

**Slide 11: X across space (40 s)**
> On the map, darker communes got bigger increases, and dark and light communes sit side by side. On the left, one line per canton: inside a single canton the increase goes from almost zero to over 20 centimes. 74 percent of the variance is within cantons, which matters because cantons set their own rules and subsidies. And 87 percent of the increase came from the energy part of the price, not from grid fees.

**Slide 12: thirds of X (40 s)**
> We split communes into three groups by their 2023 increase. Left, tariffs: the high-shock group jumped most in 2023, and in 2024 the others partly caught up. Right, installations, indexed so that 2021 equals 100: before 2022 the three lines move together; in 2023 the high-shock group reaches 290 against 238. This index adds up installations, so big communes weigh more. The next slide counts every commune once.

**Slide 13: commune by commune (40 s)**
> Here every dot is a commune, and we removed each canton's average from both axes, so we only compare communes in the same canton. The line says: 10 centimes more goes with 0.24 log points more growth, roughly 27 percent faster, with a 95 percent interval from 0.20 to 0.28. The placebo: the same test before the shock, from 2017–18 to 2020–21, gives 0.02, which is zero. So this is not an old trend.

**Slide 14: owner share (35 s)**
> We split communes at the median owner share. In both halves the high-shock group grew more, and the gap is bigger where owners dominate: 308 against 237. Two warnings: above the median, a gap was already visible in 2022, which could be anticipation. And owner share also tracks house type and commune size. So this is a pattern to test, not a finding.

**Slide 15: is there something else? (45 s)**
> The shock was not random. First, operators chose it: large operators serving ten or more communes raised less, 5.8 against 8.5 centimes. Second, operators also changed what they pay for solar power fed into the grid, and that moved with X, correlation 0.79. So we can't yet separate the two prices. Third, everyone lived through the crisis, and in 2024 the low-shock communes partly caught up, so we measure a short-run difference. Fourth, local subsidies or installer queues may differ between communes, and we don't observe them yet.

### Daoud (or whoever closes): slide 16 (40 s)

**Slide 16: the reverse? can we extrapolate? next steps**
> Could solar growth have driven tariffs instead? The 2023 tariffs were announced in 2022, before the installations we count, and the shock is unrelated to how much solar a commune already had. That doesn't fully rule it out.
> Can we extrapolate? It was one exceptional shock during a crisis, we observe communes rather than households, and 12 percent of plants are larger than 30 kilowatts, so farms and firms, not only homes. There is also some sample bias: 12 communes dropped and Z missing for 35.
> For the final we'll get better ownership data, test properly whether the effect differs by ownership, and account for feed-in tariffs and other local factors. Thank you, we're happy to take questions.

---

## Part 2. The whole study, explained simply

### The question in one sentence
When the household electricity price jumped in 2023, did communes where it jumped more see more new rooftop solar?

### Why 2023 is a good test
- **The shock.** The 2022 energy crisis pushed wholesale prices up. Swiss operators set their 2023 household tariffs in summer 2022 and had to publish them by the end of August 2022.
- **Uneven.** Operators buy electricity in different ways, so the increase differed a lot: some communes almost nothing, others over 20 ct/kWh.
- **Inside cantons.** Neighbouring communes often have different operators. That lets us compare communes inside the same canton, which holds cantonal subsidies, building rules and climate roughly fixed.

### The three variables
| | What | Source | Nature | How we prepared it | Main limit |
|---|---|---|---|---|---|
| **Y** | New solar installations per commune and year | SFOE plant register (extract 14.09.2026) | Count, very skewed, with zeros | Growth = log(1 + per-year installations 2023–24) − log(1 + per-year installations 2017–21) | Date is the grid connection, months after the decision |
| **X** | 2023 minus 2022 household tariff | ElCom, profile H4 (4,500 kWh/year, 5-room flat) | Continuous, ct/kWh | Averaged over the operators of each commune; kept in levels; 17 communes above 25 ct kept | Chosen by operators, not random |
| **Z** | Owner-occupier share | FSO census 2000 | Share 0–1 | Split at the median (56%) | 26 years old; one number for the whole commune |

### How the data was built (notebook section 1)
1. **Commune codes.** Communes merge every year, and each source uses its own year's codes. We map every source to the 2026 communes with the FSO register of mergers, which starts in 2010.
2. **Placing plants.** We keep the solar plants: 337,455 in the register. We place each one in a commune: 99.3% by coordinates (point in commune polygon), the rest by postcode.
3. **Building X.** For each commune we average the H4 tariff of its operators, then take 2023 − 2022.
4. **Building Z.** Owner-occupied dwellings divided by all occupied dwellings, from the 2000 census.
5. **The sample.** We keep communes with a 2022 and a 2023 tariff: 2,098 of 2,110. The 12 dropped have no 2022 tariff (8 in Graubünden, 2 in Aargau, 1 in Fribourg, 1 in Vaud). Years 2015–2025; 2026 is left out because the extract is from September.
6. **Result.** 297,633 plants from 2015–2025, 23,078 commune-years.

### The methods, each in plain words
- **Why log(1 + n).** A city adding 400 and a village adding 4 can't be compared in levels. Logs turn changes into percentages, so the city and the village are compared in relative terms. The +1 lets us take the log of communes with zero installations.
- **What a log point is.** A difference of 0.24 in logs is about a 27% difference, because e^0.24 − 1 ≈ 0.27. With the +1 it is approximate, so say "roughly 27%".
- **Index, 2021 = 100.** For each group we add up installations per year and divide by that group's 2021 total. The groups have different sizes, so this compares how each grew from its own starting point. 2021 is the last full year before the shock was known.
- **Thirds of X.** Communes are split into three groups of about equal size by their 2023 increase. The groups average +2.0, +5.9 and +12.3 ct.
- **"Within cantons".** We subtract each canton's average from X and from growth, then fit a line. This is the same as a regression with canton fixed effects: we only compare communes with others in the same canton.
- **Clustered confidence interval.** Communes served by the same operator got the same shock, so they are not independent. We let their errors be correlated: 495 operator clusters, not 2,098 independent communes.
- **The placebo.** We run the same slope on growth from 2017–18 to 2020–21, before anyone knew about 2023. If high-shock communes were already on a faster trend, this would be positive. It is 0.02 (CI −0.03 to 0.07): no old trend.
- **74% within cantons.** If we remove each canton's average increase, 74% of the variance in X is still there. So most of the shock varies between neighbours, not between cantons.

### What we found (descriptive, not causal)
- Installations rose 165% nationally from 2021 to 2023.
- In 2023 the high-shock third grew more (index 290 vs 238 for the low-shock third).
- Commune by commune, within cantons: +10 ct goes with about 27% faster growth (0.24, CI 0.20–0.28). The same test before the shock finds nothing (0.02).
- The gap is larger where owners dominate (308 vs 237 above the median owner share; 280 vs 241 below). But above the median a gap already existed in 2022 (160 vs 139), so this is not yet a finding.

### Why it is not (yet) causal
- **Something else (endogeneity).** Operators chose the increases. Large operators (main operator in 10+ communes) raised less (5.8 vs 8.5 ct). The same operators changed feed-in tariffs, which moved with X (r = 0.79). The low-shock communes caught up partly in 2024 (the tariff gap halved, 8.6 → 4.3 ct). Communal subsidies and installer queues are unobserved.
- **The reverse.** 2023 tariffs were set in 2022, before the installations we count. X is unrelated to the solar a commune already had (r = 0.03). And 87% of the increase was the energy part, not grid fees, which more solar could push up.
- **Extrapolation.** One exceptional crisis year; commune averages, not households; Y counts all plants (12% above 30 kW: farms, firms); 12 communes dropped and Z missing for 35 (sample bias).

### The literature, in more detail (Daoud's slides)
- **Feger, Pavanini & Radulescu (2022), *Review of Economic Studies*.**
  - Data: a structural model of electricity demand and solar adoption, with about 165,000 Swiss households (utilities in the canton of Bern), 2008–2014, matched to income, wealth and building data.
  - Findings: higher marginal electricity prices raise adoption. Relative to installation subsidies, using prices is more cost-efficient and more progressive, but costs more welfare overall. Adopters are mostly richer homeowners: home ownership goes from about a quarter of the poorest households to about three quarters of the richest.
  - Limit for us: very little price variation (a few utilities, a few years).
- **Kiso, Chan & Arino (2022), *Journal of Environmental Economics and Management*.**
  - Data: a panel of Japan's 47 prefectures, quarterly 2009–2014. After the 2011 Fukushima accident, nuclear plants shut down and electricity prices rose by roughly 20–40% over about three years.
  - Method: prices are instrumented with fuel costs.
  - Findings: higher prices raised solar on existing homes (elasticity about 1.6) but barely on new builds (about 0.5, not significant).
  - Limit for us: only ten regional monopoly utilities and a slow rise. Their feed-in tariff and subsidy started in 2009, nationwide, so for them those are not a confounder.
- **Filippini & Garnache (2026), CER-ETH working paper 26/408 (not yet peer-reviewed).**
  - Data: Norway in the 2022 crisis. Prices exploded in the southern price zones but not in the north. They compare the two with a difference-in-differences and a spatial regression discontinuity at the border.
  - Findings: installations surged in the south, and buyers seem to put about 70% weight on current prices ("projection bias"). They call this suggestive evidence.
  - Limit for us: one north–south border.
- **For questions only: Frings, Helm & Hahnel (2024), *Communications Earth & Environment*.** A two-wave survey of 1,040 Swiss and German citizens across the 2022/23 winter, on energy literacy and efficiency preferences, not solar adoption. If someone says "the Swiss crisis has been studied", this is probably it, and it does not study installations.

---

## Part 3. Numbers cheat sheet

| Number | What it is |
|---|---|
| 35 TWh | Legal target: renewable electricity excluding hydropower in 2035 (Electricity Act, vote of June 2024) |
| +28% / +5.1 ct | Median 2023 tariff increase across communes (in percent / in ct/kWh) |
| 495 / 571 | Main operators of our communes / all operators setting tariffs in them |
| 337,455 → 297,633 | PV plants in the register → plants 2015–2025 in our sample |
| 99.3% | Plants placed by coordinates (the rest by postcode) |
| 2,098 of 2,110 | Communes kept (12 lack a 2022 tariff, 8 of them in Graubünden) |
| 5.2 → 18.5 | Median installations per year, 2017–21 → 2023–24 |
| 484 | Largest commune, installations per year 2023–24 |
| +165% | National installations 2021 (23,291) → 2023 (61,682) |
| 98% | Communes with positive growth |
| 56% / 35 | Median owner share / communes without Z |
| 74% | Share of the variance of X within cantons |
| 87% | Share of the average increase that was the energy part |
| 17 | Communes with an increase above 25 ct (kept) |
| +2.0 / +5.9 / +12.3 | Mean increase in the low / middle / high third |
| 238 / 265 / 290 | 2023 installation index (2021 = 100), low / middle / high |
| 0.24 (0.20–0.28) | Within-canton slope, log points of growth per +10 ct; about +27% |
| 0.02 (−0.03 to 0.07) | Same slope before the shock (placebo) |
| 280 vs 241 / 308 vs 237 | 2023 index high vs low shock, below / above median owner share |
| 160 vs 139 | 2022 index above the median owner share (gap before the tariffs applied) |
| 5.8 vs 8.5 ct | Increase with large (10+ communes) vs other operators |
| r = 0.79 | Retail increase vs feed-in change (1,994 communes) |
| 8.6 → 4.3 ct | Tariff gap high − low third, 2023 → 2024 |
| r = 0.03 | X vs solar per 1,000 inhabitants in 2021 |
| r = −0.26 | X vs 2022 tariff level |
| 12% | Plants above 30 kW |

---

## Part 4. Questions and answers

Answer in two sentences, then stop. If you don't know: "We haven't checked that yet; it's a good point for the final."

### Likely for Daoud (question, literature, gap)
**Why is this question important?**
Switzerland needs much more renewable electricity by 2035, and rooftop solar is a big part of that. If households respond to prices, tariff design is a cheap policy lever. 2023 is a rare chance to see that response.

**Why is this a causal question?**
We ask whether a higher tariff *caused* more installations, not only whether they happened at the same time. That's why we spend two slides on what else could explain the link.

**Why did you pick these three papers?**
Each uses a real price change to study solar adoption, in three settings: a structural model in Switzerland, a natural experiment in Japan, and the same 2022 crisis in Norway. Together they show prices matter, but each relies on one narrow source of price variation.

**Feger finds prices matter. So what's new?**
They had almost no price variation, so their price effect comes mostly from the model. We have a large, sudden, real change that differs between neighbouring communes.

**Isn't Norway exactly your setting?**
Same crisis, but they have one border between two price regions. We have hundreds of operators and can compare communes within the same canton.

**Is your gap really true? Has nobody studied the Swiss 2023 increase?**
We found no study of solar adoption that uses it; our search was not exhaustive. Frings et al. (2024) studied the Swiss and German crisis, but with a survey of preferences, not installations.

**Isn't your shock also "a shock with something else"?**
Yes: feed-in tariffs moved with it and everyone saw the crisis. What we add is much more price variation, inside cantons, and slide 15 lists the problems.

**What is the 35 TWh?**
The legal target for renewable electricity excluding hydropower in 2035, approved by vote in June 2024. Today's level is far below it.

**Why does the owner share matter?**
To install panels you need to own the roof. Tenants depend on the landlord, so we expect owner-heavy communes to react more. Feger et al. also show adopters are mostly homeowners.

### Data (Marie)
**Why the H4 profile?**
It is ElCom's standard household: a 5-room flat using 4,500 kWh a year. With other household profiles (H2, H7) the 2023 increase is almost identical (correlation 0.99).

**Why the change and not the level of the tariff?**
We compare each commune with its own past growth, so permanent level differences drop out. The change is the shock. High-shock communes even had lower 2022 tariffs (r = −0.26).

**Why log(1 + n)?**
Y is a skewed count with zeros. Logs compare relative growth, and the +1 handles zeros. In the final we will use a count model that handles zeros directly.

**Why leave out 2022?**
The 2023 tariffs were published in August 2022, so 2022 is partly before and partly after the news. We compare 2017–21 with 2023–24.

**Why the connection date?**
It is the only date in the register. It comes a few months after the decision, which is why we use 2023 and 2024 together.

**Did you remove outliers?**
No. The 17 communes with increases above 25 ct are real small utilities. Big cities stay in, and logs handle their size.

**Z is from 2000. Isn't that too old?**
It is the latest owner data available for every commune. Ownership changes slowly, but it is a real limit, and better data is our first step for the final.

**Why are 35 communes missing Z?**
They merged before 2010, and the merger register we use starts in 2010, so we can't match them.

**How did you place plants in communes?**
99.3% by their coordinates: we check which commune polygon contains the point. The rest by postcode, using the commune with most of the postcode's addresses.

### Analysis (Jieyu)
**What does 0.24 mean?**
Within the same canton, a commune with 10 ct more increase had about 27% faster growth in installations from 2017–21 to 2023–24. The 95% interval is 0.20 to 0.28.

**Is it significant?**
Yes, the interval excludes zero, and it allows communes with the same operator to share errors. The same test before the shock gives zero.

**Why compare within cantons?**
Cantons set their own subsidies and building rules. Comparing within a canton holds those fixed, and 74% of the variation in X is within cantons, so we keep most of it.

**Isn't the thirds chart just big cities?**
The index adds up installations, so big communes weigh more. That's why slide 13 counts every commune once, and it gives the same picture.

**Why did installations fall in 2025?**
We haven't tested it. Tariffs came down in 2025, some 2025 plants may not be registered yet (the extract is from September 2026), and feed-in tariffs may have dropped. We wouldn't claim demand fell.

**More solar, or the same solar earlier?**
We can't tell yet. The final will check total installations over several years, not only the timing.

**Is the owner gap real?**
It is descriptive. Owner share also tracks commune size (r = −0.62) and single-family houses (r = 0.41), and above the median a gap was already there in 2022. We will test Z as a continuous variable in the final.

**Isn't it the feed-in tariff, not the retail price?**
It could be. The same operator sets both and they moved together (r = 0.79), so for now 0.24 is a response to the whole tariff package. Separating them is a goal of the final.

### Causality (anyone, ideally Daoud)
**Was the shock random?**
No. Operators set tariffs from their own costs and purchasing strategy: large operators raised less, and communes with high 2022 tariffs got smaller increases. That's why we compare within cantons, check the trend before the shock, and plan to compare neighbouring communes with different operators.

**Is there a control group?**
No. Every commune saw the crisis and the news. We compare more and less affected communes, so we measure a short-run difference, not the total effect of the crisis.

**Could solar cause higher tariffs (reverse causality)?**
In principle: more self-consumption means fewer billed kWh, which can push up grid fees. But 87% of the 2023 increase was the energy part, tariffs were set before the installations we count, and X is unrelated to existing solar (r = 0.03).

**What about anticipation?**
Tariffs were public from August 2022, so some households may have acted in late 2022. That's why we leave 2022 out, and why the 2022 gap on slide 14 is a warning. The final will look year by year.

**Spillovers between communes?**
Neighbours share installers and talk to each other, so a high-shock commune could raise installations next door. That would make our comparison of neighbours smaller than the true effect.

**Installer bottlenecks?**
Possible. Long waiting lists would delay and cap the response, so 2023 alone may understate it. That's one reason we use 2023 and 2024 together.

**Can you generalise?**
Only with care: one crisis year with heavy media coverage, commune averages rather than households, and all plant sizes. 12% of plants are above 30 kW, so not only homes.

**What will you do for the final?**
Better ownership data; a regression within cantons year by year, with pre-trend and anticipation tests; comparing neighbouring communes with different operators; Z as a continuous variable; and controlling for feed-in tariffs.

**Why cluster by operator?**
The operator sets the shock, so communes served by the same operator are not independent. With 495 operators, that is closer to 495 shocks than 2,098.

**Where does the feed-in data come from?**
VESE's pvtarif database, used under licence for our team only. Credit: "Données des tarifs de rétribution: VESE / pvtarif.ch".
