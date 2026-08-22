# From Manual QA to Team Quality Standard: Learning C# Test Automation on an Unreleased Title (PvZ3)

**Role:** Senior QA Analyst, Unreleased Title
**Tools:** C#, Visual Studio, in-house automation framework (game built in C++)

## Context

On an unreleased Plants vs. Zombies title, a large set of test cases were still fully manual, slow enough to be a real drag on both the internal dev QA team and the external QA vendor running regression passes. The game itself was built in C++, but the studio's in-house automation system was written in C#, so automating these cases meant working across that language boundary rather than inside the game's native code.

I didn't come in as an automation engineer. I came in as a Senior QA Analyst who wanted to close that gap, and the QA Engineering team was willing to teach me how.

## Approach

I started with a weekly mentorship with a QA Engineer, learning C# from close to scratch and getting oriented in the in-house automation framework and Visual Studio. As I got more comfortable, the relationship shifted from guided learning to self-driven work: I'd pick up manual test cases, automate them, and submit the work for code and peer review from the QAE rather than working step-by-step alongside them.

Beyond straightforward test automation, part of the work involved building dev cheats into the automation tooling: hooks that let QA jump to specific game states, unlock features, or skip progression gates that would otherwise take real playtime to reach. Without those, a lot of the manual cases would have stayed manual by necessity, since automated coverage is only as fast as the slowest path to the state you're testing.

## Outcome

The cases I automated reduced the manual burden on both the internal dev QA team and the external QA vendor, freeing up time for the kind of exploratory and judgment-based testing that doesn't automate well. Just as important, the review relationship with the QAE meant the code that shipped into the shared automation system met the same bar as work written by engineers on that team, not a lower one carved out for QA-authored contributions.

These tests didn't stay a QA-side convenience. They became part of engineering's golden path. Before code could go up for review, it had to pass the automation tests locally in the engineer's own editor environment. Once code was merged into the branch, the same tests ran again, this time against a real build installed on device (both Android and iPhone), to confirm the change hadn't broken the build. In effect, the coverage I wrote became a required gate on the engineering side, not just a QA reporting tool.

## Why this matters

This case traces a full arc: starting under mentorship with no C# background, moving to self-sufficient, peer-reviewed contribution, and ending with work that engineering trusted enough to fold into their own pre-review and pre-merge gates. That progression, from learner to a required part of the team's quality bar, is hands-on evidence of the automation depth behind the toolkit line on my resume, not just adjacent exposure. Building tooling like the dev cheats also shows I was thinking about what makes automation *possible* in the first place, not just running tests once someone else made that possible. The fact that the tests ran on real Android and iPhone builds, not just in an editor, speaks to the reliability bar this work had to meet: it wasn't disposable QA scripting, it was infrastructure the team relied on.
