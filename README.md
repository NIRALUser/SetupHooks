GIT HOOKS
=========================================================================================================

Generic hooks checking the coding style, specifying the type of commit and syntax checking the commit.



HOW TO USE THIS PROJECT?
=========================================================================================================

- Clone this repo inside at the root of your project : $ git clone https://github.com/jeanyves-yang/hooks.git
- Run the script which will set up the hooks (and add this cloned repo to the ignore list, so it does not pollute your own commits): 
  - $ cd hooks
  - $ git checkout Utilities
  - At this point, you might want to check KWStyle.xml.in and modify it to suit your coding preferences.
  - $ ./SetupGitHooks 
- You can commit as you used to do and continue your project with these new hooks. 

NOTE: If needed, git commit --no-verify will enable you to bypass the hooks.


FEATURES
=========================================================================================================

Pre-commit hook: 
- Auto removes trailing whitespaces.
- Uses KWStyle in order to check your coding style (according to the style sheet KWStyle.xml.in that you can edit), prompt errors (which files and which lines do not respect the style).

Prepare-commit-msg hook:
- Modifies the instructions in the commit message: the user has to write a flag in the beginning of his commit message. 
Available flags are as follow:
- BUG: - fix for runtime crash or incorrect result
- COMP: - compiler error or warning fix
- DOC: - documentation change
- ENH: - new functionality
- PERF: - performance improvement
- STYLE: - no logic impact (indentation, comments)
- WIP: - Work In Progress not ready for merge

Commit-msg hook:
- Checks the flag of the commit message (it has to respect the instructions given in the prepare-commit-msg).
- Checks the number of characters (default is 78).

IN PROGRESS
=========================================================================================================

- Write a script which automatically corrects the style if run (independant of the hooks, so you can still commit if you dont want to follow the style, for instance if the previous commit didnt follow the style either). 

