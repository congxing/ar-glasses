# Health-sensing smart eyewear (Part B) — Facense Ltd. patents

*Note on the set:* All six are from the same inventor team (Tzvieli, Thieberger, Frank / Facense Ltd.) and share overlapping figures and text. Two pairs are essentially the same invention in different legal stages: **US20180096198A1 is the pre-grant application of US10216981B2** (same app. no. 15/833,158, skin-color eyeglasses), and **US20190313915A1 shares the same application (16/453,993) as US10667697B2** (posture + blood-pressure), published under a broader title. The other two (US20180092542A1 and US20180094982A1) are thermal-camera application publications addressing confounding substances and environmental correction.

---

### US10216981B2 — Eyeglasses that measure facial skin-color changes (GRANTED)
- **In one line**: Glasses with a tiny camera aimed at your face read invisible color shifts in your skin to measure heart rate, breathing, and even hidden emotions.
- **How it works**: An inward-facing visible-light camera watches regions like the forehead, nose, and cheek. Each heartbeat pushes blood through the skin and changes its color by an amount too subtle for the eye to see; the computer tracks these "facial skin color changes" (a camera-based version of the pulse signal doctors call photoplethysmography, or PPG). A second, outward-facing camera measures the surrounding light so the system can subtract the effect of changing ambient lighting and avoid false readings.
- **Everyday analogy**: Like the pulse-oximeter glow on a fingertip clip, but done at a distance with an ordinary camera watching your face blush and un-blush with every heartbeat.
- **Why it matters for AR glasses**: Turns eyewear you already wear into a passive, contactless vital-signs monitor, and can surface emotional states that don't show up in facial expression - useful for wellness, affective computing, and adaptive interfaces.
- **Confidence**: high (full-text: abstract, summary, and claims read)

### US20180096198A1 — Eyeglasses that measure facial skin-color changes (APPLICATION of the above)
- **In one line**: The published patent application for the same skin-color-reading glasses that later granted as US10216981B2.
- **How it works**: Identical core mechanism - an inward-facing visible-light camera detects facial skin color changes to extract heart rate, heart-rate variability, breathing rate, and hidden emotional responses, optionally correcting for ambient light with an outward-facing camera. This is the earlier-published version of the same filing, so it captures the invention before the claims were narrowed for grant.
- **Everyday analogy**: The rough draft of the same idea - a color-reading blush-detector built into glasses, filed publicly before the patent office finalized it.
- **Why it matters for AR glasses**: Same significance as the granted patent; its value is mainly as the earlier priority record establishing the claim territory.
- **Confidence**: high (full-text; confirmed same application number 15/833,158 as US10216981B2)

### US10667697B2 — Identification of posture-related syncope using head-mounted sensors (GRANTED)
- **In one line**: Glasses that catch the blood-pressure drop that makes people feel faint when they stand up too fast.
- **How it works**: A head-mounted sensor measures the pulse signal (PPG) at a spot on the head, while a head-mounted camera watches your posture. The computer converts the pulse into systolic and diastolic blood-pressure values and flags "orthostatic hypotension" - a dangerous pressure drop - when the numbers fall past a threshold within seconds of moving from lying to sitting, or sitting to standing. It can also compare pulse-arrival timing between the head and a second spot (e.g., a wrist device) to sharpen the reading.
- **Everyday analogy**: Like a blood-pressure cuff that knows you just stood up and watches for the head-rush that could make you black out.
- **Why it matters for AR glasses**: Fall and fainting detection is a marquee health-safety use case for always-on eyewear, especially for older users; doing it from the head where posture is already tracked is a natural fit.
- **Confidence**: high (full-text: abstract, summary, and claim 1 read)

