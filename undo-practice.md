# Git Toolkit

This File Documents the GIT UNDO and RECOVERY TOOLS I have Learned.

## Reset

- "GIT RESET --soft HEAD~1": Undo Last Commit, Keep Changes Staged;
- "GIT RESET -- mixed HEAD~1": Undo Last Commit, Keep Changes in Working Directory (default);
- "GIT RESET -- hard HEAD~1": Undo Last Commit and Discard Changes (Dangerous);
- Only use RESET on COMMITS that have not been PUSHED;
