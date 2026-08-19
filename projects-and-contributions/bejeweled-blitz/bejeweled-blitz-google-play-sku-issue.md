# Bejeweled Blitz, Catching a Google Play SKU Limit Issue with Charles Proxy

While working on Bejeweled Blitz, I used Charles Proxy to intercept and inspect the raw API traffic between the game client and the Google Play Store backend, rather than relying only on what the Play Console surfaced. Buried in one of those API responses was a warning that the game had exceeded 20 active SKUs, a Google Play limit that ended up shutting down the store system for the game entirely.

The warning was invisible anywhere our product manager could see it. It never appeared in the Play Console dashboard the team used day to day, only in the raw API response itself. Without proxying the traffic directly, this would have stayed hidden until players started reporting broken purchases, with no clear reason why.

I escalated the finding to the PM with the API response as evidence, since the issue wasn't reproducible from the Play Console alone. The PM traced the excess SKUs to expired holiday bundles that were never cleaned up and removed them, bringing the count back under the 20-SKU limit and restoring the store. The PM estimated the outage was costing roughly $10,000 an hour, and catching it through the API call instead of waiting on player reports meant we avoided a significant chunk of that loss.

The bigger takeaway for me was that platform-level constraints like store SKU limits can fail silently if you only trust what a vendor's dashboard chooses to surface. Proxying the traffic gave us ground truth the UI didn't, and it became a habit I carried into later QA work: when a system behaves unexpectedly, check what's actually being sent and received, not just what the front end reports.
