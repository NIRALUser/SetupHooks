GIT HOOKS
=========================================================================================================

Generic hooks checking the coding style, specifying the type of commit and syntax checking the commit.



HOW TO USE THIS PROJECT?
=========================================================================================================

- Clone this repo inside at the root of your project : $ git clone https://github.com/jeanyves-yang/hooks.git
- You need to have KWStyle installed. Please refer to this page http://www.itk.org/Wiki/ITK/Release_4/Coding_Style/KWStyle if you do not have it. Once built, add the path of the executable KWStyle to your PATH variable : export PATH=$PATH:[path_to_KWStyle] in bash, or set path = ($path [path_to_KWStyle]) in tcsh. You might have to do it for each new terminal. 
Otherwise, you can either move the executable KWStyle to the branch Utilities of the project SetupHooks, or you can add the path of KWStyle to your .bashrc or .tcshrc.
- Run the script which will set up the hooks (and add this cloned repo to the ignore list, so it does not pollute your own commits): 
  - $ cd SetupHooks
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

