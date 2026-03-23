## MVP

- Epic: Task Data Model Enhancements
  - Story: Add optional dueDate field to task model
  - Story: Add priority field with values P1, P2, and P3
  - Story: Default priority to P3 on task creation
  - Story: Keep title as a required task field

- Epic: Task Validation Rules
  - Story: Accept dueDate only in YYYY-MM-DD format
  - Story: Ignore invalid dueDate values as absent

- Epic: Date-Based Task Filtering
  - Story: Add All filter tab
  - Story: Add Today filter tab
  - Story: Add Overdue filter tab
  - Story: Show completed tasks in All view
  - Story: Hide completed tasks in Today view
  - Story: Hide completed tasks in Overdue view

- Epic: Local Data Persistence
  - Story: Persist dueDate and priority in local storage
  - Story: Preserve local-only storage behavior

## Post-MVP

- Epic: Overdue Task Visibility
  - Story: Highlight overdue tasks visually

- Epic: Task Sorting Improvements
  - Story: Sort overdue tasks before non-overdue tasks
  - Story: Sort tasks by priority from P1 to P3
  - Story: Sort tasks by due date ascending
  - Story: Place tasks without due dates at the end

- Epic: Priority Visual Indicators
  - Story: Add visual badges for P1, P2, and P3 priorities
  - Story: Apply color coding to priority badges
