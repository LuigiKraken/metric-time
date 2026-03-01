# Metric Time

A decimal clock and calendar that replaces every arbitrary division in our timekeeping with clean base-10 structure.

## Why This Makes Sense

Our current calendar is a patchwork of Babylonian base-60, Roman political compromises, and papal corrections. Months have 28, 29, 30, or 31 days depending on which one. Weeks don't align with months. Hours use base-24, minutes and seconds use base-60. None of it composes, none of it is mental-math friendly, and none of it had to be this way.

Metric time fixes all of it.

### The date *is* the day number

The date format beyond the year is **Month.Week.Day** — but that's really just the three digits of the day-of-year written out. Day 237 of the year reads as month **2**, week **3**, day **7**. There is no lookup table, no irregular month lengths, no counting on your knuckles. The date *is* the number.

This one change makes everything trivial:

**How many days between two dates?**
Subtract them. June 15 to October 3 in the current system requires you to remember that June has 30 days, July has 31, August has 31, September has 30 — then sum them up. In metric time, day 164 to day 275 is just 275 − 164 = **111 days**. Done.

**What week of the year are you in?**
Read two digits. If today is day 237, you're in week **23**. No dividing by 7, no checking a reference calendar, no off-by-one confusion about whether weeks start on Sunday or Monday. Two digits, that's it.

**How many hours in a month?**
Every month is 100 days. Every day is 10 hours. So every month is **1,000 hours**. You don't calculate it — you just know it. Compare that to the current system where February has 672 hours, March has 744, and April has 720, for no good reason.

**How many days until the end of the month?**
If today's day-of-month (the Week.Day portion) reads 73, there are 100 − 73 = **27 days** left. Always. Every month.

### The time *is* the fraction of the day

The clock is equally clean:

| Unit | Division |
|------|----------|
| 1 day | 10 hours |
| 1 hour | 100 minutes |
| 1 minute | 100 seconds |

When the clock reads **5:00:00**, the day is exactly **50%** over. When it reads **2:50:00**, you're **28.5%** through. The time *is* the percentage — no dividing by 24 and then by 60. A decimal second is 0.864 SI seconds, close enough that human perception doesn't notice the difference.

### Everything composes

Because every unit is a power of 10 of the one below it, all conversions are trivial:

| Question | Answer |
|----------|--------|
| Hours in a week? | **100** (10 days × 10 hours) |
| Hours in a month? | **1,000** (100 days × 10 hours) |
| Minutes in a day? | **1,000** (10 hours × 100 minutes) |
| Seconds in a day? | **100,000** (just move the decimal point) |
| Weeks in a year? | **36.5** (365 days ÷ 10) |
| Months in a year? | **3.65** (365 days ÷ 100) |

No unit is special-cased. No conversion factor requires memorization beyond "multiply or divide by 10."

## The System

| Structure | Value |
|-----------|-------|
| 1 year | ~3.65 months of 100 days |
| 1 month | 10 weeks |
| 1 week | 10 days |
| 1 day | 10 hours |
| 1 hour | 100 minutes |
| 1 minute | 100 seconds |
| 1 decimal second | 0.864 SI seconds |

The year count is offset so year 0 aligns with roughly 100,000 years ago — the era of early shared human culture, a more honest anchor for "when civilization started" than the birth of any one figure. You don't need to remember the offset; you just prepend `10` to your year. 2026 becomes **102,026**.

## Round Numbers, Real Intuition

Metric Duration	Standard Equivalent	You Already Know This
1 metric min	1 min 26 sec	Reheat leftovers
5 metric min	7 min 12 sec	Hit snooze once
10 metric min	14 min 24 sec	Quick coffee break
25 metric min	36 min	Watch a sitcom
50 metric min	1 hr 12 min	A solid gym session
1 metric hr	2 hr 24 min	A feature film
2 metric hr	4 hr 48 min	Half a work day
3 metric hr	7 hr 12 min	Full work day
5 metric hr	12 hr exactly	Sunrise to sunset
1 metric week	10 days	A proper vacation
1 metric month	100 days	An entire season

## Themes

Cycle through styles with the **Style** button:

- **CRT** — green phosphor scanline
- **Dark** — amber glow
- **Minimal** — clean light
- **7-SEG** — red seven-segment LED display
