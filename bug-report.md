# BUG-001: Interaction Raycast Fails to Detect Ancient Stone

**Project:** Ascension (Unity 6)

**Feature:** Player Interaction System

**Testing Type:** Functional Testing / Debugging / Fix Verification

**Status:** Fixed — Verification Passed

**Severity:** Medium (provisional)

## Description
Samuel was unable to interact with the Ancient Stone despite being positioned nearby and facing the object.

When the player pressed E, the Unity Console displayed:

`Samuel found nothing to interact with.`

## Steps to Reproduce
1. Launch the Ascension test scene in Unity.
2. Enter Play Mode.
3. Move Samuel close to Stone_Platform01.
4. Face the stone.
5. Press E.
6. Observe the Unity Console.

## Expected Result
The interaction raycast detects Stone_Platform01 and executes its interaction method.

The Console displays:

`Samuel inspected: Ancient Stone`

## Actual Result
The interaction did not execute.

The Console displayed:

`Samuel found nothing to interact with.`

## Investigation
- Verified that the E key triggered the interaction attempt.
- Confirmed that Stone_Platform01 had a Box Collider and InteractableObject component.
- Used Debug.DrawRay and Unity Scene Gizmos to inspect the raycast direction.
- Investigated the raycast's height and distance.
- Lowered Ray Height from 0.5 to 0.
- Increased Interaction Range from 3 to 5 during troubleshooting.

## Root Cause
The investigation indicated that the raycast's original height caused it to miss the stone's collider. The final successful configuration also used a longer interaction range.

## Fix Verification
After adjusting the raycast configuration, the Unity Console displayed:

`Raycast hit: Stone_Platform01`

`Samuel inspected: Ancient Stone`

**Result: PASS**

## Follow-up Testing
- Verify the intended 3-unit interaction range.
- Test interaction outside the maximum range.
- Test interaction while facing away.
- Test interaction with an obstructing object.

## Evidence
- Before-fix screenshot: unsuccessful interaction message.
- After-fix screenshot: successful collider detection and interaction.

## QA Skills Demonstrated
Functional testing, debugging, controlled variable testing, defect documentation, root-cause investigation, and fix verification.
