---
sidebar_position: 3
title: Versioning
---
 Versioning helps developers track and document changes made to the software over time, making it easier to identify when and why a specific change was introduced. Versioning enables developers to revert to a previous version of the software if a bug or issue is introduced in a newer version. It also helps communicate updates and changes to users, making it clear which features or fixes are included in a specific release.

### Semantic Versioning

Semantic versioning is s one of the most common and widely used versioning systems in software development. Semantic versioning (https://semver.org/) follows the format of:
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
---
### Further reading
- https://semver.org/
- https://docs.npmjs.com/about-semantic-versioning