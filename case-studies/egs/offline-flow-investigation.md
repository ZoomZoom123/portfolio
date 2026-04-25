# EGS Offline Flow Investigation

Users were being forced to re-log into the Epic Games Store during service outages. That was the complaint. I was assigned to investigate how the store handled offline and network failure states across both the desktop launcher and the web store. I worked on it alone over about 12 days, alongside other higher-priority tasks as they came in.

The biggest obstacle upfront was that I had never worked with the EGS launcher client before. I started by finding any existing test cases that touched error handling and reproducing the errors myself. I reviewed customer feedback to understand what users were actually experiencing, not just what the system was technically doing. To map which services were responsible for which errors, I cloned the repository and used Claude to generate a detailed summary of how the services connected to the store. That gave me a working picture of the system without having to reverse-engineer it from scratch.

From there, I built a service-priority matrix, tiering each of the 14+ external services by how easily a user could encounter an error state. Tier 1 was anything with direct, immediate user impact. Tier 4 was operational edge cases. The account service sat at Tier 1. When it failed, users got logged out. I also found a circuit breaker configuration issue: the account service circuit breaker was set to metricsOnly, meaning it tracked failures but did not actually trip. The safety net existed on paper but did nothing.

I documented 32 test cases across both platforms, 20 for the desktop launcher and 12 for the web store, focused on account service failures, session persistence, error boundaries, and recovery behavior. The core success criterion was simple: zero forced re-logins during account service failures.

The gap analysis turned out to be as important as the test cases themselves. The investigation revealed that catalog, entitlement, and payment services had no test coverage for failure states. Multi-service cascade failures had no coverage at all. I documented the gaps, recommended test cases for each, and laid out a phased approach for what to tackle next and in what order.

I wrote up bugs for every issue found. They were triaged and placed in the backlog.
