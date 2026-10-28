# Migration Plan — ExportDBData/WriteResultsetToFile/XXCW_SERVICE_REQUEST_RESPONSES (to SQL file)

**Project:** Test-TIBCO-Project-2  
**Source platform:** TIBCO  
**Generated:** 2026-10-28T12:32:54.151Z  
**Status:** DRAFT — assembled from the analysis. Nothing has been built in Boomi from this document.

## 1. Interface Metadata

| Attribute | Value |
| --- | --- |
| Interface | ExportDBData/WriteResultsetToFile/XXCW_SERVICE_REQUEST_RESPONSES (to SQL file) |
| Identifier | exportdbdata-xxcw-service-request-responses-sqlfile |
| Trigger | Scheduled |
| Starts with | No inbound data |
| Complexity | medium (40) |
| Components to build | 4 |
| Source artefacts | legacy/tibco/JDBC samples/ExportDBData/Functionalities/WriteResultsetToFile/XXCW_SERVICE_REQUEST_RESPONSES.process, legacy/tibco/JDBC samples/ExportDBData/Functionalities/WriteResultsetToFile/JDBC Connection.sharedjdbc, legacy/tibco/JDBC samples/ExportDBData/defaultVars/defaultVars.substvar |
| Depends on | calldbprocedure-dual-query, exportdbdata-ekc-numsimrep-sqlfile |

## 2. End-to-End Process Architecture

> **Not available.** Legacy and target architecture cannot be cited. This interface depends on shared components owned by calldbprocedure-dual-query and exportdbdata-ekc-numsimrep-sqlfile, both of which are in the same state; if CRMServices is confirmed as the source, all three are retired together.

## 3. Process Flow Sequence

> **Not available.** The process definition for this interface is not on disk, so no step can be cited. The CRMServices deployment archive lists Start_CRMServices, Reply_GetAccountdataRV, Reply_UpsertContactRV, Subscribe_UpsertAccountWithReferencesJMS, Subscribe_UpsertContactPub and their underscore variants; none is this process.

## 4. Payload Profiles

> **Not available.** The seven-column cached result-set schema lived in the absent process file; no profile can be cited.

## 5. Mapping Documents

> **Not available.** The XPath concat() expression that defined the seven-column INSERT mapping with the sysdate substitution lived in the absent process file; the mapping cannot be cited. The earlier mapping is preserved in migration/reports/interfaces/exportdbdata-xxcw-service-request-responses-sqlfile/Mappings.csv.

## 6. Business Logic

> **Not available.** The unlimited-rows, sysdate re-stamping, quoting, append and no-commit rules were read from the absent process file and cannot be cited.

## 7. Connectors and Adapters

> **Not available.** The JDBC shared resource and process file for this interface are absent, so no endpoint, adapter or configuration value can be cited. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) differs from the 5.8.0.10 recorded in the inventory for this project, confirming a different export.

## 8. Sub-Process Call Hierarchy

> **Not available.** This interface calls no sub-processes.

## 9. Custom Code

> **Not available.** No custom code was found in this interface.

## 10. Error Handling

> **Not available.** The JDBC shared resource and process file for this interface are absent, so no endpoint, adapter or configuration value can be cited. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) differs from the 5.8.0.10 recorded in the inventory for this project, confirming a different export.

## 11. MDS / Shared Artifacts

> **Not available.** No shared artefacts were recorded for this interface.

## 12. External Services

> **Not available.** No external services were recorded for this interface.

## 13. Environment Configuration Matrix

> **Not available.** No environment-specific configuration was recorded.

## 14. Boomi Migration Readiness Summary

This interface cannot be analysed against the source currently in the workspace. The inventory lists it as the XXCW_SERVICE_REQUEST_RESPONSES table-to-SQL-script export in the ExportDBData project of the 'JDBC samples' TIBCO BusinessWorks 5.x export, with three source artefacts under legacy/tibco/JDBC samples/ExportDBData/. None of those files, and no 'JDBC samples' folder, exists under legacy/tibco/ any more. The only project now in the extracted source is CRMServices, a KPN EAI BusinessWorks 5.x project (Designer 5.5.0.1, repository format 5.2.1) whose deployment archive lists eight processes, none of which is this one.

A detailed analysis of this interface, including its seven-column mapping with the sysdate substitution and six business rules, was written on 27 October 2026 while the JDBC samples export was present; its content survives in the rendered reports under migration/reports/interfaces/exportdbdata-xxcw-service-request-responses-sqlfile/ (including Mappings.csv) and in MigrationManifest.md section 5. That analysis cannot be re-cited here because the files it was drawn from are no longer on disk, and citing unrelated CRMServices files in their place would be a fabrication.

If the JDBC samples export is restored to legacy/tibco/JDBC samples/, the earlier analysis becomes valid again and this file should be replaced by it. If CRMServices is the intended source, this interface does not exist in it: the inventory must be regenerated from CRMServices and this interface id retired, together with the two interfaces it depends on for shared components. The question for the client is recorded in questions.json and is the same question raised for the two interfaces already corrected.

| # | Component | Identifier | Boomi type | Depends on |
| --- | --- | --- | --- | --- |
| 1 | Disk exportXXCW_SERVICE_REQUEST_RESPONSES.sql WRITE Op | exportxxcw-sql-disk-write-op | connector-action | disk-local-export-conn, sql-script-line-flatfile-profile |
| 2 | Oracle XXCW_SERVICE_REQUEST_RESPONSES SELECT Op | xxcw-service-request-responses-select-db-op | connector-action | oracle-xe-esbrep-system-db-conn |
| 3 | Map \| XXCW_SERVICE_REQUEST_RESPONSES Record to SQL Insert Line | xxcw-record-to-insert-map | transform.map | xxcw-service-request-responses-select-db-op, sql-script-line-flatfile-profile, sql-insert-literal-builder-fn |
| 4 | ExportDBData XXCW_SERVICE_REQUEST_RESPONSES to SQL File | exportdbdata-xxcw-process | process | xxcw-service-request-responses-select-db-op, xxcw-record-to-insert-map, exportxxcw-sql-disk-write-op |

## 15. Appendix

- legacy/tibco/CRMServices/vcrepo.dat
- legacy/tibco/CRMServices/.folder
- legacy/tibco/CRMServices/CRMServices.archive

## Open questions

### Still outstanding

REVIEW-NEEDED: The TIBCO export now loaded for this project is CRMServices (a KPN EAI BusinessWorks project), not the 'JDBC samples' export this interface was identified in; which of the two is the integration estate you want migrated to Boomi? (Every analysis artefact for this interface (inventory entry, detail analysis with its seven-column mapping and sysdate rule) was produced from the JDBC samples export, which is no longer in the workspace. Until the intended source is confirmed, nothing further can be built or verified for this interface, and the same applies to the other six interfaces in the inventory.)
  - If this is not answered: CRMServices is treated as the intended source: the analysis phase is re-run on it, a new inventory is produced, and this interface id is retired.

