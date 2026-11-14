# CSE 320 Practice Quiz Skill

Use this Codex skill to make an interactive practice quiz for a CSE 320 midterm or final. Give Codex your exam breakdown and course materials, and it builds a quiz with five choices per question, immediate feedback on your first answer, and a results overview grouped by topic. You can ask for an explanation after answering.

## Get started

1. On this GitHub page, select **Code → Download ZIP** and unzip it. If you use Git, you can run `git clone https://github.com/Miggy-py/cse-320-practice-skill.git` instead.
2. Open the extracted or cloned folder as a project in Codex. The skill is already in `.agents/skills/` inside that folder.
3. Start a chat in that project. Attach your review slides or transcript, relevant lecture slides, and any homework specifications or diagrams you want to use. Paste your instructor’s topic list and question counts into the chat.
4. Type `$320quiziteration3`, select the skill, and paste a prompt like the one below.

## Example prompt

> Use $320quiziteration3 to make a practice quiz for my CSE 320 exam. Follow the topics, question types, and counts I pasted. Use the TA review first, then use the lecture slides to fill gaps that fit the exam scope. Tell me which questions cover topics the review skipped. Use the attached assignment specifications for the homework questions.

For the final, supply the final’s topic list and counts. If your instructor gives a topic list without counts, tell Codex how many questions you want in total.

## Taking the quiz

- Your first answer counts toward your score. You can move between questions with **Previous** and **Next**.
- After answering, select **Explain this answer** to get help with that question.
- Finish the quiz to see **Results** and what to practice next. Select **Try again** for a fresh attempt.
- If you want to study in a browser, ask Codex for a standalone HTML copy. Its explanation buttons give you a prompt to copy back into Codex.

If the skill doesn’t appear, check that you opened the extracted project folder and then start a new Codex chat in that project. [Codex skill setup docs](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills)

[Browse the skill files](.agents/skills/320quiziteration3/)
