# App name
- Earthquake Shake-Down

## Purpose
- Build a tower from columns, beams, and braces, set it on a shake table, and turn up the shaking until it falls. This is done by using a 2D physics engine such as Matter.js, which handles the collisions and collapse.

## Inputs
- Building pieces (columns, beams, braces, and floor masses) that the user places on the shake table, with joints that break when overloaded
- A shake table that moves back and forth with an amplitude and frequency the user sets, or a button that plays an earthquake ground motion
- A cost for each piece and a total cost
- A score: the strongest shaking the building survived for 10 seconds without any floor touching the ground

## Calculations
- Use Matter.js to simulate gravity, collisions, and tower collapse.
- A joint breaks when its force exceeds a breaking strength set in the app.
- Shake-table position: `x(t) = A sin(2πft)`.
- Peak acceleration for shake-table testing: `a = A(2πf)²`.
- For earthquake tests, use the largest absolute acceleration in the selected record.
- The tower fails if any floor touches the ground during the 10-second test.
- Total cost is the sum of every placed building piece's cost.
- Score is the greatest peak acceleration the tower survives for 10 seconds.
- Drop-test fall time: `t = √(2h/g)`.
- Measured shake-table frequency: `f = 10/T`.
- Measured shake-table amplitude is half the distance between its two extreme positions.

## Outputs
- An animated 2D view of the tower and shake table while the test runs.
- The selected shake-table settings or earthquake record, plus elapsed test time in seconds.
- A status message showing whether the tower survived 10 seconds or collapsed.
- A visual indication of broken joints and whether a floor touched the ground.
- The tower's total cost, in dollars.
- The strongest shaking the tower survived, shown as peak acceleration in m/s².

## Look and feel
- Use a clean, game-like layout with clear labels and readable text.
- Show the shake table and tower in a large 2D simulation area.
- Place the piece-selection controls beside the simulation area on a computer.
- Put shake settings, test controls, total cost, and score in a clearly labeled control panel.
- When the app first opens, show an empty shake table, the available building pieces, and a short instruction telling the user how to start building.
- Keep the shaking stopped until the user starts a test. Include clear buttons to start, reset, and test the tower again.
- On a phone, stack the simulation and controls vertically, resize the simulation to fit the screen, and use buttons large enough to tap easily.

## Validation
- Drop a single block from a known height and compare its fall time to
t = sqrt(2h/g). Then measure the table's motion from the animation (the time for 10 cycles and the distance between the extremes) and compare it to the frequency and amplitude you set.


## Out of scope
- The simulation will be 2D; it will not model a building in 3D.
- The app will not check building-code requirements, certify earthquake safety, or replace professional structural engineering analysis.
- The app will not provide advanced structural-analysis results or predict real-world structural performance beyond the 2D physics simulation.
- The app will use fixed building-piece types and assigned costs; it will not support user-defined materials or cost models.
- The app will include only built-in earthquake records and will not support importing, recording, editing, or uploading earthquake data.
- The app will not include user accounts, multiplayer, leaderboards, cloud storage, or saved projects across sessions.
- The app will not connect to physical shake-table equipment or use device sensors.
- The app will not include 3D graphics, sound effects, or cinematic presentation.