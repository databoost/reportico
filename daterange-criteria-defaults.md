# Reportico Date Range Criteria — Default Options

Reference for all available `<CriteriaDefaults>` values for the DATERANGE criteria type in Reportico 8.1.0.

## 1. Preset Range Names (DateRangePicker widget)

These are exact, case-sensitive strings that map to the built-in picker dropdown:

| Preset | Start | End |
|---|---|---|
| `Today` | today | today |
| `Yesterday` | yesterday | yesterday |
| `Last 7 Days` | 6 days ago | today |
| `Last 30 Days` | 30 days ago | today |
| `This Month` | 1st of this month | last day of this month |
| `Last Month` | 1st of last month | last day of last month |

## 2. Keyword Constants (used in `KEYWORD-KEYWORD` format)

All uppercase, separated by a hyphen:

| Keyword | Meaning |
|---|---|
| `TODAY` | Current date |
| `YESTERDAY` | Previous day |
| `TOMORROW` | Next day |
| `FIRSTOFMONTH` | 1st of current month |
| `LASTOFMONTH` | Last day of current month |
| `FIRSTOFLASTMONTH` | 1st of previous month |
| `LASTOFLASTMONTH` | Last day of previous month |
| `FIRSTOFYEAR` | January 1 of current year |
| `LASTOFYEAR` | December 31 of current year |
| `FIRSTOFLASTYEAR` | January 1 of previous year |
| `LASTOFLASTYEAR` | December 31 of previous year |
| `STARTOFWEEK` | Monday of current week |
| `ENDOFWEEK` | Sunday of current week |
| `STARTOFLASTWEEK` | Monday of previous week |
| `ENDOFLASTWEEK` | Sunday of previous week |
| `BLANK` | Empty value |

**Example combinations:**

- `TODAY-TODAY` — just today
- `YESTERDAY-YESTERDAY` — just yesterday
- `FIRSTOFMONTH-TODAY` — month-to-date
- `FIRSTOFMONTH-LASTOFMONTH` — full current month
- `FIRSTOFLASTMONTH-LASTOFLASTMONTH` — full previous month
- `FIRSTOFYEAR-TODAY` — year-to-date
- `FIRSTOFYEAR-LASTOFYEAR` — full current year
- `FIRSTOFLASTYEAR-LASTOFLASTYEAR` — full previous year
- `STARTOFLASTWEEK-ENDOFLASTWEEK` — full previous week

## 3. Literal Dates

Use `YYYY-MM-DD` format, and mix with keywords:

- `2024-01-01-TODAY` — literal start, keyword end
- `FIRSTOFYEAR-2024-06-30` — keyword start, literal end
- `2024-01-01-2024-12-31` — both literal

## 4. PHP DateTime Expressions (in braces)

Arbitrary PHP relative date strings wrapped in `{...}`:

- `{-30 days}` — 30 days ago
- `{+1 month}` — one month from now
- `{first day of January 2024}` — specific computed date

Any valid [PHP relative date format](https://www.php.net/manual/en/datetime.formats.relative.php) is supported.

## Fallback

If no default is specified, Reportico falls back to `TODAY-TODAY`.
