# Migration Plan — CallDBProcedure/Process Definition (DUAL connectivity query)

**Project:** Test-TIBCO-Project-2  
**Source platform:** TIBCO  
**Generated:** 2026-10-28T12:32:54.120Z  
**Status:** DRAFT — assembled from the analysis. Nothing has been built in Boomi from this document.

## 1. Interface Metadata

| Attribute | Value |
| --- | --- |
| Interface | CallDBProcedure/Process Definition (DUAL connectivity query) |
| Identifier | calldbprocedure-dual-query |
| Trigger | Scheduled |
| Starts with | No inbound data |
| Complexity | simple (10) |
| Components to build | 4 |
| Source artefacts | legacy/tibco/JDBC samples/CallDBProcedure/Process Definition.process, legacy/tibco/JDBC samples/CallDBProcedure/JDBC-Connection-1.sharedjdbc, legacy/tibco/JDBC samples/CallDBProcedure/defaultVars/defaultVars.substvar |
| Depends on | Nothing |

## 2. End-to-End Process Architecture

> **Not available.** Legacy and target architecture cannot be cited. Boomi components for this interface (connection, two operations, two database profiles, process) were already generated under active-development/ from the former export and should be retired if CRMServices is confirmed as the source.

## 3. Process Flow Sequence

> **Not available.** The process definition for this interface is not on disk, so no step can be cited. The CRMServices deployment archive lists Start_CRMServices, Reply_GetAccountdataRV, Reply_UpsertContactRV, Subscribe_UpsertAccountWithReferencesJMS, Subscribe_UpsertContactPub and their underscore variants; none is this process.

## 4. Payload Profiles

> **Not available.** No profile can be cited; the cached result-set schema lived in the absent process file.

## 5. Mapping Documents

> **Not available.** No source file exists from which a mapping could be cited. (The earlier analysis recorded no mappings for this interface in any case.)

## 6. Business Logic

> **Not available.** No source file exists from which a business rule could be cited. (The earlier analysis recorded none for this interface.)

## 7. Connectors and Adapters

> **Not available.** The JDBC shared resource and process file for this interface are absent, so no endpoint, adapter or configuration value can be cited. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) also differs from the 5.8.0.10 recorded in the inventory for this project, confirming a different export.

## 8. Sub-Process Call Hierarchy

> **Not available.** This interface calls no sub-processes.

## 9. Custom Code

> **Not available.** No custom code was found in this interface.

## 10. Error Handling

> **Not available.** The JDBC shared resource and process file for this interface are absent, so no endpoint, adapter or configuration value can be cited. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) also differs from the 5.8.0.10 recorded in the inventory for this project, confirming a different export.

## 11. MDS / Shared Artifacts

> **Not available.** No shared artefacts were recorded for this interface.

## 12. External Services

> **Not available.** No external services were recorded for this interface.

## 13. Environment Configuration Matrix

> **Not available.** No environment-specific configuration was recorded.

## 14. Boomi Migration Readiness Summary

This interface cannot be analysed against the source currently in the workspace. The inventory lists it as the DUAL connectivity query in the CallDBProcedure project of the 'JDBC samples' TIBCO BusinessWorks 5.x export, with three source artefacts under legacy/tibco/JDBC samples/CallDBProcedure/. None of those files, and no 'JDBC samples' folder, exists under legacy/tibco/ any more. The only project now in the extracted source is CRMServices, a KPN EAI BusinessWorks 5.x project (Designer 5.5.0.1, repository format 5.2.1) whose deployment archive lists eight processes, none of which is this one.

A detailed analysis of this interface was written on 27 October 2026 while the JDBC samples export was present; its content survives in the rendered reports under migration/reports/interfaces/calldbprocedure-dual-query/ and in MigrationManifest.md section 3. That analysis cannot be re-cited here because the files it was drawn from are no longer on disk, and citing unrelated CRMServices files in their place would be a fabrication.

Two outcomes are possible and they lead to opposite work. If the JDBC samples export is restored to legacy/tibco/JDBC samples/, the earlier analysis becomes valid again and this file should be replaced by it. If CRMServices is the intended source, this interface does not exist in it: the inventory must be regenerated from CRMServices and this interface id retired, together with the Boomi components already generated for it under active-development/. The question for the client is recorded in questions.json.

| # | Component | Identifier | Boomi type | Depends on |
| --- | --- | --- | --- | --- |
| 1 | Oracle XE esb-rep-wov01 DB Conn | oracle-xe-esbrep-system-db-conn | connector-settings | — |
| 2 | Oracle DUAL ROWNUM SELECT Op | dual-rownum-sqldirect-db-op | connector-action | oracle-xe-esbrep-system-db-conn |
| 3 | Oracle DUAL SELECT Op | dual-select-all-db-op | connector-action | oracle-xe-esbrep-system-db-conn |
| 4 | [TEST] CallDBProcedure DUAL Query | calldbprocedure-dual-query-process | process | dual-select-all-db-op, dual-rownum-sqldirect-db-op |

## 15. Appendix

- legacy/tibco/CRMServices/vcrepo.dat
- legacy/tibco/CRMServices/.folder
- legacy/tibco/CRMServices/CRMServices.archive

## Open questions

### Still outstanding

REVIEW-NEEDED: The TIBCO export now loaded for this project is CRMServices (a KPN EAI BusinessWorks project), not the 'JDBC samples' export this interface was identified in; which of the two is the integration estate you want migrated to Boomi? (Every analysis artefact for this interface (inventory entry, detail analysis, generated Boomi components) was produced from the JDBC samples export, which is no longer in the workspace. Until the intended source is confirmed, nothing further can be built or verified for this interface, and the same applies to the other six interfaces in the inventory.)
  - If this is not answered: CRMServices is treated as the intended source: the analysis phase is re-run on it, a new inventory is produced, this interface id is retired, and the Boomi components already generated for it under active-development/ are discarded.

