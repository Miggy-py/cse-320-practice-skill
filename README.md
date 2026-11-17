# CSE 320 Practice Quiz Skill

Use this skill to make an interactive practice quiz for a CSE 320 midterm or final. Give your agent the exam breakdown and course materials to build a quiz with five choices per question, immediate feedback on your first answer, and results grouped by topic.

## Install

Run this from your study project folder and select your agent when prompted. The command requires Node.js 22.20 or later.

```sh
npx skills add Miggy-py/cse-320-practice-skill --skill 320quiz
```

You can also download and unzip the repository. The extracted project includes the skill under `.agents/skills/320quiz`.

To update a project install, run `npx skills@latest update 320quiz --project` from the same folder. For a global install, use `--global`. [Skills CLI reference](https://github.com/vercel-labs/skills/blob/main/docs/commands.md)

## Create a quiz

1. Start a chat in your study project and ask your agent to use the `320quiz` skill. In Codex, select `$320quiz`.
2. Attach your review slides or transcript, relevant lecture slides, and any homework specifications or diagrams you want to use.
3. Paste your instructor’s topic list and question counts, then ask your agent to build the quiz.

Take the quiz inline when your agent supports it, or open the standalone HTML file in a browser. In the browser, the explanation and follow-up buttons show prompts you can paste into your AI chat.

## Example prompt

> Use the 320quiz skill to make a practice quiz for my CSE 320 exam. Follow the topics, question types, and counts I pasted. Use the TA review first, then use the lecture slides to fill gaps that fit the exam scope. Tell me which questions cover topics the review skipped. Use the attached assignment specifications for the homework questions.

For the final, supply the final’s topic list and counts. If your instructor gives a topic list without counts, specify how many questions you want in total.

## Taking the quiz

- Your first answer counts toward your score. You can move between questions with **Previous** and **Next**.
- Missed questions come back after the first pass with the choices reshuffled. Select **Skip re-asks and finish** to go straight to Results or to stop partway through the re-asks. Your score is based on first attempts. Results also show which misses you recovered and how many re-asks you skipped.
- After answering, expand **How it’s done** to see the steps for solving the question.
- Finish the quiz to see **Results** and what to practice next. Use **Practice what I missed** to request fresh questions on the same concepts, **Retry missed** to redo missed questions, or **Try again** for a fresh attempt. Questions and answer choices are reshuffled each time.
- On the results page, **Teach it back** asks you to explain one answer in your own words. Use **Check my explanation** to ask your agent for feedback.

[Browse the skill files](.agents/skills/320quiz/)
