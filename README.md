# To-Do List App
 
A minimal, single-file to-do list built with HTML, CSS, and jQuery. Add tasks, mark them complete, and delete them — all in one page, no backend or build step required.
 
## Features
 
- **Add tasks** by typing into the input field and clicking "Add" or pressing Enter.
- **Mark tasks complete** with a green ✓ button, which applies a strikethrough style.
- **Delete tasks** with a red ✕ button.
- **Input validation** — clicking "Add" with an empty input shows an alert instead of adding a blank task.
## Tech Stack
 
| Layer | Technology |
|---|---|
| Structure | HTML5 |
| Styling | Inline `<style>` block (vanilla CSS) |
| Behavior | jQuery 3.7.1 (via CDN) |
 
Everything — markup, styles, and script — lives in a single `index.html` file. No installation or dependencies needed beyond an internet connection to load jQuery from the CDN.
 
## File Structure
 
```
index.html   → everything: markup, embedded <style>, embedded <script>
```
 
## How to Run
 
1. Download `index.html`.
2. Open it in any modern browser (Chrome, Firefox, Edge, Safari).
That's it — no server, no build process.
 
## How to Use
 
1. Type a task into the **Enter Task** field.
2. Click **Add**, or press **Enter**, to add it to the list.
3. Click the green **✓** on a task to toggle it as complete (strikethrough).
4. Click the red **✕** on a task to delete it.
## How It Works
 
- **Adding tasks** — Clicking `#add-btn` (or pressing Enter, which triggers the same click handler) reads and trims the input value, builds a `.task-item` block as an HTML string, and appends it to `.task`.
- **Event delegation** — The complete and delete buttons use `$(document).on("click", ...)` delegation rather than binding directly, so the handlers work correctly on tasks added after the page loads.
- **Completing tasks** — Toggles a `.completed` class (strikethrough + gray text) on the task's text via `toggleClass`, so clicking again un-marks it.
- **Deleting tasks** — Removes the closest `.task-item` ancestor of the clicked delete button from the DOM.
## Known Limitations / Notes
 
- **No persistence** — Tasks live only in the DOM; refreshing the page clears the entire list. (Could be fixed by saving to `localStorage`.)
- **No editing** — There's no way to rename a task once it's added; you'd need to delete it and re-add it.
- **No duplicate checking** — The same task text can be added multiple times with no warning.
- **No task count or filtering** — There's no indicator of how many tasks remain, and no way to filter by complete/incomplete.
## Possible Next Steps
 
Persist tasks with `localStorage` so they survive a page refresh, add an "Edit" button per task, show a remaining-tasks counter, and add filter buttons (All / Active / Completed).
