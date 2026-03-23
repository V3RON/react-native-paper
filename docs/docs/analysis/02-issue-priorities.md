---
title: Issue priorities
---

# Issue priorities

This fork currently has **0 open issues**, so the most useful signal comes from the upstream tracker referenced by the package metadata: [`callstack/react-native-paper`](https://github.com/callstack/react-native-paper/issues).

The best first fixes are the ones that either:

- block React Native upgrades,
- break common interactive components,
- or create accessibility/documentation failures for everyday usage.

## Priority 0: unblock React Native and React upgrades

These issues should be treated as release blockers because they stop teams from adopting current React Native versions.

| Issue | Why it should go first |
| --- | --- |
| `#4809` Crash on latest React Native | A crash is a hard blocker for production adoption |
| `#4810` TouchableRipple ripple effect not working in RN 0.81 | Breaks a core visual interaction after a framework upgrade |
| `#4794` Dialog.Actions spreads `compact` into `Fragment` on RN 0.81 / React 19 | Framework compatibility issues erode confidence quickly |
| `#4874` Babel plugin does not handle re-exports, causing incorrect theming | Silent theming failures create high debugging cost |
| `#4871` TypeScript errors around `Text` as JSX / `styled(Text)` | Breaks consumer builds even when runtime behavior is fine |

## Priority 1: fix repeated regressions in high-traffic components

These issues affect common UI flows and should be addressed immediately after upgrade blockers.

| Issue | Component area | Why it matters |
| --- | --- | --- |
| `#4827` Menu flashes in the top-left corner before opening | Menu | Highly visible UX defect |
| `#4763` Menu closes and fails to reopen on re-render | Menu | Real workflows become unreliable |
| `#4878` Outlined TextInput label background shows through Modal backdrop | TextInput | Breaks a common overlay composition pattern |
| `#4830` TextInput scrolling not working on Android 15+ | TextInput | Platform upgrade regression in a core form component |
| `#4873` Native TouchableRipple does not support function children/style | TouchableRipple | API inconsistency between native and web behavior |

## Priority 2: accessibility and onboarding fixes

These are high-value because they improve both UX quality and trust in the library.

| Issue | Why it matters |
| --- | --- |
| `#4881` RadioButton.Item is reachable twice with Android TalkBack | Direct accessibility regression |
| `#4844` Chip announces incorrectly to screen readers | Accessibility quality issue in a common component |
| `#4840` Expo Snack examples do not work | Slows evaluation and first-time adoption |
| `#4022` React Navigation and Portal integration question | Repeated integration confusion should become documentation |
| `#4875` Appbar subtitle deprecation confusion | Signals a mismatch between docs, API, and Material guidance |

## What these issues say about the library

### The biggest risk areas are already visible

- **Upgrade safety**: the library needs a firmer compatibility story for recent React Native and React releases.
- **Interactive overlays**: `Menu`, `Dialog`, `Portal`, and `TextInput` keep appearing in bug reports.
- **Accessibility regression prevention** is not strong enough yet.
- **Documentation debt** is turning repeated support questions into issue backlog.

### The best triage rule

If the team can only work on a small number of fixes, it should prioritize in this order:

1. **Crashes and upgrade blockers**
2. **Broken or visibly glitchy interactions in core components**
3. **Accessibility regressions**
4. **Documentation issues that repeatedly generate support traffic**
5. **Net-new feature requests**

## Recommended backlog labels

To make prioritization easier, adopt a small, opinionated label set:

- `p0-upgrade-blocker`
- `p1-core-ux`
- `p1-accessibility`
- `p2-docs-gap`
- `p3-feature-request`
- `needs-repro`
- `new-architecture`

That label model would make it much easier to separate “cannot ship safely” from “nice to have.”
