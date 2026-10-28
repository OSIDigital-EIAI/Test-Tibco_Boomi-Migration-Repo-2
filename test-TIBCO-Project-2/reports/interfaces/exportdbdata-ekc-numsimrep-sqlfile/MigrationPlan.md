# Migration Plan — ExportDBData/WriteResultsetToFile/Process Definition (EKC_NUMSIMREP_ESB_XML to SQL file)

**Project:** Test-TIBCO-Project-2  
**Source platform:** TIBCO  
**Generated:** 2026-10-28T12:32:54.139Z  
**Status:** DRAFT — assembled from the analysis. Nothing has been built in Boomi from this document.

## 1. Interface Metadata

| Attribute | Value |
| --- | --- |
| Interface | ExportDBData/WriteResultsetToFile/Process Definition (EKC_NUMSIMREP_ESB_XML to SQL file) |
| Identifier | exportdbdata-ekc-numsimrep-sqlfile |
| Trigger | Scheduled |
| Starts with | No inbound data |
| Complexity | medium (45) |
| Components to build | 7 |
| Source artefacts | legacy/tibco/JDBC samples/ExportDBData/Functionalities/WriteResultsetToFile/Process Definition.process, legacy/tibco/JDBC samples/ExportDBData/Functionalities/WriteResultsetToFile/JDBC Connection.sharedjdbc, legacy/tibco/JDBC samples/ExportDBData/defaultVars/defaultVars.substvar |
| Depends on | calldbprocedure-dual-query |

## 2. End-to-End Process Architecture

> **Not available.** Legacy and target architecture cannot be cited. This interface owns the shared Disk connection, flat file profile and SQL builder function used by exportdbdata-xxcw-service-request-responses-sqlfile; if CRMServices is confirmed as the source, all of them are retired together with the interface.

## 3. Process Flow Sequence

> **Not available.** The process definition for this interface is not on disk, so no step can be cited. The CRMServices deployment archive lists Start_CRMServices, Reply_GetAccountdataRV, Reply_UpsertContactRV, Subscribe_UpsertAccountWithReferencesJMS, Subscribe_UpsertContactPub and their underscore variants; none is this process.

## 4. Payload Profiles

> **Not available.** The fourteen-column cached result-set schema lived in the absent process file; no profile can be cited.

## 5. Mapping Documents

> **Not available.** The XPath concat() expression that defined the fourteen-column INSERT mapping lived in the absent process file; the mapping cannot be cited. The earlier mapping is preserved in migration/reports/interfaces/exportdbdata-ekc-numsimrep-sqlfile/Mappings.csv.

## 6. Business Logic

> **Not available.** The row cap, schema retargeting, quoting, append and no-commit rules were read from the absent process file and cannot be cited.

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

This interface cannot be analysed against the source currently in the workspace. The inventory lists it as the EKC_NUMSIMREP_ESB_XML table-to-SQL-script export in the ExportDBData project of the 'JDBC samples' TIBCO BusinessWorks 5.x export, with three source artefacts under legacy/tibco/JDBC samples/ExportDBData/. None of those files, and no 'JDBC samples' folder, exists under legacy/tibco/ any more. The only project now in the extracted source is CRMServices, a KPN EAI BusinessWorks 5.x project (Designer 5.5.0.1, repository format 5.2.1) whose deployment archive lists eight processes, none of which is this one.

A detailed analysis of this interface, including its fourteen-column mapping and six business rules, was written on 27 October 2026 while the JDBC samples export was present; its content survives in the rendered reports under migration/reports/interfaces/exportdbdata-ekc-numsimrep-sqlfile/ (including Mappings.csv) and in MigrationManifest.md section 4. That analysis cannot be re-cited here because the files it was drawn from are no longer on disk, and citing unrelated CRMServices files in their place would be a fabrication.

If the JDBC samples export is restored to legacy/tibco/JDBC samples/, the earlier analysis becomes valid again and this file should be replaced by it. If CRMServices is the intended source, this interface does not exist in it: the inventory must be regenerated from CRMServices and this interface id retired. This interface also owns three shared components (Disk connection, SQL line flat file profile, SQL builder function) that its sibling XXCW export depends on; they are retired with it. The question for the client is recorded in questions.json.

| # | Component | Identifier | Boomi type | Depends on |
| --- | --- | --- | --- | --- |
| 1 | SQL Script Line FF Prof | sql-script-line-flatfile-profile | profile.flatfile | — |
| 2 | Disk Local Export Conn | disk-local-export-conn | connector-settings | — |
| 3 | Disk exportCramer.sql WRITE Op | exportcramer-sql-disk-write-op | connector-action | disk-local-export-conn, sql-script-line-flatfile-profile |
| 4 | Oracle EKC_NUMSIMREP_ESB_XML SELECT Op | ekc-numsimrep-select-db-op | connector-action | oracle-xe-esbrep-system-db-conn |
| 5 | SQL Insert Literal Builder Fn | sql-insert-literal-builder-fn | transform.function | — |
| 6 | Map \| EKC_NUMSIMREP Record to SQL Insert Line | ekc-numsimrep-record-to-insert-map | transform.map | ekc-numsimrep-select-db-op, sql-script-line-flatfile-profile, sql-insert-literal-builder-fn |
| 7 | ExportDBData EKC_NUMSIMREP_ESB_XML to SQL File | exportdbdata-ekc-numsimrep-process | process | ekc-numsimrep-select-db-op, ekc-numsimrep-record-to-insert-map, exportcramer-sql-disk-write-op |

## 15. Appendix

- legacy/tibco/CRMServices/vcrepo.dat
- legacy/tibco/CRMServices/.folder
- legacy/tibco/CRMServices/CRMServices.archive

## Open questions

### Still outstanding

REVIEW-NEEDED: The TIBCO export now loaded for this project is CRMServices (a KPN EAI BusinessWorks project), not the 'JDBC samples' export this interface was identified in; which of the two is the integration estate you want migrated to Boomi? (Every analysis artefact for this interface (inventory entry, detail analysis with its fourteen-column mapping, shared components it owns for the sibling XXCW export) was produced from the JDBC samples export, which is no longer in the workspace. Until the intended source is confirmed, nothing further can be built or verified for this interface, and the same applies to the other six interfaces in the inventory.)
  - If this is not answered: CRMServices is treated as the intended source: the analysis phase is re-run on it, a new inventory is produced, and this interface id and the shared components it owns are retired.

