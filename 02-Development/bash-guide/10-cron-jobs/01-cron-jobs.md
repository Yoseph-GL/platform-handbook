# Bash Cron Jobs: Cron Jobs

## Architecture / Rationale

Cron reads a file called a crontab that lists commands and when to run them. Each line has five time fields followed by the command to run.

Crontab format:
```
* * * * * command
│ │ │ │ │
│ │ │ │ └── day of week (0-7, 0=Sunday)
│ │ │ └──── month (1-12)
│ │ └────── day of month (1-31)
│ └──────── hour (0-23)
└────────── minute (0-59)
```

## Query / Code Blocks

```bash
# Edit your crontab
crontab -e

# List your cron jobs
crontab -l

# Remove all your cron jobs
crontab -r

# Crontab examples:
# Run every day at 2:30 AM
# 30 2 * * * /home/user/scripts/backup.sh

# Run every Monday at 8:00 AM
# 0 8 * * 1 /home/user/scripts/report.sh

# Run every 15 minutes
# */15 * * * * /home/user/scripts/check.sh

# Run at midnight on the first day of every month
# 0 0 1 * * /home/user/scripts/monthly.sh
```

## Performance / Optimization Notes

- Use `crontab -e` to edit. Never edit the crontab file directly — you might break the syntax.
- Always use absolute paths in cron jobs. Cron does not have your normal `$PATH`.
- Redirect output to a log file: `command >> /var/log/myscript.log 2>&1`. Otherwise, cron emails the output.
