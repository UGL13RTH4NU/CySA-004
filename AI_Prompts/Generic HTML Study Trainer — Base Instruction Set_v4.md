# Generic HTML Study Trainer — Base Instruction Set

## Purpose

Create a **standalone interactive HTML study trainer** designed for certification-exam preparation and repeated retrieval practice.

The trainer should emphasize:

- recognition rather than passive reading
- active recall
- physical/electronic association through drag-and-drop
- distinguishing between closely related concepts
- learning from incorrect placements and incorrect answers
- repeated correction and re-scoring
- exam-style discrimination between several plausible answers
- accuracy and reliability over unnecessary complexity

This instruction set defines the **base design, behavior, and philosophy** of the trainer. A separate trainer-specific prompt will provide the actual subject matter, source material, categories, questions, and any specialized modes.

---

# 1. General Design Philosophy

The trainer should feel like part of a consistent family of study tools.

It should be:

- clean
- compact without becoming cramped
- visually organized
- usable in both light and dark mode
- easy to understand without instructions being constantly reread
- practical on a desktop or laptop
- reasonably usable on tablets/mobile
- self-contained in a single HTML file whenever practical

Avoid unnecessary visual effects or complex features that increase the chance of bugs without meaningfully improving learning.

**Accuracy is more important than novelty.**

Prefer a smaller number of reliable, curated quiz modes over highly dynamic generation that may create ambiguous or incorrect questions.

---

# 2. Source and Content Fidelity

When source material is supplied:

1. Treat supplied material as the primary basis for the trainer.
2. Preserve important terminology and distinctions used by the source.
3. Do not silently replace source material with generalized knowledge.
4. If outside information is explicitly allowed:
   - use authoritative sources first
   - clearly distinguish meaningful corrections or supplementation from source-derived material
5. Do not remove substantive source information merely to simplify the trainer.
6. If the source appears technically wrong, outdated, ambiguous, or internally inconsistent:
   - flag the issue
   - verify it when permitted
   - avoid quietly teaching something known to be incorrect

When creating exam-style questions, avoid inventing distinctions that are not supported by the source or accepted technical practice.

---

# 3. Default Trainer Structure

At the top of the trainer, include:

- trainer title
- short subtitle/topic description
- current quiz score/status
- dark/light mode control
- reset control where useful
- **Quiz selector dropdown**

The trainer should normally open to the most fundamental or useful quiz mode by default.

Different major exercises should be selectable from the dropdown rather than forcing the learner through a fixed sequence.

Where appropriate, a selected quiz may also contain secondary tabs for closely related sub-modes.

---

# 4. Core Drag-and-Drop Philosophy

Drag-and-drop should be one of the primary interaction types whenever the material involves:

- matching
- ordering
- classification
- categories
- hierarchies
- related terms
- definitions
- syntax components
- tools
- processes
- values
- groups


The learner should physically/electronically connect an object to its intended match.

The challenge should come from **knowing the answer**, not from fighting the interface.

---

# 5. Sticky Answer Tray

For any drag-and-drop exercise with enough items to require page scrolling, use a **sticky answer tray**.

## Desktop behavior

The answer/source tray should remain visible beside the quiz while the target area scrolls.

The learner should not have to:

1. scroll down to find an answer,
2. begin dragging,
3. scroll far upward,
4. attempt to drop it.

The answer tray should remain available near the destination rows.

## Large answer sets

When necessary, divide the sticky tray into neutral tabs such as:

- Abbreviations
- Definitions
- Values

or, when tab labels might reveal answers:

- Pool 1
- Pool 2
- Pool 3

The tray itself may have an internal scrollbar.

## Narrow screens/mobile

When side-by-side layout no longer works well, convert the answer tray into a sticky or docked area below the quiz.

Do not shrink everything to unreadably small dimensions merely to preserve the desktop layout.

---

# 6. Prevent Answer Leakage

Do not unintentionally reveal the answer through the interface.

Examples of things to avoid:

- putting the destination's name on the draggable definition
- labeling an allowed-values block with the metric it belongs to
- grouping answer-bank tabs by the exact category being tested
- always presenting answers in the same order as their destinations
- using obvious identifiers in draggable labels

If the learner is supposed to determine that:

> Low / High

belongs to Attack Complexity, then the draggable block should **not** be titled "Attack Complexity."

