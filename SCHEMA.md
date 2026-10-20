# Question bank schema (contract between questions.js and index.html)

`questions.js` sets one global:

```js
window.QUESTION_BANK = [
  {
    id: "sig-001",            // unique, stable. prefix = topic code
    topic: "signals",         // one of the TOPICS below
    subtopic: "yellow arrow", // short free text
    q: "You are in a left-turn lane. The green arrow changes to a solid yellow arrow. You:",
    choices: [                // exactly 3, like the real CA test
      "Know the protected turn is ending and should stop if you can safely",
      "May keep turning, oncoming traffic will wait",
      "Must turn immediately"
    ],
    answer: 0,                // index into choices
    explanation: "A solid yellow arrow means the protected left turn is ending. Stop if you can do it safely; if you are already in the intersection, finish the turn. A flashing yellow arrow is different: you may turn, but you must yield.",
    source: "CA Driver Handbook, Section 7: Traffic Signals"
  }
];
```

TOPICS (code → label):
- speed: Speed limits and Basic Speed Law
- distances: Distances and numbers (signal 100 ft, 3 s, 15 ft, 18 in, 200 ft, 300/500 ft)
- signs: Signs (shapes, colors, meanings)
- signals: Traffic and pedestrian signals
- lanes: Lane lines, lane use, carpool, center turn lane, bike lanes
- rightofway: Right of way (4-way stop, pedestrians, roundabouts, emergency vehicles, school bus, mountain roads)
- turns: Turns, U-turns, left/right on red, signaling
- parking: Parking (curb colors, hills, hydrants, crosshatch, disabled)
- freeway: Freeway driving (merging, exits, lane changes, passing)
- sharing: Sharing the road (bicycles, pedestrians, motorcycles, trucks, blind spots)
- weather: Weather, night, skids, hydroplaning, headlights, fog
- alcohol: Alcohol and drugs (BAC, open container, implied consent)
- safety: Safety and equipment (seat belts, child seats, phones, headsets, airbags, children in cars)
- collisions: Collisions, insurance, reporting, points, license actions
- emergencies: Emergencies and breakdowns (brake failure, tire blowout, stuck accelerator, railroad)

Rules for every question:
- Written from the official CA Driver Handbook or the DMV's official sample tests. `source` names the section.
- Real-test style: mostly "what should you do" situations; plus signs, signals, lane lines; some exact numbers.
- Exactly 3 choices. One is clearly correct per the handbook. The other two are plausible (common wrong beliefs).
- Explanation: 2-4 sentences. State the rule, why, and the nearby rule people confuse it with.
