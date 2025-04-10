# Logstash Project

## Overview
This project showcases the configuration of Logstash to ingest, parse, and normalize security log data. It includes a custom Logstash pipeline that transforms syslog-formatted logs into structured JSON, enabling easier analysis and integration with downstream security tools.

---

## Project Structure
- `README.md`: This file — describes the approach and configuration.
- `input_log.txt`: Contains the raw security syslog log samples.
- `output.json`: Sample output from Logstash showing the normalized JSON structure.
- `output_formatted.json`: sample output from logstash in formatted JSON structure for better understanding
- `parser_conf.txt`: The Logstash configuration file used to parse and normalize logs.

---

## How It Works

### Ingestion
- Input Plugin: The `file` input plugin reads from `input.log`.

### Filtering
- Filter Plugin: The `grok` plugin is used to match and extract key fields from the raw syslog format.
- Mutate Plugin: Removes unnecessary fields like `host`, `ip`, etc., to keep the output clean.

### Output
- **Output Plugin**: The `file` output plugin writes the normalized JSON to `output.json`.

---

## Normalization Design
The configuration is designed to:
- Support any log line with the same format.
- Extract values like `source_ip`, `hostname`, `severity`, `timestamp`, etc., into clearly defined fields.
- Maintain flexibility to adapt to new log values without changing the grok pattern drastically.
