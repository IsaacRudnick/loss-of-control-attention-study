# Loss of Control, Stakes, and Attention

A browser-based game experiment testing whether losing control narrows attention, and whether high stakes make that narrowing worse.

**Authors:** Jackson Chidiac, Irene Kim, Beatrice Messaris, and Isaac Rudnick  
**Affiliation:** Vassar College, COGS-219 Research Methods, Spring 2025

## Resources

- **Full paper:** [`paper/control-interruption-stakes-attention-2025.pdf`](paper/control-interruption-stakes-attention-2025.pdf)
- **Data, stimuli, and analysis scripts:** <https://osf.io/kc9gd/>
- **Pre-registration:** <https://osf.io/vnh7x>

## Contents

- [Task](#task)
- [Design](#design)
- [Results](#results)
- [Repository Layout](#repository-layout)
- [Running the Experiment](#running-the-experiment)

## Task

Participants steer Mr. Frog across three lanes of logs with the arrow keys, collecting bugs (+10 points) and avoiding water (−100 points). Occasionally a purple bonus bug fades in, either in the center lane or at the left edge of the screen. Pressing the space bar collects it (+50 points); pressing the space bar when no bonus bug is present costs 50 points.

Reaction time to the bonus bug is the measure of attention to a task-noncritical stimulus.

## Design

A 2 × 2 × 2 within-participants design with 10 trials per cell, shuffled with filler trials into one continuous stream. The three factors are:

1. **Stakes.** *High:* the frog is on course to hit water unless it moves. *Low:* staying put only forfeits a 10-point bug.
2. **Interruption of control.** The frog "slips": the next arrow press is ignored and movement is locked for 1 s. Slips are queued and fire only on the next keypress, so there is no advance warning.
3. **Bonus bug location.** Central vs. peripheral (left edge of the screen).

## Results

Sixty-four participants were recruited on Prolific; 53 remained after exclusions, and 42 had data in every cell for the confirmatory three-way ANOVA. Effect sizes are reported as generalized eta squared (η²<sub>G</sub>).

1. **Bug location dominated.** Peripheral bugs were collected much more slowly, *F*(1, 41) = 570.1, η²<sub>G</sub> = .47.
2. **High stakes and interruption each slowed responses, but the effects were tiny.** Stakes: *F* = 18.3, *p* < .001, η²<sub>G</sub> = .013. Interruption: *F* = 5.2, *p* = .028, η²<sub>G</sub> = .008.
3. **The predicted three-way interaction was absent,** *F* = 0.29, *p* = .60. High stakes combined with lost control did not narrow attention more than either did alone.
4. **The two-way interactions with bug location were significant but negligible** (η²<sub>G</sub> < .01) and did not survive exploratory analyses with more participants.
5. **Exploratory analysis, collapsing over location (*n* = 52).** Reaction times were similar in every condition except low stakes with uninterrupted control, which was fastest. Either stressor slows responses; the two do not add.

## Repository Layout

| Path                       | Contents                                                         |
| -------------------------- | ---------------------------------------------------------------- |
| `index.html`, `styles.css` | Page and styling                                                 |
| `game.js`                  | Game loop, level loading, event logging, data upload (DataPipe)  |
| `surveys.js`               | Demographics, rules comprehension quiz, post-game survey         |
| `levels/`                  | One CSV of timed events per condition, plus practice and fillers |
| `imgs/`                    | Sprites                                                          |
| `paper/`                   | Full write-up of the study (PDF)                                 |

## Running the Experiment

1. Open `index.html` in a desktop browser on a screen of at least 1400 × 900 px.
2. Complete the session, which takes about 12 minutes.

> [!NOTE]
> The Prolific completion redirect and DataPipe experiment ID in `game.js` belong to the original study. Change them before collecting your own data.
