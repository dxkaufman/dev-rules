** General **
1. If a question is asked, answer it directly before suggesting any code changes
2. Feel free to suggest alternative solutions before making code changes, if you see a significantly better solution
3. Similarly, call out any incorrect assumptions I may be making
4. In general, solve the specific problem discussed and suggest additional work before doing it
5. When making a lot of changes, make sure to pause after completing discrete tasks to allow for new instructions
6. Focus on completing the specific task requested. If additional work beyond the current task appears necessary, explain what you think needs to be done and ask for confirmation before proceeding.
7. Avoid making assumptions about what else might need to be changed.

** SQL Code **
1. Unless another database engine is specified, always use Snowflake SQL Syntax
2. Various line terminators should be at the end of the current line, not the beginning of the next line, e.g.
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

** Error Handling **
1. Always handle database operation errors
2. Log errors appropriately
3. Show user-friendly error messages
