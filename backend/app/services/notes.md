# Assignment Bugs

## Bug 1

"The revenue numbers on your dashboard don't match our internal records. We're showing different totals for March, and we're worried about accuracy for our board meeting next week."

- Cause: different timezones
- Fix: add timezone conversion before monthly revenue calculation

## Bug 2

"Something strange is happening - sometimes when we refresh the page, we see revenue numbers that look like they belong to another company. This is a serious privacy concern."

- Cause: cross-tenant "poisoned" cache
- Fix: use tenant's id in cache key

## Bug 3

Additionally, our finance team mentioned they've noticed some revenue totals that seem "slightly off" by a few cents here and there, but they couldn't pin down exactly when or why.

- Cause: floating point conversion error
- Fix: avoid casting to float on the backend side, use 2 decimal points rounding in dashboard