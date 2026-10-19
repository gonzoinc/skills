# Upstream source and updates

- Collection repository: https://github.com/gonzoinc/skills
- Source repository: https://github.com/mattpocock/skills
- Base revision: `5beb35b040e3de97e54fa9e386d7e42d15c295c2`
- Upstream plugin version: `1.3.1`
- Checked on: October 19, 2026 (America/New_York)
- Observed upstream HEAD: `5beb35b040e3de97e54fa9e386d7e42d15c295c2`
- Relevant newer changes: **none** at this check. No newer changes incorporated.

Only the 22 selected skill directories and required supporting resources were
imported. Setup's `triage-labels.md` was deliberately omitted. No upstream guidance,
marketplace, package scripts, CI, excluded skills, misc or in-progress skills are
part of the plugin.

`upstream-lock.json` records each imported resource's original path and SHA-256.
Hashes refer to the upstream bytes before adaptation, not local content.
The MIT LICENSE was copied unchanged. Inspect the pinned originals using the
commit URL or fetch the revision deliberately into Git object storage.

For a future update:

1. Resolve a specific candidate revision and compare it with the pinned base.
2. Review changes to the selected skills and all resources they reference.
3. Describe relevant newer changes separately before choosing what to incorporate.
4. Reapply only accepted adaptations. Keep renamed references, explicit-only policy,
   support-skill acceptance and existing project boundaries consistent.
5. Reject excluded skills as dependencies; make needed guidance self-contained or
   report a material unresolved dependency. No automatic update or installation.
6. Update the lock and manifest deliberately, validate, and present for review.

Avoid re-running an upstream installer or replacing these independently maintained
files wholesale. The collection version is independent of the upstream version.

`post-mortem` was added as an original gonzoinc skill in collection version
`0.2.0`. It is not part of the 22 upstream imports or `upstream-lock.json`.
Its standalone distribution is https://github.com/gonzoinc/post-mortem.
