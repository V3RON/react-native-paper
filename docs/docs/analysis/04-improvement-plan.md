---
title: Improvement plan
---

# Improvement plan

This plan is intentionally pragmatic: it focuses on the smallest set of changes that would produce the biggest DX and UX gains.

## Phase 1: make support expectations explicit (0-30 days)

### 1. Publish a support matrix

Add one maintainer-facing and user-facing document that answers:

- Which React Native versions are supported?
- Which React versions are supported?
- Which Expo ranges are validated?
- What does “New Architecture supported” mean in practice?

### 2. Align the example app with the root package

The example app should track the same React Native baseline as `/package.json` wherever possible. If it cannot, the drift should be documented prominently.

### 3. Introduce priority labels and a short triage policy

Codify:

- upgrade blockers,
- core UX regressions,
- accessibility regressions,
- docs gaps,
- and feature requests.

This does more for maintainer focus than adding more process documents.

## Phase 2: reduce regression hotspots (30-90 days)

### 4. Refactor and harden the most failure-prone components

Do this in order:

1. `Menu`
2. `TextInput`
3. `Dialog` / `Portal`
4. `TouchableRipple`
5. `BottomNavigationBar`

The goal is not a broad rewrite. The goal is to extract the logic that is most sensitive to:

- measurement,
- animation timing,
- focus behavior,
- overlays,
- and platform-version changes.

### 5. Add targeted regression tests instead of only broader suites

Add focused behavior tests for:

- menu reopen after re-render,
- anchored menu positioning,
- text input rendering behind translucent overlays,
- TalkBack/VoiceOver semantics,
- and React 19 / recent React Native compatibility edges.

## Phase 3: improve adoption and self-service (60-120 days)

### 6. Fill the highest-value documentation gaps

Recommended new guides:

- New Architecture support
- Troubleshooting
- React Navigation + Portal patterns
- Forms and validation patterns
- Accessibility expectations for Paper components

### 7. Turn repeated issue themes into docs before adding features

The upstream tracker already shows recurring questions in areas like:

- overlays,
- navigation integration,
- theming,
- and component behavior differences across platforms.

Every question answered only in issues is a future support ticket waiting to happen.

## Phase 4: improve project health signals (90-180 days)

### 8. Publish a lightweight roadmap

A roadmap does not need to be large. It only needs to answer:

- what is being stabilized now,
- what is intentionally deferred,
- and what criteria will unlock larger feature work.

### 9. Add release-quality gates around compatibility

Before each release, verify:

- root typecheck,
- root tests,
- lint,
- example app install and smoke validation,
- and compatibility notes for any React Native or React version changes.

## Recommended order of execution

If only a few things can be done, do them in this order:

1. Support matrix + New Architecture guide
2. Upgrade-blocker triage
3. `Menu` and `TextInput` stabilization
4. Accessibility regression fixes
5. Integration and troubleshooting docs
6. Roadmap publication

## Success criteria

The library is in a meaningfully better state when:

- consumers know whether their React Native stack is supported before opening an issue,
- upgrade regressions are rare and clearly prioritized,
- core interactive components stop producing recurring issue themes,
- accessibility bugs are treated like product bugs,
- and the docs answer common integration questions without sending users to issue threads.
