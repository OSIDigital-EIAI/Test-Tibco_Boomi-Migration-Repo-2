# Migration Plan — GetObjectsFromDB/GetObjectFromDB/Starter (call BLA.TEST.GET with O_COLLECTION)

**Project:** Test-TIBCO-Project-2  
**Source platform:** TIBCO  
**Generated:** 2026-10-28T12:32:54.179Z  
**Status:** DRAFT — assembled from the analysis. Nothing has been built in Boomi from this document.

## 1. Interface Metadata

| Attribute | Value |
| --- | --- |
| Interface | GetObjectsFromDB/GetObjectFromDB/Starter (call BLA.TEST.GET with O_COLLECTION) |
| Identifier | getobjectsfromdb-get-procedure |
| Trigger | Scheduled |
| Starts with | No inbound data |
| Complexity | complex (65) |
| Components to build | 3 |
| Source artefacts | legacy/tibco/JDBC samples/GetObjectsFromDB/Functionalities/GetObjectFromDB/Starter.process, legacy/tibco/JDBC samples/GetObjectsFromDB/Functionalities/GetObjectFromDB/JDBC Connection.sharedjdbc, legacy/tibco/JDBC samples/GetObjectsFromDB/Functionalities/GetObjectFromDB/AliasLibrary.aliaslib, legacy/tibco/JDBC samples/GetObjectsFromDB/defaultVars/defaultVars.substvar |
| Depends on | Nothing |

## 2. End-to-End Process Architecture

> **Not available.** Legacy and target architecture cannot be cited. This interface owns the shared Oracle connection used by ziggo-sqldate-createb2cnumnetwinv and calldbprocedure-getcomplex-java; if CRMServices is confirmed as the source, all three are retired together.

## 3. Process Flow Sequence

> **Not available.** The process definition for this interface is not on disk, so no step can be cited. The CRMServices deployment archive lists Start_CRMServices, Reply_GetAccountdataRV, Reply_UpsertContactRV, Subscribe_UpsertAccountWithReferencesJMS, Subscribe_UpsertContactPub and their underscore variants; none is this process.

## 4. Payload Profiles

> **Not available.** The stored-procedure parameter view (COLLECTIONLIST IN O_COLLECTION, I_TELECOMNUMBER OUT VARCHAR2) lived in the absent process file; no profile can be cited.

## 5. Mapping Documents

> **Not available.** The constant input bindings to the O_COLLECTION object parameter and the OUT parameter capture lived in the absent process file; the mapping cannot be cited.

## 6. Business Logic

> **Not available.** The disabled-branch (1=0), constant-input, single-call, discarded-output and hard-coded-owner rules were read from the absent process file and cannot be cited.

## 7. Connectors and Adapters

> **Not available.** The JDBC shared resource, process file and alias library for this interface are absent, so no endpoint, adapter or configuration value can be cited. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) differs from the 5.8.0.10 recorded in the inventory for this project, confirming a different export.

## 8. Sub-Process Call Hierarchy

> **Not available.** This interface calls no sub-processes.

## 9. Custom Code

> **Not available.** No custom code was found in this interface.

## 10. Error Handling

> **Not available.** The JDBC shared resource, process file and alias library for this interface are absent, so no endpoint, adapter or configuration value can be cited. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) differs from the 5.8.0.10 recorded in the inventory for this project, confirming a different export.

## 11. MDS / Shared Artifacts

> **Not available.** No shared artefacts were recorded for this interface.

## 12. External Services

> **Not available.** No external services were recorded for this interface.

## 13. Environment Configuration Matrix

> **Not available.** No environment-specific configuration was recorded.

## 14. Boomi Migration Readiness Summary

This interface cannot be analysed against the source currently in the workspace. The inventory lists it as the BLA.TEST.GET stored-procedure call in the GetObjectsFromDB project of the 'JDBC samples' TIBCO BusinessWorks 5.x export, with four source artefacts under legacy/tibco/JDBC samples/GetObjectsFromDB/. None of those files, and no 'JDBC samples' folder, exists under legacy/tibco/ any more. The only project now in the extracted source is CRMServices, a KPN EAI BusinessWorks 5.x project (Designer 5.5.0.1, repository format 5.2.1) whose deployment archive lists eight processes, none of which is this one.

A detailed analysis of this interface, including the Oracle object-type parameter problem, the dead SQL Direct branch and ten client questions, was written on 27 October 2026 while the JDBC samples export was present; its content survives in the rendered reports under migration/reports/interfaces/getobjectsfromdb-get-procedure/ and in MigrationManifest.md section 7. That analysis cannot be re-cited here because the files it was drawn from are no longer on disk, and citing unrelated CRMServices files in their place would be a fabrication.

If the JDBC samples export is restored to legacy/tibco/JDBC samples/, the earlier analysis becomes valid again and this file should be replaced by it. If CRMServices is the intended source, this interface does not exist in it: the inventory must be regenerated from CRMServices and this interface id retired. This interface owns the shared Oracle connection that the Ziggo and GETCOMPLEX interfaces depend on; it is retired with them. The question for the client is recorded in questions.json.

| # | Component | Identifier | Boomi type | Depends on |
| --- | --- | --- | --- | --- |
| 1 | Oracle XE localhost DB Conn | oracle-xe-localhost-system-db-conn | connector-settings | — |
| 2 | Oracle BLA.TEST.GET Stored Procedure Op | bla-test-get-sp-db-op | connector-action | oracle-xe-localhost-system-db-conn |
| 3 | GetObjectsFromDB Call BLA.TEST.GET | getobjectsfromdb-get-procedure-process | process | bla-test-get-sp-db-op |

## 15. Appendix

- legacy/tibco/CRMServices/vcrepo.dat
- legacy/tibco/CRMServices/.folder
- legacy/tibco/CRMServices/CRMServices.archive

## Open questions

### Still outstanding

REVIEW-NEEDED: The TIBCO export now loaded for this project is CRMServices (a KPN EAI BusinessWorks project), not the 'JDBC samples' export this interface was identified in; which of the two is the integration estate you want migrated to Boomi? (Every analysis artefact for this interface (inventory entry, detail analysis of the BLA.TEST.GET call and its Oracle object-type parameter, the shared Oracle connection it owns for two other interfaces) was produced from the JDBC samples export, which is no longer in the workspace. Until the intended source is confirmed, nothing further can be built or verified for this interface, and the same applies to the other six interfaces in the inventory.)
  - If this is not answered: CRMServices is treated as the intended source: the analysis phase is re-run on it, a new inventory is produced, and this interface id and the shared connection it owns are retired.

