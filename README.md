# Video Annotation Mini-Project

> **Status: 🚧 Work in progress.** The guidelines and labeling workbook are ready; data collection, labeling and evaluation are underway. Results will be added when the project is complete.

A small, end-to-end data annotation project: build a 50-clip video dataset, write the labeling guidelines, label every clip, evaluate AI-generated captions against my labels, and measure my own labeling consistency.

The goal is to practice guideline-based annotation work the way it is done on real data-labeling and AI-evaluation teams: clear rules, consistent labels, honest error analysis, and measured quality.

## Progress

- [x] Annotation guidelines written (v1.0)
- [x] Labeling workbook built (dropdown-validated labels, caption evaluation, consistency check, auto-calculated summary)
- [ ] Collect 50 short clips (5-15 s) from Creative Commons YouTube videos and public datasets
- [ ] Label all clips (scene, action, objects, audio events, safety, confidence)
- [ ] Evaluate AI-generated captions (1-5 accuracy rating and error types)
- [ ] Re-label 20 clips several days later and measure self-agreement
- [ ] Write the final summary and add results to this README

## Workflow

| Step | What it involves | Where to look |
|---|---|---|
| 1. Collect | Gather 50 short clips from Creative Commons YouTube videos and public datasets | `Clips` sheet |
| 2. Guidelines | Label definitions, edge-case rules and worked examples | [`guidelines/annotation_guidelines.md`](guidelines/annotation_guidelines.md) |
| 3. Label | Label scene, main action, objects, audio events, safety flag and confidence for each clip | `Labels` sheet |
| 4. Evaluate AI | Generate a caption per clip with an AI tool, rate accuracy 1-5, and flag error types | `Caption_Eval` sheet |
| 5. Consistency | Re-label 20 clips several days later without looking at the first answers | `Relabel` sheet |
| 6. Summary | Write up findings, tricky cases and how uncertainty was handled | `docs/summary.md` (coming soon) |

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

## Approach to uncertainty

- A 60-second rule: if a label can't be decided in about a minute, pick the best option, set Confidence to Low and add a note.
- The `needs_review` safety flag is used for borderline clips instead of guessing.
- Guidelines are versioned; any change made after the consistency check will be recorded in the change log.

## Results

Coming soon. This section will report label distribution, AI caption accuracy and error types, and self-agreement on the re-labeled clips.

## Repository structure

```
.
├── README.md
├── guidelines/
│   └── annotation_guidelines.md
└── data/
    └── video_annotation_workbook.xlsx   # all sheets, formulas calculate the summary
```

`labels.csv`, `caption_eval.csv` and `docs/summary.md` will be added once the data is complete.

## Data and licensing

Video files will not be stored in this repository. The `Clips` sheet lists each clip's title, source URL and licence (Creative Commons or public dataset) so the originals can be found and attributed. My own labels, guidelines and write-up are released under the MIT licence.

## Tools

Google Sheets / Excel (data validation and formulas), an AI captioning tool for the evaluation step, and Git/GitHub for version history.

## Known limitations

This is a 50-clip, single-annotator project. Agreement is measured against my own earlier labels, not a second person, and a sample of 20 re-labeled clips gives a rough rather than statistically strong estimate. With more time, the next steps would be a second annotator, Cohen's kappa, and a tool like Label Studio.
