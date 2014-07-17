GIT HOOKS
=========================================================================================================

Generic hooks checking the coding style, specifying the type of commit and syntax checking the commit.



HOW TO USE THEM?
=========================================================================================================
- Copy the Utilities folder inside your repository.
- Run the script SetupGitHooks (make sure it is executable), it pulls the hooks directly from this repository so you dont need to copy them manually.
- You can do your commit as you used to do.



FEATURES
=========================================================================================================

Pre-commit hook: 
- Auto removes trailing whitespaces.
- Uses KWStyle in order to check your coding style (according to the style sheet KWStyle.xml.in that you can edit), prompt errors (which files and which lines do not respect the style).

Prepare-commit-msg hook:
- Modifies the instructions in the commit message: the user has to write a flag in the beginning of his commit message. 
Available flags are as follow:
# BUG: - fix for runtime crash or incorrect result
# COMP: - compiler error or warning fix
# DOC: - documentation change
# ENH: - new functionality
# PERF: - performance improvement
# STYLE: - no logic impact (indentation, comments)
# WIP: - Work In Progress not ready for merge

Commit-msg hook:
- Checks the flag of the commit message (it has to respect the instructions given in the prepare-commit-msg).
- Checks the number of characters (default is 78).

IN PROGRESS
=========================================================================================================

- Automatically pull the KWStyle/uncrustify files so that only the script SetupGitHooks would have to be copied and run to setup everything.
- Script which automatically corrects the style if run (independant of the hooks, so you can still commit if you dont want to follow the style, for instance if the previous commit didnt follow the style either).

