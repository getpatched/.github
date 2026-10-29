# GetPatched

![GetPatched security-fix workflow](https://raw.githubusercontent.com/getpatched/.github/refs/heads/main/profile/banner.png)

### Security fixes for software that still matters.

GetPatched maintains selected software still used on Ubuntu 20.04 LTS (Focal). We backport upstream security fixes to public, non-ESM Ubuntu package sources, build the packages, and validate each release with targeted regression tests and published evidence. We maintain selected packages; this is not security support for the complete Ubuntu operating system, and GetPatched is not affiliated with Canonical.

## Initial pilot

The first release targets **Ubuntu 20.04 LTS (Focal), amd64**. Package versions are refreshed from Ubuntu's latest public non-ESM source indexes before release.

| Package | Pilot security issue | Planned availability |
| --- | --- | --- |
| `libxml2` | CVE-2025-49794 | Seven-day sponsor early access, then public |
| `libarchive` | CVE-2026-4111 | Public immediately |

These are pilot candidates and planned access policies, not claims that packages are available. **No GetPatched packages are published for installation yet.** Each release must pass source and version checks, package-specific regressions, vulnerability evidence, signed APT repository checks, and access-control checks.

## How releases work

1. Select a security fix and verify the affected public Ubuntu package source.
2. Backport the fix and build the Ubuntu package with a reproducible recipe.
3. Test the vulnerable baseline and patched package, then retain reports and package provenance.
4. Publish signed APT metadata and binaries only after release checks pass.
5. For selected packages, provide sponsor early access for seven days before making the same package public. Other packages are public immediately.

The access policy applies to package downloads during the early period. Sponsorship does not change the package source or grant access to unrelated services.

## Project repositories

- [Platform](https://github.com/getpatched/platform) — catalogue, repository service, and release workflows.
- [libxml2 packaging](https://github.com/getpatched/packaging-libxml2) — source packaging and fix verification.
- [libarchive packaging](https://github.com/getpatched/packaging-libarchive) — source packaging and fix verification.

## Support and scope

The initial compatibility scope is **Ubuntu 20.04 LTS (Focal), amd64**, and only the packages listed in the live catalogue. Ubuntu Pro/ESM packages and other Ubuntu releases are outside this pilot's support scope. Check [getpatched.dev](https://getpatched.dev) for current package status and installation instructions; do not add an APT source until a release is published there.
