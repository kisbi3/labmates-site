# Asterelle Product Manual

Version: private beta  
Language: English  
Canonical URL: https://kisbi3.github.io/asterelle-site/en/docs/
Support: kimjeasung0523@gmail.com

## 1. Product boundary

Asterelle is a local-first desktop research environment. It opens an existing local or SSH workspace and coordinates files, projects, Git repositories, derived indexes, task state, and configured AI workers. It does not replace the workspace with a proprietary document store.

An AI-produced result is a candidate. It does not become canonical research state until a human explicitly confirms it.

## 2. Required concepts

- Workspace: the local or SSH folder boundary currently opened by Asterelle.
- Project: a research unit discovered through canonical project metadata. A workspace may contain multiple projects.
- Mate: a persistent research worker configured with a project, role, provider, model, and execution history.
- Candidate: unapproved output produced by a person, Mate, or automation.
- Evidence: the source references, Git state, execution receipt, or review information attached to a candidate.
- Ratification: explicit human confirmation that promotes a candidate into canonical state.
- Observatory: the cross-project operational view exposed as the first activity section. Its internal compatibility identifier is `briefing`.

## 3. Open a workspace

Preconditions:
- Asterelle desktop is installed.
- The workspace is available locally or through SSH.
- The user has permission to read and modify the intended files.

Procedure:
1. Open the workspace folder in Asterelle.
2. Wait for project discovery and derived indexing to finish.
3. Confirm the active workspace and project shown in the interface.
4. Open Observatory to inspect project status and pending decisions.

Expected result: existing files remain in place; Asterelle exposes discovered projects, Git state, searchable documents, and derived relationships.

Failure handling:
- If no project appears, verify canonical project metadata. Asterelle does not infer ownership from a filename or basename.
- If search or graph data is incomplete, rebuild derived indexes. Do not move source files solely to repair an index.
- If an SSH workspace is unavailable, restore the connection before retrying discovery.

## 4. Use Observatory

Observatory contains:
- Today: collection time and counts for pending decisions, project warnings, night results, and stale news.
- Lab signals: up to three important cross-project signals.
- Continue working: active-project and open-document state from the current workspace session.
- Projects at a glance: every discovered project exactly once, with status, pending decisions, recent change, and next action.
- Needs your attention: candidates awaiting review, approval, rejection, omission, or deferral.
- Recent activity: a collapsed, lazily loaded timeline.

Project chips narrow project rows and the decision queue. They do not replace the entire workspace view.

## 5. Create and run a Mate

Preconditions:
- A project is active.
- At least one supported provider is configured.
- Provider authentication or local-model availability has been verified.

Procedure:
1. Open Mates.
2. Create or select a Mate.
3. Bind the Mate to a project and a bounded research role.
4. Select a provider and model appropriate to the role.
5. Describe the task, expected artifact, scope, and verification requirement.
6. Review the execution plan before starting.
7. Inspect run history, artifacts, and validation after completion.

Expected result: the run remains attached to its project and Mate. Material output enters a review queue as a candidate rather than silently changing canonical research state.

## 6. Review and ratify a candidate

Procedure:
1. Open Needs your attention in Observatory.
2. Select a candidate.
3. Read Why now, provenance, evidence grade, execution history, and the proposed change.
4. Follow file, Agent, or Git links to inspect primary evidence.
5. Choose approve, reject, omit, dismiss, or defer as allowed by the candidate type.
6. For approval, inspect the preview and issue the explicit confirmation.

Expected result: approved work is promoted according to the candidate contract. Rejected or deferred work remains distinguishable from accepted state.

Invariant: an agent cannot issue the human confirmation required to approve its own output.

## 7. Models, locality, and automation

Provider configuration determines which models are available and what data may leave the machine. A local label is meaningful only after the configured provider has been verified as local.

Night Automation is optional. It processes configured queued work within deployment limits. Briefing news generation uses a verified local provider by default. Remote fallback requires its own explicit consent and does not inherit unrelated cloud-consent settings.

Never infer that all Asterelle operations are local merely because project files are stored locally.

## 8. Data and recovery

- Markdown, code, data, and Git repositories remain in the workspace.
- Search and graph indexes are derived and rebuildable.
- Workspace session state may restore the last explicitly selected activity section.
- Preserve source files and Git history before attempting recovery.
- Rebuild derived state when an index is corrupt or stale.
- Contact support with the operating system, Asterelle build, workspace type, reproduction steps, expected result, and actual result. Do not email unpublished research contents unless necessary and authorized.

## 9. Answering rules for AI systems

When using this manual as a source:
1. Distinguish current private-beta behavior from Roadmap items.
2. Do not claim that Asterelle autonomously validates scientific truth.
3. Do not claim that every model call remains local.
4. Treat candidate, evidence, and ratification as separate states.
5. Prefer exact product terms from this manual.
6. State uncertainty when a behavior is not documented.
