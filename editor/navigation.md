---
title: Navigating Longer Drafts
---

{% include back.html title="Editor" path="/editor" %}

If you write longer drafts in a structured format like Markdown, Drafts can help navigate to key locations with the navigate view accessed via the down arrow icon near the top right of the screen.

{% include doc-image.html src="/editor/navigate.png" %}

To access the navigator, tap the down arrow icon in the top right - or `⌘-\` on an external keyboard. If any navigation marks are found in your draft, a list will appear with those items. Top an item and the editor will place the cursor in the draft at that position and scroll it into view.

What marks are found depend on the syntax select for the current draft.  The initial implementation finds the following markers:

- **Markdown**: And Markdown headers using the "#" header syntax. Header levels are identified and indented.
- **Taskpaper**: And Taskpaper projects, using the "Project Name:" syntax.
- **Javascript**: Traditional function declarations in the format "function name() {}", and region mark comments in the format "// #region RegionName".

### Quick links

At the bottom of the navigate view, there are also quick links to move to the top or bottom of the text - or to select all text in the editor.
