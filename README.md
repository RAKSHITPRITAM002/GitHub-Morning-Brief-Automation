The workflow is designed to run automatically every hour.

Tools and APIs Used

n8n: Workflow automation platform.

GitHub REST API – Search Repositories: Retrieves repositories with more than 1,000 stars.

GitHub REST API – Get Repository README: Retrieves README information for the selected repositories.

Telegram Bot API: Sends the generated report and notifications.

Workflow Steps

Schedule Trigger: Starts the workflow automatically every hour.

HTTP Request – GitHub Search: Fetches GitHub repositories with more than 1,000 stars, sorted by star count.

Code – Select Top 5: Filters, sorts, and selects the five repositories with the highest star counts.

HTTP Request – Get README: Retrieves README information for each selected repository.

Code – Prepare Report: Combines repository details and README links into a readable summary.

IF Condition: Checks whether the top repository has at least 1,0000 stars.

Telegram Notification: Sends the report through Telegram using separate True and False branches.

Conditional Logic

True branch: Runs when the top repository has 1,000 or more stars.

False branch: Runs when the top repository has fewer than 1,000 stars.

Both branches send a Telegram notification.

Error Handling

Error handling is configured for API request failures so that errors can be directed to a notification path. The workflow can notify the user when an API request fails, making it easier to identify and troubleshoot problems.

Output

The Telegram message includes:

The top 5 GitHub repositories.

Repository descriptions.

Star counts.

Links to the repositories.

A link to the top repository's README, when available.

How to Run

Open the n8n workflow.

Ensure the GitHub API requests and Telegram credentials are configured.

Ensure the Telegram bot is accessible.

Activate the workflow to run it automatically every hour, or execute it manually for testing.

Deliverables

Exported n8n workflow JSON file.

Screenshot of the complete workflow.

Screenshot of a successful execution.

Screenshot of the Telegram notification.

Project: GitHub Morning Brief
Task: Task 2 – API Integration and Workflow Automation
