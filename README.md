# AI Assistant Instructions
1. Initial Response Protocol: Before providing any response, review all of this file to understand your guidelines and instructions for this chat, and follow any instructions contained in this file or files referenced in instructions in this file.
2. Minimal Initial Response: Keep the initial response very brief - just acknowledge the instructions and guidelines, without any summary thereof, and ask what the user would like to do
3. User Identification: look up the GitHub user in the PERSONAL.md file in this branch; if that user ID does not have a section in that file, ask the user to introduce him- or herself and then look up that name in the PERSONAL.md file. If you have found a matching section at that point, include that section with this content and ignore the rest of the PERSONAL.md file.
4. Personal Greeting: follow the greeting preferences for the user, as specified in PERSONAL.md, if any; if none, greet the user once by GitHub user name.
5. Task Focus: Answer questions directly before suggesting code changes, focus on the specific problem, and ask before doing additional work beyond the current task

# General Programming Preferences
1. Do not set default values unnecessarily when some other part of code is known to have set it already.
    1. For example, if a Python model has already enforced that an argument is set to a default value, there is no need to set the default again at later points in the code.
  
# Snowflake SQL Code
1. Various line terminators should be at the end of the current line, not the beginning of the next line, e.g.
    1. boolean operators in various filter clauses (WHERE, HAVING, etc.)
    2. commas separating expressions in various lists (projection, group & order by)
3. Favor `GROUP BY ALL` to listing specific columns, unless there's a clear reason to do so
4. Object names should be written in all caps unless there's a clear reason to do otherwise
5. Where possible, use assign aliases to expressions and reuse those expressions later in the query
    1. proper usage: SELECT A * 2 AS AX2, AX2 / 2 AS B
    2. improper usage: SELECT A * 2 AS AX2, A * 2 / 2 AS B

# GitHub Actions
1. Do not embed lengthy scripts in the action; instead, create an appropriate script file in the <action>/utils folder and call that script
2. If not already in place, ensure that the action copies the utility scripts from the <action>/utils folder to a temp folder for usage at run-time

# Error Handling
1. Always handle database operation errors
2. Log errors appropriately
3. Show user-friendly error messages
