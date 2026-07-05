# XR tracking & spatial — bending correction / bending-assisted calibration

Snap's ultra-light Spectacles frame flexes slightly when it's pushed onto different-sized heads. The two forward-facing "eyes" (stereo cameras) live on the left and right temples, so if the frame bends even a fraction of a millimetre, the cameras rotate relative to each other. Since depth perception comes from comparing the two camera views, that tiny twist wrecks the sense of how far away things are — and virtual objects drift, float, or sit at the wrong distance. These patents fall into two distinct invention families that both attack "the frame bends on your face."

Two families:
- **Family A — Depth-from-stereo bending correction (VIO features):** measures and cancels the bend in real time so depth stays accurate. (US20220366600A1, US20240029302A1, WO2022240933A1)
- **Family B — Bending-assisted calibration:** uses *how much* the frame is bent as an anonymous fingerprint of who's wearing it, to decide whether to reuse a saved hand-tracking calibration or start over. (US12271517B1, US20250110547A1)

---

### US20220366600A1 — Depth-from-stereo bending correction using VIO features (Family A, lead patent)
- **In one line:** Continuously catches when the flexing frame has knocked the two stereo cameras out of alignment and mathematically re-aligns them so depth stays correct.
- **How it works:** The glasses already run a "visual-inertial odometry" (VIO) system — a tracker that fuses what the cameras see with motion readings from a tiny inertial sensor (accelerometer + gyroscope) to know exactly how the device is moving and to pin 3D "landmark" points in the world. The trick is to use that independent, trusted 3D knowledge as a truth-check on the stereo cameras. It splits the misalignment into two kinds. **Pitch-roll bending:** it takes matched feature points seen in the left and right camera and checks whether they land on the *same horizontal scan line* — on a properly aligned stereo pair they must; if a point sits higher in one image than the other, the frame has twisted, and the size of that vertical offset gives the pitch/roll error. **Yaw bending** (the sideways splay that directly fakes distance): it compares the depth the stereo cameras report against the depth the VIO system independently computes for the same landmarks; any mismatch, converted into an equivalent camera rotation and averaged over many landmarks, is the yaw bias. It then updates the camera "rectification" map to cancel both biases before rendering the next frame. Using VIO landmarks that persist over time gives it a wide, stable baseline that works even indoors where objects are close.
- **Everyday analogy:** Like a carpenter who doesn't trust a warped ruler, so he checks every measurement against a laser level he knows is true — and quietly re-marks the ruler each time it's off.
- **Why it matters for AR glasses:** This is what lets Spectacles be feather-light and one-size-flexes-all without depth perception falling apart. A rigid, heavy frame could hold calibration but nobody wants to wear it; this makes "comfortable" and "accurate" coexist.
- **Confidence:** high (full-text).

### US20240029302A1 — Depth-from-stereo bending correction using VIO features (Family A, continuation)
- **In one line:** Same invention as US20220366600A1, re-filed to pursue broader/updated claims.
- **How it works:** Continuation of application 17/480,405 (the lead patent). Identical abstract and the identical bending-correction block diagram (pitch-roll module 402, yaw module 404, mitigation module 406 feeding the AR/VR app). No mechanistic difference; the continuation exists to extend patent coverage of the same disclosure.
- **Everyday analogy:** Same "check the warped ruler against a laser level" idea — this is a second claim staked on the same land.
- **Why it matters for AR glasses:** Signals Snap protecting the core depth-correction method with layered claims — the mark of a foundational technique, not a throwaway.
- **Confidence:** high (vision — page 1 abstract + FIG 4 confirm identity; mechanism read in full via the lead patent).

### WO2022240933A1 — Depth-from-stereo bending correction (Family A, PCT/international)
- **In one line:** The international (PCT) version of the same depth-from-stereo bending fix, filed to secure rights outside the US.
- **How it works:** Same priority filings (provisional 63/188,815 and US parent 17/480,405) and the same abstract and FIG 4 block diagram as the lead patent. Designates the full slate of countries for national patent protection. Mechanism is identical: VIO landmarks validate stereo rectification, split into pitch-roll (same-scan-line check) and yaw (VIO-depth vs stereo-depth) corrections.
- **Everyday analogy:** Same laser-level-vs-warped-ruler trick, filed at the "world" patent office so it's protected in Europe, Asia, etc.
- **Why it matters for AR glasses:** International filing shows Snap treats bending correction as globally strategic IP, not a US-only curiosity.
- **Confidence:** high (vision — page 1 abstract + FIG 4 confirm identity with the lead patent).

