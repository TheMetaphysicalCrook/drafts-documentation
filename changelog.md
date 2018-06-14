---
title: Changelog
---

**Also visit the [News & Updates Topic](https://forums.getdrafts.com/c/news) on the Community for for update notes.**

## 5.2.1

- **New:** [Navigate window](http://getdrafts.com/editor/navigation) (access via down arrow at top right) now also offers navigation to recent drafts. Defaults to displaying recent drafts if current draft does not have any identifiable navigation markers.
- **New:** Sprinkle in more user activity registrations.
- **Fix:** Clean up a couple of crashers with unexpected arguments in scripting methods.
- **Fix:** Avoid deadlock running OneDrive append action with a subfolder path configured.
- **Fix:** If the URL provided to Drafts in an x-success parameter did not already have any parameters, return parameters might not get appended correctly.
- **Fix:** Matching projects in Taskpaper syntax should be less greedy matching : in tasks.
- **Fix:** Resuming dictation after editing while paused could lose edits.
- **Fix:** Spotlight in-app search continuation was not configured properly.
- **Fix:** Better handling of more than one watch connected to an iPhone.
- **Fix:** Request refresh of calendar store data before script methods that read from calendars.
- **Fix:** Crash deleting multiple action log entries.
- **Fix:** Crash requesting product information from App Store in poor network conditions.

## 5.2.0

#### New in 5.2

- **Actions now have an "Assign tags" after success setting.** In addition to moving a draft to the archive or trash, after success can now also assign tags - great for marking or filing away drafts automatically when processing them. For example, set the Tweet action to automatically assign the "tweet" tag when run on a draft and you can later easily filter for tweets. [Details](http://getdrafts.com/actions/advancedsettings)
- **In-draft navigation to jump between key marks in longer drafts**. Accessed via the navigate button (down arrow icon) in the upper right (or ⌘-\ shortcut). Currently navigation supports jumping to headers in a Markdown draft, projects in a Taskpaper draft, and functions and "// #region Name" region comments in Javascript drafts. [Details](http://getdrafts.com/editor/navigation)
- **Scripting additions to support switching workspaces and action groups**:
  - Allows for action setup to load a workspace, and simultaneously switch selected action list and keyboard row.
  - Inquiry about and toggle visibility of drafts and action lists:
      - `app.isDraftListVisible`, `app.showDraftList()`, `app.hideDraftList()`
      - `app.isActionListVisible`, `app.showActionList()`, `app.hideActionList()`
  - Load action groups and apply workspaces in script:
      - `app.loadActionGroup(group)`, `app.loadKeyboardActionGroup(group)`
      - `app.applyWorkspace(workspace)`
  - Also Workspace and ActionGroup objects to allow lookup of groups and workspaces.
  - More details on [scripting reference site](http://reference.getdrafts.com)
- **Additional URL Actions**
  - `/loadActionGroup?name=GROUP-NAME` - loads action group in action list
  - `/loadKeyboardActionGroup?name=GROUP-NAME` - loads action group in extended keyboard.
  - Details in [URL scheme documentation](http://getdrafts.com/urls)
- **"List in Reminders" action step now has a template**. Useful to create one for sending only [[selection]] or passing in values from script or prompt. [Details](http://getdrafts.com/actions/steps/listinreminders)

#### Other Fixes and Changes in 5.2

- **Fix (Watch):** Improvements to communication between Watch and Phone to address some issues with stuck transfers.
- **Fix (Watch):** Watch app auto-capture from complication did not work if app was already running and open to a view other than the main capture view.
- **Fix:** Some tweaks to Taskpaper syntax.
- **Change:** Do not dismiss any presented views when the new draft creation timeout is fired to avoid loosing unsaved work in actions, etc.
- **Fix:** Moving through action list with up-down arrow keys should scroll items into view when necessary.
- **Fix:** URL action step should ignore "Open in Drafts" option if the URL generated is a non-http(s) URL.
- **Fix:** Opening current list options without making changes could result it "current list options" erroneously displayed in list filter.
- **Fix:** "Insert text" action step now plays nicer with other subsequent action steps.
- **Fix:** Address a case where sync could get stalled in odd timing situations where sync was requested more than once quickly.
- **Fix:** [[draft_open_url]] tag was not working.
- **Change:** Work on some general improvements to syntax highlighting to avoid a few glitches in rendering.
- **Change:** Several improvements to Markdown syntax, including highlighting of horizontal rules and indented code blocks.
- **New:** Add keyboard shortcut preview when managing action groups actions.
- **Change:** Some under-the-hood improvements to Action Directory sharing to support additional features on the web site.

## 5.1.0

- **New action steps**
  - `Event` action step returns for creating calendar events with default system card. [Docs and sample action](http://getdrafts.com/actions/steps/event).
  - `Box` action step to create, append, prepend to files in Box.com service. [Docs and Examples](/actions/steps/box)
  - `Open in...` action step to support old-style document interaction export. [Docs and Examples](/actions/steps/openin)
- **Other new bits**
  - Workspaces and tag filters now support "All - Any" mode selection to control whether drafts in the filter should match all the selected tags (and), or any of them (or).  This setting will be saved with Workspaces.
  - Action steps in an action can now be disabled and duplicated (swipe on step in action editing to select). Handy addition for work-in-progress step modifications and testing variants of scripts.
  - Recent action log history (not specific to individual drafts) is now accessible from history button at top of action list.  Makes access to recently performed actions quicker. Great for troubleshooting errors as well.
  - Action log entries can now be deleted (Swipe right).
  - CMD-Return external keyboard shortcut to toggle editor focus.
  - Support traditional table edit mode for better VoiceOver experience.
- **Scripting changes**
  - Better scripting of Calendars and Events, including the ability to read calendar events. Details:
      - `Calendar.default` property which returns the system default calendar for new events.
      - `Calendar.find(title)` method looks up a calendar by name.
      - `Calendar.getAllCalendars();` returns array of all known calendars on the device.
      - `events(startDate, endDate);` method to query the contents of a calendar. Returns an array of `Event` objects. This can be used to import calendar events into a drafts, among other things.
      - `event.edit()` method. Displays a `Event` object in the system event editing card. Allows scripting to create modify the default values for the event (start/end, add alarms, etc.) then display the event for modification/editing and adding to the calendar.
      - More detail in [scripting reference](http://beta-reference.getdrafts.com/)
  - `Box` script object to read and write files to Box.com service. [Docs](http://beta-reference.getdrafts.com/objects/Box.html)
  - `editor.isActive` bool property to determine if editor is currently in edit mode.
- **Other fixes and updates**
  - **Fix:** Restore last selection when opening a draft.
  - **Fix:** Better restore of text selections when undo/redo are used.
  - **Fix:** Improve frequency of updates to app badge.
  - **Fix:** Evernote action setup to use "Text" output not properly encoding some HTML entities.
  - **Fix:** Omit drafts in the trash from queries unless the trash folder is explicitly queried.
  - **Fix:** Various improvements for dynamic text.
  - **Change:** Better error reporting when file imports fail for some reason.
  - **Fix:** Workaround dark theme tinting of the system file import view.
  - **Fix:** Do not allow external keyboard shortcuts to interfere with arrow keys while editing search fields.

## 5.0.5

- **New:** Full access to Twitter API via Twitter object `request` method. Drafts will handle the OAuth, and you can make any valid calls against the Twitter API. [Details on methods in scripting documentation](http://reference.getdrafts.com/objects/Twitter.html). Same actions, like a Tweet Storm example, in the [Twitter integration guide](https://forums.getdrafts.com/t/using-twitter-with-drafts/109).
- **Fix:** Refactor animation to avoid oddball case where the side panels could get stuck when the cursor was in certain positions with certain content in a draft.
- **Fix:** Threading issue scripting twitter updateStatus calls.
- **New:** Inbox/Flagged/Archive/Trash tabs now support drag and drop. Draft drafts from list onto them to move them (or assign flags).

## 5.0.4

- **New:** iMessages app is back and better than ever. With tag filtering, it makes it really easy to use Drafts as a snippet library to insert text into Messages. [More information](/messages)
- **New:** Inbox/Flagged/Archive/Trash tabs in draft list now support drag and drop. Drag drafts from list onto them to move them (or assign flags).
- **New:** "Inbox default swipe action" setting in "..." options of draft list. Allow changing of the default behavior of a full swipe on a draft in the inbox between "Archive" and "Trash". Default is "Archive".
- **New:** External keyboard shortcuts for cancel (cmd-.) and continue (cmd-return) options in HTML Previews.
- **New:** Improvements to drafts selection screen, which is used in iMessages, the Share extension and the `app.selectDraft()` method. Can now be filtered by a tag and archive can be browsed. Sometime down the road it will get better filtering, but this will do for now.
- **New:** Twitter action now logs URL for tweet in action log when successful in the action log. - **New:** `Twitter` script object with `updateStatus(string)` method to post a tweet, returns bool success value. Details in scripting reference. [Details](https://github.com/agiletortoise/drafts-documentation/wiki/Twitter)
- **New:** `editor.deactivate();` script method to resign focus - opposite of existing `editor.activate();` method

- **Change:** Update MultiMarkdown from 6.0 to 6.3.2 to incorporate latest fixes/updates. Includes a few bugs rendering tables w/o opening closing pipe characters and with maintaining indents in code blocks.
- **Change:** Improve margin calculations to better optimize readable line lengths, especially on the big iPads.
- **Change:** Use Safari View Controller in-app to open http links in Link mode.
- **Change:** Improved refresh of processed updates when viewing a draft on Apple Watch.
- **Change:** Improve visibility in Workspaces Today widget.
- **Change:** A few tweaks to Evernote login process to try to fix login for some in China - this may or may not help users seeing these issues, please report back.
- **Change:** Some improvements for migrating actions from Drafts 4.

- **Fix:** `editor.undo()`, `editor.redo()` were not working properly.
- **Fix:** Maintain position of quick access tabs (both Workspace and Action Groups) after selecting new tab.
- **Fix:** Text could go behind keyboard row on iPhone X with external keyboard connected. - **Fix:** Crash accessing App Store with poor network connectivity.
- **Fix:** Clean up a few crashes calling Javascript methods is bad arguments.
- **Fix:** Do not allow edit of name in current list options workspace.
- **Fix:** VoiceOver issues with tag selection and editing.

## 5.0.3

- **New:** Better drag and drop in action list. Actions can now be dragged between groups by switching group tabs, and also dropped on a different group in the group list to move them.
- **Fix:** Automatic theme change would loose cursor position and not update keyboard appearance.
- **Fix:** Rework implementation of "Insert text" to be faster and work better with TextExpander snippets.
- **Fix:** Better updating of app badge when background sync completes or Siri creates draft.
- **Fix:** [[selection]] tag not return correct result when selection was at very end of draft.
- **Fix:** If a query was left in the draft list search field, it would get restored on a cold start of the app, but the not show in the search text in the text box making you wonder where all your drafts went.
- **Fix:** Changes to tags made in scripting might not save if the action had after success setting.
- **Fix:** Share extension might not immediately unlock pro features when subscription is initiated.
- **Fix:** Clear button in recent tag suggestions would not stay in scrollable view.
- **Fix:** Make sure custom template tags generated in an action are cleared when action is finished running.
- **Fix:** Remove some overhead from scripts which manipulate editor selections to prevent some race conditions with the selection when actions are run quickly, repeatedly, like from a keyboard shortcut.
- **Fix:** Case where bad tag filter could get applied to draft list after launching to search from widget.
- **Fix:** Changing syntax highlighting for draft without making any other changes to draft did not save change.
- **Fix:** Add "after success" label in group editing.
- **Fix:** Scripting theme change should require Pro subscription.

## 5.0.2

- Initial public release.
