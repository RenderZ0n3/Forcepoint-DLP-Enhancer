# Forcepoint-DLP-Enhancer

# Forcepoint DLP Management Scripts

## Overview

This repository contains two Python scripts for managing and retrieving data from Forcepoint Data Loss Prevention (DLP) system:

1. `forcepoint_policy_management.py`: Manages and retrieves policy information
2. `forcepoint_incident_management.py`: Manages and retrieves incident information

## Prerequisites

- Python 3.7+
- `requests` library
- `urllib3` library

## Installation

1. Clone the repository
2. Install required dependencies:
   ```bash
   pip install requests urllib3
   ```

## Configuration

Before running the scripts, update the following configuration variables in each script:

- `DLP_MANAGER_URL`: URL of your Forcepoint DLP Manager
- `USERNAME`: API username
- `PASSWORD`: API password

### Policy Management Script (`forcepoint_policy_management.py`)

#### Features
- Authenticate with Forcepoint DLP
- Retrieve enabled policies
- Fetch policy rules
- Get policy severity and actions
- Retrieve source and destination details
- Fetch rule exceptions

#### Usage
```bash
python forcepoint_policy_management.py
```

#### Customization
You can modify the script to:
- Change policy type
- Add more detailed logging
- Customize report generation

### Incident Management Script (`forcepoint_incident_management.py`)

#### Features
- Authenticate with Forcepoint DLP
- Retrieve incidents with various filters
- Fetch detailed incident information
- Generate incident statistics
- Paginated incident retrieval

#### Usage
```bash
python forcepoint_incident_management.py
```

#### Customization
Modify these variables in the script:
- `DAYS_BACK`: Number of days to retrieve incidents
- `SEVERITY_FILTER`: Filter incidents by severity (High, Medium, Low)
- `STATUS_FILTER`: Filter incidents by status (Open, Closed, InProgress)
- `MAX_INCIDENTS`: Limit the number of incidents retrieved

## Output

Both scripts generate JSON reports in their respective directories:
- Policy reports: `Policy_Report/`
- Incident reports: `Incident_Reports/`

Reports include:
- Metadata (timestamp, date range)
- Detailed policy or incident data
- Optional statistics

## Logging

Logging is configured with DEBUG level. Check the console output for detailed information about the retrieval process.

## Security Notes

- Disable SSL verification is enabled (`verify=False`). In production, replace with proper SSL certificate handling.
- Store credentials securely, preferably using environment variables or a secure configuration management system.

## Error Handling

The scripts include comprehensive error handling for:
- Authentication failures
- Network connection issues
- API request timeouts
- Unexpected errors

## Contributing

Contributions are welcome! Please submit pull requests or open issues for any improvements or bug fixes.

## Disclaimer

These scripts are provided as-is. Always test in a non-production environment first and ensure compliance with your organization's security policies.
