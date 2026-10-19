# Video Annotation Mini-Project

A small, end-to-end data annotation project: build a 50-clip video dataset, write the labeling guidelines, label every clip, evaluate AI-generated captions against my labels, and measure my own labeling consistency.

The goal is to practice guideline-based annotation work the way it is done on real data-labeling and AI-evaluation teams: clear rules, consistent labels, honest error analysis, and measured quality.

## Workflow

| Step | What I did | Where to look |
|---|---|---|
| 1. Collect | Gathered 50 short clips (5-15 s) from Creative Commons YouTube videos and public datasets | `Clips` sheet |
| 2. Guidelines | Wrote label definitions, edge-case rules and worked examples | [`guidelines/annotation_guidelines.md`](guidelines/annotation_guidelines.md) |
| 3. Label | Labeled scene, main action, objects, audio events, safety flag and confidence for each clip | `Labels` sheet |
| 4. Evaluate AI | Generated a caption per clip with an AI tool, rated accuracy 1-5, and flagged error types | `Caption_Eval` sheet |
| 5. Consistency | Re-labeled 20 clips several days later without looking at my first answers | `Relabel` sheet |
| 6. Summary | Wrote up findings, tricky cases and how I handled uncertainty | [`docs/summary.md`](docs/summary.md) |

## Label schema

| Field | Values |
|---|---|
| Scene | indoor_home, indoor_public, outdoor_urban, outdoor_nature, vehicle, studio_screen, unclear |
| Main_Action | walking, running, cooking, eating, talking, playing_instrument, playing_sport, driving, dancing, working_on_device, cleaning, animal_moving, no_clear_action, other |
| Objects | up to 5 salient objects, lowercase nouns |
| Audio_Event | speech, music, vehicle_noise, animal_sound, crowd_noise, impact_noise, nature_ambient, silence, other |
| Safety_Flag | safe, unsafe, needs_review |
| Confidence | High, Medium, Low |

Full definitions, edge cases and examples are in the guidelines.

## Results

> Fill these in from the `Summary` sheet once labeling and the re-label round are done.

| Metric | Result |
|---|---|
| Clips labeled | _/50 |
| Safe / unsafe / needs_review | _ / _ / _ |
| Low-confidence labels | _ |
| Mean AI caption accuracy (1-5) | _ |
| Captions with hallucinated details | _ / 50 |
| Captions that missed an object or action | _ / 50 |
| Captions with wrong scene or audio | _ / 50 |
| Captions that missed a safety issue | _ / 50 |
| Overall self-agreement (scene + action + safety) | _% on 20 clips |
| Scene / action / safety agreement | _% / _% / _% |

## Key findings

- **AI caption errors:** _most common error types, with 1-2 clip IDs as examples_
- **Hardest clips to label:** _what made them ambiguous and which rule resolved them_
- **Consistency:** _which field I disagreed with myself on most, and what I changed in the guidelines as a result_

See [`docs/summary.md`](docs/summary.md) for the full write-up.

## Handling uncertainty

- A 60-second rule: if I could not decide in about a minute, I picked the best label, set Confidence to Low and added a note.
- The `needs_review` safety flag is used for borderline clips instead of guessing.
- Guidelines were versioned; changes made after the consistency check are logged in the guidelines' change log.

## Repository structure

```
.
├── README.md
├── guidelines/
│   └── annotation_guidelines.md
├── data/
│   ├── video_annotation_workbook.xlsx   # all sheets, formulas calculate the summary
│   ├── labels.csv                       # export of the Labels sheet
│   └── caption_eval.csv                 # export of the Caption_Eval sheet
└── docs/
    └── summary.md
```

## Data and licensing

Video files are not stored in this repository. The `Clips` sheet lists each clip's title, source URL and licence (Creative Commons or public dataset) so the originals can be found and attributed. My own labels, guidelines and write-up are released under the MIT licence.

## Tools used

Google Sheets / Excel (data validation and formulas), an AI captioning tool for the evaluation step, and Git/GitHub for version history.

## Limitations

This is a 50-clip, single-annotator project. Agreement is measured against my own earlier labels, not a second person, and a sample of 20 re-labeled clips gives a rough rather than statistically strong estimate. With more time, the next steps would be a second annotator, Cohen's kappa, and a tool like Label Studio.
