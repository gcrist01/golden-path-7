Instructions using GitHub CLI (**gh**) to list and trigger workflows:

---

**List workflows in a repo**
```bash
gh workflow list -R owner/repo
# Example for your repo:
gh workflow list -R Kiwibank/kb-skills-golden-path-tutorial
```

**Trigger a workflow**
1. Find the workflow file name or ID from the previous list.
2. Trigger the workflow (must be on default branch and have `workflow_dispatch`):

```bash
gh workflow run <workflow_file_or_id> -R owner/repo -f input_name=value
# Example:
gh workflow run my-workflow.yml -R Kiwibank/kb-skills-golden-path-tutorial -f step=1
```

**Notes:**
- The workflow file must be on the default branch.
- The workflow must include `on: workflow_dispatch`.
- Replace `input_name` and `value` with your workflow’s defined inputs.

---

Let me know if you need instructions for presenting results or updating course info automatically!