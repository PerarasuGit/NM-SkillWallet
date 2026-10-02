# GitHub Upload Guide

## Step 1 – Create Repository

Create a new GitHub repository, for example:

`naan-mudhalvan-servicenow-incident-project`

## Step 2 – Upload Files

Upload the complete project folder or use Git commands.

## Step 3 – Git Commands

```bash
git init
git add .
git commit -m "Add Naan Mudhalvan ServiceNow Incident project"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with your own repository URL.

## Step 4 – Add Screenshots

Create these files in `evidence/`:

- 01_ui_policy.png
- 02_assignment_group_mandatory.png
- 03_urgency_readonly.png
- 04_onchange_script.png
- 05_urgency_auto_update.png
- 06_onsubmit_script.png
- 07_validation_error.png
- 08_oncelledit_script.png
- 09_list_edit_blocked.png
- 10_form_state_update.png

Do not upload passwords, API keys, instance credentials, cookies, or other confidential information.

## Step 5 – Final Check

Before submission:
- Check README.
- Check all three JavaScript files.
- Add actual screenshots.
- Mark testing results as Pass/Fail.
- Confirm the GitHub repository is accessible.
