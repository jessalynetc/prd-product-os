# Optional Notion Adapter

Use only when the user asks to read or synchronize a Notion project and the connector is available.

## Read

1. Locate the project record.
2. Read PRD Stage, Build Budget, PRD Gaps, and the complete page.
3. Reconstruct confirmed facts, assumptions, decisions, missing information, gate status, and last meaningful update.
4. Treat Notion as the persistent source of truth; conversation memory is supplementary.

## Write back

After a meaningful interview round or decision:

- update confirmed information and assumptions;
- append or revise decisions and rationale;
- update current stage;
- replace PRD Gaps with the current blocking or next-stage gaps;
- record the next interview question;
- never write inferred information as confirmed without approval.

Do not require workspace-specific database IDs, property IDs, credentials, or URLs in the public skill. Discover schema at runtime. If Notion is unavailable, continue with the local project brief instead of blocking the PRD workflow.

