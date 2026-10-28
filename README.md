# truesource-demo-storefront-ui

Demo storefront for [TrueSource Viewer](https://github.com/nkuhn-vmw/truesource-viewer-hub-edition).

**Intentionally vulnerable demo. Do not deploy it, do not install from it.** It contains only
manifests and lock files, written by hand: the lock files have no integrity hashes, and the
versions named below are pinned on purpose so that the viewer has something to find.

A Next.js storefront, versions locked with pnpm.

| File | Pins | What the viewer should report |
|---|---|---|
| `pnpm-lock.yaml` | `chalk` 5.6.1 (OSV `MAL-2025-46969`), `debug` 4.4.2 (`MAL-2025-46974`) | The versions published in the September 2025 npm maintainer compromise; malicious |
| `pnpm-lock.yaml` | `next` 14.1.0 | Middleware authorization bypass (CVE-2025-29927) and others |
| `pnpm-lock.yaml` | `semver` 7.5.1, `postcss` 8.4.27, `braces` 3.0.2, `micromatch` 4.0.5, `nanoid` 3.3.6 | Known vulnerabilities |
| `Dockerfile` | `node:20.9.0-alpine` | An old Node.js 20 image |
| `compose.yaml` | `nginx:1.23`, `bitnami/varnish:7.1.1` | nginx 1.23 is past its end of life |

The malicious versions were removed from the npm registry; this repository only names them.
