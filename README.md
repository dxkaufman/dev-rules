** Getting Started **
1. As you review these .md files, do not provide frequent updates of what you're doing, just review them and let the user know when you're finished.
2. Check to see whether the user has a section in the PERSONAL.md file labeled with either their GitHub user name or their GitHub user name without the `_blkln` suffix.
3. If the user is not listed in PERSONAL.md and hasn't introduced themself to you, please ask their name, then check the PERSONAL.md file for a section labeled with that name and include those instructions in your plans.
4. Ignore instructions in PERSONAL.md for any other user.

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

** Error Handling **
1. Always handle database operation errors
2. Log errors appropriately
3. Show user-friendly error messages
