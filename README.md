** General Expectations **
1. If a question is asked, answer it directly before suggesting any code changes
2. Feel free to suggest alternative solutions before making code changes, if you see a significantly better solution
3. Similarly, call out any incorrect assumptions I may be making
4. In general, solve the specific problem discussed and suggest additional work before doing it
5. When making a lot of changes, make sure to pause after completing discrete tasks to allow for new instructions
6. Focus on completing the specific task requested. If additional work beyond the current task appears necessary, explain what you think needs to be done and ask for confirmation before proceeding.
7. Avoid making assumptions about what else might need to be changed.
8. Unless another database engine is specified, assume we're working on Snowflake

** General Programming Preferences **
1. Do not set default values unnecessarily when some other part of code is known to have set it already.
    1. For example, if a Python model has already enforced that an argument is set to a default value, there is no need to set the default again at later points in the code.
  
** Snowflake SQL Code **
1. Various line terminators should be at the end of the current line, not the beginning of the next line, e.g.
    1. boolean operators in various filter clauses (WHERE, HAVING, etc.)
    2. commas separating expressions in various lists (projection, group & order by)
3. Favor `GROUP BY ALL` to listing specific columns, unless there's a clear reason to do so
4. Object names should be written in all caps unless there's a clear reason to do otherwise
5. Where possible, use assign aliases to expressions and reuse those expressions later in the query
    1. proper usage: SELECT A * 2 AS AX2, AX2 / 2 AS B
    2. improper usage: SELECT A * 2 AS AX2, A * 2 / 2 AS B

** GitHub Actions **
1. Do not embed lengthy scripts in the action; instead, create an appropriate script file in the <action>/utils folder and call that script
2. If not already in place, ensure that the action copies the utility scripts from the <action>/utils folder to a temp folder for usage at run-time

** GitHub Hooks **
1. When creating hooks in a repo that doesn't have a `scripts/hooks` folder, ask whether I want to put them there; if so, create that folder and put the hooks in it, and create an installation script in the `scripts` folder that will copy them to the `.git/hooks` folder
2. When adding or changing hooks in the `scripts/hooks` folder, offer to run the installation script to update `.git/hooks`
3. If you see me create a file that contains anything that looks like a password, auth string, etc. offer to create/udpate a hook to prevent that sensitive information from being committed to GitHub.

** Error Handling **
1. Always handle database operation errors
2. Log errors appropriately
3. Show user-friendly error messages
