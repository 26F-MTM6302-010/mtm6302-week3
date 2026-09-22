# Adopt a Tiny Monster — MTM6302 Week 3

A console-driven follow-along covering DOM selection, traversal, attributes, classes, conditionals, and functions. No installation, internet connection, framework, or server is needed. All portraits are original local SVG assets supplied with this exercise.

## Open the demo

- **Students:** open `starter/index.html` in Chrome and edit `starter/script.js` in VS Code.
- **Instructor:** open `instructor/index.html` to demonstrate the completed version.
- Open Chrome DevTools → Console (Mac: Option–Command–J; Windows: Ctrl–Shift–J).
- Save the script and refresh after edits. Refresh resets all state.
- Use the main page's console context. Commands belong in the console; students do not need a terminal.

Distribute only `starter/` (or the separate student ZIP). Keep `instructor/`, `checkpoints/`, and `TEACHING-GUIDE.md` for your own use. Both page versions share the same HTML, CSS, and assets; only their JavaScript differs.

## Try the completed version

Run these commands one at a time:

```js
renameMonster('Professor Pickles')
feedMonster(15)
feedMonster(40)
playMonster(60)
toggleParty()
resetMonster()
adoptMonster()
```

Use numeric arguments from 0 to 100 for feeding and playing. This beginner demo assumes the documented argument types; input validation is a later extension. There are deliberately no event listeners, loops, arrays of application data, storage, or network requests in the core exercise.

## Checkpoints

Each checkpoint is a complete replacement for `starter/script.js`, not an extra script to load. Copy its contents, replace the whole file, save, and refresh. Asset paths assume the code remains in the starter folder.

1. Document title
2. Selection and text
3. Traversal and collection inspection
4. Attributes and classes
5. Conditional text changes
6. Functions, actions, and synchronized appearance
7. Return values and the complete solution

The first checkpoints are experiments; stage 5 intentionally changes the mood text only. Stage 6 refactors those experiments into a consistent display function. The portraits and text then always agree after an action.
