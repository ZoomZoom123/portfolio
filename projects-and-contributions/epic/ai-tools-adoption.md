# AI Tool Evaluation and Adoption at Epic

I joined Epic in August 2025 right as the team got the green light to start exploring AI tools for QA work. I'd never used AI professionally before that, so I was starting from zero along with everyone else. My manager asked me to figure out which of our four available tools, Claude, ChatGPT, Gemini, and Copilot, was actually useful, and for what.

I tested all four against the same tasks and watched where they diverged. I started simple: turning meeting notes into documentation. Then I moved to harder things: summarizing technical docs, and eventually asking each tool to reverse-engineer how our product worked just from reading the repo. As the tasks got harder, tools started falling off one by one. Claude was the only one that held up on the genuinely complex work. I documented what worked and what didn't, then compared notes with our project SDET, who was independently seeing the same pattern. That was enough to make the call: we'd standardize on Claude Code for QA work.

Instead of keeping what I'd learned to myself, I built a context folder for the whole QA team so everyone could work with Claude consistently and get comparable results, rather than everyone rediscovering the same lessons individually. There was a ramp-up period while people got comfortable with it, but once it stuck, we were saving about 26 hours per cycle on test planning documentation alone.

That time went back into the parts of the job that actually needed a person: thinking through strategy and edge cases, instead of writing documentation by hand. Looking back, the real win wasn't picking the right tool, it was being willing to start from nothing and figure it out methodically, then making sure the whole team benefited instead of just me.
