---
sidebar_position: 3
title: Versioning
---
### Semantic Versioning

Semantic versioning (https://semver.org/) follows the format of:
```
MAJOR.MINOR.PATCH
```
,where
- `MAJOR`: Major is incremented for breaking changes that break backward compatibility
- `MINOR`: Minor is incremented for backward-compatible functionality additions.
- `PATCH`: Patch is Incremented for backward-compatible bug fixes.

Example:
- 1.0.0: Initial stable release
- 1.0.1: Bug fixes
- 1.1.0: New features, backward-compatible
- 2.0.0: Breaking changes


MORE CONTENT ABOUT
- Tag releases in Git and GitHub.
https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases
- Automate with CI pipelines using tags.
- Deploy tagged versions / rollback

---
### Further reading
- https://semver.org/
- https://docs.npmjs.com/about-semantic-versioning