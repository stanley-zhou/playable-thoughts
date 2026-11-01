# Agents vs. Tasks — design notes

How the game got from a one-line thought to its current version, October 2026.

## Starting point

The note that started it:

> LLMs are moving fast and agents can work in parallel. To be efficient, people keep tracking several tasks at once: one agent runs, so you go manage another. The process gets sped up so much that you lose a lot of your own thinking. Your attention is forced apart and you end up like a zombie. Working like this is exhausting.
>
> People's attention is all you need!

The goal was not a game about productivity tips. It was to let people *feel* one thing: thinking only grows where attention stays. So, from the start: no numbers, no scores, as little theory as possible.

Plants vs. Zombies turned out to be the right shape. Plants work on their own in lanes, waves of enemies keep coming, and you spend your time clicking a falling resource. Mapped onto agent work:

| Plants vs. Zombies | Agents vs. Tasks |
|---|---|
| Plants | AI agents (named after real models) |
| Zombies | Tasks, drawn as walking sticky notes |
| Sun | Your attention, the only resource, which nothing can generate for you |
| Your house | Your own thinking |
| "The zombies ate your brains!" | "Cognitive overload ate your brains!" |

## v1: first playable

- Flat cartoon look on an evening lawn. Called *Army of Claudes*.
- Three stages: one lane → five lanes → lanes that keep doubling up to forty.
- A pot on the desk holds **your own thought**. It grows only while you aren't clicking, and grows slower the more things are calling for you.
- Agents stop now and then to ask for a review and do nothing until you click them.
- Ending: the player turns into a zombie, then a calm screen with *Human attention is all you need.*
- Decided against a hidden ending. The story stays linear.

## v2: Agents vs. Tasks

- **Renamed.** Not every agent is a Claude, so *Army of Claudes* had to go. The enemies are named after what agents actually process: tasks.
- **Stages renamed** to *Single agent → Multi-agent → Army of agents*. As the stages go on, you have less and less control: you plant one, then you look after five, then they multiply on their own.
- **Sketchbook style.** Ruled notebook paper as the lawn, the red margin line as the fence, sticky-note tasks, highlighter-yellow attention eyes, taped index cards, lines that gently boil.
- **Color drains** stage by stage. At the end the page is gray and only the sprout keeps its color.
- **One fixed model per lane** in stage 2: Haiku 5.5, Sonnet 5.5, Opus 5.5, GPT-6.1 Sol, Gemini 3.8 Flash. The player plants each one by hand, then the card row becomes a status panel.
- **Models differ in how they ask for your attention**, not in strategy. Haiku asks often, Sonnet is steady, Opus rarely asks, Sol sometimes asks twice in a row, Gemini asks in bursts. Firepower differences are only visual.

## v3: the ending, and difficulty

- **The last line is written slowly by a pencil**, with a pause after each word and the longest after "attention". The pencil only writes while you're still. Move or click and it lifts, then waits about a second. Nothing tells you this.
- **"Multitasking ate your brains!" became "Cognitive overload ate your brains!"** Multitasking itself isn't the problem. Too much of it is.
- **Big waves**, marked by flags on the progress bar: *A big wave of tasks is coming!*
- **Pressure climbs within each stage.** Stage 1 starts calm and tightens near the end. Stage 2 keeps climbing.
- **Credit to Plants vs. Zombies** in the footnote.
- Difficulty tuned with simulated players at different reaction speeds. Average tasks slipped per run, 8 runs each:

| Stage | Fast | Average | Slow |
|---|---|---|---|
| Single agent | 0 | ~1 | ~1 |
| Multi-agent | ~1 | ~3 | ~14 |

## v4: tasks stuck in your head

- **Playtesting said v3 was too hard.** Simulated players click faster than people do. Stage 2 got about 25% fewer tasks, slower tasks and smaller waves.

| Stage | Fast | Average | Slow |
|---|---|---|---|
| Single agent | 0 | 0 | ~0.3 |
| Multi-agent | ~0.3 | ~1 | ~4.5 |

- **Tasks that slip through no longer pile up on the desk. They get stuck in your head.** A sticky note flies to the avatar's head and circles there. You didn't solve it and you had no time for it, so it's shelved, and it stays with you until the stage ends.
  - Every note in your head slows the thought in the pot. Unfinished work keeps taking part of your attention even when you stop clicking. This is attention residue, but the game never says so.
  - Notes also push the avatar toward zombie.
  - In the last stage the head gets buried, which makes "Cognitive overload ate your brains!" literal. That line now stays on screen for about seven seconds.

## Ideas that were tried or discussed and dropped

- **A hidden ending** where you could choose to stop clicking. Dropped to keep the story linear.
- **Several copies of the same agent in one lane.** Dropped to keep the stages simple.
- **A backlog pile on the desk with tally marks.** Replaced by tasks stuck in your head, which says more.
- **"The tasks ate your brain!", "Overtasking…", "Context switching…".** "Cognitive overload" named the excess most directly.
