---
name: 320quiz
description: Create interactive CSE 320 practice quizzes for a midterm, the final, or a cumulative review using the supplied exam scope, review materials, slides, and assignment specifications. Each quiz has five close choices per question, immediate first-choice scoring, explanations on demand, and a grouped results overview.
---

# CSE 320 Practice Quiz

## Choose the material

Use the user's current topic list, counts, and question formats as the exam blueprint. For a final or cumulative review, use the scope supplied for that exam. Use TA review slides and transcripts first, then consult lecture slides for gaps that plausibly fit the posted scope. Treat course materials as sources. Cross-check unclear spoken claims with the worked slides and assignment specifications. When asked to identify extra coverage, list question numbers and distinguish lecture material absent from the review deck from examples the TA skipped live.

Use assignment specifications or READMEs for homework questions about purpose, data representations, invariants, or the intended workflow. Keep locators precise. Base implementation-specific questions on code only when the user supplies or authorizes it and you have inspected it.

## Build the quiz

Start from [assets/quiz.html](assets/quiz.html). Set a title, use a unique root and element ID prefix for the quiz, and replace the sample JSON bank. The bank drives question count and invalidates progress when it changes. Keep exactly five distinct, plausible choices and one unambiguous answer. The template shuffles question order and option order from a per-attempt seed, so write the bank in blueprint order and leave the correct option wherever it is easiest to verify. Use [references/question-bank.md](references/question-bank.md) for the schema, table diagrams, and distractor patterns.

State assumptions needed to calculate an answer or trace code. Use original variants of review problems. For diagram-based questions, transcribe reference values and valid/present bits and specify how to interpret them. State when accesses are independent and when they form a sequence. Verify every key before delivery. Generate explanations and practice advice only on request.

## Preserve the interaction

- Present one question at a time. Mark the first selection immediately, reveal the correct option, and lock the answer for scoring. Keep feedback visible until the user navigates. Previous and Next preserve answers.
- Queue missed questions after the first pass and reshuffle their choices. A question can appear up to twice in the re-ask queue. Once all first attempts are answered, offer **Start re-asks** and **Skip re-asks and finish**. Keep the skip button available until every re-ask is answered. Skipping opens Results with the first-attempt score and any completed re-asks.
- Offer **Explain this answer** after a selection. On click, send the explanation request through a supported chat integration or show the prompt for the learner to paste into their AI chat. Include the full stem, five choices, selected choice, answer key, assumptions, code or diagram, and source. When answering, verify the key and explain the correct answer. If the selected choice was wrong, explain its specific flaw and give one practice step. If it was correct, identify what it gets right and suggest a small challenge. Discuss other choices only if asked.
- When no questions remain, enable **Results** and offer **View overview** at the end. Show **What was correct**, **What was wrong**, and **What to improve**. Base scores and results groups on first attempts. Report how many missed questions were recovered and how many queued re-asks were skipped. Prioritize up to three missed groups. On a perfect attempt, suggest a harder check. When every answer is wrong, report that outcome plainly.
- Keep **Explain my results**, **Practice what I missed**, expandable question details with sources, **Retry missed**, and **Try again**. Both retries reshuffle questions and options. Send actual question contexts for priority groups and request up to three concrete practice steps.
- Keep **Teach it back** on the results page. It asks the learner to explain, in their own words, why the correct answer to the first question of the top missed group is right (or of the top correct group on a perfect attempt). **Check my explanation** sends their text with the question context. When answering, verify the key, then say in one line whether the explanation is correct, incomplete, or wrong; if not correct, name the single missing step and ask one leading question. Do not restate the full solution.

## Build the next quiz from results

The widget reports `correct`, `missedTopics`, `correctTopics`, `reasks`, `recovered`, and `skippedReasks` in its model content, and **Practice what I missed** sends the full missed-question contexts. When the learner asks for another quiz, or that button fires, use these rather than starting from the blueprint alone:

- Weight the new bank toward the missed groups, prioritizing concepts the learner has yet to recover. Keep a few questions from groups answered correctly so the learner still has to switch between skills.
- Write near-transfer variants, not repeats. Keep the skill, change the numbers, addresses, code values, or event ordering, and do not reuse stems or answer texts. Tell the learner which original question each variant practices.
- Keep the same template, five close choices, and verification steps. If the learner has no misses, offer a harder check on the strongest groups instead.

## Deliver and verify

- For a Codex inline quiz, use the visualization skill when available and give it the completed fragment. The template uses `window.openai.sendFollowUpMessage` and widget state when those APIs are available. Keep widget state under 16 KiB.
- For other agents or a requested browser copy, use [assets/standalone.html](assets/standalone.html). Set its document title and replace `<!-- QUIZ_FRAGMENT -->` with the completed fragment. Present the resulting `.html` file inline if the host supports standalone HTML previews, or save and link it for the learner to open. The file works offline, shows copyable prompts for AI follow-ups, and saves the attempt locally when browser storage is available. Test it by opening the file in a browser.

Keep `display: flow-root` on the quiz root when changing its ID or styles. This includes the last row's margins in the height measured by the chat and lets the surrounding page handle scrolling over quiz controls. For inline layout changes, check wheel scrolling over a navigation button in the preview iframe after it has resized.

Check all topic counts, five distinct choices, answer indices, source locators, and calculations or traces. In a short interaction pass, check correct and incorrect feedback, first-choice locking, Previous/Next retention, explanation context, Results, Practice what I missed, Teach it back, Retry missed, and Try again. Confirm feedback and explanation context use the displayed letters, not the bank positions. Miss a question on purpose and confirm it returns after the first pass, the score counts only the first attempt, and the review shows both outcomes. Verify that skipping also opens Results and preserves completed answers. Inspect a regular and narrow layout for each code or diagram format used. Use a sample attempt or injected progress for overview edge cases.
