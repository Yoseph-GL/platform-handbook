# Bash Cron Jobs: Exercises

## Architecture / Rationale

These exercises practice creating and understanding cron schedules.

## Query / Code Blocks

```bash
# Exercise 1: View your current crontab with `crontab -l`.
# Exercise 2: Write a cron schedule that runs a script every day at 9:00 AM.
# Exercise 3: Write a cron schedule that runs every hour.
# Exercise 4: Write a cron schedule that runs every Sunday at midnight.
# Exercise 5: Write a cron schedule that runs every 5 minutes.
# Exercise 6: Create a simple script that writes the date to a log file. Schedule it with cron.
# Exercise 7: Check that your cron job ran by reading the log file.
# Exercise 8: Remove your test cron job with `crontab -r`.
```

## Performance / Optimization Notes

- For exercise 6, use `echo "$(date): Cron ran successfully" >> ~/cron-test.log`.
- Check `/var/log/syslog` (or `journalctl -u cron`) if your cron job does not run.
- Always remove test cron jobs when done. Old cron jobs can fill up logs or cause unexpected behavior.
