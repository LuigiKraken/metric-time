# Metric Time

A decimal clock and calendar that replaces every arbitrary division in our timekeeping with clean base-10 structure.

**[Live Demo](https://luigikraken.github.io/metric-time/)**

## The Argument

Our current calendar is a patchwork of Babylonian base-60, Roman political compromises, and papal corrections. Months have 28, 29, 30, or 31 days depending on which one. Weeks don't align with months. Hours use base-24, minutes and seconds use base-60. None of it composes, none of it is mental-math friendly, and none of it had to be this way.

Metric time tries to fix all of it.

### The date *is* the day number

The date format beyond the year is **Month.Week.Day**, but that's really just the three digits of the day-of-year written out. Day 237 of the year reads as month **2**, week **3**, day **7**. There is no lookup table, no irregular month lengths, no counting on your knuckles. The date *is* the number.

This one change simplifies a surprising amount:

**How many days between two dates?**
Subtract them. June 15 to October 3 in the current system requires you to remember that June has 30 days, July has 31, August has 31, September has 30, then sum them up. In metric time, day 164 to day 275 is just 275 - 164 = **111 days**. Done.

**What week of the year are you in?**
Read two digits. If today is day 237, you're in week **23**. No dividing by 7, no checking a reference calendar, no off-by-one confusion about whether weeks start on Sunday or Monday. Two digits, that's it.

**How many hours in a month?**
Every month is 100 days. Every day is 10 hours. So every month is **1,000 hours**. You don't calculate it, you just know it. Compare that to the current system where February has 672 hours, March has 744, and April has 720, for no good reason.

**How many days until the end of the month?**
If today's day-of-month (the Week.Day portion) reads 73, there are 100 - 73 = **27 days** left. Always. Every month.

### The time *is* the fraction of the day

The clock follows the same principle:

| Unit | Division |
|------|----------|
| 1 day | 10 hours |
| 1 hour | 100 minutes |
| 1 minute | 100 seconds |

When the clock reads **5:00:00**, the day is exactly **50%** over. When it reads **2:50:00**, you're **25%** through. The time *is* the percentage, no dividing by 24 and then by 60. A decimal second is 0.864 SI seconds, close enough that human perception doesn't notice the difference.

### Everything composes

Because every unit is a power of 10 of the one below it, all conversions are trivial:

| Question | Answer |
|----------|--------|
| Hours in a week? | **100** (10 days x 10 hours) |
| Hours in a month? | **1,000** (100 days x 10 hours) |
| Minutes in a day? | **1,000** (10 hours x 100 minutes) |
| Seconds in a day? | **100,000** (just move the decimal point) |
| Weeks in a year? | **36.5** (365 days / 10) |
| Months in a year? | **3.65** (365 days / 100) |

No unit is special-cased. The only conversion factor is "multiply or divide by 10."

## The System

| Structure | Value |
|-----------|-------|
| 1 year | ~3.65 months of 100 days |
| 1 month | 10 weeks |
| 1 week | 10 days |
| 1 day | 10 hours |
| 1 hour | 100 minutes |
| 1 minute | 100 seconds |
| 1 decimal second | 0.864 Standard seconds |

### The year epoch and boundary

Our current calendar counts years from the traditionally estimated birth of Jesus — religiously specific, historically uncertain, and encoding the assumptions of one culture into a system that now serves all of humanity. This calendar anchors year 0 to the emergence of *Homo sapiens* instead. Fossil evidence places that at roughly 300,000 years ago, tying the dating system to the scientifically established origin of our species rather than to religion, empire, or civilization. The current year is **302,026**.

The year offset is easy to carry in your head: just prepend "30" to the Gregorian year. 2026 becomes 302,026. Ancient dates work the same way in reverse — subtract any BCE year from 300,000. 12,000 BCE becomes year 288,000.

January 1st has no astronomical meaning. It was set by Roman political decree. This calendar uses the **December solstice** as the year boundary instead — the moment Earth's axial tilt reaches its maximum relative to the Sun, the shortest day in the northern hemisphere and the longest in the south. It is a real, recurring, astronomically precise event observable by every culture on Earth. The epoch is the **December solstice of metric year 0**, approximately 302,026 years ago (Gregorian year ~300,001 BCE). The clock is anchored to a single known solstice — December 21, 2024, the start of metric year 302,025 — and every other year boundary is computed from that point using the leap day rule.

### Leap days

The tropical year is approximately 365.24219 days. To keep the calendar aligned with the solstice, a leap day (day 366) is added at the end of certain years:

| Rule | Effect |
|------|--------|
| Year divisible by 4 | Leap year (366 days) |
| Year divisible by 128 | Not a leap year (overrides ÷4) |

This gives an average year length of **365.2421875 days** — accurate to within one day per 100,000 years. The Gregorian system's three-rule cycle (÷4, skip ÷100, keep ÷400) drifts a full day every ~3,300 years.

If you observe a single December solstice, note the metric year number, and apply the ÷4 / ÷128 rule from that point forward, you can count days indefinitely without ever looking at the sky again. On a desert island with a stick and a tally, this calendar stays accurate for thousands of years.

The epoch choice is still arbitrary in the way all epoch choices are. The point of this system was never to find a more natural zero — it's that the *structure* tries to derive from physical reality so units compose cleanly regardless of where counting starts. Whether the base-10 structure actually succeeds at that is a fair question, but it's the core idea. The epoch is simply the least culturally loaded option we could find: a scientific estimate, subject to revision, belonging to no religion, no empire, and no single civilization.

## Round Numbers, Real Intuition

| Metric Duration | Standard Equivalent | You Already Know This        |
|----------------|---------------------|------------------------------|
| 1 metric min  | 1 min 26 sec        | Reheat leftovers             |
| 5 metric min  | 7 min 12 sec        | Hit snooze once              |
| 10 metric min | 14 min 24 sec       | Quick coffee break           |
| 25 metric min | 36 min              | Watch a sitcom               |
| 50 metric min | 1 hr 12 min         | A solid gym session          |
| 1 metric hr   | 2 hr 24 min         | A feature film               |
| 2 metric hr   | 4 hr 48 min         | Half a work day              |
| 3 metric hr   | 7 hr 12 min         | Full work day                |
| 5 metric hr   | 12 hr exactly       | Sunrise to sunset            |
| 1 metric week | 10 days             | A proper vacation            |
| 1 metric month| 100 days            | An entire season             |

## Themes

Cycle through styles with the **Style** button:

- **CRT** -- green phosphor scanline
- **Dark** -- amber glow
- **Minimal** -- clean light
- **7-SEG** -- red seven-segment LED display
