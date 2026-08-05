# PvZ2 Staging-to-Production Validation Tool

At PopCap, we validated staging-to-production content for Plants vs. Zombies 2 by hand before every release. It was tedious and slow, and subtle changes kept slipping past us anyway. I didn't have a coding background beyond what I was picking up on Codecademy at the time, but I wanted to fix it regardless.

I wrote a Python script that parsed the tar folder structure for a release and generated a side-by-side HTML report showing exactly what had been added, removed, or modified between staging and production. Once I had something working, I found an SWE 2 on the team and asked for code review and mentorship, since I knew my first pass wouldn't hold up on its own. I refined the script with their feedback until it was solid enough to hand off.

The tool saved QA about 20 hours per release cycle and became a standard part of the release process across the team. It also cut down on the human error that came with eyeballing folder diffs by hand, and caught production risks before they shipped. The bigger lesson for me was that not having a formal engineering background wasn't a real blocker, I just had to be willing to try, get it wrong, and ask someone who knew more than me for help.
