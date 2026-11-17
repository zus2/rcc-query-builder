# RCC Report Query Builder

An independent, client-side query builder for **GoDaddy Reseller Control Center (RCC)** commission reports, designed to make report date ranges predictable.

**[Use the live tool](https://www.exdem.com/rcc-query-builder.html)**

## Features

- Run **Commission** or **Products** reports.
- Choose a date range by **day, month, quarter, or year**.
- Select an inclusive end date: for example, 1–31 January includes all of 31 January.
- Start a 12-month reporting year in any month.
- See the selected reporting period before running a report.
- Reuse the same report tab for subsequent queries.

## How it works

The tool constructs URLs for the RCC reporting endpoints and opens them in a separate, named browser tab. It does not log in, access credentials, or make authenticated requests itself. **Sign in to RCC first** in your browser.

The date calculations use UTC boundaries. The interface shows inclusive calendar dates, while the generated RCC query uses an **exclusive end boundary** at midnight on the next day.

For example, a report displayed as **1–31 January 2026** sends:

```text
startDate=2026-01-01T00:00:00.000Z
endDate=2026-02-01T00:00:00.000Z
```

This is deliberate: it includes the entire last day, assuming RCC interprets the end boundary exclusively.

## Run locally

Download `rcc-query-builder.html` and open it in a modern browser. No build step, dependencies, server, or API key is required.

## Disclaimer

Independent tool; not affiliated with, endorsed by, or supported by GoDaddy. Verify report dates and results before relying on them. Do not automate, batch, or send bulk enquiries to your account provider. You are responsible for requests made through your RCC account.

## License

MIT © 2026 Paul Walsh. See [LICENSE](LICENSE).
