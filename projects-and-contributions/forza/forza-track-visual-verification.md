# Forza Motorsport (2023) -- Track Visual Verification

Turn 10 had a manual process for visually verifying track assets before
sign-off from the content team to the larger production pipeline. For each
track submission, someone had to launch the game on an Xbox devkit, drive
the car around, and capture images across multiple weather conditions by
hand. It didn't scale.

The team had a tool -- DMV Field Office, a C# application that automated
the whole process: connecting to devkits over IP, launching Forza with
scripted configuration, running AI-controlled laps, and capturing frames
across Day, Night, and Wet conditions. It also verified each image on
capture and retried on failure, with full logging. I didn't write it from
scratch -- I inherited it, kept it updated, and ran it as part of the track
submission workflow.

The tool got adopted on additional tracks. Kyalami and Laguna Seca were
both in the run configuration I maintained. The sign-off process that
previously required someone to do this by hand became something the content
team could rely on from consistent, automated results.
