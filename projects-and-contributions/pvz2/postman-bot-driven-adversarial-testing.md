# Adversarial Testing of a Server-Authoritative PvP System (Plants vs. Zombies 2)

**Role:** Senior QA Analyst, Live Service Game
**Tools:** Postman, automated API scripting, bot-driven data simulation

## Context

PvZ2 was largely a client-authoritative game, meaning the client handled most game logic and state locally for performance and responsiveness. However, the PvP leaderboard and tournament system was deliberately built as an exception: strictly server-authoritative. Because this system directly controlled competitive rankings, promotion/relegation between tournament tiers, and reward distribution, the team couldn't afford to trust anything the client reported about it. Any manipulation at the client level needed to be structurally impossible to act on server-side.

My job was to confirm that boundary actually held under real adversarial pressure, not just in code review, but in practice.

## Approach

I built a Postman-based automation script originally intended for straightforward API verification, then extended it to generate bot-driven traffic that simulated large volumes of players interacting with the PvP leaderboard system. This let me test the system the way a motivated bad actor would, rather than the way a typical QA pass would.

Specifically, the bot data was used to:

- **Stress-test tournament state transitions** — validating promotion and relegation logic held up correctly across tier boundaries under high volume and unusual sequences of match results.
- **Probe for client-side manipulation vectors** — attempting to influence rankings, scores, or rewards in ways that should only have been possible if server authority had a gap.
- **Surface bad-actor/cheating patterns** — simulating behaviors consistent with known cheating strategies (score manipulation, rapid-fire match submission, out-of-order state changes) to confirm detection and rejection logic caught them.
- **Validate reward distribution integrity** — confirming rewards were only issued based on server-verified outcomes, never client-reported ones.
- **Check for downstream security issues** — looking for cases where a compromised or modified client could cause unintended server-side effects.

## Outcome

This work confirmed the server-authoritative boundary was holding as designed, while also surfacing edge cases in tournament end/transition logic that weren't caught by standard functional testing. It shifted my own approach to QA on systems with mixed trust models: for any feature carrying real player-facing stakes (competitive integrity, economy, rewards), the right question isn't just "does this work," it's "can this be made to lie to itself."

## Why this matters

This is the kind of adversarial, security-minded QA thinking that generic functional/regression testing doesn't require: understanding *why* an architectural trust boundary exists, then deliberately trying to break it from the position of someone who wants to exploit it, not just someone verifying a feature spec.
