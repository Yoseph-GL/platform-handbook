# Bash Level 10: Cron Jobs

## Architecture / Rationale

Cron is a scheduler that runs commands at specific times. You use it to automate backups, cleanups, and reports.

Scope:
- How cron works and the crontab format.
- Creating and editing cron jobs.
- Understanding the five time fields.

## Query / Code Blocks

```bash
# Module pages
# [[01-cron-jobs]]
# [[02-exercises-cron-jobs]]
```

## Performance / Optimization Notes

- Cron jobs run in a minimal environment. Always use absolute paths in cron commands.
- Test your script manually before adding it to cron. A cron job that fails silently is hard to debug.
