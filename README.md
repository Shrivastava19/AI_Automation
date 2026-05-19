# AI Automation Dashboard

A runnable Python project that demonstrates automation workflows for structured datasets, interactive analytics dashboards, operational report summarization, and API-based data retrieval.

## Features

- Python + Pandas workflow for cleaning and processing operational data
- SQLite storage layer with reusable database initialization
- Interactive Flask dashboard with filters, KPIs, charts, and recent records
- Local GenAI-style assistant that summarizes operational reports without requiring an API key
- API endpoints for automated retrieval and processing

## Project Structure

```text
ai-automation-dashboard/
  app.py
  requirements.txt
  README.md
  data/sample_operations.csv
  scripts/init_db.py
  static/styles.css
  templates/index.html
```

## How To Run

1. Create and activate a virtual environment:

```bash
python -m venv .venv
.venv\Scripts\activate
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Initialize the SQLite database:

```bash
python scripts/init_db.py
```

4. Start the dashboard:

```bash
python app.py
```

5. Open this URL in your browser:

```text
http://127.0.0.1:5000
```

## API Examples

Health check:

```bash
curl http://127.0.0.1:5000/api/health
```

Get processed records:

```bash
curl http://127.0.0.1:5000/api/records
```

Get dashboard metrics:

```bash
curl http://127.0.0.1:5000/api/metrics
```

Generate an operational summary:

```bash
curl -X POST http://127.0.0.1:5000/api/summarize ^
  -H "Content-Type: application/json" ^
  -d "{\"report\":\"Automation completed 245 records today. Finance queue had 3 delayed jobs and support improved SLA compliance.\"}"
```

Ingest a new record:

```bash
curl -X POST http://127.0.0.1:5000/api/ingest ^
  -H "Content-Type: application/json" ^
  -d "{\"date\":\"2026-05-19\",\"department\":\"Operations\",\"workflow\":\"Invoice Reconciliation\",\"records_processed\":340,\"success_rate\":98.1,\"processing_time_min\":22,\"cost_saved_usd\":680,\"status\":\"Completed\"}"
```

Project Preview:

<img width="1361" height="928" alt="Screenshot 2026-05-19 203838" src="https://github.com/user-attachments/assets/59c303d4-57b8-4ded-96f0-bb750a7a9344" />
<img width="1854" height="914" alt="image" src="https://github.com/user-attachments/assets/5dfb6050-9ebf-45eb-bc5c-15716d705e30" />
