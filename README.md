<div align="center">

<h1>authnz-policy-governance-pack</h1>

<p>
  <a href="https://pypi.org/project/authnz-policy-governance-pack/"><img alt="PyPI version" src="https://img.shields.io/pypi/v/authnz-policy-governance-pack.svg"></a>
  <a href="https://github.com/groupsum/authnz-policy-governance-pack/actions/workflows/ci.yml"><img alt="CI" src="https://github.com/groupsum/authnz-policy-governance-pack/actions/workflows/ci.yml/badge.svg?branch=master"></a>
  <a href="https://github.com/groupsum/authnz-policy-governance-pack/blob/master/LICENSE"><img alt="License" src="https://img.shields.io/pypi/l/authnz-policy-governance-pack.svg"></a>
</p>

</div>

`authnz-policy-governance-pack` is an SSOT Registry integration pack for the trust boundary and responsibility handoff between authentication (AuthN) and authorization (AuthZ).

It intentionally does not duplicate authenticator, session, permission, entitlement, policy-engine, or enforcement requirements. Those belong to the focused `authentication-governance-pack` and `authorization-policy-governance-pack` distributions.

## Boundary Governed By This Pack

Authentication proves identity and authentication-event facts. Authorization independently decides whether a subject may perform an action on a resource in the current context.

This pack governs only the handoff between those surfaces:

- ownership of the authentication producer and authorization consumer
- accepted identity artifacts and stable subject identifiers
- issuer, audience, integrity, freshness, and replay validation
- authentication time, assurance, and method indicators
- provenance-preserving identity-to-policy-context mapping
- tenant-context preservation and identity-data minimization
- fail-closed behavior before policy evaluation
- evidence that successful authentication does not imply authorization

## Pack Metadata

- Pack ID: `pack:authnz-policy`
- PyPI package: `authnz-policy-governance-pack`
- Import package: `authnz_policy_governance_pack`
- GitHub repository: [groupsum/authnz-policy-governance-pack](https://github.com/groupsum/authnz-policy-governance-pack)
- Reservation owner: `extension-pack:authnz-policy-governance-pack`

## Included Documents

- [`adr:authentication-and-authorization-are-separate-governance-surfaces`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1000-authentication-and-authorization-are-separate-governance-surfaces.yaml)
- [`spc:authn-authz-boundary-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2000-authn-authz-boundary-contract.yaml)

## Install And Synchronize

```bash
uv add ssot-registry authnz-policy-governance-pack
uv run ssot pack inspect authnz_policy_governance_pack
uv run ssot pack preflight . authnz_policy_governance_pack --all
uv run ssot pack sync . authnz_policy_governance_pack --all --trust --yes
```

## Programmatic Usage

```python
from authnz_policy_governance_pack import load_document_manifest, read_packaged_document_text

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
