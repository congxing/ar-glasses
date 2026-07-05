# Head-worn interaction & neural/EMG input — plain-English explainers

Two flagship "how you control the glasses" inventions from Snap's Spectacles portfolio, aimed at controlling AR glasses with no mouse, keyboard, or handheld controller — discreetly.

---

### US20240393887A1 — Micro hand gestures for controlling virtual and graphical elements

- **In one line**: The cameras already built into the glasses watch your hand, and tiny thumb movements — like sliding your thumb up and down the side of your index finger — act as an invisible dial, slider, and button to control what you see in the display.

- **How it works**: The glasses' outward-facing video cameras capture your hand, and an image-recognition model (a convolutional neural network, i.e. software trained to recognize shapes in pictures) maps out a 3D skeleton of your hand — the wrist, all the finger joints, and the fingertips. Instead of big waving motions, the system watches for "micro" gestures: it treats your extended index finger as a ruler (a "finger scale" running from the base of the finger, through the middle knuckle, to the tip) and reads exactly where your thumb is touching along it. It then mathematically stretches a virtual scale (say, a slider's full travel) to match that finger length, so a slight thumb slide moves the on-screen slider a matching amount, in real time. A tap of the thumb against the finger is a "select/click," and rotating the hand at the wrist or a sideways thumb-swipe flips to the next or previous menu item.

- **Everyday analogy**: Your own index finger becomes a touch-slider, and your thumb is the fingertip dragging along it — like running your thumb down the volume strip on the side of a device, except the "strip" is your own finger and nothing physical is there.

- **Why it matters for AR glasses**: It solves the "how do you control glasses in public without looking ridiculous or carrying a controller" problem. Because the motions are tiny thumb-on-finger movements your hand can make down at your side, control is discreet, precise (many fine increments along one finger), and needs no extra hardware — the glasses' existing cameras do all the sensing.

- **Confidence**: high (vision — read front page, full detailed description, figures 9-13, and all 20 claims)

---

### US12346500B1 — EMG speech signal detection ("silent speech")

- **In one line**: Skin sensors pick up the faint electrical crackle your face and throat muscles make when you silently mouth or even just "inner-speak" words without making a sound, and a trained model turns that into commands or text — so you can talk to your glasses without anyone hearing you.

- **How it works**: An EMG (electromyography = measuring the tiny electrical voltages muscles give off when they contract) device holds electrodes against the skin over your speech-producing muscles. When you mouth words silently or "imagine" speaking, those muscles fire at a whisper-below-speech level — the patent calls these "subthreshold muscle activation signals," its term for inner speech. The raw signal is cleaned of electrical noise, chopped into short overlapping ~27-millisecond frames, and boiled down into a feature vector describing each slice's timing and frequency content (including an STFT, a standard way to summarize a signal's frequencies). A machine-learning classifier (e.g. XGBoost, a neural network, or similar) scores each ~50ms chunk for the probability that inner speech is present, and those scores are averaged over about a quarter-second and compared to a threshold to decide "yes, they're silently speaking." A detection can trigger an action — snap a photo, scroll, pause, or feed the decoded words to a chatbot/LLM whose reply comes back visually or through an earbud, all covertly.

- **Per-user calibration**: Yes. The model is first trained on many people through a guided session — an on-screen coach (GUI) tells the subject when to silently inner-speak, when to speak out loud, and when to rest, and the system auto-labels the recordings and balances the data. That general model is then applied to (and can be retuned for) the individual wearer of the specific EMG device.

- **Everyday analogy**: Like a lip-reader who reads the muscles instead of the lips — you mouth "take a photo" with no sound, and the glasses "hear" it from the electrical twitch of your face.

- **Why it matters for AR glasses**: It's the most private, hands-free input imaginable — no voice for bystanders to overhear, no gesture to see. It lets you command glasses (and query an AI assistant) silently in a meeting, on a train, or anywhere talking aloud or waving your hands would be awkward, and it's an accessibility path for people who can't speak aloud.

- **Confidence**: high (vision — read front page, block diagrams, and the full detailed-description text; note the electrode illustrations are schematic and the invention is framed as a general EMG/wearable system that the glasses are one use of)

---

## Area synthesis — Head-worn interaction & neural/EMG input

- **The big idea**: These two patents answer the hardest unsolved question in AR glasses — how do you control them with no mouse, keyboard, or handheld controller, and without looking foolish in public? One reads tiny thumb-against-finger movements through the glasses' own cameras; the other reads the faint electrical signals of words you mouth silently. Both replace conspicuous input with something almost invisible.

- **Challenge -> breakthrough**: The challenge is that glasses have no surface to touch and no room for buttons, while big mid-air hand-waving is tiring and socially awkward, and voice commands broadcast your business to everyone nearby. The breakthrough is shrinking the interface down to the body itself: your index finger becomes a precise slider your thumb drags along (cameras do the sensing, no controller needed), and your own facial muscles become a silent microphone (skin electrodes catch inner speech before it's ever voiced). Control gets smaller, more precise, and more private at the same time.

- **ELI5 one-liner**: Instead of a remote, you steer the glasses by sliding your thumb along your finger like a tiny dial — or by silently mouthing words that only the glasses can "hear."
