---
title: Ecosystem benchmark
---

# Ecosystem benchmark

This comparison uses public repository metadata visible on GitHub on **2026-03-23** together with the positioning stated by each library in its repository description.

## Reference set

| Library | Public positioning |
| --- | --- |
| **React Native Paper** (`callstack/react-native-paper`) | Material Design component library for React Native |
| **Tamagui** (`tamagui/tamagui`) | Style system + optional UI kit with an optimizing compiler |
| **gluestack-ui** (`gluestack/gluestack-ui`) | Copy-paste components and patterns for React and React Native |
| **React Native Elements** (`react-native-elements/react-native-elements`) | General cross-platform React Native UI toolkit |
| **NativeBase** (`GeekyAnts/NativeBase`) | Accessible mobile-first components for React Native and web |

## Public repository signals

| Library | Stars | Open issues | Discussions enabled | Recent push signal |
| --- | ---: | ---: | --- | --- |
| React Native Paper | 14,313 | 365 | Yes | 2026-03-15 |
| Tamagui | 13,836 | 92 | Yes | 2026-03-22 |
| gluestack-ui | 4,987 | 153 | Yes | 2026-03-23 |
| React Native Elements | 25,786 | 146 | Yes | 2026-01-27 |
| NativeBase | 20,389 | 379 | Yes | 2026-01-31 |

## Where React Native Paper is strongest

### 1. Clear product identity

Paper has a sharper default opinion than most of the comparison set:

- it is the **Material Design** choice,
- it has a strong theme model,
- and its component API is approachable without introducing a new styling language.

That is a real advantage over broader toolkits.

### 2. Mature contributor and documentation foundation

Compared with many UI libraries, Paper already has:

- solid issue templates,
- a Docusaurus site,
- an example app,
- and a substantial automated test suite.

The raw foundation is not the problem; prioritization and maintainer-facing guidance are.

## Where competitors currently set a better example

### Tamagui: stronger modernization story

What stands out:

- very explicit modern positioning,
- stronger “performance/compiler” narrative,
- clearer differentiation around architecture and rendering strategy.

What Paper can learn:

- publish a more explicit technical vision,
- especially around **New Architecture**, rendering, and performance trade-offs.

### gluestack-ui: stronger customization narrative

What stands out:

- the project is very clear about being a **copy-paste and pattern** system,
- which reduces confusion about ownership and customization.

What Paper can learn:

- explain when the library is intentionally opinionated,
- and where consumers should extend, compose, or replace components.

### React Native Elements: stronger “safe default” reputation

What stands out:

- large adoption footprint,
- broad familiarity as a generic UI toolkit,
- and a simpler mental model for teams that do not want a design-system opinion.

What Paper can learn:

- make upgrade safety and migration guidance more visible, so “Material Design opinionated” does not also feel “higher risk to adopt.”

### NativeBase: stronger accessibility positioning in branding

What stands out:

- accessibility is part of the public product story, not just an implementation detail.

What Paper can learn:

- move accessibility from “we support accessibility props” to “we actively prevent accessibility regressions.”

## Where React Native Paper should differentiate more aggressively

If the library is going to be “the best Material Design library for React Native,” it should be stronger in four areas:

1. **New Architecture readiness**
   - Make support explicit.
   - Test it in CI.
   - Document it.

2. **Upgrade confidence**
   - Publish supported version ranges and known incompatibilities.
   - Treat framework-upgrade regressions as top-tier issues.

3. **Accessibility quality**
   - Add explicit accessibility goals to docs and release notes.
   - Test TalkBack/VoiceOver-sensitive components more intentionally.

4. **Integration guidance**
   - Paper + React Navigation
   - Paper + forms
   - Paper + overlays/portals
   - Paper + web

## Benchmark conclusion

React Native Paper does **not** need to become Tamagui or gluestack-ui.

Its best path is to stay opinionated and ergonomic, while becoming more explicit and more disciplined in the places where competitors inspire more confidence:

- architecture stance,
- upgrade safety,
- accessibility,
- and integration documentation.
