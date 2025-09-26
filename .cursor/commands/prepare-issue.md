## Steps to follow
1. Pick an issue to solve
    1. Check first if there is an issue number in the user's message
    2. If there isn't an issue number, look at all the github issues (using "github prodose" mcp tool), and pick one of the bugs, not the feature requests
    3. **Prioritize by**: severity (critical/blocking first), recency (newer issues), impact (affects more users), and ease of fix
    4. **Skip if**: requires database schema changes, complex architectural decisions, or external dependencies

2. Solve the issue, and make sure you don't break existing functionality (if there is a CI/CD pipeline, tests or linting, use the appropriate command to verify your work)

3. When user gives green light, create a commit with a commitizen message
    - **Format**: `type: short description`
    - **Types**: `fix:` for bugs, `feat:` for features, `refactor:` for code improvements
    - **Include**: What was changed and why, reference the issue number (`Fixes #123`)
    - **Example**: `fix: resolve missing plage_horaire table references\n\n- Updated getPlanningById() function to use planning_events\n- Changed JOIN from plage_horaire to templates_planning_event\n\nFixes #69`

4. Push the changes to the remote server

5. Close the issue using "github prodose" mcp tool
    - **Include**: Clear explanation of what was broken, what you did to fix it, and the result
    - **Format**: You can be a bit verbose, but you need to be informative for future reference
