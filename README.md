# Joint Movement Trainer

A single-file, no-build study tool for medical students to learn joint movement terminology.
Open `index.html` in a browser (or host it with GitHub Pages). It also runs inside
Quizzboard at quizzboard.online/JointMover/, which copies `index.html` unchanged.

## Tabs
- **Flexion / Extension** – side-view figure; neck, shoulder, elbow, wrist, hip, knee, ankle. Wrist uses palmar flexion/dorsiflexion, ankle uses dorsiflexion/plantarflexion. The view zooms to the part of the body that moves.
- **Valgus / Varus** – front view for knee, elbow, ankle; hip is shown as the femoral neck-shaft angle (coxa valga/vara). A dashed line shows the straight-line reference the angle is measured from.
- **Rotation** – front-view figure (kneecaps/toes for hip, hands for shoulder) plus a close-up from above of the femoral head/neck or humeral head in the glenoid.
- **Study mode** – pick the term that takes the joint from the faint starting outline to the solid figure; four options; score, streak and best streak; practice all movements or one category. Keys 1–4 answer, N or Enter moves on.

Every explore view has a slider, ±5° buttons and a drag handle on the figure (mouse or touch). Moving parts are drawn in blue with an angle arc.

## Code map (all in `index.html`)
- `DEF` – joint data: name, slider range (AAOS typical adult values for flexion/extension), positive term `p`, negative term `q`, teaching tip. `RULE` – per-tab rule text. `NORM` – normal alignment notes for valgus/varus.
- `Z` – start values. `VALS` – current values. Positive = flexion / valgus / internal rotation (ankle: dorsiflexion). Elbow and knee are hinges whose start is full extension (0°).
- `feP`/`feBody`/`feSVG` – side-view kinematics. Angles are measured from straight down, positive toward anterior.
- `vvP`/`vvBody`/`hipB`/`hipSVG`/`vvSVG` – front view; `s` is the lateral sign (-1 = patient’s right, drawn on screen left). `FEM` is the femur's slight medial slope on the mechanical axis.
- `rotSVG` – rotation tab (cropped front figure + top-down joint close-up, helper `P(O,r,deg)` for polar points).
- `arc` – angle arc and dashed reference line. `handle` – drag handles; each figure render lists them in `HANDLES` with a function that turns a pointer position into a joint value.
- `newQ`/`quiz`/`answer`/`next` – study mode. `render`, `explore`, `upd`, `setVal` – UI wiring (event delegation and pointer dragging at the bottom).

## Known caveats / next ideas
- Geometry is schematic, not to scale. The hip close-up assumes about 15° of femoral neck anteversion; tuberosity positions in the shoulder close-up are approximate. Please verify against an anatomy atlas.
- Ideas: abduction/adduction, pronation/supination, inversion/eversion, more joints in the quiz, a hard mode with no labels, spaced repetition of missed terms, integrate pathology.

## References
- Ranges of motion: American Academy of Orthopaedic Surgeons reference values, as tabulated in Norkin & White, *Measurement of Joint Motion: A Guide to Goniometry*.
- Flexion/extension explanations: https://tommorrison.uk/blog/flexion--extension-in-detail
