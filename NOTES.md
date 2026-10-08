# Patch Notes

## Summary of changes

I focused on four high-value issues across the SQL, backend, and frontend layers.

1. Fixed incorrect search and status filtering caused by SQL AND/OR precedence. I grouped the title and description search conditions so archived and status filters are applied consistently. I also applied the same correction to the Oracle reference SQL.
2. Removed the artificial Thread.sleep delay from the backend because it unnecessarily blocks the request thread and slows API responses.
3. Fixed frontend error handling so the loading state is cleared when an API request fails.
4. Reset pagination when the search or status filter changes so the UI does not remain on a stale page.

## What I chose not to change

I did not perform a larger architectural refactor or make unrelated UI changes because the exercise is time-boxed. I focused on correctness, responsiveness, and user-facing behavior.

## Biggest remaining risk

The application could benefit from more automated tests, especially around combined filtering, pagination, invalid API parameters, and API failure scenarios.

## AI / Tools Used

I used ChatGPT to help inspect the codebase, identify potential bugs, and reason about SQL and frontend behavior. I manually verified the issues, tested the application locally, and made the final implementation decisions myself.