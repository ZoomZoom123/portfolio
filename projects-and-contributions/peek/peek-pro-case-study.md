# Peek Pro 7, Client Issue Resolution

Peek Travel runs booking and point-of-sale software for tour and activity
operators. I joined as a Senior QA Engineer working on Peek Pro 7, the
platform's POS and reservation system, at a point where partner-reported
issues needed a dedicated triage process.

I worked through client issue tickets by severity, replicating problems
across individual partner configurations rather than testing against a
single reference setup. Each operator ran their own combination of POS
hardware, reservation rules, and integrations, so an issue that looked
simple in isolation often only reproduced under a specific partner's setup.

Beyond reactive triage, I validated new features against existing client
configurations before release, checking that a change built for one
partner's workflow wouldn't break another's. That meant testing releases
against the messiness of real, varied client setups instead of a clean
staging environment.