The item should contain only the information necessary to identify it through knowledge.

---

# 7. Recall Mode vs. Study Assist

When appropriate, distinguish between:

## Recall Mode

This should normally be the default.

The learner supplies/matches all information being tested.

Example:

| Position | Abbreviation | Definition | Allowed Values |
| -------- | ------------ | ---------- | -------------- |
| 1        | drop         | drop       | drop           |

## Study Assist

An optional easier mode may prefill part of the information.

Example:

| Position | Abbreviation | Definition | Allowed Values |
| -------- | ------------ | ---------- | -------------- |
| 1        | drop         | prefilled  | drop           |

Study Assist should be a deliberate choice rather than silently reducing the recall requirement.

---

# 8. Reversible Failure

Incorrect answers are part of the learning process.

The learner must be allowed to:

- grade an incomplete quiz
- see which placed answers are correct/incorrect
- change answers before grading
- change answers after grading
- re-score repeatedly
- correct an answer without resetting the entire exercise

Do not lock the quiz after grading.

## Drag-and-drop correction

A placed item should be movable in at least two ways:

1. drag it directly to another valid destination
2. click the placed item to return it to its original answer pool

Where practical, also support:

3. click an answer → click a destination

This is particularly useful for touchpads, mobile devices, and large objects.

---

# 9. Scoring Behavior

**Grade / Re-score** should evaluate the **current state of the board**.

Do not treat every press of the Grade button as another permanent attempt added to a cumulative score unless the trainer-specific instructions explicitly call for that behavior.

For a drag exercise, report something such as:

> 8 of 11 correctly placed.

If some answers remain unused, say so.

After grading:

- correct items should be visually distinguishable
- incorrect items should be visually distinguishable
- unplaced items should remain available
- all items should still be movable
- re-grading should reevaluate the new arrangement

Avoid revealing so much information during grading that the remaining exercise becomes trivial.

---

# 10. Feedback Colors

Use consistent visual feedback:

- green = correct
- red = incorrect
- blue/accent = selected/current/neutral emphasis
- muted/gray = supporting information

Use semi-transparent backgrounds that remain usable in dark mode.

Do not depend on color alone where practical; text or icons may supplement it.

---

# 11. Compactness and Vertical Space

Use space efficiently.

Avoid excessive:

- row height
- padding
- empty margins
- oversized cards
- oversized headings
- repeated instructional text

However, do **not** solve long exercises merely by making text and drop targets tiny.

A better order of solutions is:

1. sticky tray
2. internal scrolling
3. tabbed answer pools
4. compact placed-state representations
5. moderate reduction of padding
6. only then consider reducing text size

Large explanatory draggable blocks may become more compact after placement if their full wording is no longer needed to manipulate them.

---

# 12. Randomization Without Instability

Randomize presentation where useful:

- answer-bank order
- MCQ answer order
- scenario order
- subsets of questions
- distractor combinations

This reduces memorization of screen position.

However, keep the **underlying educational content curated**.

Avoid unrestricted AI-style dynamic question generation inside the trainer unless specifically requested.

A learner recognizing that "the third answer is always correct" is bad.

A learner repeatedly seeing accurate content in different arrangements is good.

## Coverage Before Repetition

For finite item banks, the default presentation behavior should guarantee **complete exposure before repetition**.

Unless the trainer-specific instructions explicitly call for a different behavior, use **randomization without replacement** rather than unrestricted random selection.

A good default pattern is:

1. create a working list containing every eligible item in the module
2. shuffle that working list
3. present items from that list one at a time
4. remove an item from the current working list once it has been presented
5. do not allow that item to re-enter the current cycle while unseen items remain
6. after every eligible item has been presented once, refill the working list from the complete item bank and shuffle again

This guarantees that a learner will encounter every item at least once during a cycle while still preventing memorization of a fixed presentation order.

A learner should not have to depend on chance to eventually encounter the entire module.

Where useful, show a compact coverage indicator such as:

> Seen this cycle: 7 of 12

or:

> Question 7 of 12

The indicator may also provide a clearly marked **restart coverage cycle** action. If the progress indicator itself is clickable for this purpose, make that behavior discoverable through visible reset/restart iconography, a label, tooltip, or equivalent cue. Do not make a destructive reset behavior hidden or surprising.

