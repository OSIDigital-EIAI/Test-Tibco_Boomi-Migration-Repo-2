# JDBCGetConnTest/BusinessProcesses/GetConnTestProcess (connection metadata test)

Test-TIBCO-Project-2 · Scheduled · complex complexity

[← All interfaces](../../Extraction_Report.md)

- [Interface Overview](#interface-overview)
- [Interface Summary](#interface-summary)
- [Functional Analysis](#functional-analysis)
- [Technical Analysis](#technical-analysis)
- [Mappings](#mappings)
- [Business Rules](#business-rules)
- [Flow Diagram](#flow-diagram)
- [Data Model](#data-model)
- [Architecture](#architecture)

---

## Interface Overview

_The inventory's only source artefact (legacy/tibco/JDBC samples/JDBCGetConnTest.zip) is not in the extracted source. legacy/tibco/ contains only the CRMServices project, whose vcrepo.dat identifies it as displayName CRMServices, version 5.2.1. Purpose and systems cannot be cited._

| Field | Value |
| --- | --- |
| Interface | JDBCGetConnTest/BusinessProcesses/GetConnTestProcess (connection metadata test) |
| Type | Scheduled |
| Complexity | complex |
| Components to build | 3 |
| Mapping rules | 0 |
| Business rules | 0 |

## Interface Summary

This interface cannot be analysed against the source currently in the workspace. The inventory lists it as the connection-metadata smoke test in the JDBCGetConnTest project, which existed only as the archive legacy/tibco/JDBC samples/JDBCGetConnTest.zip inside the 'JDBC samples' TIBCO BusinessWorks 5.x export. That zip, and the whole 'JDBC samples' folder, no longer exist under legacy/tibco/. The only project now in the extracted source is CRMServices, a KPN EAI BusinessWorks 5.x project (Designer 5.5.0.1, repository format 5.2.1) whose deployment archive lists eight processes, none of which is this one.  A detailed analysis of this interface was written on 27 October 2026 while the zip was present; it recommended dropping the interface because it was a developer's connectivity test with embedded Java that has no Boomi equivalent. That content survives in the rendered reports under migration/reports/interfaces/jdbcgetconntest-connection-smoke-test/ and in MigrationManifest.md section 6. It cannot be re-cited here because the zip is no longer on disk, and citing unrelated CRMServices files in its place would be a fabrication.  If the JDBC samples export is restored, the earlier analysis becomes valid again and this file should be replaced by it. If CRMServices is the intended source, this interface does not exist in it and the inventory must be regenerated. In either case the earlier recommendation to drop this interface stands. The question for the client is recorded in questions.json.

**Complexity:** complex (score 30)

## Functional Analysis

_The process definition (GetConnTestProcess.process inside the absent zip) cannot be cited. The CRMServices deployment archive lists Start\_CRMServices, Reply\_GetAccountdataRV, Reply\_UpsertContactRV, Subscribe\_UpsertAccountWithReferencesJMS, Subscribe\_UpsertContactPub and their underscore variants; none is this process._

## Technical Analysis

_The JDBC shared resource and the Java Code activity source inside the absent zip cannot be cited, so no endpoint, adapter, custom code or configuration value can be recorded. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) differs from the 5.8.0 repository version the zip's vcrepo.dat carried, confirming a different export._

## Mappings

_The only bindings (a connection object reference into Java and a constant log message) lived in the absent zip and cannot be cited._

## Business Rules

_No source file exists from which a rule could be cited. (The earlier analysis recorded none for this interface.)_

## Flow Diagram

_The process definition is absent; a flow graph would have to be reproduced from memory of the former export and could not be cited._

## Data Model

_No profile can be cited. (The earlier analysis recorded no data profile for this interface in any case.)_

## Architecture

_Legacy and target architecture cannot be cited. The earlier recommendation (drop the interface; a Boomi connection test replaces it) is preserved in migration/reports/interfaces/jdbcgetconntest-connection-smoke-test/ and holds under either outcome._

## Client questions

- **Q-001** The TIBCO export now loaded for this project is CRMServices (a KPN EAI BusinessWorks project), not the 'JDBC samples' export this interface was identified in; which of the two is the integration estate you want migrated to Boomi?
  **If this is not answered:** CRMServices is treated as the intended source: the analysis phase is re-run on it, a new inventory is produced, and this interface id is retired.
