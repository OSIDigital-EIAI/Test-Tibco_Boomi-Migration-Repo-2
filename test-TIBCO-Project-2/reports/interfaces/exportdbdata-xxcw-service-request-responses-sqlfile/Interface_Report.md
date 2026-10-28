# ExportDBData/WriteResultsetToFile/XXCW\_SERVICE\_REQUEST\_RESPONSES (to SQL file)

Test-TIBCO-Project-2 · Scheduled · medium complexity

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

_The inventory's source artefacts (legacy/tibco/JDBC samples/ExportDBData/Functionalities/WriteResultsetToFile/XXCW\_SERVICE\_REQUEST\_RESPONSES.process, JDBC Connection.sharedjdbc, defaultVars/defaultVars.substvar) are not in the extracted source. legacy/tibco/ contains only the CRMServices project, whose vcrepo.dat identifies it as displayName CRMServices, version 5.2.1. Purpose and systems cannot be cited._

| Field | Value |
| --- | --- |
| Interface | ExportDBData/WriteResultsetToFile/XXCW\_SERVICE\_REQUEST\_RESPONSES (to SQL file) |
| Type | Scheduled |
| Complexity | medium |
| Components to build | 4 |
| Mapping rules | 0 |
| Business rules | 0 |

## Interface Summary

This interface cannot be analysed against the source currently in the workspace. The inventory lists it as the XXCW\_SERVICE\_REQUEST\_RESPONSES table-to-SQL-script export in the ExportDBData project of the 'JDBC samples' TIBCO BusinessWorks 5.x export, with three source artefacts under legacy/tibco/JDBC samples/ExportDBData/. None of those files, and no 'JDBC samples' folder, exists under legacy/tibco/ any more. The only project now in the extracted source is CRMServices, a KPN EAI BusinessWorks 5.x project (Designer 5.5.0.1, repository format 5.2.1) whose deployment archive lists eight processes, none of which is this one.  A detailed analysis of this interface, including its seven-column mapping with the sysdate substitution and six business rules, was written on 27 October 2026 while the JDBC samples export was present; its content survives in the rendered reports under migration/reports/interfaces/exportdbdata-xxcw-service-request-responses-sqlfile/ (including Mappings.csv) and in MigrationManifest.md section 5. That analysis cannot be re-cited here because the files it was drawn from are no longer on disk, and citing unrelated CRMServices files in their place would be a fabrication.  If the JDBC samples export is restored to legacy/tibco/JDBC samples/, the earlier analysis becomes valid again and this file should be replaced by it. If CRMServices is the intended source, this interface does not exist in it: the inventory must be regenerated from CRMServices and this interface id retired, together with the two interfaces it depends on for shared components. The question for the client is recorded in questions.json and is the same question raised for the two interfaces already corrected.

**Complexity:** medium (score 40)

## Functional Analysis

_The process definition for this interface is not on disk, so no step can be cited. The CRMServices deployment archive lists Start\_CRMServices, Reply\_GetAccountdataRV, Reply\_UpsertContactRV, Subscribe\_UpsertAccountWithReferencesJMS, Subscribe\_UpsertContactPub and their underscore variants; none is this process._

## Technical Analysis

_The JDBC shared resource and process file for this interface are absent, so no endpoint, adapter or configuration value can be cited. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) differs from the 5.8.0.10 recorded in the inventory for this project, confirming a different export._

## Mappings

_The XPath concat() expression that defined the seven-column INSERT mapping with the sysdate substitution lived in the absent process file; the mapping cannot be cited. The earlier mapping is preserved in migration/reports/interfaces/exportdbdata-xxcw-service-request-responses-sqlfile/Mappings.csv._

## Business Rules

_The unlimited-rows, sysdate re-stamping, quoting, append and no-commit rules were read from the absent process file and cannot be cited._

## Flow Diagram

_The process definition is absent; a flow graph would have to be reproduced from memory of the former export and could not be cited. Decision blocked: whether this interface exists at all in the intended source._

## Data Model

_The seven-column cached result-set schema lived in the absent process file; no profile can be cited._

## Architecture

_Legacy and target architecture cannot be cited. This interface depends on shared components owned by calldbprocedure-dual-query and exportdbdata-ekc-numsimrep-sqlfile, both of which are in the same state; if CRMServices is confirmed as the source, all three are retired together._

## Client questions

- **Q-001** The TIBCO export now loaded for this project is CRMServices (a KPN EAI BusinessWorks project), not the 'JDBC samples' export this interface was identified in; which of the two is the integration estate you want migrated to Boomi?
  **If this is not answered:** CRMServices is treated as the intended source: the analysis phase is re-run on it, a new inventory is produced, and this interface id is retired.
