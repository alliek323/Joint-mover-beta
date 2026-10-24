# Joint Movement Trainer

A single-file, no-build study tool for medical students to learn joint movement terminology.
Open `index.html` in a browser (or host it with GitHub Pages).

## Tabs
- **Flexion / Extension** – side-view figure; neck, shoulder, elbow, wrist, hip, knee, ankle. Wrist uses palmar flexion/dorsiflexion, ankle uses dorsiflexion/plantarflexion.
- **Valgus / Varus** – front view for knee, elbow, ankle; hip is shown as the femoral neck-shaft angle (coxa valga/vara).
- **Rotation** – front-view figure (kneecaps/toes for hip, hands for shoulder) plus a close-up from above of the femoral head/neck or humeral head in the glenoid.
- **Study mode** – random joint moved from neutral; pick the correct term from four options; score and streak; optional neutral outline.

## Code map (all in `index.html`)
- `DEF` – joint data: name, slider range, positive term `p`, negative term `q`, teaching tip. `RULE` – per-tab rule text.
- `Z` – neutral values. `VALS` – current slider values. Positive = flexion / valgus / internal rotation (ankle: dorsiflexion).
- `feP`/`feBody`/`feSVG` – side-view kinematics. Angles are measured from straight down, positive toward anterior.
- `vvBody`/`hipB`/`hipSVG`/`vvSVG` – front view; `s` is the lateral sign (-1 = patient’s right, drawn on screen left).
- `rotSVG` – rotation tab (front figure overlay + top-down joint close-up, helper `P(O,r,deg)` for polar points).
- `newQ`/`quiz` – study mode. `render`, `explore`, `upd` – UI wiring (event delegation at the bottom).

## Known caveats / next ideas
- Geometry is schematic, not to scale. The hip close-up assumes about 15° of femoral neck anteversion; tuberosity positions in the shoulder close-up are approximate. Please verify against an anatomy atlas.
- The rotation figures have not had a thorough visual review on all screen sizes.
- Ideas: abduction/adduction, pronation/supination, more joints in the quiz, a hard mode with no labels, spaced-repetition of missed terms, option to plant ankles, integrate pathology.

## Reference
Flexion/extension conventions follow https://tommorrison.uk/blog/flexion--extension-in-detail
