# Product Requirements Document for Lifely

## ## App Overview
- **Name:** Lifely
- **Tagline:** Finance, habits, and planning—tracked in one calm monthly view.
- **Category:** productivity_utility
- **Visual Style:** Editorial (e.g. Medium, Readwise)

## ## Workflow
User signs in (platform auth) and lands on the last-used tab.
- **Finance:** Add income/expenses in a ledger grid, optionally mark Fixed Payments as paid. Dashboard updates totals and per-category budget usage.
- **Habits:** Define habits and tap cells in a month grid to mark daily completion. Progress bars and trend lines update instantly.
- **Planner:** Browse weeks, add tasks to specific days, update status, and pick a daily mood. Computes weekly productivity %.
- **Reports:** Aggregate summaries across all three modules for any selected month.

## ## Navigation
- **Navigation Pattern:** hybrid

### ### Screens

#### #### FinanceTab (main) 🔒 Requires Authentication
- Spreadsheet-like ledger for income/expense entries.
- Features: quick-add row, inline editable cells, sortable/filterable columns (Date, Amount, Type, Category, Author).
- Header: Shows Current Balance, Total Income, Total Expenses, and category budget usage.
- Section: 'Fixed Payments' list with due dates and paid/unpaid toggle.

#### #### HabitsTab (main) 🔒 Requires Authentication
- Monthly habit grid (rows = habits, columns = days of month).
- Features: tap-to-toggle completion, progress bar vs monthly target, trend line chart of total completions.

#### #### PlannerTab (main) 🔒 Requires Authentication
- Week-organized view (week selector + vertical stack).
- Daily cards: Tasks (with optional Time and Status: Todo/In Progress/Done), 'Daily Mood' emoji selector.
- Summary: Computed 'Weekly Productivity %'.

#### #### MonthlyReports (main) 🔒 Requires Authentication
- Unified report: Finance totals, budget vs actual, Fixed Payments rate, Habit completion totals/streaks, Planner stats, and mood distribution.
- Actions: Lightweight export/copy for sharing.

## ## Potentially Relevant Utility Functions
- **getAuth:** Potential usage: Require login and scope user data per account.
- **getBaseUrl:** Potential usage: Build shareable links for monthly reports.

## ## Device Capabilities
- Access required to: **clipboard**.

## ## Relevant NPM Packages
- **date-fns:** Purpose: Month/week calculations, date formatting, and grid generation.
- **recharts:** Purpose: Line charts for habit trends and report charts.

## ## Resources
- **Design reference:** Spreadsheet-like grid interactions.

## ## Development Considerations
- Follow iOS Human Interface Guidelines for native experience.
- Ensure touch targets are at least 44x44 points.
- Implement iOS navigation gestures (swipe back, pull to refresh).
- Support iOS accessibility features (VoiceOver, Dynamic Type).
