# Reusing a Server-Authoritative Testing Architecture Across Titles (PvZ2 to PvZ3)

**Role:** Senior QA Analyst, Unreleased Title
**Tools:** Postman, automated API scripting, bot-driven data simulation

## Context

On PvZ2, I'd built a Postman-based automation architecture to adversarially test the server-authoritative PvP leaderboard system — generating bot-driven traffic to probe for client-side manipulation, validate promotion/relegation logic, and confirm rewards were only issued on server-verified outcomes. When I moved onto the unreleased PvZ3 project, that same leaderboard/tournament model existed again, this time on a new set of APIs. Rather than starting from scratch, I reused the architecture and rebuilt it against PvZ3's endpoints.

## Approach

The underlying goals carried over directly, since PvZ3's leaderboard system was, like PvZ2's, server-authoritative: automated verification of the APIs, checking for security gaps, and looking for possible ways players could exploit the system. What changed was the target — I adapted the Postman scripts to PvZ3's new API surface, then used bot-generated data to exercise the same categories of leaderboard behavior:

- **Promotion, relegation, and tier stability** — confirming players moved (or stayed) in the correct tier based on server-verified results, not anything the client reported.
- **Rewards** — validating reward distribution matched actual, server-confirmed outcomes.
- **Tournament start/stop** — checking that tournament state transitions triggered and closed correctly under bot-driven load.
- **Server-authoritative data integrity** — the same core question as PvZ2: could the client be made to lie to the server, and did the server ever trust it if it tried.

I left the team and company in January 2020, before PvZ3's first public soft-launch on February 25, 2020, so this work was completed and handed off ahead of that release rather than iterated on further by me post-launch.

## Outcome

Reusing a proven architecture instead of designing adversarial API testing from zero meant PvZ3's leaderboard system got the same level of scrutiny PvZ2's had, without paying the full cost of building that approach twice. The core trust-boundary questions — can the client manipulate its own promotion, its own rewards, its own tournament state — were being asked and tested against PvZ3's APIs before I left the project.

## Why this matters

This is a case study in leverage: recognizing that a testing architecture built for one title's problem (a server-authoritative leaderboard that can't trust the client) is portable to another title with the same architecture, even on a completely different API surface. It also reflects how I approach automation generally — not as a one-off script tied to a single feature, but as reusable infrastructure built around a testing *philosophy* (assume the client will try to lie, verify the server never believes it) that outlasts any one project.