### US20190313915A1 — Posture-adjusted calculation of physiological signals (APPLICATION, same filing as US10667697B2)
- **In one line**: The broader-titled application from the same filing, covering the idea that vital-sign math must change depending on whether you're standing, sitting, or lying down.
- **How it works**: The same head-mounted PPG-plus-posture-camera setup, but framed around a general principle: for the *identical* pulse signal, the computer deliberately outputs *different* values for blood pressure, cardiac output, or tissue perfusion depending on body posture. Posture changes how blood pools and flows, so ignoring it corrupts the numbers; this invention makes posture an explicit input to the calculation.
- **Everyday analogy**: Like a scale that automatically corrects for whether you're weighing yourself on carpet or tile - same raw reading, adjusted answer based on context.
- **Why it matters for AR glasses**: Establishes the general posture-correction claim underlying reliable, everyday vital-sign tracking on a device worn during constant movement and position changes.
- **Confidence**: high (full-text; confirmed same application number 16/453,993 as US10667697B2)

### US20180092542A1 — Detecting physiological responses while accounting for consumption of confounding substances (APPLICATION)
- **In one line**: Face-reading glasses that don't get fooled when caffeine, alcohol, nicotine, or medication changes your body's signals.
- **How it works**: An inward-facing thermal (heat) camera measures temperature at facial regions to infer physiological responses. The catch: substances like a coffee, a drink, a cigarette, or a pill shift those readings on their own. The system takes in an indication that you've consumed such a substance and uses a machine-learning model - trained on data both with and without the substance's effect - to interpret the measurement correctly rather than misreading the drug's effect as a real physiological change.
- **Everyday analogy**: Like a breathalyzer-aware fitness tracker that knows "her heart rate is up because of the espresso, not because she's stressed."
- **Why it matters for AR glasses**: Confounder-awareness is what separates a gimmick from a trustworthy health sensor; real-world wearers eat, drink, and medicate constantly, and accounting for it is essential for credible readings.
- **Confidence**: high (full-text: abstract and summary read; application only, not yet granted)

### US20180094982A1 — Eyeglasses having inward-facing and outward-facing thermal cameras (APPLICATION)
- **In one line**: Glasses with two heat cameras - one on your face, one on the world - so room temperature and drafts don't corrupt your body-heat readings.
- **How it works**: An inward-facing thermal camera measures heat at a facial region of interest (positioned so it doesn't block or touch that region), while an outward-facing thermal camera measures the temperature of the surrounding environment. A computer feeds both into a machine-learning model, using the environmental reading to cancel out effects of a hot room, a cold wind, or sunlight so the physiological signal it detects reflects your body, not your surroundings.
- **Everyday analogy**: Like noise-cancelling headphones for temperature - one sensor listens to your face, the other listens to the room, and the system subtracts the room.
- **Why it matters for AR glasses**: Thermal sensing from eyewear enables contactless fever, stress, and breathing detection; the outward camera is the key trick that makes it work outside a controlled lab.
- **Confidence**: high (full-text: abstract and summary read; application only, not yet granted)

---

## Area synthesis — Health-sensing smart eyewear (part B)

- **The big idea**: This Facense portfolio turns ordinary-looking eyeglasses into a passive, contactless medical sensor by pointing tiny cameras - both visible-light and thermal - at the wearer's face. From subtle skin-color shifts and heat patterns, the glasses read heart rate, blood pressure, breathing, and even hidden emotions without ever touching the skin with a cuff or electrode.

- **Challenge → breakthrough arc**: The core signals - a blush of blood flow, a flush of heat - are real but tiny, and they are easily drowned out by the messiness of real life: changing room light, a cold breeze, the caffeine in your coffee, or simply standing up and making blood rush from your head. The breakthrough across these patents is not a single new sensor but a systematic war on those confounders: an outward-facing camera to subtract ambient light and room temperature, a posture camera so the same pulse yields the right blood-pressure number in every body position, and machine-learning models that explicitly account for substances like alcohol and medication. Together they move face-sensing from a lab curiosity toward a reading you could actually trust while walking around.

- **ELI5 one-liner**: Smart glasses that watch your face blush and warm up with each heartbeat to check your health - and are clever enough not to be fooled by the lighting, the weather, your coffee, or whether you're standing or lying down.
