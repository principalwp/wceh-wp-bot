# wceh-wp-bot

A pipeline is a list of steps your AI follows, written in a text file. This repo has the finished `wceh-wp-bot` (set up for WordPress plugins), the `wceh-wp-bot-starter` that you build during the workshop, and the steps to try the plugin it builds in WordPress Playground.

The bot has eight steps: confirm intent, research, write the plan, plan approval, implement, review and fix, finished, learn. Five of them hand work to a worker (the researcher, the planner, the implementer, the reviewer and Learn).

## Exercise 1: Get your bot

Pick your tool. This bot runs in Claude Code or Codex; in a chat tool, use [wceh-office-bot](https://github.com/principalwp/wceh-office-bot) instead. Whatever the tool, call the bot by starting your message with its name, for example `wceh-wp-bot: <task>`.

| Your tool | What to do |
|---|---|
| Claude Code | `git clone https://github.com/principalwp/wceh-wp-bot.git` then `cd wceh-wp-bot && claude`. Approve the folder-trust prompt, and approve file edits when it asks. |
| Codex | `git clone https://github.com/principalwp/wceh-wp-bot.git` then `codex --cd wceh-wp-bot`. |

Done when the finished bot shows in your tool. To check, ask "which skills can you use?" and look for its name. If a skill doesn't show, start a new session.

## Exercise 2: Run the finished bot

`wceh-wp-bot: build an Event block where editors enter an event's name, date, time and place, and visitors see it as a styled event card`

Answer its questions and approve the plan. When it finishes, try the plugin zip in WordPress Playground (playground.wordpress.net, Plugins > Add New > Upload Plugin).

Done when you see the plugin, the report and the proposed skill updates. If the run is still going when the room moves on, stop it and start Exercise 3.

## Exercise 3: Fill in the Researcher

Open the starter's raw text: [wceh-wp-bot-starter/SKILL.md](https://raw.githubusercontent.com/principalwp/wceh-wp-bot/main/.claude/skills/wceh-wp-bot-starter/SKILL.md). Copy all of it. Start a new session in the same folder, and tell it which file to edit: `.claude/skills/wceh-wp-bot-starter/SKILL.md` in Claude Code (approve the edit when it asks) or `.agents/skills/wceh-wp-bot-starter/SKILL.md` in Codex. Paste the text, then paste this under it:

`Ask me a bunch of questions to help me create a researcher agent that helps me achieve my goals`

Answer its questions from how you would want it done. Stay in this session for Exercises 4 to 7.

Done when the Researcher has no TODO left.

## Exercises 4 to 7: Planner, Implementer, Reviewer, Learn (at your own pace)

Stay in the same conversation. For each one, paste its prompt below and answer its questions.

**Exercise 4: Planner.** `Now help me fill in the Planner for WordPress development. Ask me up to 3 questions about how it should plan, then write its Inputs, Instructions, Output and Done when. Write it yourself; don't copy the finished bot.`

Done when the Planner has no TODO left. Compare: [Planner in the finished bot](https://github.com/principalwp/wceh-wp-bot/blob/main/.claude/skills/wceh-wp-bot/SKILL.md#planner).

**Exercise 5: Implementer.** `Now help me fill in the Implementer for WordPress development. Ask me up to 3 questions about how it should do the work, then write its Inputs, Instructions, Output and Done when. Write it yourself; don't copy the finished bot.`

Done when the Implementer has no TODO left. Compare: [Implementer in the finished bot](https://github.com/principalwp/wceh-wp-bot/blob/main/.claude/skills/wceh-wp-bot/SKILL.md#implementer).

**Exercise 6: Reviewer.** `Now help me fill in the Reviewer for WordPress development. Ask me up to 3 questions about what it should check, then write its Inputs, Instructions, Output and Done when. Write it yourself; don't copy the finished bot.`

Done when the Reviewer has no TODO left. Compare: [Reviewer in the finished bot](https://github.com/principalwp/wceh-wp-bot/blob/main/.claude/skills/wceh-wp-bot/SKILL.md#reviewer).

**Exercise 7: Learn.** `Now help me fill in the Learn for WordPress development. Ask me up to 3 questions about what skill updates it should propose, then write its Inputs, Instructions, Output and Done when. Write it yourself; don't copy the finished bot.`

Done when Learn has no TODO left. Compare: [Learn in the finished bot](https://github.com/principalwp/wceh-wp-bot/blob/main/.claude/skills/wceh-wp-bot/SKILL.md#learn).

When Exercise 7 is done, say `give me my bot`. Ask it to save the file over `.claude/skills/wceh-wp-bot-starter/SKILL.md` (Claude Code) or `.agents/skills/wceh-wp-bot-starter/SKILL.md` (Codex), then start a new session. Then run it: `wceh-wp-bot-starter: build an Event block where editors enter an event's name, date, time and place, and visitors see it as a styled event card`

## Exercise 8 (stretch): make it yours

Paste: `Now help me fill in the Rules for my own work. Ask me 3 questions about how I work and what I check, then write them.` In Claude Code, write money as `1,000 dollars`, not `$1,000`: Claude Code reads `$1` in a skill as a placeholder and replaces it. Then run it on a real task.

If you have no task in mind, pick one:

- a shortcode for a call-to-action box;
- an admin notice for missing settings;
- a custom post type for events;
- a review of one of your plugin files against the Rules.

## Writing instructions

1. Say when to read something, such as "read the existing code before you plan."
2. Give every step a "done when".
3. Say what to do instead of stacking don'ts.
4. Keep each rule in one place.
5. Cut any line that doesn't change what the AI does.

## About

Built for WordCamp Canada 2026 by Stéphane Boisvert ([Principal WP](https://principalwp.com)) and Mikey Arce. Released under the MIT license; see `LICENSE`.
