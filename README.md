<div align="center">

<h1>oidc-authn-authz-boundary-governance-pack</h1>

<p>
  <a href="https://pypi.org/project/oidc-authn-authz-boundary-governance-pack/"><img alt="PyPI version" src="https://img.shields.io/pypi/v/oidc-authn-authz-boundary-governance-pack.svg"></a>
  <a href="https://github.com/groupsum/oidc-authn-authz-boundary-governance-pack/actions/workflows/ci.yml"><img alt="CI" src="https://github.com/groupsum/oidc-authn-authz-boundary-governance-pack/actions/workflows/ci.yml/badge.svg?branch=master"></a>
  <a href="https://github.com/groupsum/oidc-authn-authz-boundary-governance-pack/blob/master/LICENSE"><img alt="License" src="https://img.shields.io/pypi/l/oidc-authn-authz-boundary-governance-pack.svg"></a>
</p>

</div>

`oidc-authn-authz-boundary-governance-pack` is an SSOT Registry integration pack for the trust boundary and responsibility handoff between authentication (AuthN) and authorization (AuthZ), including the safe use of OIDC ID Token and UserInfo claims as authorization inputs.

It intentionally does not duplicate authenticator, session, permission, entitlement, policy-engine, or enforcement requirements. Those belong to the focused `authentication-governance-pack` and `authorization-policy-governance-pack` distributions.

## Boundary Governed By This Pack

Authentication proves identity and authentication-event facts. Authorization independently decides whether a subject may perform an action on a resource in the current context.

This pack governs only the handoff between those surfaces and its OIDC identity-claim contract:

- ownership of the authentication producer and authorization consumer
- accepted identity artifacts and stable subject identifiers
- issuer, audience, integrity, freshness, and replay validation
- authentication time, assurance, and method indicators
- provenance-preserving identity-to-policy-context mapping
- tenant-context preservation and identity-data minimization
- fail-closed behavior before policy evaluation
- evidence that successful authentication does not imply authorization
- validation and normalization of OIDC ID Token and UserInfo identity claims
- rejection of claim presence, provider groups, or ID Token possession as direct application permission

## Pack Metadata

- Pack ID: `pack:oidc-authn-authz-boundary`
- PyPI package: `oidc-authn-authz-boundary-governance-pack`
- Import package: `oidc_authn_authz_boundary_governance_pack`
- GitHub repository: [groupsum/oidc-authn-authz-boundary-governance-pack](https://github.com/groupsum/oidc-authn-authz-boundary-governance-pack)
- Reservation owner: `extension-pack:oidc-authn-authz-boundary-governance-pack`

## Included Documents

- [`adr:authentication-and-authorization-are-separate-governance-surfaces`](https://github.com/groupsum/oidc-authn-authz-boundary-governance-pack/blob/master/src/oidc_authn_authz_boundary_governance_pack/templates/adr/ADR-1000-authentication-and-authorization-are-separate-governance-surfaces.yaml)
- [`adr:oidc-claims-identify-subjects-not-application-permissions`](https://github.com/groupsum/oidc-authn-authz-boundary-governance-pack/blob/master/src/oidc_authn_authz_boundary_governance_pack/templates/adr/ADR-1001-oidc-claims-identify-subjects-not-application-permissions.yaml)
- [`spc:authn-authz-boundary-contract`](https://github.com/groupsum/oidc-authn-authz-boundary-governance-pack/blob/master/src/oidc_authn_authz_boundary_governance_pack/templates/specs/SPEC-2000-authn-authz-boundary-contract.yaml)
- [`spc:oidc-id-token-and-userinfo-claims-contract`](https://github.com/groupsum/oidc-authn-authz-boundary-governance-pack/blob/master/src/oidc_authn_authz_boundary_governance_pack/templates/specs/SPEC-2001-oidc-id-token-and-userinfo-claims-contract.yaml)

## Install And Synchronize

```bash
uv add ssot-registry oidc-authn-authz-boundary-governance-pack
uv run ssot pack inspect oidc_authn_authz_boundary_governance_pack
uv run ssot pack preflight . oidc_authn_authz_boundary_governance_pack --all
uv run ssot pack sync . oidc_authn_authz_boundary_governance_pack --all --trust --yes
```

## Programmatic Usage

```python
from oidc_authn_authz_boundary_governance_pack import load_document_manifest, read_packaged_document_text

adr_manifest = load_document_manifest("adr")
spec_manifest = load_document_manifest("spec")
text = read_packaged_document_text("spec", "SPEC-2000-authn-authz-boundary-contract.yaml")
```

## Authority Sources

- [OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0-18.html)
- [JWT Profile for OAuth 2.0 Access Tokens, RFC 9068](https://www.rfc-editor.org/rfc/rfc9068)
- [OAuth 2.0 Security Best Current Practice, RFC 9700](https://www.rfc-editor.org/rfc/rfc9700)
- [NIST SP 800-63C-4 Federation and Assertions](https://pages.nist.gov/800-63-4/sp800-63c.html)
- [NIST SP 800-162 Attribute Based Access Control](https://csrc.nist.gov/pubs/sp/800/162/upd2/final)

## Resources

- [SSOT Registry](https://pypi.org/project/ssot-registry/)
- [Authentication governance pack](https://github.com/groupsum/authentication-governance-pack)
- [Authorization policy governance pack](https://github.com/groupsum/authorization-policy-governance-pack)