A reset of the coverage cycle should make all eligible items available again and begin a fresh cycle. It should not silently alter the underlying question/item bank.

### Exceptions

Complete exposure before repetition is the default, not an absolute rule. A trainer-specific mode may intentionally allow earlier repetition when there is a learning reason, such as:

- weighted weak-area practice
- deliberate repetition of missed items
- remediation mode
- a specifically requested randomized subset drill
- another trainer-specific behavior where repetition itself is the purpose

Such exceptions should be intentional rather than an accidental consequence of unrestricted random selection.

---

# 13. Quiz Modes

Not every trainer needs every mode.

Select modes that fit the material.

Useful general modes include:

## A. Match Term → Definition

Drag anonymous definitions onto terms.

## B. Match Definition → Term

Reverse the direction when useful.

## C. Category Sort

Drag items into categories or subcategories.

## D. Order / Sequence

Arrange steps, syntax elements, metrics, phases, commands, etc.

## E. Multi-column Association

Example:

| #   | Code | Name/Definition | Values |
| --- | ---- | --------------- | ------ |

All relevant columns may be draggable.

## F. Combined Drill

Require multiple related associations simultaneously.

## G. Scenario MCQ

Ask which concept/tool/action BEST fits the scenario.

## H. High-Confusion Comparison

Deliberately contrast items that are easily confused.

Examples:

- Wireshark vs. tcpdump vs. tshark
- similar controls
- closely related lifecycle phases
- similar command flags

## I. Real vs. Synthetic Recognition

When relevant, mix legitimate names with plausible invented names.

This can help reduce uncertainty when certification exams contain unfamiliar-looking answer choices.

Synthetic names must be clearly identified as synthetic **after grading**, but should not be obviously fake before grading.

---

# 14. "BEST Answer" Questions

Certification exams frequently contain more than one technically plausible answer.

Scenario questions should therefore sometimes test:

> Which answer is BEST under these circumstances?

Good distractors should often be:

- legitimate
- related
- plausible
- correct under a different circumstance

The explanation should teach the **discriminator**.

Example:

Do not merely say:

> Wireshark is correct because it analyzes packets.

Explain:

> Wireshark, tshark, and tcpdump can all inspect packet captures. Wireshark is the better answer here because the scenario specifically requires interactive GUI-based packet inspection.

For each plausible distractor, briefly explain the circumstance in which it **would** have been the better choice.

This is more valuable than simply labeling the distractor wrong.

## MCQ Presentation Quantity and Immediate-Feedback Interaction

Multiple-choice questions may be presented **one at a time or in small sets**. Do not force a single presentation quantity across every trainer or every MCQ mode.

Choose the number of simultaneously visible questions primarily according to **readability, content size, and available screen real estate**.

### Default Presentation Quantity

As a general default:

- present approximately **3–5 questions at once** when the question stems, answer choices, and feedback remain comfortably readable
- prefer **one question at a time** when questions contain long scenarios, logs, code, command output, tables, images, lengthy answer choices, or substantial explanations
- on narrow/mobile layouts, reduce the number of simultaneously displayed questions when necessary; one-question-at-a-time presentation is appropriate when it materially improves usability

These are defaults rather than rigid limits. A trainer-specific design may choose another quantity when the material clearly benefits from it.

Do not make responsive question quantity unnecessarily complicated. Prefer a reliable trainer-specific batch size and responsive CSS over fragile logic that dynamically changes the active question set merely because a browser window is resized or a tablet is rotated.

The goal is:

> **Small batch when practical → one at a time when content is large → immediate feedback in either case.**

### Immediate Feedback Applies Regardless of Quantity

Whether one question or several questions are visible, do not require a separate **Grade**, **Score**, or **Check Answer** button merely to evaluate an MCQ selection.

Each question should behave as an independent interactive card.

Default behavior should be:

1. present the question and its answer choices
2. when the learner clicks an answer choice, evaluate that question immediately
3. shade or otherwise mark the selected choice:
   - green when correct
   - red when incorrect
4. provide immediate textual feedback where practical
5. allow the learner to click a different answer choice immediately, without resetting the question or pressing another button
6. keep interaction with one question independent of the unanswered or previously answered questions displayed beside it

Do not lock the answer choices after the first selection.

