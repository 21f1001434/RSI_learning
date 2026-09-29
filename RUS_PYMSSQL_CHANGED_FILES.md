# RUS PyMSSQL changed files

Changes relative to `RUS_v11_62_7_FULL_SOURCE_COVERAGE_FIXED.zip`: **24 modified, 5 added, 1 removed**.

The full updated archive includes all application components and the earlier full-source coverage/shared-runner fixes. The patch contains only the differences below; its base is the previous full-source-coverage ZIP, not an arbitrary deployment checkout.

Baseline SHA-256: `2849b2a3df6bc136148c231dc260a62b79d5b0c92cbf488cddc9dd5c447d90be`

Full updated ZIP: `RUS_v11_62_7_PYMSSQL_FULL_CODE.zip`

Full updated SHA-256: `eb093c19e5f3733acf5d8390deef18fddbef51e08c78be75409ec8536ba881e7`

Paths below are relative to the repository root (`RUS/` in the ZIP). The patch does not replace corporate CI files or overwrite runtime logs. Preserve deployment-specific secrets and configuration when merging.

## Modified

| File | Change |
| --- | --- |
| `AgenticDataDisparity.API/.env.example` | Direct connection, port, timeouts, TDS and certificate settings. |
| `AgenticDataDisparity.API/Dockerfile` | Remove unixODBC build/runtime packages; retain CA certificates. |
| `AgenticDataDisparity.API/README.md` | Update database setup and link the PyMSSQL migration guide. |
| `AgenticDataDisparity.API/coverage-summary.json` | Refresh test totals, full-source coverage and source hashes. |
| `AgenticDataDisparity.API/coverage.xml` | Refresh current measured coverage with base-directory-correct source paths. |
| `AgenticDataDisparity.API/junit.xml` | Refresh the complete passing test report. |
| `AgenticDataDisparity.API/requirements.txt` | Replace pyodbc with pymssql==2.4.2. |
| `AgenticDataDisparity.API/scripts/bootstrap.ps1` | Check and install the PyMSSQL runtime through project requirements. |
| `AgenticDataDisparity.API/src/app_settings.py` | Remove legacy ODBC metadata from the local fallback connection string. |
| `AgenticDataDisparity.API/src/services/disparity_agent/connectors/rewards_db.py` | Use PyMSSQL connections, bound parameters, cleanup and numeric error mapping. |
| `AgenticDataDisparity.API/src/services/disparity_agent/settings.py` | Add PyMSSQL port/TDS/login settings and safely quote connection values. |
| `AgenticDataDisparity.API/tests/unit_tests/test_failure_and_compatibility_paths.py` | Verify normalized connection-string semantics. |
| `AgenticDataDisparity.API/tests/unit_tests/test_integration_boundaries_full_coverage.py` | Replace legacy ODBC helper coverage with PyMSSQL behavior checks. |
| `AgenticDataDisparity.API/tests/unit_tests/test_transport_and_batch_workflows.py` | Exercise PyMSSQL binding, lifecycle and error handling. |
| `AgenticDataDisparity.API/tests/unit_tests/test_v1159_runtime_parity.py` | Require the current PyMSSQL helper in the package contract. |
| `Documentation/Reference/FOLDER_STRUCTURE_V11_62.md` | Update the connector helper path. |
| `Documentation/Validation/FILE_MANIFEST_SHA256.txt` | Refresh hashes for every packaged file except the manifest itself. |
| `Documentation/Validation/README.md` | Identify the current verification report and mark older reports as historical. |
| `Documentation/Validation/VALIDATION_ENVIRONMENT.txt` | Record the actual current test runtime and dependency versions. |
| `README_FIRST.md` | Identify the current build and link migration/verification instructions. |
| `coverage-summary.json` | Refresh test totals, full-source coverage and source hashes. |
| `coverage.xml` | Refresh current measured coverage with base-directory-correct source paths. |
| `junit.xml` | Refresh the complete passing test report. |
| `scripts/validate_v11_62_full_parity.py` | Validate the current helper path while retaining runtime contracts. |

## Added

| File | Change |
| --- | --- |
| `AgenticDataDisparity.API/src/resources/freetds.conf` | Default encryption, CA and hostname verification for FreeTDS. |
| `AgenticDataDisparity.API/src/services/disparity_agent/connectors/mssql_utils.py` | Parse connection strings and validate authentication, TLS and native connection options. |
| `AgenticDataDisparity.API/tests/unit_tests/test_pymssql_migration.py` | Add 71 migration regression cases, including runtime dependency checks. |
| `Documentation/PYMSSQL_MIGRATION.md` | Installation, supported settings, certificate configuration and patch instructions. |
| `Documentation/Validation/PYMSSQL_VERIFICATION.md` | Current measured results, reproduction steps and validation limits. |

## Removed — delete on in-place merge

| File | Change |
| --- | --- |
| `AgenticDataDisparity.API/src/services/disparity_agent/connectors/odbc_utils.py` | Delete the unused ODBC driver selection module. |
