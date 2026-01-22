# LogicMonitor OpenAPI Specification

[![OpenAPI 3.0](https://img.shields.io/badge/OpenAPI-3.0-green.svg)](https://www.openapis.org/)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)

A complete, fully compliant OpenAPI 3.0 specification for the [LogicMonitor](https://www.logicmonitor.com/) REST API v3.

## Overview

This repository contains an enhanced OpenAPI specification for LogicMonitor's monitoring platform API. The spec has been enriched with:

- Full parameter descriptions for all 856 parameters
- Schema descriptions for all 673 data models
- Response examples for all endpoints
- Standardized error responses (400, 401, 403, 404, 429, 500)
- Proper server URL templating for multi-tenant access
- Both LMv1 signature and Bearer token authentication

## Files

| File | Description |
|------|-------------|
| `openapi.json` | OpenAPI 3.0 specification (JSON format) |
| `openapi.yaml` | OpenAPI 3.0 specification (YAML format) |
| `source/` | Original specifications from LogicMonitor |

## Quick Start

### Using with API Clients

**Postman:**
```
Import > Link > https://raw.githubusercontent.com/YOUR_USERNAME/logicmonitor-api/main/openapi.json
```

**Insomnia:**
```
Import/Export > Import Data > From URL
```

### Code Generation

Generate client libraries using [OpenAPI Generator](https://openapi-generator.tech/):

```bash
# Python
openapi-generator-cli generate -i openapi.yaml -g python -o ./clients/python

# TypeScript
openapi-generator-cli generate -i openapi.yaml -g typescript-axios -o ./clients/typescript

# Go
openapi-generator-cli generate -i openapi.yaml -g go -o ./clients/go
```

## API Statistics

| Metric | Count |
|--------|-------|
| Total Endpoints | 353 |
| GET endpoints | 151 |
| POST endpoints | 77 |
| PUT endpoints | 44 |
| PATCH endpoints | 43 |
| DELETE endpoints | 38 |
| Data Models | 673 |

## API Categories

The API covers these major areas:

- **Monitoring**: Devices, Device Groups, Collectors, Datasources
- **Alerting**: Alerts, Alert Rules, Escalation Chains
- **Visualization**: Dashboards, Widgets, Reports
- **Configuration**: ConfigSources, EventSources, PropertySources
- **Web Monitoring**: Websites, Website Groups
- **Administration**: Users, Roles, API Tokens, Audit Logs
- **Scheduling**: SDTs (Scheduled Downtime)
- **Discovery**: Netscans, Auto-discovery

## Authentication

The API supports two authentication methods:

### LMv1 Token Authentication (Recommended)

Uses HMAC-SHA256 signature-based authentication:

```
Authorization: LMv1 AccessId:Signature:Timestamp
```

### Bearer Token Authentication

JWT-based authentication:

```
Authorization: Bearer <token>
```

## Server URL

The API uses a multi-tenant URL pattern:

```
https://{company}.logicmonitor.com/santaba/rest
```

Replace `{company}` with your LogicMonitor account name.

## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Areas for Improvement

- [ ] Add more detailed response examples from live API
- [ ] Document rate limiting behavior
- [ ] Add webhook payload schemas
- [ ] Include x-code-samples for common operations

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

## Disclaimer

This is an unofficial, community-maintained specification. LogicMonitor is a trademark of LogicMonitor, Inc. This project is not affiliated with or endorsed by LogicMonitor, Inc.

## Resources

- [LogicMonitor Official Documentation](https://www.logicmonitor.com/support)
- [LogicMonitor REST API v3 Docs](https://www.logicmonitor.com/support/rest-api-v3-swagger-documentation)
- [LogicMonitor Community](https://community.logicmonitor.com/)
