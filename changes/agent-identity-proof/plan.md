# Implementation Plan

## Summary

Disposable identity proof. This change shows that a branch push and a pull request made through the `naelonambul-agent` GitHub App installation token are attributed to `naelonambul-agent[bot]`, not to the owner's personal account. It is never merged.

## Files and components that change

Only this packet. `write_scope` is empty.

## Order of work

1. Commit this packet as `naelonambul-agent[bot]`.
2. Push over HTTPS with the installation token.
3. Open a pull request with the same token.

## Tests and proof

- The pull request author is `naelonambul-agent[bot]`, and so is the pushed commit's author.
- The `repository` workflow runs on the pull request. `status` reports this packet as not approved, and nothing outside the packet changes.

## Risks and mitigations

None beyond an open throwaway pull request. It is closed unmerged, and its branch is deleted after review.

## Rollback or recovery

Close the pull request and delete the `change/agent-identity-proof` branch.

## Open questions

None.
