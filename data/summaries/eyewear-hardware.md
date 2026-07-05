# Eyewear hardware & form factor — plain-English patent explainers

*Area: how a whole computer fits into a glasses frame (Snap / Spectacles portfolio).*

---

### KR20240047454A — System-on-chip with simultaneous USB communication (dual-brain glasses)
- **In one line**: Splits the glasses' computer across two chips (one in each temple/arm) and lets a single USB connection do two jobs at once, so a slim frame can carry a real computer.
- **How it works**: The frame has electronics on both sides. A "system-on-chip" (SoC — an entire computer's worth of processor, memory and controllers squeezed onto one chip) sits near one side, and a second SoC sits in the other arm; the two share the work so neither overheats or drains the battery alone (Korean claim 1 + abstract). The headline trick is the USB part: one physical USB 3.0 connector's pins are divided into two independent "sub-interfaces" — a slower High-Speed lane (USB 2.0) wired to an internal peripheral, and a Super-Speed lane (USB 3.0) wired to an external device — so the glasses can talk to an internal component and a PC/charger at the same time over one cramped port.
- **Everyday analogy**: Like turning a single doorway into a revolving door with two lanes, so people can walk in and out simultaneously instead of waiting their turn — and staffing the building with two managers (one per wing) instead of overworking one.
- **Why it matters for AR glasses**: Space, heat and battery are the enemies of any wearable computer. Reusing one connector for two data streams and balancing load across two chips is exactly how you cram desktop-class capability into eyewear that still looks like glasses.
- **Confidence**: high (full-text, Korean original + English abstract cross-checked in CSV)

---

### US11099643B1 — Headware with computer and optical element (the foundational architecture)
- **In one line**: The founding patent for camera-glasses that see the world, do part of the thinking on-board, and hand the heavy thinking off to your phone — showing results on a tiny display in front of your eye.
- **How it works**: A head-worn frame carries a microcomputer, an outward-facing camera, an optional inward-facing eye-tracking camera, near-eye optics with a micro-display, and a wireless transceiver (claims 1-2, summary). The defining move is "distributed computation": the glasses' small computer runs the *first part* of a task (e.g., pulling data out of a captured image), wirelessly ships the *second part* to a more powerful mobile computer, and the two run **simultaneously**, with the phone's result fed back to the glasses. The patent enumerates a laundry list of on-board functions — AI/machine-learning, voice and biometric processing, eye tracking via pupil position — anticipating a full computer on your face.
- **Everyday analogy**: Like a paramedic in an ambulance who stabilizes the patient on the spot while radioing the hospital to prep surgery — near work and far work happening at the same time, not one after the other.
- **Why it matters for AR glasses**: This is the blueprint the whole portfolio builds on: glasses can't fit a supercomputer, so the winning form factor does light work locally and leans on the phone/cloud for the rest, in parallel, to stay small and cool.
- **Confidence**: high (full-text)

---

### US11778149B2 — Headware with computer and optical element (grant continuation of US11099643)
- **In one line**: The same head-worn-computer invention, re-granted as a patent with refreshed claims to extend protection.
- **How it works**: Direct continuation of US11099643 — identical abstract (frame + near-ocular optics + micro-display + computing device + biometric sensor) and the same distributed-computing architecture diagram (glasses feeding a laptop/phone/tablet through layers labeled distributed cloud, artificial intelligence, computer vision, a "secure obstruction layer," and external vs. locally-executed applications).
- **Everyday analogy**: The director's cut of the same film — same story, re-released to keep the rights locked down.
- **Why it matters for AR glasses**: Shows Snap actively fencing off the foundational "computer-in-glasses + offload to phone" idea with a family of patents rather than a single filing.
- **Confidence**: high (vision — front page confirms it is a continuation of US11099643; overlap noted rather than re-derived)

---

### US20230412780A1 — Headware with computer and optical element (published application, same family)
- **In one line**: A later-published version of the same foundational glasses-computer patent, still pending as an application.
- **How it works**: Continuation tracing back through US11778149 → US11099643 → filings from 2011-2013. Same abstract and same distributed-computing figure (biometrics/voice/video signal streams → distributed computing + AI/computer vision → secure layers → display). The updated classification codes add more computer-vision and image-analysis categories, hinting at broader claim ambitions.
- **Everyday analogy**: A patent "sequel" left open-ended so the studio can still write new chapters into the same universe.
- **Why it matters for AR glasses**: Confirms this architecture is a living, still-expanding patent family — Snap keeps the foundational idea in prosecution to adapt claims as AR glasses evolve.
- **Confidence**: high (vision — front page shows the continuation chain; near-duplicate of US11099643/US11778149)

---

### US11297224B2 — Automated eyewear device sharing system
- **In one line**: Set your sharing preferences on your phone once, and photos your glasses snap get sent to the right people automatically — no fiddling on the glasses themselves.
- **How it works**: A two-device system: eyewear (frame, temple, camera, a button/input) plus a client mobile device holding a "sharing profile" (claim 1, abstract). Before you shoot, you pick a **send profile** (send immediately on connection, send after a delay, or hold for review) and an **audience profile** (last-used audience, most-recent chat, or a Story). When the glasses hand their images to the phone, the phone acts on those pre-set rules automatically. This is a form-factor enabler: it moves all the fiddly menus off the button-only glasses and onto the phone.
- **Everyday analogy**: Like a mail-forwarding order at the post office — you set the rules once, and everything that arrives afterward gets routed to the right address without you touching it.
- **Why it matters for AR glasses**: Glasses have almost no buttons or screen, so the interaction has to live elsewhere. Pre-programmed sharing lets a near-controls-free device still do something useful the instant you press one button.
- **Confidence**: high (full-text; note this is more of a software/UX patent than pure hardware)

---

### US11563886B2 — Automated eyewear device sharing system (grant continuation of US11297224)
- **In one line**: The same auto-sharing invention, re-granted with fresh claims.
- **How it works**: Continuation of application 16/587,158 (US11297224), and the published form of US20220159178. Identical abstract and the same figure: a Client Device (smartphone) holding "Set Capture and Processing Profiles" and "Set Automatic Sharing Profiles" (default/last-selected, auto send/share, delay, hold for review) paired with a Companion Device (eyewear) that pairs over WiFi/Direct and shares/posts to a network.
- **Everyday analogy**: The same recipe reprinted in a new cookbook edition.
- **Why it matters for AR glasses**: More portfolio-fencing around the phone-does-the-thinking, glasses-do-the-capturing division of labor.
- **Confidence**: high (vision — front page confirms continuation of US11297224 / prior-pub US20220159178; overlap noted)

---

### US20220159178A1 — Automated eyewear device sharing system (published application, same family)
- **In one line**: The published application form of the auto-sharing system that became US11297224/US11563886.
- **How it works**: Explicitly a continuation of application 16/587,158 (US11297224), same abstract word-for-word: capture raw images on the wearable, automate processing/uploading/audience-targeting on the phone, following profile settings chosen before capture.
- **Everyday analogy**: The published draft that later became the bound book.
- **Why it matters for AR glasses**: Same significance as the granted versions — it documents the family's breadth around offloading sharing logic to the companion phone.
- **Confidence**: high (full-text; near-duplicate of US11297224)

---

### US11451707B2 — Image capture eyewear with auto-send
- **In one line**: Little lights on the glasses let you pick who a photo goes to *before* you take it, then the shot auto-sends to that person the moment you capture it.
- **How it works**: Image-capture eyewear with a support structure, a selector (button), a camera, and a display system — e.g., LEDs on the frame that distinctly show "recipient markers" (claim 1, abstract). You assign recipients to a first and second marker; whichever marker is lit when you shoot determines who the image is transmitted to. The tiny on-frame display substitutes for a full screen, so recipient selection happens with a couple of LEDs and one button.
- **Everyday analogy**: Like the toaster-dial that's already turned to "person 2" before you push the lever down — the setting is picked in advance, so the result is delivered without a second thought.
- **Why it matters for AR glasses**: A masterclass in minimalist form-factor UX: with no touchscreen room, a single button plus a couple of indicator lights is enough to route media to the right person.
- **Confidence**: high (full-text)

---

### US11968460B2 — Image capture eyewear with auto-send (grant continuation of US11451707)
- **In one line**: The same LED-marker auto-send invention, re-granted with new claims.
- **How it works**: Continuation of application 17/218,824 (US11451707), identical abstract. The front-page flowchart spells out the flow: detect trigger of button → select assignable recipient markers for distinct presentation → capture image → store and/or transmit image + recipient ID to a personal computing device. The representative figure shows the classic round-lens Spectacles-style frame with camera hardware in the corners.
- **Everyday analogy**: The re-issued edition of the "pre-set the recipient, then shoot" idea.
- **Why it matters for AR glasses**: Reinforces Snap's fence around one-button, near-screenless media routing — a core requirement for glasses that must stay simple.
- **Confidence**: high (vision — front page confirms continuation of US11451707; overlap noted)

---

## Area synthesis — Eyewear hardware & form factor

- **The big idea**: Snap's hardware patents keep circling one problem — a full computer will not fit (or stay cool, or stay charged) inside something that still looks like a pair of glasses. Their answer is *division of labor at every level*: split the processor across two chips in the two temples, split one USB port into two data lanes, and above all split every task between the glasses (light, on-board, real-time work) and a paired phone or cloud (the heavy lifting), running in parallel. What can't be squeezed in is offloaded; what can't be controlled on a screenless frame is pushed to the phone or reduced to one button and a couple of LEDs.

- **Challenge -> breakthrough arc**: The challenge is brutally physical — no room, no heat budget, no battery, and almost no controls on a device the size of eyewear. The foundational breakthrough (US11099643 and its family US11778149 / US20230412780) is *simultaneous distributed computation*: do part of the job locally, ship the rest to your phone, and run both at once so the glasses feel fast without carrying a supercomputer. The Korean SoC patent (KR20240047454A) pushes the same philosophy down into the silicon — two chips balancing the load, one USB port doing two jobs. And the sharing/auto-send family (US11297224 / US11563886 / US20220159178 and US11451707 / US11968460) solves the *controls* half of the form-factor problem: with no touchscreen, you pre-load your intent on the phone or onto LED "recipient markers," so a single button press does something genuinely useful.

- **ELI5 one-liner**: You can't stuff a whole computer into glasses, so Snap made the glasses do the easy bits, phone-a-friend for the hard bits at the same time, and shrank all the buttons down to one press plus a couple of blinking lights.
