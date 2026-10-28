# Client questions — ExportDBData/WriteResultsetToFile/Process Definition (EKC_NUMSIMREP_ESB_XML to SQL file)

Click the pencil at the top right to edit this file, type each answer **between the two
comment lines** under its question, then choose **Propose changes**. That opens a pull
request we review — you do not need to know git, and nothing you write takes effect until
we have read it.

Leave a question alone if you do not know the answer; blank means still outstanding, not
declined. Type `[not applicable]` on its own line to say a question does not apply.

---
### Q-001 · The TIBCO export now loaded for this project is CRMServices (a KPN EAI BusinessWorks project), not the 'JDBC samples' export this interface was identified in; which of the two is the integration estate you want migrated to Boomi?

**This one blocks the build.** We cannot complete this interface without it.

**Why we are asking:** Every analysis artefact for this interface (inventory entry, detail analysis with its fourteen-column mapping, shared components it owns for the sibling XXCW export) was produced from the JDBC samples export, which is no longer in the workspace. Until the intended source is confirmed, nothing further can be built or verified for this interface, and the same applies to the other six interfaces in the inventory.

**If this is not answered:** CRMServices is treated as the intended source: the analysis phase is re-run on it, a new inventory is produced, and this interface id and the shared components it owns are retired.

**The choices as we understand them:**

- The JDBC samples export (restore it) — Reload the original 60-file export under legacy/tibco/JDBC samples/; the existing inventory and analyses become valid again without rework.
- The CRMServices export (re-analyse) — Run the analysis phase again on CRMServices; the seven current interface ids are retired.
- Both exports are in scope — They must be loaded as separate migration projects; this project cannot hold two unrelated sources at once.

**Answer:**

<!-- answer:Q-001 -->
<!-- /answer:Q-001 -->
