# CallDBProcedure/Process Definition (DUAL connectivity query)

Test-TIBCO-Project-2 · Scheduled · simple complexity

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

_The inventory's source artefacts (legacy/tibco/JDBC samples/CallDBProcedure/Process Definition.process, JDBC-Connection-1.sharedjdbc, defaultVars/defaultVars.substvar) are not in the extracted source. legacy/tibco/ contains only the CRMServices project, whose vcrepo.dat identifies it as displayName CRMServices, version 5.2.1. Purpose and systems cannot be cited._

| Field | Value |
| --- | --- |
| Interface | CallDBProcedure/Process Definition (DUAL connectivity query) |
| Type | Scheduled |
| Complexity | simple |
| Components to build | 4 |
| Mapping rules | 0 |
| Business rules | 0 |

## Interface Summary

This interface cannot be analysed against the source currently in the workspace. The inventory lists it as the DUAL connectivity query in the CallDBProcedure project of the 'JDBC samples' TIBCO BusinessWorks 5.x export, with three source artefacts under legacy/tibco/JDBC samples/CallDBProcedure/. None of those files, and no 'JDBC samples' folder, exists under legacy/tibco/ any more. The only project now in the extracted source is CRMServices, a KPN EAI BusinessWorks 5.x project (Designer 5.5.0.1, repository format 5.2.1) whose deployment archive lists eight processes, none of which is this one.  A detailed analysis of this interface was written on 27 October 2026 while the JDBC samples export was present; its content survives in the rendered reports under migration/reports/interfaces/calldbprocedure-dual-query/ and in MigrationManifest.md section 3. That analysis cannot be re-cited here because the files it was drawn from are no longer on disk, and citing unrelated CRMServices files in their place would be a fabrication.  Two outcomes are possible and they lead to opposite work. If the JDBC samples export is restored to legacy/tibco/JDBC samples/, the earlier analysis becomes valid again and this file should be replaced by it. If CRMServices is the intended source, this interface does not exist in it: the inventory must be regenerated from CRMServices and this interface id retired, together with the Boomi components already generated for it under active-development/. The question for the client is recorded in questions.json.

**Complexity:** simple (score 10)

## Functional Analysis

_The process definition for this interface is not on disk, so no step can be cited. The CRMServices deployment archive lists Start\_CRMServices, Reply\_GetAccountdataRV, Reply\_UpsertContactRV, Subscribe\_UpsertAccountWithReferencesJMS, Subscribe\_UpsertContactPub and their underscore variants; none is this process._

## Technical Analysis

_The JDBC shared resource and process file for this interface are absent, so no endpoint, adapter or configuration value can be cited. The Designer version now in the export (ae.designerapp.version 5.5.0.1 in CRMServices/.folder) also differs from the 5.8.0.10 recorded in the inventory for this project, confirming a different export._

## Mappings

_No source file exists from which a mapping could be cited. (The earlier analysis recorded no mappings for this interface in any case.)_

## Business Rules

_No source file exists from which a business rule could be cited. (The earlier analysis recorded none for this interface.)_

## Flow Diagram

_The process definition is absent; a flow graph would have to be reproduced from memory of the former export and could not be cited. Decision blocked: whether this interface exists at all in the intended source._

## Data Model

_No profile can be cited; the cached result-set schema lived in the absent process file._

## Architecture

_Legacy and target architecture cannot be cited. Boomi components for this interface (connection, two operations, two database profiles, process) were already generated under active-development/ from the former export and should be retired if CRMServices is confirmed as the source._

## Client questions

- **Q-001** The TIBCO export now loaded for this project is CRMServices (a KPN EAI BusinessWorks project), not the 'JDBC samples' export this interface was identified in; which of the two is the integration estate you want migrated to Boomi?
  **If this is not answered:** CRMServices is treated as the intended source: the analysis phase is re-run on it, a new inventory is produced, this interface id is retired, and the Boomi components already generated for it under active-development/ are discarded.
