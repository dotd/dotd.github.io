# PLAN — The Surgeon's New Hands: Autonomy, AI, and the Future of Medical Robotics

The medical-robotics piece will live under `writings/medical_robotics_and_AI/`.

I want to write a structured long-form essay (~4000+ words) on the future of
autonomous medical robotics and AI, aimed at a **technical / investor**
audience — assumes familiarity with robotics and venture, can go deep on
autonomy levels, data moats, and market structure without hand-holding.

Authorial stance, like the Kolmogorov piece: these are informed postulations on
the trajectory by someone close to robotics, not formal prediction.

Form: structured long-form with section headers, company profiles, and one
top-5 comparison table. Figures, rankings, and funding must be **verified with
current sources and cited** before publishing.

## Organizing device
The **surgical autonomy ladder** (L0 none → L5 full, paralleled to driving
levels) is introduced first and threads through the whole piece. Central
tension: the climb from teleoperation (L0–1, where commercial systems sit
today) toward supervised autonomy (L2–3). Medicine is the hardest rung —
irreversible errors, a regulator in the room, liability.

## Structure

### 0 — Opening
Scene contrasting a robot that *steadies the surgeon's hands* vs. one that
*knows where to cut*. Plant the autonomy ladder and the authorial stance.

### Part I — The autonomy ladder (frame for everything after)
- 6-level surgical-autonomy taxonomy, explicitly paralleled to driving levels.
- Where broad robotics sits: imitation learning / learning-from-demonstration
  turn, foundation-model control.
- Why surgery is the hardest rung. Today's commercial systems are L0–1; the
  essay is the climb from 1 toward 3.

### Part II — The landscape today: the top 5
Profiles, each scored on the ladder (what's automated / what stays human /
level): Intuitive Surgical (da Vinci, Ion) · Medtronic (Hugo) · Stryker (Mako,
most autonomous today) · J&J MedTech (Ottava/Monarch) · 5th slot (CMR Surgical
Versius / Zimmer Biomet Rosa — decide by angle).
- One comparison table: company · system · specialty · autonomy level ·
  differentiator.
- Closing beat: the moat is installed base + regulatory file, not kinematics —
  foreshadows Part IV.

### Part III — The open frontier: money and the problems startups attack
- Verified venture flows into surgical robotics + recent rounds (cited).
- Organized by problem, not company: cost/access · new anatomies (endoluminal,
  ophthalmic, neuro, vascular, micro) · autonomous sub-tasks (suturing,
  anastomosis, needle steering — the STAR lineage) · the AI/perception layer
  (surgical scene understanding, sim-to-real, data platforms) · adjacencies
  (rehab/exo, capsule/nano).
- Transition: the recurring bottleneck is validated demonstration data.

### Part IV — What the future holds (four-beat crescendo)
1. **Data as the real moat** — installed base → procedure-video flywheel →
   compounding advantage; who owns the corpus.
2. **The GPT moment for surgery** — can a general surgical world-model emerge
   from pooled video? What L2–3 supervised autonomy it unlocks; what it can't.
3. **The human as teacher in medicine** — surgeons demonstrating frame-by-frame;
   the apprentice is the machine (the social-graph thread, now in the OR).
   Effects on training, geography of expertise, surgeon identity.
4. **Forward claim** — medicine will be among the last to reach full autonomy
   and among the most transformed by partial autonomy; the inflection is the
   corpus, not the hardware. Regulation / reimbursement / liability set the
   pace, not the direction.

## Open decisions
- 5th company slot (CMR Versius vs. Zimmer Rosa vs. an endoluminal player).
- Final word count and whether to add a Hebrew version (other pieces have one).

---

# RESEARCH (verified, cited — May 2026)

## The autonomy ladder (Part I)
- Canonical scale: Yang et al., "Medical robotics—Regulatory, ethical, and legal
  considerations for increasing levels of autonomy," *Science Robotics* 2017.
  6 levels, paralleled to SAE driving: L0 none/teleop · L1 robot assistance
  (virtual fixtures / active constraints, human drives) · L2 task autonomy
  (robot executes a surgeon-initiated task) · L3 conditional autonomy (robot
  plans + adapts, surgeon supervises) · L4 high autonomy (robot decides under
  oversight) · L5 full autonomy. Paper says L2–3 are "within reach today."
  https://www.science.org/doi/10.1126/scirobotics.aam8638
- Where commercial sits: Han et al., *npj Digital Medicine* 7:103 (Apr 2024).
  Of 49 FDA-cleared surgical robots, **86% are Level 1**; highest cleared = L3
  (Think Surgical TSolution One, orthopedic bone milling). Soft-tissue commercial
  = L1. None at L4/L5. https://www.nature.com/articles/s41746-024-01102-y
- STAR (Smart Tissue Autonomous Robot), Saeidi/Krieger et al., *Science Robotics*
  Jan 2022: autonomous laparoscopic bowel anastomosis **in vivo in pigs** (4 of 5
  by STAR), more consistent than expert surgeon. Classical planning/control.
  Research only, not human/commercial. https://www.science.org/doi/10.1126/scirobotics.abj2908
- The learning generation (imitation learning / VLA models in the OR):
  - SRT (Surgical Robot Transformer), Kim/.../Finn/Krieger, CoRL Jul 2024 —
    imitation learning on da Vinci for tissue manipulation, needle handling,
    knot-tying; relative-action trick beats da Vinci's bad absolute kinematics.
    https://arxiv.org/abs/2407.12998
  - SRT-H, *Science Robotics* Jul 2025 — language-conditioned hierarchical IL did
    a full autonomous phase of cholecystectomy (clip+cut cystic duct/artery),
    **100% on 8 ex vivo pig gallbladders**, error recovery via language policy.
    Ex vivo, not human. https://www.science.org/doi/10.1126/scirobotics.adt5254
  - Framing pieces: Schmidgall/Krieger "General-purpose foundation models for
    increased autonomy in RAS" (arXiv 2401.00678); "The robot will see you now:
    Foundation models are the path forward..." *Science Robotics* 2025.
  - General-robotics VLA lineage: RT-2 (Jul 2023), Physical Intelligence π₀
    (Oct 2024, open-sourced), π₀.₅ (2025). Chelsea Finn links both worlds.

