# Mini Video Annotation Project: Plan and Summary Template

## Part A. 90-minute plan (Day 1)

| Time | Step | Output |
|---|---|---|
| 0:00-0:20 | Collect 50 clips. Use YouTube search with the Creative Commons filter (Filters > Features > Creative Commons) and short public-dataset samples (Kinetics, AudioSet, or Hugging Face video datasets). Aim for variety: indoor, outdoor, vehicle, sports, animals, a few noisy or ambiguous clips. Trim to 5-15 s or note start/end times. | `Clips` sheet filled (ID, title, URL, licence) |
| 0:20-0:25 | Skim `annotation_guidelines.md` once. | |
| 0:25-1:00 | Label all 50 clips in `Labels` (about 40 s each). | `Labels` sheet complete |
| 1:00-1:20 | Run the clips through an AI captioner (any video-capable assistant or captioning model). Paste each caption into `Caption_Eval`; rate accuracy 1-5, mark error types, add a one-line error note. Do this AFTER labeling and don't edit your labels. | `Caption_Eval` complete |
| 1:20-1:30 | Write the first draft of the summary (Part B). | Summary draft |

**Day 3-5 (about 15 minutes):** Re-label the 20 pre-picked clips in `Relabel` without looking at Round 1 (hide columns B:E first). Then read the `Summary` sheet for agreement rates and finish Part B.

**Time-saving tips:** Keep the guidelines open; don't re-watch clips unless needed; if a clip takes more than a minute, mark it Low or needs_review with a note and move on.

**Accuracy rating scale for captions:** 5 = fully correct and complete; 4 = correct, minor omission; 3 = mostly correct, one clear error or notable omission; 2 = several errors; 1 = mostly wrong or hallucinated.

## Part B. Summary (fill in; aim for about 1 page)

**1. Dataset overview.** [N clips, sources, licences, total duration, label distribution (scene, safe/unsafe/needs_review).]

**2. What the AI captions got right and wrong.** [Mean accuracy score. Most common error types: missed objects, hallucinated details, wrong scene, ignored audio, missed safety issue. Give 2-3 concrete examples with clip IDs.]

**3. Tricky cases.** [3-5 clips that were hard to label: what made them ambiguous, what you chose, which guideline rule applied or what rule was missing.]

**4. Handling uncertainty.** [How you used Confidence and needs_review; how many Low-confidence labels; the 60-second rule; one example where you chose to flag instead of guess.]

**5. Consistency.** [Overall agreement % on the 20 re-labeled clips, plus per-field rates. Which fields disagreed most and why. What you changed in the guidelines (v1.1) as a result.]

**6. Guideline changes and lessons.** [Edge cases added or tightened; what you'd do differently on a 10,000-clip job (e.g., double-labeling, adjudication, spot checks).]

Note: write only findings you actually observed; the numbers come from your own labeling and the Summary sheet.