### US12271517B1 — Bending-assisted calibration for extended reality tracking (Family B, granted patent)
- **In one line:** Uses *how much the frame bends* as an anonymous stand-in for "who's wearing this," so the glasses know whether to reuse a saved hand-tracking calibration or recalibrate — without ever storing your identity.
- **How it works:** Accurate hand tracking needs a per-user "hand feature calibration" (roughly, your hand's size) so the glasses don't confuse a big hand far away with a small hand up close. That calibration is user-specific and useless for the next person. Instead of tying it to a login or stored biometric profile (privacy risk) or recalibrating every single session (slow), the device measures the frame's bend — via a strain gauge, or by computer vision comparing how much the two cameras' fields of view overlap now versus at the factory, or via the VIO system. Because a bigger head splays the frame more, the bend value acts as an anonymous fingerprint of the wearer. When you put the glasses on, it compares the current bend against the cached bend from the last session; if they "match" within a tolerance (e.g., strain within ~5-10%), it assumes the same person and instantly loads the previous hand calibration (Mode 1); if not, it runs a fresh calibration for the new wearer (Mode 2). The cached bend data is temporary and anonymous — not linked to any name or profile.
- **Everyday analogy:** Like a well-worn armchair that "remembers" its regular sitter by the shape of the dent — sit down and it fits instantly; a heavier guest presses a different dent, so it adjusts. The chair never needs to know your name.
- **Why it matters for AR glasses:** Faster startup (no recalibration wait for the usual wearer) and a genuinely privacy-preserving way to personalize — the device recognizes "same user vs. different user" from a mechanical signal alone, storing no biometric identity.
- **Confidence:** high (vision — abstract + detailed-description pages read directly).

### US20250110547A1 — Bending-assisted calibration for extended reality tracking (Family B, application)
- **In one line:** The still-pending application version of the granted US12271517B1 bending-as-fingerprint idea.
- **How it works:** Same inventors, same abstract, same disclosure as the granted patent. Its FIG 5 flowchart lays the mechanism out step by step: detect user putting the device on and start session 1 → record biometric (hand) data and its corresponding bending value → detect removal / session end → detect a new session → measure the new bending value → compare to the stored value → if MATCH, select Mode 1 and load the previously identified biometric data; if NO match, select Mode 2 and run a fresh calibration → perform tracking. Being an application (not yet granted), its final claim scope may still shift.
- **Everyday analogy:** The same "armchair remembers you by the dent" idea, shown here as an explicit checklist the glasses run each time you put them on.
- **Why it matters for AR glasses:** A companion filing to the granted patent — reinforces that bending-as-anonymous-fingerprint is a deliberate, defended pillar of Snap's tracking stack.
- **Confidence:** high (vision — abstract + FIG 5 flowchart read directly; matches granted patent).

---

## Area synthesis — XR tracking & spatial (bending correction)

- **The big idea:** For glasses light enough to wear all day, the frame *will* flex on different faces, and its two stereo cameras will drift out of alignment — which normally destroys depth perception and makes virtual objects float away. Snap turns this liability into a two-part strategy: continuously *cancel* the bend so depth stays locked (Family A, using the glasses' own motion-plus-vision tracker as an independent truth-check on the cameras), and separately *read* the bend as an anonymous fingerprint of who's wearing the device to skip redundant calibration (Family B).

- **Challenge → breakthrough arc:** The challenge is brutal precision — a fraction of a millimetre of camera twist ruins depth, and the frame bends by design every time it's put on a new head. The naive fix, re-solving the alignment from scratch every frame, is too slow and gets shaky indoors where everything is close. The breakthrough is to stop treating the stereo cameras as the source of truth and instead cross-check them against the visual-inertial odometry system — a tracker that fuses camera images with inertial-sensor motion to hold stable 3D landmarks over time. Any disagreement between what the cameras report and what that landmark tracker knows *is* the bend, cleanly split into vertical twist (a same-scan-line check) and the dangerous sideways splay (stereo-depth vs. VIO-depth). The second leap is realizing the bend itself is information: how far the frame splays reveals head size, so the device can recognize "same wearer vs. new wearer" mechanically — reusing personalization instantly while storing nothing about your identity.

- **ELI5 one-liner:** The glasses gently bend on your face, which would normally make 3D things look wrong — so they constantly double-check their cameras against a built-in motion sensor to straighten out the picture, and they even use *how much* they bend to tell who's wearing them without ever knowing your name.
