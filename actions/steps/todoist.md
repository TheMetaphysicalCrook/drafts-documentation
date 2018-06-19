---
title: Action Step – Todoist
---

{% include back.html title="Action Steps" path="/actions/steps" %}

Add a task to your inbox on the [Todoist](http://todoist.com) task management service. More advanced integration with Todoist is also available via the Todoist script object.

#### Examples

- [Tweet](http://actions.getdrafts.com/a/1E5)

#### Options

- **Template**: Template for the content of the new task.
- **Due String**: Optional human-readable date specifier in a format Todoist understands, like "next Wednesday" or "Tomorrow". If blank, no due date will be assigned to the task.
- **Comment**: Also optional, but if this template generates text, it will be added to the new task as a comment.
- **Identifier**: Arbitrary string identifier for the Todoist credentials to use to use. This value is only needed if you wish to use more than one account with Drafts. If used, all actions with the same identifier will use the same alternate login for Twitter.  The identifier can be any value, but something useful, like the twitter username, is helpful for identifying credentials in settings.
