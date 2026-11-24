# Process Simulator

A scenario-testing tool that checks whether a set of process flows still holds up when something unexpected happens, and turns the results into prioritised requirements.

**▶ Try it live:** [buildflowwludwig.github.io/process-simulator](https://buildflowwludwig.github.io/process-simulator/) (in Swedish)

Built for a project with **Svensk Scen**, where our group mapped the flows for three roles: **visitor**, **organiser** and **Svensk Scen** itself.

## The problem
A process flow drawn on a whiteboard almost always looks complete, because it is checked against the requirements the team already had in mind. The gaps show up later, when a real situation doesn't follow the happy path. We needed a way to test the flows against reality before using them to compare solution alternatives.

## What the tool does
- **71 scenarios** of things that can go wrong or deviate (60 against version 1 of the flows, 11 against version 2)
- The group runs each scenario together: read it out loud, follow the flow step by step and find where it stops
- Every scenario has a prepared **outcome**:
  - **Confirmation:** the flow holds all the way, so the requirement is captured correctly
  - **Ambiguity:** the flow holds, but something isn't decided, so the requirement needs to be sharpened
  - **Gap:** the flow ends, so a need is missing from the requirements
- A **summary** and an exportable **log** of every run

## The thinking behind it
**Frequency matters, not just the number of gaps.** Each scenario is tagged with how often it is expected to happen. A flow that breaks on something weekly is more serious than one that breaks once a year, so the summary weighs each outcome against frequency.

**Outcomes become prioritised requirements (MoSCoW):**

| Priority | When |
|---|---|
| Must have | The flow ends on something that happens often or sometimes |
| Should have | The flow ends on something rare, or is unclear on something frequent |
| Could have | The flow is unclear on something less frequent |

Prioritisation then comes out of the validation instead of gut feeling, and it can be explained to the client.

**Requirements, not pictures.** The flows are solution-neutral. Every step places a requirement on the solution, and those requirements are what the alternatives are compared against. New requirements found in testing are often the ones that separate the alternatives.

**Honest about uncertainty.** The flows are built on our needs analysis, so they mix facts and assumptions. Frequencies are our estimates, responses are simulated, and the tool doesn't replace letting someone outside the group walk through the flows. The tool says this explicitly so the conclusions aren't oversold.

## Documentation built in
For every scenario we save the test task, what we observed (not what we thought), and the improvement made or the confirmation. Flows are saved both before and after the changes. That difference is what shows the validation was worth doing.

## Tech
A single self-contained HTML file (HTML, CSS, JavaScript) with no dependencies or backend. Built with AI-assisted development (Claude).