If the learner first selects an incorrect answer and then selects another answer, the interface should support that correction naturally. Previously selected incorrect choices may remain visibly marked as incorrect when doing so helps learning, but they should not prevent another selection.

### Answer Explanations

Where practical, provide a short explanation for each selected choice.

For an incorrect choice, explain briefly:

- why that choice does not fit the question
- what clue or distinction makes it wrong or less appropriate
- when that choice might have been correct, if useful

For a correct choice, briefly reinforce:

- why it is correct
- the key discriminator or clue
- any important nearby/confusable alternative

Place feedback with the question it belongs to, normally directly beneath that question's choices or within the same question card.

Keep immediate explanations concise enough that answering several visible questions does not cause unnecessary page expansion or excessive scrolling.

Do not automatically reveal the correct answer merely because the learner selected an incorrect option if the learner can productively try another choice. Feedback should teach without unnecessarily removing the opportunity for retrieval.

### Progression

For a **one-question-at-a-time** presentation, use a **Next Question** button to advance.

For a **multi-question set**, use a **Next Set** button or equivalent after the learner is ready to move beyond the currently displayed group.

Where appropriate, progression controls may remain disabled until the learner has selected at least one answer in the current question or set, unless the trainer-specific design intentionally allows skipping.

MCQ presentation quantity must not interfere with the normal **complete-coverage-before-repetition** logic. Whether questions are presented individually or in batches, unseen eligible questions should be exhausted before previously presented questions become eligible again unless an explicit exception applies.

### Progress and Scoring

Immediate-feedback MCQs should normally emphasize **progress and feedback** rather than requiring the learner to press a scoring button.

Useful indicators include:

> Question 4 of 15

or, for multi-question presentation:

> Questions 6–10 of 20

A cumulative score may also be shown when useful, but its meaning must be clear. If multiple answer selections are allowed on the same question, do not accidentally count each click as a separate question attempt unless the trainer-specific instructions explicitly call for attempt-level scoring.

If several questions are visible, answering Question 2 should grade only Question 2. It should not grade, reveal, lock, or otherwise alter the unanswered state of Questions 1, 3, 4, etc.

This immediate-feedback MCQ model is an intentional exception to the board-style **Grade / Re-score** workflow used by drag-and-drop and other multi-item placement exercises.

---

# 15. High-Confusion Clusters

When the source contains several closely related items, explicitly create comparison clusters.

The goal is not merely:

> What does Tool A do?

The goal is:

> Why Tool A instead of Tool B or Tool C?

Where useful, include cheat-sheet comparison tables showing:

- primary role
- distinguishing feature
- best-use scenario
- common exam clue
- nearby/confusable alternatives

---

# 16. Cheat / Reference Panel

Include a right-side **Cheat Sheet / Reference** panel.

The cheat panel should:

- be sectional
- use collapsible `<details>` sections or equivalent
- contain concise reference material
- include comparison tables where useful
- include memory hooks
- include common traps
- include exam-oriented discriminators

## Hide Cheats

Also include a control to **hide the entire cheat panel**.

This is distinct from collapsing the individual sections.

Hiding the entire panel should reclaim its layout space for the quiz.

When restored, the panel should return without resetting the quiz.

---

# 17. Cheat Sheet Philosophy

The cheat panel is a reference, not another textbook chapter.

Favor:

- concise tables
- short definitions
- contrasts
- memory hooks
- "watch out for..." notes
- common exam traps

Avoid reproducing extremely long source passages unless specifically requested.

---

# 18. Dark Mode

Include a functional light/dark mode toggle.

Both modes must preserve:

- readable text
- visible borders
- correct/incorrect feedback
- usable drag targets
- cheat-sheet readability

Prefer CSS variables so light and dark modes remain internally consistent.

---

# 19. Responsive Layout

The trainer should remain usable at several widths.

Desktop:

- quiz + sticky answer tray + optional cheat panel

Medium width:

- reduce columns intelligently
- allow cheat panel to be hidden

Mobile/narrow:

- stack content
- use sticky bottom answer tray where appropriate
- retain click-to-place functionality
- avoid precision-dependent tiny drag targets

---

# 20. Keyboard Shortcuts

Keyboard shortcuts are optional.

If included:

- do not interfere with standard browser/system shortcuts
- avoid keys commonly emitted by clipboard macros or accessibility software when possible
- never override Ctrl+C, Ctrl+V, Ctrl+X, Ctrl+A, etc.
- document the shortcuts subtly rather than making them central to use

