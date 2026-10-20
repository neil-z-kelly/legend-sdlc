# AGENTS.md

legend-sdlc is a fork of a FINOS project (finos/legend-sdlc) used for a delegated, supervised framework-upgrade demo. The default branch is pinned to upstream `eac32cb7a125`; never sync it with upstream and never push to it directly — every change goes through a **draft pull request**.

## Toolchain
- JDK 17 (Temurin), Maven 3.9

## Build
```
mvn -q -DskipTests install -pl '!legend-sdlc-backend-gitlab'
```

## Test
```
mvn -q test -pl '!legend-sdlc-backend-gitlab'
```

**Always exclude** `-pl '!legend-sdlc-backend-gitlab'` — that module needs a GitLab token this environment does not have.

## Rules
- Never edit anything under `.github/workflows/` (release/docker/publish workflows were intentionally removed in this fork).
- Never delete, `@Ignore`, or weaken tests to get a build green; document irreducible failures in the PR body instead.
- Touch only `pom.xml`, `CHANGELOG.md`, and the `src` files an upgrade requires.
