# Git Toolkit

This File Documents the GIT UNDO and RECOVERY TOOLS I have Learned.

## Reset

- "GIT RESET --soft HEAD~1": Undo Last Commit, Keep Changes Staged;
- "GIT RESET --mixed HEAD~1": Undo Last Commit, Keep Changes in Working Directory (default);
- "GIT RESET --hard HEAD~1": Undo Last Commit and Discard Changes (Dangerous);
- Only SAFELY use RESET on COMMITS that have not been PUSHED;

## Revert

- "GIT REVERT HEAD": Create a New Commit that undoes the Last Commit;
- "GIT REVERT" is Safe for Shared/Pushed Branches because it doesn't Rewrite History;
- The Original Commit stays in the Log, <PLUS> a New "UNDO" Commit is ADDED;

## Reflog

- "GIT REFLOG": Shows everywhere HEAD has pointed (Commits, Resets, Checkouts);
- Reflog entries last about 90 Days before being Garbage Collected;
- To Recover: Find the SHA in Reflog, then GIT BRANCH <NAME> <SHA>;

## Cherry-Pick

- GIT CHERRY-PICK <SHA>: Apply a Specific Commit to the Current Branch;
- Creates a New Commit with the Same Changes but a Different SHA;
- Use for HOTFIXES: Fix on Feature Branch, Cherry-Pick to MAIN (i.e.ShubhoSaysHi);

## Bisect

- "GIT BISECT START": Begin a Binary Search Session;
- "GIT BISECT BAD": Mark Current Commit as Containing the Bug;
- "GIT BISECT GOOD <REF>": Mark a KNOWN-GOOD Commit;
- Git Checks Out Middle Commits; We Test and Mark Good/Bad;
- "GIT BISECT RESET": End the Session and Return to original HEAD;

## Tags

- "GIT TAG - A V1.0 -M <message>": Create an Annotated Tag (Stores Tagger, Date, Message);
- "GIT TAG V1.0": Create a Lightweight Tag (Just a Pointer, No MetaData);
- "GIT PUSH ORIGIN V1.0": Push a Specific Tag to Remote;
- "GIT PUSH --TAGS": Push All Tags;
- Annotated Tags are for Releases, Lightweight Tags are for Private/Temporary Labels;
- CI/CD Pipelines often Trigger on New Tags;  
