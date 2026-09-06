---
name: Frontend contract fixtures
description: Preserve frozen API wire shapes in client fixtures while adapting them only at component-facing boundaries.
---

Mock fixtures for frontend-only API consumers should match the documented REST response shapes exactly, including enum values, numeric ranges, IDs, GeoJSON envelopes, and error fields. Component helpers can normalize those responses for presentation, but the fixture/client boundary must remain contract-faithful.

**Why:** A visually polished mock can still hide integration failures if its data uses invented endpoint shapes or presentation-friendly values that the live API will never return.

**How to apply:** When building a mock-first frontend, validate fixtures and client paths against the API brief before polishing individual screens.