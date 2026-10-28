# CallDBProcedure/CallDBProcedure (Java call of ESB\_STUBS.TEST.GETCOMPLEX with nested Oracle objects)

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

_The inventory's source artefacts (legacy/tibco/JDBC samples/CallDBProcedure/CallDBProcedure.process, JDBC Connection.sharedjdbc, AliasLibrary.aliaslib, README.txt, defaultVars/defaultVars.substvar) are not in the extracted source. legacy/tibco/ contains only the CRMServices project, whose vcrepo.dat identifies it as displayName CRMServices, version 5.2.1. Purpose and systems cannot be cited._

| Field | Value |
| --- | --- |
| Interface | CallDBProcedure/CallDBProcedure (Java call of ESB\_STUBS.TEST.GETCOMPLEX with nested Oracle objects) |
| Type | Scheduled |
| Complexity | complex |
| Components to build | 3 |
| Mapping rules | 0 |
| Business rules | 0 |

## Interface Summary

This interface cannot be analysed against the source currently in the workspace. The inventory lists it as the Java-based ESB\_STUBS.TEST.GETCOMPLEX call in the CallDBProcedure project of the 'JDBC samples' TIBCO BusinessWorks 5.x export, with five source artefacts under legacy/tibco/JDBC samples/CallDBProcedure/. None of those files, and no 'JDBC samples' folder, exists under legacy/tibco/ any more. The only project now in the extracted source is CRMServices, a KPN EAI BusinessWorks 5.x project (Designer 5.5.0.1, repository format 5.2.1) whose deployment archive lists eight processes, none of which is this one.  A detailed analysis of this interface, the most complex in the former inventory, was written on 27 October 2026 while the JDBC samples export was present; it documented the embedded Java that builds nested Oracle object types with ojdbc6.jar, the error-swallowing behaviour, the inactive hard-coded login in the Java source, and the wrapper-versus-Groovy decision. That content survives in the rendered reports under migration/reports/interfaces/calldbprocedure-getcomplex-java/ and in MigrationManifest.md section 9. It cannot be re-cited here because the files it was drawn from are no longer on disk, and citing unrelated CRMServices files in their place would be a fabrication.  If the JDBC samples export is restored to legacy/tibco/JDBC samples/, the earlier analysis becomes valid again and this file should be replaced by it. If CRMServices is the intended source, this interface does not exist in it: the inventory must be regenerated from CRMServices and this interface id retired. The question for the client is recorded in questions.json and is the same question raised for the other six interfaces.

**Complexity:** complex (score 85)

## Functional Analysis

_The process definition for this interface is not on disk, so no step can be cited. The CRMServices deployment archive lists Start\_CRMServices, Reply\_GetAccountdataRV, Reply\_UpsertContactRV, Subscribe\_UpsertAccountWithReferencesJMS, Subscribe\_UpsertContactPub and their underscore variants; none is this process._

## Technical Analysis

_The JDBC shared resource, the process file containing the inline Java source, the alias library and the README for this interface are absent, so no endpoint, adapter, custom code or configuration value can be cited. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) differs from the 5.8.0.10 recorded in the inventory for this project, confirming a different export._

## Mappings

_The positional construction of O\_COLLECTIONSIMPLE, T\_COLLECTIONLISTSIMPLE and O\_COLLECTIONCOMPLEX and the VARCHAR OUT capture lived in the Java source inside the absent process file; the mapping cannot be cited._

## Business Rules

_The single-entry collection, placeholder values, swallowed-exception, discarded-result, no-commit and unqualified-type-descriptor rules were read from the absent Java source and cannot be cited._

## Flow Diagram

_The process definition is absent; a flow graph would have to be reproduced from memory of the former export and could not be cited. Decision blocked: whether this interface exists at all in the intended source._

## Data Model

_The nested object structure the Java constructs lived in the absent process file; no profile can be cited._

## Architecture

_Legacy and target architecture cannot be cited. This interface depends on the shared Oracle connection owned by getobjectsfromdb-get-procedure, which is in the same state; if CRMServices is confirmed as the source, both are retired together._

## Client questions

- **Q-001** The TIBCO export now loaded for this project is CRMServices (a KPN EAI BusinessWorks project), not the 'JDBC samples' export this interface was identified in; which of the two is the integration estate you want migrated to Boomi?
  **If this is not answered:** CRMServices is treated as the intended source: the analysis phase is re-run on it, a new inventory is produced, and this interface id is retired.
