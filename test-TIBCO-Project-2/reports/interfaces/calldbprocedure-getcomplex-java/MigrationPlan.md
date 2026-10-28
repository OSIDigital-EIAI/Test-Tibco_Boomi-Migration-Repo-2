# Migration Plan — CallDBProcedure/CallDBProcedure (Java call of ESB_STUBS.TEST.GETCOMPLEX with nested Oracle objects)

**Project:** Test-TIBCO-Project-2  
**Source platform:** TIBCO  
**Generated:** 2026-10-28T12:32:54.211Z  
**Status:** DRAFT — assembled from the analysis. Nothing has been built in Boomi from this document.

## 1. Interface Metadata

| Attribute | Value |
| --- | --- |
| Interface | CallDBProcedure/CallDBProcedure (Java call of ESB_STUBS.TEST.GETCOMPLEX with nested Oracle objects) |
| Identifier | calldbprocedure-getcomplex-java |
| Trigger | Scheduled |
| Starts with | No inbound data |
| Complexity | complex (85) |
| Components to build | 3 |
| Source artefacts | legacy/tibco/JDBC samples/CallDBProcedure/CallDBProcedure.process, legacy/tibco/JDBC samples/CallDBProcedure/JDBC Connection.sharedjdbc, legacy/tibco/JDBC samples/CallDBProcedure/AliasLibrary.aliaslib, legacy/tibco/JDBC samples/CallDBProcedure/README.txt, legacy/tibco/JDBC samples/CallDBProcedure/defaultVars/defaultVars.substvar |
| Depends on | getobjectsfromdb-get-procedure |

## 2. End-to-End Process Architecture

> **Not available.** Legacy and target architecture cannot be cited. This interface depends on the shared Oracle connection owned by getobjectsfromdb-get-procedure, which is in the same state; if CRMServices is confirmed as the source, both are retired together.

## 3. Process Flow Sequence

> **Not available.** The process definition for this interface is not on disk, so no step can be cited. The CRMServices deployment archive lists Start_CRMServices, Reply_GetAccountdataRV, Reply_UpsertContactRV, Subscribe_UpsertAccountWithReferencesJMS, Subscribe_UpsertContactPub and their underscore variants; none is this process.

## 4. Payload Profiles

> **Not available.** The nested object structure the Java constructs lived in the absent process file; no profile can be cited.

## 5. Mapping Documents

> **Not available.** The positional construction of O_COLLECTIONSIMPLE, T_COLLECTIONLISTSIMPLE and O_COLLECTIONCOMPLEX and the VARCHAR OUT capture lived in the Java source inside the absent process file; the mapping cannot be cited.

## 6. Business Logic

> **Not available.** The single-entry collection, placeholder values, swallowed-exception, discarded-result, no-commit and unqualified-type-descriptor rules were read from the absent Java source and cannot be cited.

## 7. Connectors and Adapters

> **Not available.** The JDBC shared resource, the process file containing the inline Java source, the alias library and the README for this interface are absent, so no endpoint, adapter, custom code or configuration value can be cited. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) differs from the 5.8.0.10 recorded in the inventory for this project, confirming a different export.

## 8. Sub-Process Call Hierarchy

> **Not available.** This interface calls no sub-processes.

## 9. Custom Code

> **Not available.** No custom code was found in this interface.

## 10. Error Handling

> **Not available.** The JDBC shared resource, the process file containing the inline Java source, the alias library and the README for this interface are absent, so no endpoint, adapter, custom code or configuration value can be cited. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) differs from the 5.8.0.10 recorded in the inventory for this project, confirming a different export.

## 11. MDS / Shared Artifacts

> **Not available.** No shared artefacts were recorded for this interface.

## 12. External Services

> **Not available.** No external services were recorded for this interface.

## 13. Environment Configuration Matrix

> **Not available.** No environment-specific configuration was recorded.

## 14. Boomi Migration Readiness Summary

This interface cannot be analysed against the source currently in the workspace. The inventory lists it as the Java-based ESB_STUBS.TEST.GETCOMPLEX call in the CallDBProcedure project of the 'JDBC samples' TIBCO BusinessWorks 5.x export, with five source artefacts under legacy/tibco/JDBC samples/CallDBProcedure/. None of those files, and no 'JDBC samples' folder, exists under legacy/tibco/ any more. The only project now in the extracted source is CRMServices, a KPN EAI BusinessWorks 5.x project (Designer 5.5.0.1, repository format 5.2.1) whose deployment archive lists eight processes, none of which is this one.

A detailed analysis of this interface, the most complex in the former inventory, was written on 27 October 2026 while the JDBC samples export was present; it documented the embedded Java that builds nested Oracle object types with ojdbc6.jar, the error-swallowing behaviour, the inactive hard-coded login in the Java source, and the wrapper-versus-Groovy decision. That content survives in the rendered reports under migration/reports/interfaces/calldbprocedure-getcomplex-java/ and in MigrationManifest.md section 9. It cannot be re-cited here because the files it was drawn from are no longer on disk, and citing unrelated CRMServices files in their place would be a fabrication.

If the JDBC samples export is restored to legacy/tibco/JDBC samples/, the earlier analysis becomes valid again and this file should be replaced by it. If CRMServices is the intended source, this interface does not exist in it: the inventory must be regenerated from CRMServices and this interface id retired. The question for the client is recorded in questions.json and is the same question raised for the other six interfaces.

| # | Component | Identifier | Boomi type | Depends on |
| --- | --- | --- | --- | --- |
| 1 | Oracle ESB_STUBS.TEST.GETCOMPLEX Stored Procedure Op | getcomplex-wrapper-sp-db-op | connector-action | oracle-xe-localhost-system-db-conn |
| 2 | GETCOMPLEX Oracle STRUCT Call Fn | getcomplex-oracle-struct-groovy-fn | transform.function | — |
| 3 | CallDBProcedure GETCOMPLEX via Java | calldbprocedure-getcomplex-process | process | getcomplex-oracle-struct-groovy-fn, getcomplex-wrapper-sp-db-op |

## 15. Appendix

- legacy/tibco/CRMServices/vcrepo.dat
- legacy/tibco/CRMServices/.folder
- legacy/tibco/CRMServices/CRMServices.archive

## Open questions

### Still outstanding

REVIEW-NEEDED: The TIBCO export now loaded for this project is CRMServices (a KPN EAI BusinessWorks project), not the 'JDBC samples' export this interface was identified in; which of the two is the integration estate you want migrated to Boomi? (Every analysis artefact for this interface (inventory entry, detail analysis of the Java-based GETCOMPLEX call with nested Oracle object types, the wrapper-versus-script decision and its ten client questions) was produced from the JDBC samples export, which is no longer in the workspace. Until the intended source is confirmed, nothing further can be built or verified for this interface, and the same applies to the other six interfaces in the inventory.)
  - If this is not answered: CRMServices is treated as the intended source: the analysis phase is re-run on it, a new inventory is produced, and this interface id is retired.

