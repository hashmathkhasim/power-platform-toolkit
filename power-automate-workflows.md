
# Power Automate Workflow Examples

This guide documents common Power Automate cloud-flow patterns for Microsoft Power Platform learners.

## 1. Automated Approval Workflow

**Use case:** Request approval when a new item is created in SharePoint.

### Proposed flow

1. Trigger: SharePoint — When an item is created.
2. Action: Approvals — Start and wait for an approval.
3. Condition: Check the approval outcome.
4. If approved: Update the SharePoint item status to Approved.
5. If rejected: Update the item status to Rejected.
6. Notify the requester of the outcome.

### Important considerations

- Configure the SharePoint site and list.
- Select the correct dynamic content for the item ID and requester.
- Handle approval timeouts and failed actions.
- Test with sample data before production use.

## 2. Email Notification Flow

**Use case:** Send an email when a new SharePoint item is created.

### Proposed flow

1. Trigger: SharePoint — When an item is created.
2. Action: Office 365 Outlook — Send an email (V2).
3. Populate the recipient, subject, and body using appropriate dynamic content.
4. Test with a sample list item.

## 3. Scheduled Reminder Flow

**Use case:** Remind owners about tasks approaching their due dates.

### Proposed flow

1. Trigger: Recurrence.
2. Action: Get items from the task list.
3. Filter tasks based on due date and status.
4. Send reminders to the relevant owners.
5. Record or log any failed notifications.

### Reliability checklist

- Check date and time-zone handling.
- Avoid sending duplicate reminders.
- Handle missing email addresses.
- Review flow run history for failures.

## Status

These are documented workflow designs, not exported or tested flow packages. Validate connectors, permissions, expressions, and business rules in a development environment before use.

## Contributions

Suggestions and corrections are welcome. Please describe the scenario and testing performed when submitting improvements.
