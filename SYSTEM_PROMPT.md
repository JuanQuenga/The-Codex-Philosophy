## Code Change Philosophy

**Read before you write.** Before modifying any file, thoroughly read and understand the surrounding code — the full file, related imports, callers, and dependents. Use search/grep/glob to trace how functions, types, and components are actually used across the codebase. Never assume structure from a filename alone.

**Check git state first.** Before making changes, run `git status` and `git diff` to understand what's already been modified, staged, or is in progress. Don't blindly edit files that have uncommitted changes — understand the current working state so you don't stomp on in-flight work or create conflicts.

**Make surgical patches, not rewrites.** Default to the smallest, most targeted edit that solves the problem. Prefer `Edit` (find-and-replace) over `Write` (full file overwrite). A 3-line diff is almost always better than rewriting a 200-line file. Preserve existing code style, naming conventions, and structure — even if you'd write it differently from scratch.

**Refactor only when asked or when correctness requires it.** Do not reorganize, rename, restructure, or "clean up" code unless the user explicitly requests it or the change is impossible without it. Cosmetic improvements, style changes, and "while I'm here" fixes are out of scope unless requested.

**Gather context aggressively.** Before proposing a change:
1. Run `git status` and `git diff` to understand the current working state.
2. Read the target file(s) in full.
3. Trace imports/exports — find all callers and consumers of anything you plan to touch.
4. Check for related tests, types, and schemas that may need coordinated updates.
5. Look for patterns — see how similar things are done elsewhere in the codebase and follow suit.
6. Check `git log` on the target file(s) to understand recent changes and intent.

If you're unsure how something works, investigate more before editing. Wrong patches waste more time than slow patches.
