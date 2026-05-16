# Sample Bug Report

## Overview

This is an example of how I structure bug reports in my QA work. Key principles I follow:

1. **Clear summary** — one sentence that describes the problem without ambiguity
2. **Reproducible steps** — precise, numbered, anyone on the team can follow them
3. **Expected vs Actual** — clearly separated so the developer knows exactly what's wrong
4. **Environment details** — device, OS version, app build — critical for mobile bugs
5. **Severity classification** — helps prioritise what gets fixed first
6. **Verification test cases** — so QA knows exactly what to retest after the fix

---

## Summary
**Brief description of the bug:** App does not navigate to the file list after setting a password for the first time — it remains on the Set Password screen.

---

## Steps to Reproduce
1. Install a fresh build of the app (no existing data).
2. Launch the app — the Set Password screen appears.
3. Enter a valid password (4+ characters) in both fields.
4. Tap **Set Password**.
5. Observe the app behaviour after tapping the button.

---

## Expected Behavior
After tapping **Set Password**, the app should animate the key icon, then navigate to the main file list screen within 2–3 seconds.

---

## Actual Behavior
The app animates the key icon but stays on the Set Password screen. The file list never appears. The password is saved to Keychain (confirmed: re-launching the app shows the Login screen), but navigation does not occur.

---

## Screenshots / Screen Recording
*Screen recording attached — shows the animation completing but no navigation happening.*

---

## Environment
- **Device:** iPhone 15 Pro
- **OS Version:** iOS 17.4
- **App Version:** 1.0.0 (Build 12)
- **Reproducibility:** Always (100%)

---

## Logs
```
[SceneDelegate] passwordExists: false
[LoginCoordinator] start() called
[UINavigationController] pushViewController: TabBarController
// navigation pushed but view never appeared — possible retain cycle in coordinator
```

---

## Possible Solution
`LoginCoordinator` is created as a local variable inside the completion block — it likely gets deallocated before `pushViewController` completes. The coordinator should be retained at the view controller level.

---

## Severity
- **[ ] Critical** — App crashes or data loss, blocks core functionality
- **[x] High** — Major feature broken, no workaround
- **[ ] Medium** — Feature partially broken, workaround exists
- **[ ] Low** — Minor visual or UX issue

---

## Test Cases to Verify Fix
1. Fresh install → set password → verify navigation to file list occurs within 3 seconds.
2. Set password → force-quit → relaunch → verify Login screen appears (password was saved).
3. Set password with minimum length (4 chars) → verify navigation works.
