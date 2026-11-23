# Log Scanner

A small Python script that scans an application log file after a
release and flags failures, so nobody has to read the whole log by
hand.

## Why I built it

After every release, my team used to check application logs manually
to find errors. That took time and things were easy to miss. This
script does the first pass automatically: it counts failures and
warnings and shows the first failure lines with line numbers, so
debugging starts in the right place.

## How to run

```bash
python log_scanner.py sample_app.log
```

## Example output

```
Scanned 12 lines from sample_app.log
Failures found: 3
Warnings found: 2

--- First failures ---
Line 6: 2026-11-23 09:00:19 ERROR Payment gateway timeout after 30s
Line 7: 2026-11-23 09:00:19 ERROR Failed to process payment for order_id=882
Line 11: 2026-11-23 09:00:44 ERROR NullPointerException in ReportService.generate()
```

## Tech used

- Python 3 (standard library only, no installs needed)