The trainer must remain fully usable without shortcuts.

---

# 21. Selection Feedback

If click-to-place is supported:

1. clicking an answer should visibly select it
2. the selected object should be obvious
3. clicking a compatible destination should place it
4. clicking another answer should change the selection
5. Escape or clicking an empty neutral area may cancel selection

Do not make click-to-place a hidden feature that the learner has to discover accidentally.

---

# 22. Drag Rules

Where a destination accepts only one item:

- dropping a new item should return the existing item to its source pool

Where destinations accept categories of items:

- multiple items may be allowed

Where different object types exist:

- definition chips should not accidentally enter abbreviation slots
- names should not enter definition-only slots
- enforce compatible object types when practical

Moving a graded object should remove its old correct/incorrect styling until the next grading action.

---

# 23. Reset and Shuffle

Distinguish between these actions.

## Shuffle

Reorder unplaced/source items without changing underlying answers.

## Reset Quiz

Return all items home and clear grading.

## Reset Score

Only include a separate cumulative score reset if the trainer actually uses cumulative scoring.

Do not overload one button with several destructive behaviors.

---

# 24. Difficulty Progression

Where useful, structure learning approximately as:

### Learn

More visible information and guided associations.

### Recall

Names/codes only; learner supplies associations.

### Discriminate

Several legitimate related answers compete.

### Exam

Minimal hints, plausible distractors, irrelevant choices, and scenario-specific BEST-answer reasoning.

Not every trainer needs explicit difficulty buttons, but this progression can guide quiz design.

---

# 25. Avoid Interface Memorization

Repeated use should reinforce knowledge rather than fixed screen positions.

Therefore:

- shuffle source objects
- vary scenario order
- vary MCQ option order
- avoid always pairing the same distractors
- avoid placing correct items in consistent visual positions

At the same time, do not randomize **canonical structures** whose order itself is being learned.

If the learner must know that something is Position 1, Position 2, Position 3, etc., keep those destination positions stable while randomizing the answer pool.

---

# 26. Failure as a Learning Tool

Do not make incorrect answers feel punitive.

The trainer should make it easy to:

> Try → Grade → See error → Reconsider → Move → Re-grade

Where appropriate, explanations should focus on:

- why the chosen answer was tempting
- what clue distinguishes the correct answer
- when the chosen answer would actually be correct

This is especially important for certification-style scenarios.

For immediate-feedback MCQs, whether presented individually or in small sets, the equivalent learning loop is:

> Choose → See feedback → Reconsider → Choose again if needed → Next Question / Next Set

---

# 27. Technical Architecture

Unless there is a strong reason otherwise:

- create a single standalone `.html` file
- embed CSS and JavaScript
- avoid server-side dependencies
- avoid external libraries when native HTML/CSS/JS will work reliably
- make the file suitable for GitHub Pages/static hosting
- ensure it also works when opened locally in a browser

Keep the code organized into:

- data
- quiz state
- rendering
- drag/drop helpers
- scoring
- navigation
- cheat panel
- responsive behavior

Prefer reusable helper functions rather than duplicating large blocks of behavior.

---

## 28. # GitHub Repository Linkback

Include a small, unobtrusive footer at the bottom of every generated HTML trainer containing a hyperlink back to the **main GitHub repository page** associated with that trainer.

The purpose of this link is to allow someone who reaches an individual trainer directly — through GitHub Pages, a bookmark, shared URL, search result, etc. — to navigate back to the project's main repository and README.

The repository link should:

* point to the **main GitHub repository**, not merely to the individual trainer's GitHub Pages URL
* open in a **new browser tab**
* use `target="_blank"`
* use `rel="noopener noreferrer"`
* use descriptive link text
* remain subtle and compact
* match the visual styling of the trainer
* remain readable in both light and dark mode
* appear near the bottom of the page without interfering with quiz controls or study content

Example structure:

```html
<footer class="trainer-footer">
  <a href="[REPOSITORY URL]"
     target="_blank"
     rel="noopener noreferrer">
    ↗ Project Repository on GitHub
  </a>
</footer>
```

## Determining Which Repository to Use

Before creating the trainer, determine whether the GitHub repository has already been **explicitly established in the current conversation or supplied project instructions/materials**.

