# Logstash Project

## Overview
This project demonstrates my ability to configure Logstash for ingesting and parsing security log data. It includes a configuration to transform syslog-style logs into structured JSON.

---

## Project Structure
- `input.log`: Contains the raw security syslog log samples.
- `parser.conf`: The Logstash configuration file used to parse and normalize logs.
- `output.json`: Sample output from Logstash showing the normalized JSON structure.
- `output_formatted.json`: sample output from logstash in formatted JSON structure for better understanding
- `README.md`: This file — describes the approach and configuration.

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
