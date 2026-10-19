# Video Clip Annotation Guidelines (v1.0)

**Project:** Mini video-understanding dataset (50 clips, 5-15 seconds each)
**Annotator:** [your name] **Date:** 2026-10-19

## 1. Purpose and unit of work
Each clip is labeled independently, watched **in full with sound on**, before any label is chosen. One row per clip. Label only what is observable in the clip; never guess about what happens before or after it. If you can't decide in about 60 seconds, pick your best label, set Confidence to Low, and add a note. Don't agonize.

## 2. Fields and label definitions

| Field | Type | Allowed values |
|---|---|---|
| Scene | single choice | indoor_home, indoor_public, outdoor_urban, outdoor_nature, vehicle, studio_screen, unclear |
| Main_Action | single choice | the most prominent ongoing action (see 2.2) |
| Objects | multi (up to 5) | the most visually salient objects, comma-separated, lowercase nouns |
| Audio_Event | multi | speech, music, vehicle_noise, animal_sound, crowd_noise, impact_noise, nature_ambient, silence, other |
| Safety_Flag | single choice | safe, unsafe, needs_review |
| Confidence | single choice | High, Medium, Low |
| Notes | free text | any ambiguity, one line |

### 2.1 Scene
Where the camera is, not where the subject is going.
- **indoor_home**: private residential interior (living room, kitchen).
- **indoor_public**: shops, gyms, offices, schools, stations.
- **outdoor_urban**: streets, parks with buildings visible, parking lots.
- **outdoor_nature**: forest, beach, mountains, farmland, open water.
- **vehicle**: camera is inside a car, bus, train, plane or boat.
- **studio_screen**: staged backdrop, green screen, or a screen recording/slideshow.
- **unclear**: too dark, blurred, or cropped to tell. Use sparingly.

### 2.2 Main_Action
Choose the one action that occupies most of the clip. Use a short verb phrase from the working list: walking, running, cooking, eating, talking, playing_instrument, playing_sport, driving, dancing, working_on_device, cleaning, animal_moving, no_clear_action, other (explain in Notes).
- Two actions at once (talking while cooking): pick the one with the most screen time; mention the other in Notes.
- Someone merely present and not doing anything notable: no_clear_action.

### 2.3 Objects
List only objects you could name from a still frame. Use singular lowercase nouns (dog, guitar, car). Skip background clutter, tiny items and anything you only infer. Max 5, most prominent first.

### 2.4 Audio_Event
Listen to the actual track, not the visuals. Tag every distinct event clearly audible for more than about 2 seconds. Background music under speech gets both labels. If audio is missing or muted, use silence and note "no audio track".

### 2.5 Safety_Flag
- **safe**: nothing a reasonable reviewer would object to.
- **unsafe**: depicts or strongly implies violence or injury, weapons used aggressively, dangerous stunts a viewer might imitate, self-harm, nudity or sexual content, hate symbols, or minors in a risky situation.
- **needs_review**: unclear or borderline. Prefer this over guessing, then explain in Notes.
Use public, non-graphic material for this project; if a clip turns out graphic, mark unsafe, don't linger, and replace it.

## 3. Edge cases and decisions

| Situation | Decision |
|---|---|
| Sports with contact (boxing, football tackle) | safe if regulated, normal play; unsafe only if it shows a clear injury or foul violence |
| Fireworks, bonfire, kitchen flame | safe if controlled; needs_review if people appear in danger |
| Cartoon or video-game footage | Scene = studio_screen; judge Safety on the depicted content, graphic violence is still unsafe |
| Clip mixes two scenes (cut from kitchen to street) | Label the scene covering most of the clip, note the cut |
| Narration over unrelated footage | Audio = speech; Main_Action describes the visuals, not the narration |
| Very short motion (under 1 second) | Ignore, don't treat as Main_Action |
| Text overlays or subtitles | Do not use as evidence for Objects or Audio unless the visual or sound matches |
| Cannot identify an object | Leave it out; never guess brand or species beyond what is clear |
| People's identity, age, ethnicity, gender | Never label or infer. Describe actions only |

## 4. Worked examples

1. *Someone chopping vegetables at a counter, radio playing.* Scene indoor_home, Action cooking, Objects knife, cutting_board, pot, Audio music, Safety safe, Confidence High.
2. *Dashcam driving down a street, engine hum, no speech.* Scene vehicle, Action driving, Objects road, car, traffic_light, Audio vehicle_noise, Safety safe, High.
3. *Crowded market, people talking, one person shouting.* Scene outdoor_urban, Action walking, Objects stall, basket, Audio crowd_noise, speech, Safety safe, Medium (note: shouting, no threat visible).
4. *Dim handheld shot, loud bang, shaky camera.* Scene unclear, Action no_clear_action, Audio impact_noise, Safety needs_review, Low (note: cannot tell source of bang).

## 5. Quality rules
- Watch the whole clip before labeling; label in sessions of at most 20 clips with short breaks.
- Do not change labels after seeing AI captions. Caption evaluation happens in a separate step.
- When you revise these guidelines, bump the version number and note what changed and why in the log below.

## 6. Change log
| Version | Date | Change |
|---|---|---|
| 1.0 | 2026-10-19 | Initial release |