## Top systems (Part II) — verified 2025/2026
- **Intuitive (da Vinci 5 + Ion):** 11,106 da Vinci installed (Dec 31 2025, +12%);
  ~3.15M procedures in 2025 (+18%); ~17M cumulative; ~$10.06B FY2025 revenue
  (preliminary). da Vinci 5 cleared Mar 2024, Force Feedback (first haptic).
  Autonomy = **L0 teleop**. The data flywheel. ISRG Q4/FY2025 release.
- **Medtronic (Hugo RAS):** **US FDA urologic clearance Dec 3 2025** (Expand URO,
  137 pts); CE 2021; first US case at Cleveland Clinic. Autonomy = **L0**.
  No clean US installed-base number (in 30+ countries). 
- **Stryker (Mako):** >3,000 robots, >1.5M procedures, 45 countries; Mako 4 at
  AAOS Mar 2025. CT → patient-specific plan → robotic arm enforces haptic
  boundary + auto-deactivates tool at edge. **Highest mainstream autonomy = L1
  (bounded/shared control).** CAUTION: Stryker stresses it does NOT cut
  autonomously — moves in tandem with surgeon. Don't overstate.
- **J&J MedTech (Ottava + Monarch):** Ottava IDE late 2024, first cases early
  2025, **De Novo submitted to FDA Jan 2026** (not cleared). Table-integrated
  4-arm design. Monarch: bronchoscopy 510(k) Mar 2025 + AI update (Nvidia/GE).
  Autonomy = **L0** (Ottava), L0–1 (Monarch). No standalone figures disclosed.
- **5th slot options:**
  - CMR Surgical (Versius): de novo Oct 2024, **Versius Plus 510(k) Dec 17 2025**
    (cholecystectomy), US launch 2026, >40,000 procedures ex-US, raised >$200M
    Apr 2025. L0 teleop, modular/portable challenger.
  - Zimmer Biomet (ROSA): knee/hip/shoulder + brain/neuro; ~2,000 installs;
    **ROSA Knee w/ OptimiZe 510(k) Nov 14 2025.** L1, imageless vs Mako's CT —
    good second ortho contrast for the autonomy-ladder spine. RECOMMENDED if
    spine = autonomy ladder.

## Investment + startups (Part III) — verified
- Market: analyst estimates cluster ~$10–14B in 2025, ~14–17% CAGR (Precedence,
  MarketsandMarkets, GM Insights, Mordor). Wide spread; cite as range. "$60B+ by
  2034 / ~20%" is an aggressive outlier.
- Robotics VC broadly: >$3B in 2024, deal count falling (671→473) = capital
  concentrating into fewer/larger rounds. No clean surgical-only VC annual total.
- By problem:
  - **Cost/access:** Distalmotion (Dexter) $150M Series G Nov 2025; CMR >$200M
    Apr 2025; Moon Surgical (Maestro) $55.4M 2023 (Sofinnova+NVIDIA); Ronovo
    $67M Series D Sep 2025 (J&J JJDC).
  - **New anatomies:** **ForSight Robotics (Oryom, ophthalmic) — $125M Series B
    Jun 24 2025, total $195M** (Eclipse, Fred Moll, Adani); Israeli; first-in-human
    prep; founders Shoham/Glozman/Nathan. Noah Medical (Galaxy bronch) $150M
    2023, >5,000 procedures. MMI/Symani (microsurgery) $110M Series C Feb 2024.
    Vicarious (public, cash-constrained, timeline slipped to FY2026). Remedy
    Robotics (remote endovascular, world-first remote cases). Caranx (TAVI AI,
    FDA Jul 2025).
  - **AI/perception + sub-tasks:** Caresyntax $180M Series C ext Aug 2024 ($310M
    total); Theator (~$42.5M total, NO Series B — correct the record); Proximie
    $80M Series C 2022; Activ Surgical (ActivSight, ~$77–100M). Vanderbilt won up
    to $12M ARPA-H Sep 2024 for a fully autonomous surgical robot.
  - **Adjacencies:** Wandercraft (exo) $75M Series D Jun 2025. Capsule/micro/nano
    = still academic, no fundable rounds — flag as research-stage.

## Data moat + foundation models (Part IV)
- **Intuitive is the dominant corpus holder:** >12,000 systems, >20M cumulative
  procedures (~8,700/day), multimodal (video+kinematics+force on dV5); Case
  Insights productizes it. Structurally larger than any startup corpus.
- Independent data layer: Caresyntax, Theator, Proximie capture/annotate OR video
  at scale; none publish a foundation model yet.
- Academic surgical-video foundation models: GSViT (>680 hrs YouTube), EndoFM
  (>33k clips), SurgVISTA (2025), UniSurg/"SurgMotion-15M" (~3,658 hrs, 50
  sources — very recent preprint). The corpus race is currently research-led.

## Accuracy flags
- Intuitive FY2025 = preliminary (verify vs final 10-K). Hugo/Ottava/Monarch/
  Versius/Rosa lack clean disclosed installed-base/procedure/revenue figures —
  cite as approximate/company-reported. Autonomy "levels" are an academic, not
  regulatory, framework. Never describe Mako/Rosa as "autonomous cutting."
