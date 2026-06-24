# Security Policy

This is an educational / portfolio project demonstrating a secure container
build pipeline. It is not intended for production use as-is.

## Reporting a vulnerability

If you find a security issue in this repo, please:

- Open a GitHub issue

Please do not include exploit details in public issues for anything sensitive —
email first and I'll respond before disclosure.

## How this project handles security

- **CI security gate** — every build is scanned by [Trivy](https://github.com/aquasecurity/trivy).
  HIGH and CRITICAL vulnerabilities fail the build.
- **Image hardening** — multi-stage build, non-root runtime user, minimal final image.
- **Pinned base images** — base images are pinned by digest, not floating tags.
- **SBOM** — a Software Bill of Materials is generated with [Syft](https://github.com/anchore/syft).
- **Second opinion** — images are also scanned with Docker Scout.
- **Documented exceptions** — accepted base-image CVEs are listed and justified in `.trivyignore`.

## Supported versions

Only the `main` branch is maintained.
