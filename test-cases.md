# Ascension — Interaction System Test Cases

**Environment:** Unity 6, Windows, Ascension Terrain Prototype

| Test ID | Test Scenario | Expected Result | Status |
|---|---|---|---|
| TC-001 | Press E while facing Ancient Stone in successful test configuration | Interaction executes | PASS |
| TC-002 | Raycast intersects Stone_Platform01 | Console identifies collider | PASS |
| TC-003 | InteractableObject component receives interaction | Console displays inspection message | PASS |
| TC-004 | Press E outside interaction range | No interaction occurs | NOT RUN |
| TC-005 | Press E while facing away from stone | No interaction occurs | NOT RUN |
| TC-006 | Place another collider between Samuel and the stone | Interaction does not pass through obstruction | NOT RUN |
| TC-007 | Restore interaction range to 3 units and retest | Interaction succeeds within intended range | NOT RUN |

## Test Execution Summary

**Executed:** 3

**Passed:** 3

**Failed:** 0

**Not Run:** 4

## Notes
The successful interaction path was verified using Unity Console messages. Negative testing, obstruction testing, and final interaction-range verification remain outstanding.
