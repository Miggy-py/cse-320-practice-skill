# CSE 320 Practice Quiz Skill

Use this Codex skill to make an interactive practice quiz for a CSE 320 midterm or final. Give Codex your exam breakdown and course materials, and it builds a quiz with five choices per question, immediate feedback on your first answer, and a results overview grouped by topic. You can ask for an explanation after answering.

## Install in Codex

Run this from your study project folder. The command requires Node.js 22.20 or later.

```sh
npx skills add Miggy-py/cse-320-practice-skill --skill 320quiz -a codex
```

You can also choose **Code → Download ZIP** on GitHub, unzip it, and open the extracted folder in Codex. The downloaded project already contains the skill. [Skills CLI docs](https://github.com/vercel-labs/skills#install-a-skill)

## Create a quiz

1. Start a chat in your Codex project and select `$320quiz`.
2. Attach your review slides or transcript, relevant lecture slides, and any homework specifications or diagrams you want to use.
3. Paste your instructor’s topic list and question counts, then ask Codex to build the quiz using the example below.

## Example prompt

> Use $320quiz to make a practice quiz for my CSE 320 exam. Follow the topics, question types, and counts I pasted. Use the TA review first, then use the lecture slides to fill gaps that fit the exam scope. Tell me which questions cover topics the review skipped. Use the attached assignment specifications for the homework questions.

For the final, supply the final’s topic list and counts. If your instructor gives a topic list without counts, tell Codex how many questions you want in total.

## Taking the quiz

- Your first answer counts toward your score. You can move between questions with **Previous** and **Next**.
- If you miss a question, it comes back a few questions later with the choices reshuffled. Getting it right then doesn't change your score, but the results show which misses you recovered and which you still need to study.
- After answering, select **Explain this answer** to get help with that question.
- Finish the quiz to see **Results** and what to practice next. Select **Practice what I missed** and Codex builds a new quiz with fresh variants of the questions you got wrong, so you practice the skill instead of memorizing the answers. Select **Retry missed** to redo only the questions you got wrong, or **Try again** for a fresh attempt. Questions and answer choices are reshuffled every attempt, so you can't rely on remembering "it was B."
- On the results page, **Teach it back** asks you to explain one answer in your own words. Select **Check my explanation** and Codex tells you whether it's right and, if not, which step is missing.
- If you want to study in a browser, ask Codex for a standalone HTML copy. Its explanation buttons give you a prompt to copy back into Codex.

If the skill doesn’t appear, check that you opened the extracted project folder and then start a new Codex chat in that project. [Codex skill setup docs](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills)

[Browse the skill files](.agents/skills/320quiz/)
