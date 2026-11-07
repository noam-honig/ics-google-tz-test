# Google Calendar time zone test (card 17221)

Synthetic feeds. Each has shifts 09:00-17:00 floating on Nov 9-11 2026.
Commit 1 (phase A): all feeds have no zone except P. Commit 2 (phase B): one change per feed, and shift 3 renamed "v2" to show Google re-read the feed.

Viewed from a calendar in Israel (UTC+2): 11:00 = read as UTC, 16:00 = read as New York, 09:00 = read as the calendar's zone.

| Feed | Phase B change |
|---|---|
| C | nothing (DTSTAMP only) |
| H | X-WR-TIMEZONE only |
| N | X-WR-TIMEZONE + new shift 4 (Nov 12) |
| S | X-WR-TIMEZONE + SEQUENCE+1 on shifts 1-2 |
| U | X-WR-TIMEZONE + new UID on shifts 1-2 |
| T | TZID=America/New_York + VTIMEZONE on shifts 1-2 |
| P | header from the start (positive control) |
