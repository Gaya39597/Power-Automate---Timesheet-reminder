# Timesheet Reminder Power Automate Flow

## Overview
This Power Automate flow is designed to send weekly reminders for timesheet submission to employees. The flow triggers every Monday at 4 PM, sending an adaptive card to each employee listed in an Excel sheet. The card contains a reminder message and an acknowledgment button. Based on user responses, the flow updates the status in the Excel sheet, sends a success or pending email, and filters out those who have not responded.

## Flow Description

### Trigger:
- **Recurrence**: The flow triggers every Monday at 4:00 PM.

### Actions:
1. **Post Adaptive Card**:
   - An adaptive card with a timesheet reminder message is posted to each employee listed in an Excel sheet.
   - The card includes an acknowledgment button for the employee to submit their status.

2. **Track Acknowledgment**:
   - When the button is clicked, the flow captures the user's response and logs the status (submitted/not submitted) in the Excel sheet.

3. **Condition Logic**:
   - The flow checks if the acknowledgment button was clicked.
   - It records both the **submitted** and **not submitted** status for each employee.

4. **Excel Update**:
   - The flow updates the record in Excel with the latest status.

5. **Filter Array**:
   - A filter array action is used to identify employees who have not responded.

6. **Send Emails**:
   - If there are employees who have not submitted, an email is sent with a list of pending individuals.
   - If all employees have submitted their timesheets, a success email is sent to confirm that all submissions are complete.

## Tools Used:
- **Power Automate**: For automating the flow.
- **Excel**: For storing employee details and timesheet submission status.
- **Adaptive Card**: For posting a reminder with an acknowledgment button.
- **Outlook/Email**: For sending success and pending emails.

## How it Works:
1. The flow automatically triggers on Monday at 4 PM.
2. It posts an adaptive card to each employee, asking for acknowledgment of their timesheet submission.
3. Based on the employee’s response, the flow logs their status in Excel.
4. The flow filters for those who haven't responded and sends appropriate emails to notify pending users or confirm that everyone has submitted their timesheet.

## Requirements:
- An Excel sheet with employee details (name, email, etc.) and submission status.
- Power Automate license for automating the flow and sending emails.
