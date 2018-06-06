---
title: Action Step – List in Reminders
---

{% include back.html title="Action Steps" path="/actions/steps" %}

Create or add reminders to a list in the iOS Reminders app, using each line of the draft as a separate reminder.

#### Examples

- [List in Reminders](http://actions.getdrafts.com/a/1E7)

#### Options

- **List Template**: Name of the Reminders list to use. If not found, it will be created.
- **Note Delimiter**: Separator to distinguish beginning of notes on the line. Any text after this character on each line will be treated as a note, and text before will be used as the title of the task.
- **Template**: Template for the lines to use to create reminder tasks. Default value `[[draft]]` uses the full content of the current draft.

#### Dynamic List Specifiers

In addition to pre-defining a list name for a List in Reminders step, the step will look at the first line of the text of the draft and if it starts with a "#", "!" or "@" character, the text on that line will override the "List" value on the step and be used as the list name.
