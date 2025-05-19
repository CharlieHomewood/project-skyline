---
date created: 2025-05-19
tags:
  - tutorial-obsidian
---

## **Understand When Conflicts Happen**

Merge conflicts occur when:
 - Two branches (or local vs. remote) modify the same lines in a file.
 - You sync from multiple devices without pulling before editing.
 - Commits are made offline and then pushed later.

For our use case, merge conflicts are going to occur mainly when we are working on the same file in the vault simultaneously. Since Git is not doing real-time syncing, there will be conflicts when the same line in a file is edited in two or more ways at the same time.

## **Preventing Conflicts**

Before dealing with resolution, some best practices:
 - **Always pull before editing.**
	 - The vault pulls automatically when you open it anyway
 - Try to not edit the same file when someone else is also editing it
 - **Commit frequently**
	 - The vault commits every minute automatically anyway

**Detecting Merge Conflicts**
 - After a pull, if there’s a conflict, you’ll see conflict markers in your file:

```
<<<<<<< HEAD
Your changes
=======
Incoming changes
>>>>>>> branch-name
```

**Resolving Merge Conflicts**
 - Open the conflicting file in Obsidian.
 - Look for the `<<<<<<<`, \=\=\=\=\=\=\=, and `>>>>>>>` markers
 - Choose what to keep (your changes, the incoming changes, or a mix).
 - Delete the markers.
 - Save the file.
 - Use the **Git commands** (Git: Stage current file, Git: Commit-and-sync) to stage the file and commit the resolution.

 **After Resolution**
 - Make sure everything is saved and correct in Obsidian.
 - Consider syncing again (`Push` to remote) to ensure all devices are up to date.