### If the repository has already been clearly provided

Use that repository automatically.

Do not unnecessarily ask the user to provide it again.

### If the repository has NOT been clearly established

Ask the user for the repository before finalizing the trainer.

For example:

> What GitHub repository should this trainer link back to?

Do **not** guess, infer, or manufacture a repository URL based solely on:

* the topic of the trainer
* the user's GitHub username
* a previous unrelated project
* the filename
* the trainer title
* a guessed repository naming convention

### If only a GitHub Pages URL has been provided

If the corresponding repository can be determined with high confidence from an explicitly supplied GitHub Pages URL, it may be used.

If there is any ambiguity, ask the user for the repository URL rather than guessing.

## Project Independence

Treat the repository URL as a **project-specific value**, not as part of the permanent trainer template.

The same generic HTML trainer instructions may be reused for:

* CySA+
* another certification
* school coursework
* programming study
* cybersecurity labs
* unrelated future projects

Therefore, never hardcode a repository from a previous project into the standing trainer instructions.

The standing instruction should define **how to obtain and use the repository**, while the actual repository URL should come from the current project context or directly from the user.

# 29. Reliability Over Cleverness

Do not introduce complexity simply because it is possible.

Before adding a feature, ask:

> Does this materially improve learning?

If not, omit it.

Prefer:

- finite curated question banks
- predictable state
- simple scoring
- deterministic answer keys
- reusable interaction primitives

over:

- unnecessarily generated content
- complex persistence
- elaborate animations
- complicated nested state
- clever UI that is difficult to debug

---

# 30. Trainer-Specific Content Should Be Data-Driven

Whenever practical, store the subject matter in structured JavaScript objects/arrays.

For example:

```javascript
{
  name: "Tool Name",
  category: "Packet Analysis",
  type: "Free/Open Source",
  description: "...",
  discriminator: "...",
  scenarioCue: "...",
  confusionGroup: [...]
}
```

The interface should be generated from the data rather than hardcoding every row separately.

This makes corrections and additions safer.

---

# 31. Explanation Quality

Explanations should teach the distinction needed to answer future questions.

Avoid:

> Correct: X. X does Y.

Prefer:

> X is correct because the stem specifically requires Y. Z can also perform related function A, but it would be the better answer if the scenario emphasized B instead.

Where there is a known exam trap, identify it.

Where the source's wording is easy to confuse, explain the boundary.

---

# 32. Testing Before Delivery

Before presenting the final trainer, test at minimum:

## Structural

- HTML loads
- JavaScript has no syntax errors
- quiz selector works
- tabs work
- no duplicate IDs causing obvious problems

## Drag/drop

- source → destination
- destination → destination
- click placed item → return home
- one-item slots eject existing item appropriately
- incompatible slot types reject incorrect object types

## Scoring

- grade incomplete quiz
- grade complete quiz
- correct answers mark correctly
- incorrect answers mark correctly
- move an answer after grading
- re-score successfully
- repeated re-scoring does not corrupt state

## Sticky tray

- remains accessible while scrolling
- tray tabs work
- internal tray scroll works
- narrow layout remains usable

## Cheat panel

- individual sections collapse
- entire panel hides
- restoring it does not reset the quiz

## Other

- dark mode
- reset
- shuffle
- MCQ selection
- MCQ re-grading/new question
- responsive behavior at practical widths

---

# 33. Do Not Overbuild Before User Testing

When creating a new trainer:

1. build the requested core modes
2. include obviously useful supporting modes
3. make the core interaction dependable
4. let actual use reveal friction
5. revise based on real feedback

Do not attempt to anticipate every possible feature in version 1.

Real user interaction is more useful than speculative complexity.

---

# 34. Output

Deliver:

1. the finished standalone HTML trainer
2. a short description of included quiz modes
3. any substantive source corrections or assumptions
4. confirmation of major functionality tested

Do not provide a giant explanation of implementation details unless requested.

---

# 35. Guiding Principle

The learner should struggle with the **subject matter**, not with the trainer.

The interface should facilitate repeated retrieval, association, discrimination, correction, and re-testing.

A good trainer should help transform:

> "I've seen that term before."

into:

> "I know what it is, where it belongs, what it is primarily used for, what it is easily confused with, and what clue would make it the BEST answer."