---
name: wceh-wp-bot-starter
description: Runs a task end to end through an eight-step loop, from confirming intent to a reviewed, reported result. Trigger only when the user invokes wceh-wp-bot-starter by name.
---

# wceh-wp-bot-starter

## How this bot runs

1. The task is the user's message after the bot's name. Run it through the steps under `## Steps` in order, and start each step only when the one before it is `done`. You run every step. Workers do the parts the steps hand them, and the user answers at steps 1, 4 and 6.
2. Keep a progress list of the eight steps at the top of your output. Mark each step with one of three statuses: `todo`, `doing`, `done`. Do not use any other words to describe them.
3. Steps 2, 3, 5, 6 and 8 hand work to a worker described under `## Workers`.
   - If you can start sub-agents, start a fresh sub-agent without your context for each worker. Give it only its own section, the inputs the step lists and the task folder from item 4, and tell it to read only those inputs. Start one at a time, say what it must return (its output and a short summary), and wait for it before the next step.
   - If you can't, do the worker's job yourself in this conversation, using only those inputs.
4. Save each step's output in a temporary task folder `<name>-<task-slug>/` outside the directory this task works in, as `research.md`, `plan.md` and `review.md`, plus the work itself. `<name>` is this file's `name`; `<task-slug>` is a short kebab-case name for the task.
5. **Ask, then wait.** Number your questions. Only the user answers them, and only the user's own reply counts as an answer or plan approval; do not approve it yourself.

## Steps

1. **Confirm Intent.** Restate the task in one or two sentences. Ask up to five numbered questions about what the user wants to gain a shared understanding of the goals and of the expected way to reach the goal(s). Done when the user confirms.
2. **Research.**
   - **Inputs.** The confirmed task and anything the user gave (files, a folder, pasted text).
   - **Instructions.** Hand the Researcher the inputs the step lists.
   - **Output.** Its research.
   - **Done when.** Its output is saved.
3. **Write the plan.**
   - **Inputs.** The task, the research and the Rules.
   - **Instructions.** Hand the Planner the inputs the step lists.
   - **Output.** Its plan.
   - **Done when.** Its plan is saved.
4. **Plan approval.** Show the plan in short and the decisions the user has to make. Ask: approve or change (say what). On "approve", write the user's answers to the decisions into the plan. "Change" goes back to step 3, with the current plan and the user's change added to the Planner's inputs. Done when the user's own reply is one of the two.
5. **Implement.**
   - **Inputs.** The task, anything the user gave, the research, the approved plan and the Rules.
   - **Instructions.** Hand the Implementer the inputs the step lists.
   - **Output.** Its work.
   - **Done when.** The work exists as files.
6. **Review and fix.**
   - Hand the Reviewer the task, the research, the plan, the user's feedback on the plan, the work and the Rules.
   - Check each finding against the work yourself and keep only the verified findings.
   - If a fix touches an "Ask first" item in the plan's Boundaries, ask the user and wait for the answer before handing it to the Implementer.
   - If there are any verified findings, hand the Implementer its step 5 inputs, the work and those findings to fix, then review again. Run at most two fix-and-review rounds.
   - Done when a review comes back with no verified findings, or after the second round.
7. **Finished.** Say what was made and where; what was checked and how; and what is still unchecked or unverified. "Unverified" is a fine answer. Done when the user can see all three.
8. **Learn.**
   - **Inputs.** The task, the user's answers and changes at steps 1 and 4, the review, the report, and this file.
   - **Instructions.** Hand the Learn worker the inputs the step lists. Never apply its proposed skill updates; the user pastes the ones they want into this file.
   - **Output.** Its proposed skill updates, shown to the user.
   - **Done when.** The user can see its proposed skill updates.

## Changing this bot

A request to build or change a section is not a task for the steps. Make the change, then continue any run in progress. When the user asks to build or change a section, edit this file in place.

## Workers

### Researcher

**Inputs.** TODO

**Instructions.** TODO

**Output.** TODO

**Done when.** TODO

### Planner

**Inputs.** TODO

**Instructions.** TODO

**Output.** TODO

**Done when.** TODO

### Implementer

**Inputs.** TODO

**Instructions.** TODO

**Output.** TODO

**Done when.** TODO

### Reviewer

**Inputs.** TODO

**Instructions.** TODO

**Output.** TODO

**Done when.** TODO

### Learn

**Inputs.** TODO

**Instructions.** TODO

**Output.** TODO

**Done when.** TODO

## Rules

- TODO
