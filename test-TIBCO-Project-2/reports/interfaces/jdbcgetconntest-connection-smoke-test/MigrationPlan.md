# Migration Plan — JDBCGetConnTest/BusinessProcesses/GetConnTestProcess (connection metadata test)

**Project:** Test-TIBCO-Project-2  
**Source platform:** TIBCO  
**Generated:** 2026-10-28T12:32:54.163Z  
**Status:** DRAFT — assembled from the analysis. Nothing has been built in Boomi from this document.

## 1. Interface Metadata

| Attribute | Value |
| --- | --- |
| Interface | JDBCGetConnTest/BusinessProcesses/GetConnTestProcess (connection metadata test) |
| Identifier | jdbcgetconntest-connection-smoke-test |
| Trigger | Scheduled |
| Starts with | No inbound data |
| Complexity | complex (30) |
| Components to build | 3 |
| Source artefacts | legacy/tibco/JDBC samples/JDBCGetConnTest.zip |
| Depends on | Nothing |

## 2. End-to-End Process Architecture

> **Not available.** Legacy and target architecture cannot be cited. The earlier recommendation (drop the interface; a Boomi connection test replaces it) is preserved in migration/reports/interfaces/jdbcgetconntest-connection-smoke-test/ and holds under either outcome.

## 3. Process Flow Sequence

> **Not available.** The process definition (GetConnTestProcess.process inside the absent zip) cannot be cited. The CRMServices deployment archive lists Start_CRMServices, Reply_GetAccountdataRV, Reply_UpsertContactRV, Subscribe_UpsertAccountWithReferencesJMS, Subscribe_UpsertContactPub and their underscore variants; none is this process.

## 4. Payload Profiles

> **Not available.** No profile can be cited. (The earlier analysis recorded no data profile for this interface in any case.)

## 5. Mapping Documents

> **Not available.** The only bindings (a connection object reference into Java and a constant log message) lived in the absent zip and cannot be cited.

## 6. Business Logic

> **Not available.** No source file exists from which a rule could be cited. (The earlier analysis recorded none for this interface.)

## 7. Connectors and Adapters

> **Not available.** The JDBC shared resource and the Java Code activity source inside the absent zip cannot be cited, so no endpoint, adapter, custom code or configuration value can be recorded. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) differs from the 5.8.0 repository version the zip's vcrepo.dat carried, confirming a different export.

## 8. Sub-Process Call Hierarchy

> **Not available.** This interface calls no sub-processes.

## 9. Custom Code

> **Not available.** No custom code was found in this interface.

## 10. Error Handling

> **Not available.** The JDBC shared resource and the Java Code activity source inside the absent zip cannot be cited, so no endpoint, adapter, custom code or configuration value can be recorded. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) differs from the 5.8.0 repository version the zip's vcrepo.dat carried, confirming a different export.

## 11. MDS / Shared Artifacts

> **Not available.** No shared artefacts were recorded for this interface.

## 12. External Services

> **Not available.** No external services were recorded for this interface.

## 13. Environment Configuration Matrix

> **Not available.** No environment-specific configuration was recorded.

## 14. Boomi Migration Readiness Summary

This interface cannot be analysed against the source currently in the workspace. The inventory lists it as the connection-metadata smoke test in the JDBCGetConnTest project, which existed only as the archive legacy/tibco/JDBC samples/JDBCGetConnTest.zip inside the 'JDBC samples' TIBCO BusinessWorks 5.x export. That zip, and the whole 'JDBC samples' folder, no longer exist under legacy/tibco/. The only project now in the extracted source is CRMServices, a KPN EAI BusinessWorks 5.x project (Designer 5.5.0.1, repository format 5.2.1) whose deployment archive lists eight processes, none of which is this one.

A detailed analysis of this interface was written on 27 October 2026 while the zip was present; it recommended dropping the interface because it was a developer's connectivity test with embedded Java that has no Boomi equivalent. That content survives in the rendered reports under migration/reports/interfaces/jdbcgetconntest-connection-smoke-test/ and in MigrationManifest.md section 6. It cannot be re-cited here because the zip is no longer on disk, and citing unrelated CRMServices files in its place would be a fabrication.

If the JDBC samples export is restored, the earlier analysis becomes valid again and this file should be replaced by it. If CRMServices is the intended source, this interface does not exist in it and the inventory must be regenerated. In either case the earlier recommendation to drop this interface stands. The question for the client is recorded in questions.json.

| # | Component | Identifier | Boomi type | Depends on |
| --- | --- | --- | --- | --- |
| 1 | Oracle ORCL localhost DB Conn | oracle-orcl-scott-db-conn | connector-settings | — |
| 2 | Connection Metadata Log Fn | getconntest-metadata-groovy-fn | transform.function | — |
| 3 | [TEST] JDBC Get Connection Smoke Test | getconntest-process | process | oracle-orcl-scott-db-conn, getconntest-metadata-groovy-fn |

## 15. Appendix

- legacy/tibco/CRMServices/vcrepo.dat
- legacy/tibco/CRMServices/.folder
- legacy/tibco/CRMServices/CRMServices.archive

## Open questions

### Still outstanding

REVIEW-NEEDED: The TIBCO export now loaded for this project is CRMServices (a KPN EAI BusinessWorks project), not the 'JDBC samples' export this interface was identified in; which of the two is the integration estate you want migrated to Boomi? (Every analysis artefact for this interface was produced from the JDBC samples export, which is no longer in the workspace. Until the intended source is confirmed, nothing further can be verified for this interface, and the same applies to the other six interfaces in the inventory. Note that the earlier analysis already recommended dropping this interface as a developer connectivity test, so its disposition is the same under either answer.)
  - If this is not answered: CRMServices is treated as the intended source: the analysis phase is re-run on it, a new inventory is produced, and this interface id is retired.

