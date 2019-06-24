A package analysis tool.

## Design

No data element may know its parent. A file can appear in multiple packages. A package can appear in multiple distributions.

- File - A single string or buffer blob
  - Dependencies - References to other Files
  - Version - A hash of File checksums / Or a single prefixed checksum
- Package - A directly referenced group of Files
  - Dependencies - File Dependencies that cannot be found in the Package
  - Files - A map of Files by their path in the Package inter-package relationships
- Distribution - A package on a Provider
  - Origin - The source of the Distribution (e.g. local, npm, github)
  - Version - A Version identifier of the Package (e.g. semver, commit hash)
  - Package
- Project
  - Distributions
