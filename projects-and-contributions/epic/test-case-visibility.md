# Test Case Visibility During a Product Revamp

About seven weeks into my time at Epic, we were in the middle of a product revamp, and engineers and the product and production teams had no visibility into what QA was actually testing. Test cases lived in QMetry, and QMetry was siloed off from everyone outside QA.

The obvious fix was to expand QMetry access to the rest of the team, so I raised it with the group managing the licenses. Their answer was that it would cost more and require training everyone from scratch, neither of which was a fast or cheap option given where we were in the revamp. Rather than push on a solution that had already hit a wall, I proposed moving the test cases into the repository instead, somewhere engineers already worked and didn't need new tooling or training to read. I migrated the full set of test cases from QMetry into the repo myself.

Once the test cases were visible, engineers could see exactly which ones were still manual and which had automation coverage. They started closing gaps themselves and suggesting new test cases without being asked. The approach worked well enough that we expanded it to the backend team too, and quality ownership shifted from something QA owned alone to something the whole team could see and contribute to.
