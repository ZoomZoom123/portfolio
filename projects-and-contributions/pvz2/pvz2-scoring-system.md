# PvZ2 Scoring System

PvZ2 had a retention problem. DAU would climb when a new world shipped and fall back down once the novelty wore off. The team needed something to keep players engaged between content drops. A scoring system had been sitting in the backlog for years. During an internal game jam, I took it on by myself.

The core idea was that winning a level shouldn't be enough. The score should reflect how well you won. I built it around what the game already rewarded and punished, but never tracked. Basic zombies were worth 100 points. Gargantuars were worth 5,000. Each of the 25 zombie types had a defined value. For every tile a zombie advanced toward your home base before you stopped it, you lost 20 points. If a plant was eaten, you lost points scaled to that plant's value. Premium plants were worth more than base plants. And if a lawnmower was consumed, the level score went to zero instead of the completion bonus. The safety net should feel like a failure, not a fallback.

The output was a 0 to 3-star rating per level and an aggregate rating for the whole world. I worked with the UI artist on mockups, so it wasn't just a spreadsheet; it looked like something real.

I documented everything in Confluence, built out the calculations in Excel for all 25 zombie types and the full plant roster, presented it to the team at the end of camp, and collected feedback. Then I got moved to PvZ Heroes to help spin up QA for that team, which was in alpha.

The lead designer took my document and modified it. They ran internal playtest sessions with a leaderboard to test whether the system actually changed how people engaged with the game. I heard about it secondhand.

After PvZ Heroes shipped, I came back and worked on the PvP mode, which was built on the scoring system. It wasn't head-to-head; it matched you against a stored score from someone in your bracket. You were competing against someone's best run, not a live opponent. I also participated in the company-wide playtest before launch.

When the scoring mode shipped, DAU went up. Retention improved. Transactions increased.
