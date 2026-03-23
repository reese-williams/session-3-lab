# Product Requirements Document (PRD) - TODO App Upgrade (MVP + Post-MVP)

## 1. Overview

The TODO app currently supports only a task title and completion status. This upgrade introduces lightweight planning features so users can organize work by urgency while keeping implementation simple and teachable.

The MVP focuses on adding due dates, priorities, and date-based filtering using local storage only. More advanced presentation and ordering behavior is deferred to Post-MVP.

---

## 2. MVP Scope

- Add an optional `dueDate` field to each task.
- `dueDate` must use ISO date format `YYYY-MM-DD`.
- Invalid `dueDate` values must be ignored and treated as absent.
- Add a `priority` field with enum values `P1 | P2 | P3`.
- Default `priority` to `P3` when not provided.
- Keep `title` as a required field.
- Add filter tabs/views: `All`, `Today`, `Overdue`.
- In `All`, show both complete and incomplete tasks.
- In `Today` and `Overdue`, show only incomplete tasks.
- Keep data persistence local only (no backend or external storage changes).

---

## 3. Post-MVP Scope

- Visually highlight overdue tasks so they stand out (e.g., red treatment).
- Add sorting with this precedence: overdue first -> priority (`P1` to `P3`) -> due date ascending -> tasks without due dates last.
- Add visual priority badges/colors (requested in requirements discussion) after MVP scope is complete.

---

## 4. Out of Scope

- Notifications
- Recurring tasks
- Multi-user functionality
- Keyboard navigation/accessibility enhancements beyond current baseline
- External storage integrations
- Backend changes
