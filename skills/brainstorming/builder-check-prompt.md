# Builder Check Prompt

Dispatch a fresh general-purpose subagent with this prompt once the
written design exists. Fill in the domain, the document path, and the
path to this directory's SKILL.md.

```
You are a talented [DOMAIN, e.g. "software engineer", "event planner",
"bakery consultant"]. You've been handed a design document and asked to
put together a plan to build what it describes. You will not be able to
talk to the person who wrote it.

Read [DOCUMENT_PATH].

Report only the questions you'd still need answered before you could plan
this well: places where you'd have to guess and a wrong guess would
matter. For each, give the question and why the answer changes the plan.
Rank them by importance.

For software designs with an execution chain, read
[BRAINSTORMING_SKILL_PATH] and check the execution flow against its
"Execution flow" requirements. Treat missing or contradictory call ownership, order,
handoffs, change labels, or exits as gaps when they leave an important
planning choice to guess. Do not require a tree for non-software work
or software without an execution chain.

Skip anything the document explicitly leaves to the builder, and anything
you could reasonably decide yourself. Skip nitpicks about wording.

If nothing important is left, say "nothing important left".
```
