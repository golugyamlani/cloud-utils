# Utils Package

Cloud-agnostic utility package for serverless microservices.

## Package Structure

```
utils/
├── __init__.py
├── README.md
├── core/
│   ├── __init__.py
│   ├── logging.py        # Renamed from logger.py
│   ├── responses.py      # Renamed from response_headers.py
│   └── errors.py         # New file for error handling utilities
├── aws/
│   ├── __init__.py
│   ├── s3.py
│   ├── ssm.py
│   ├── lambda_utils.py   # Renamed from invoke_lambda.py
│   └── dynamodb.py       # Renamed from ddb.py
├── db/
│   ├── __init__.py
│   ├── connector.py      # Renamed from db_connector.py
│   ├── query_builder.py  # Renamed from sql_query.py
│   └── generic_query.py
├── scripts/
│   ├── __init__.py
│   └── create_tables.py  # Renamed from create_table.py
└── helpers/
    ├── __init__.py
    └── utils.py          # Core utility functions
```

## Installation

git submodule add <repo-url> utils
git submodule update --init --recursive

## Environment Variables

CURRENT_STAGE=dev|prod     # Deployment stage
LOG_LEVEL=INFO            # Logging level

## Quick Start

from utils import log, fetch_sql, handle_response

# Logging
log.info("Starting application...")

# Database operations
error, results = fetch_sql("SELECT * FROM users WHERE id = %s", (user_id,))

# Response handling
response = handle_response(
    status_code=200,
    status="Success",
    message="Operation completed",
    response=results
)

## Contributing
1. Fork the repository
2. Create a feature branch
3. Submit a pull request

## License
[Your License]