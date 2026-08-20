# Security Baseline

This repository provides a secure-by-default application shell and explicit integration boundaries. Production use requires deployment-specific controls and security review.

## Browser boundary

- Strict Content Security Policy is declared in the document shell.
- Framing is denied with `frame-ancestors 'none'` and `X-Frame-Options: DENY`.
- `Referrer-Policy: no-referrer` is used by default.
- Unused browser capabilities are disabled through `Permissions-Policy`.
- No credentials or scientific reference structures are embedded in the frontend.

## API boundary

- Origin allowlisting is enabled.
- Request bodies are size limited.
- JSON payloads are contract-first.
- Enterprise mode requires a session token boundary.
- API responses are sent with `Cache-Control: no-store`.

## Scientific integrity

- Submitted structures should be hashed at the edge.
- Validation jobs should carry immutable job and mission identifiers.
- Secret reference structures must remain behind a protected vault boundary.
- Scientific scores and commercial reward decisions are separate records.
- Policy versions should be immutable and auditable.

## Corporate IP boundary

Production mission orchestration, customer-specific policies, confidential integrations and private deployment configuration belong in the qFoldIT corporate surface. Any source already distributed under an open-source license remains governed by that license; this document does not revoke previously granted rights.

## Production controls

Use an enterprise IdP (OIDC/SAML), short-lived credentials, hardware-backed secrets where available, TLS everywhere, private networking for the scientific cluster, malware scanning for uploads, immutable audit storage, dependency scanning, signed release artifacts, least-privilege service accounts, protected default branches and private repository access for production corporate code.
