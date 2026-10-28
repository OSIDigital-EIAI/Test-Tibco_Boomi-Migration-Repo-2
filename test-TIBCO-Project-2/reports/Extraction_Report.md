# Test-TIBCO-Project-2

Every interface found in the tibco export, and what the analysis was able to establish about each one.

**7 of 7** interfaces have a full report.

| # | Interface | Type | Complexity | Components |
| --- | --- | --- | --- | --- |
| 1 | [CallDBProcedure/Process Definition (DUAL connectivity query)](interfaces/calldbprocedure-dual-query/Interface_Report.md) | scheduled | simple | 4 |
| 2 | [ExportDBData/WriteResultsetToFile/Process Definition (EKC\_NUMSIMREP\_ESB\_XML to SQL file)](interfaces/exportdbdata-ekc-numsimrep-sqlfile/Interface_Report.md) | scheduled | medium | 7 |
| 3 | [ExportDBData/WriteResultsetToFile/XXCW\_SERVICE\_REQUEST\_RESPONSES (to SQL file)](interfaces/exportdbdata-xxcw-service-request-responses-sqlfile/Interface_Report.md) | scheduled | medium | 4 |
| 4 | [JDBCGetConnTest/BusinessProcesses/GetConnTestProcess (connection metadata test)](interfaces/jdbcgetconntest-connection-smoke-test/Interface_Report.md) | scheduled | complex | 3 |
| 5 | [GetObjectsFromDB/GetObjectFromDB/Starter (call BLA.TEST.GET with O\_COLLECTION)](interfaces/getobjectsfromdb-get-procedure/Interface_Report.md) | scheduled | complex | 3 |
| 6 | [Ziggo\_SqlDateIssue\_BWProject/TestSqlDateIssue (CREATEB2CNUMNETWINV\_1 DATE round-trip)](interfaces/ziggo-sqldate-createb2cnumnetwinv/Interface_Report.md) | scheduled | complex | 3 |
| 7 | [CallDBProcedure/CallDBProcedure (Java call of ESB\_STUBS.TEST.GETCOMPLEX with nested Oracle objects)](interfaces/calldbprocedure-getcomplex-java/Interface_Report.md) | scheduled | complex | 3 |

---

_Interfaces without a report are listed above with the reason. They are not omitted: an interface missing from this list would read as one that does not exist._
