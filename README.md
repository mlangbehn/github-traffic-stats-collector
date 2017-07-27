# github-traffic-stats-collector

WORK IN PROGRESS

## Architecture

### Diagram

```text
                          +---------------+
                          | +-----------+ | <-------+
                          | | Database  | |         |
                          | +-----------+ | <-----+ |
                          |               |   GH  | |
            Cron Trigger  |               | Stats | |
+--------+ <------------- | +-----------+ | ------+ |
| GitHub |                | | OpenWhisk | |         | Points to
+--------+ -------------> | +-----------+ |         | Database
           Traffic Stats  |               |         |
                          |               |         |
                          | +-----------+ |         |
                          | | Dashboard | | --------+
                          | +-----------+ |
                          +---------------+
```

### Chronology

1. OpenWhisk cron trigger sends request for traffic statistics to GitHub
2. GitHub Returns traffic statistics
3. OpenWhisk sends GitHub Statistics to database
4. Dashboard displays reports
