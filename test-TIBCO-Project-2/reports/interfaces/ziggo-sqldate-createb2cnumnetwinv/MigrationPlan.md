# Migration Plan — Ziggo_SqlDateIssue_BWProject/TestSqlDateIssue (CREATEB2CNUMNETWINV_1 DATE round-trip)

**Project:** Test-TIBCO-Project-2  
**Source platform:** TIBCO  
**Generated:** 2026-10-28T12:32:54.194Z  
**Status:** DRAFT — assembled from the analysis. Nothing has been built in Boomi from this document.

## 1. Interface Metadata

| Attribute | Value |
| --- | --- |
| Interface | Ziggo_SqlDateIssue_BWProject/TestSqlDateIssue (CREATEB2CNUMNETWINV_1 DATE round-trip) |
| Identifier | ziggo-sqldate-createb2cnumnetwinv |
| Trigger | Scheduled |
| Starts with | No inbound data |
| Complexity | complex (70) |
| Components to build | 3 |
| Source artefacts | legacy/tibco/JDBC samples/Ziggo_SqlDateIssue_BWProject/TestSqlDateIssue.process, legacy/tibco/JDBC samples/Ziggo_SqlDateIssue_BWProject/JDBC Connection oracle.sharedjdbc, legacy/tibco/JDBC samples/Ziggo_SqlDateIssue_BWProject/JDBC Connection tibcosoftwareinc.sharedjdbc, legacy/tibco/JDBC samples/Ziggo_SqlDateIssue_BWProject/defaultVars/defaultVars.substvar |
| Depends on | getobjectsfromdb-get-procedure |

## 2. End-to-End Process Architecture

> **Not available.** Legacy and target architecture cannot be cited. This interface depends on the shared Oracle connection owned by getobjectsfromdb-get-procedure, which is in the same state; if CRMServices is confirmed as the source, both are retired together.

## 3. Process Flow Sequence

> **Not available.** The process definition for this interface is not on disk, so no step can be cited. The CRMServices deployment archive lists Start_CRMServices, Reply_GetAccountdataRV, Reply_UpsertContactRV, Subscribe_UpsertAccountWithReferencesJMS, Subscribe_UpsertContactPub and their underscore variants; none is this process.

## 4. Payload Profiles

> **Not available.** The stored-procedure parameter view (I_SERVICE IN O_FULFILL_NRNW_C_IN_SERV with NUMBERSTATUSENDDATE) and the INPUTTABLE result-set schema lived in the absent process file; no profile can be cited.

## 5. Mapping Documents

> **Not available.** The current-dateTime() binding to the O_FULFILL_NRNW_C_IN_SERV object attribute and the INPUTTABLE read-back lived in the absent process file; the mappings cannot be cited.

## 6. Business Logic

> **Not available.** The current-date-time, double-invocation, AND-join, discarded-read-back and unused-DataDirect-connection rules were read from the absent process and resource files and cannot be cited.

## 7. Connectors and Adapters

> **Not available.** The two JDBC shared resources and the process file for this interface are absent, so no endpoint, adapter or configuration value can be cited. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) differs from the 5.8.0.10 recorded in the inventory for this project, confirming a different export.

## 8. Sub-Process Call Hierarchy

> **Not available.** This interface calls no sub-processes.

## 9. Custom Code

> **Not available.** No custom code was found in this interface.

## 10. Error Handling

> **Not available.** The two JDBC shared resources and the process file for this interface are absent, so no endpoint, adapter or configuration value can be cited. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) differs from the 5.8.0.10 recorded in the inventory for this project, confirming a different export.

## 11. MDS / Shared Artifacts

> **Not available.** No shared artefacts were recorded for this interface.

## 12. External Services

> **Not available.** No external services were recorded for this interface.

## 13. Environment Configuration Matrix

> **Not available.** No environment-specific configuration was recorded.

## 14. Boomi Migration Readiness Summary

This interface cannot be analysed against the source currently in the workspace. The inventory lists it as the CREATEB2CNUMNETWINV_1 date round-trip test in the Ziggo_SqlDateIssue_BWProject project of the 'JDBC samples' TIBCO BusinessWorks 5.x export, with four source artefacts under legacy/tibco/JDBC samples/Ziggo_SqlDateIssue_BWProject/. None of those files, and no 'JDBC samples' folder, exists under legacy/tibco/ any more. The only project now in the extracted source is CRMServices, a KPN EAI BusinessWorks 5.x project (Designer 5.5.0.1, repository format 5.2.1) whose deployment archive lists eight processes, none of which is this one.

A detailed analysis of this interface was written on 27 October 2026 while the JDBC samples export was present; it identified the project as a driver-comparison reproduction of a date-precision defect, recommended dropping it, and recorded the Oracle object-type parameter problem and the double procedure invocation. That content survives in the rendered reports under migration/reports/interfaces/ziggo-sqldate-createb2cnumnetwinv/ and in MigrationManifest.md section 8. It cannot be re-cited here because the files it was drawn from are no longer on disk, and citing unrelated CRMServices files in their place would be a fabrication.

If the JDBC samples export is restored to legacy/tibco/JDBC samples/, the earlier analysis becomes valid again and this file should be replaced by it. If CRMServices is the intended source, this interface does not exist in it: the inventory must be regenerated from CRMServices and this interface id retired. The earlier recommendation to drop this interface stands under either outcome. The question for the client is recorded in questions.json.

| # | Component | Identifier | Boomi type | Depends on |
| --- | --- | --- | --- | --- |
| 1 | Oracle CRAMERTEST.INPUTTABLE SELECT Op | cramertest-inputtable-select-db-op | connector-action | oracle-xe-localhost-system-db-conn |
| 2 | Oracle CRAMERTEST.PKGB2CNUMNETWINV.CREATEB2CNUMNETWINV_1 Stored Procedure Op | createb2cnumnetwinv-sp-db-op | connector-action | oracle-xe-localhost-system-db-conn |
| 3 | [TEST] Ziggo SQL Date Issue CREATEB2CNUMNETWINV_1 | ziggo-sqldate-process | process | createb2cnumnetwinv-sp-db-op, cramertest-inputtable-select-db-op |

## 15. Appendix

- legacy/tibco/CRMServices/vcrepo.dat
- legacy/tibco/CRMServices/.folder
- legacy/tibco/CRMServices/CRMServices.archive

## Open questions

### Still outstanding

REVIEW-NEEDED: The TIBCO export now loaded for this project is CRMServices (a KPN EAI BusinessWorks project), not the 'JDBC samples' export this interface was identified in; which of the two is the integration estate you want migrated to Boomi? (Every analysis artefact for this interface was produced from the JDBC samples export, which is no longer in the workspace. Until the intended source is confirmed, nothing further can be verified for this interface, and the same applies to the other six interfaces in the inventory. The earlier analysis already recommended dropping this interface as a defect-reproduction test, so its disposition is the same under either answer.)
  - If this is not answered: CRMServices is treated as the intended source: the analysis phase is re-run on it, a new inventory is produced, and this interface id is retired.

