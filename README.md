<div align="center">

<h1>authnz-policy-governance-pack</h1>

<p>
  <a href="https://pypi.org/project/authnz-policy-governance-pack/"><img alt="PyPI version" src="https://img.shields.io/pypi/v/authnz-policy-governance-pack.svg"></a>
  <a href="https://pepy.tech/projects/authnz-policy-governance-pack"><img alt="Downloads" src="https://static.pepy.tech/badge/authnz-policy-governance-pack"></a>
  <a href="https://hits.sh/github.com/groupsum/authnz-policy-governance-pack/"><img alt="Hits" src="https://hits.sh/github.com/groupsum/authnz-policy-governance-pack.svg"></a>
  <a href="https://pypi.org/project/authnz-policy-governance-pack/"><img alt="Python versions" src="https://img.shields.io/pypi/pyversions/authnz-policy-governance-pack.svg"></a>
  <a href="https://github.com/groupsum/authnz-policy-governance-pack/blob/master/LICENSE"><img alt="License" src="https://img.shields.io/pypi/l/authnz-policy-governance-pack.svg"></a>
  <a href="https://github.com/groupsum/authnz-policy-governance-pack/actions/workflows/ci.yml"><img alt="CI" src="https://github.com/groupsum/authnz-policy-governance-pack/actions/workflows/ci.yml/badge.svg?branch=master"></a>
</p>

<p>
  <a href="https://github.com/groupsum/authnz-policy-governance-pack"><img alt="GitHub repo" src="https://img.shields.io/badge/GitHub-groupsum%2Fauthnz--policy--governance--pack-181717?logo=github"></a>
</p>

</div>

`authnz-policy-governance-pack` is an SSOT Registry pack for authentication and authorization boundaries, OIDC claims, OAuth scopes, permissions, entitlements, access-control models, PDP/PEP/PIP/PAP architecture, policy gateways, and policy-as-code engines such as Cedar and OPA/Rego.

It gives product, platform, identity, security, compliance, and application teams a reusable ADR/SPEC starting point for repositories that need to govern identity claims, delegated grants, access-token validation, runtime permissions, provisioned entitlements, RBAC, ABAC, PBAC, ReBAC, XACML vocabulary, Cedar, OPA/Rego, policy gateways, authorization audit evidence, and deny-path release gates.

## What Is An SSOT Registry Pack?

An SSOT Registry pack is an installable package of governed Architecture Decision Records (ADRs) and Specifications (SPECs) for [`ssot-registry`](https://pypi.org/project/ssot-registry/). The pack supplies reusable decision and requirement documents that downstream repositories can synchronize into their local `.ssot` registry and link to features, tests, claims, evidence, and releases.

This makes governance portable. A project can adopt the pack, synchronize the documents, list the active requirements, and connect local implementation or test work to the shared IDs.

## Why This Pack Exists

Authentication and authorization fail when identity facts, OAuth grants, application permissions, provisioned entitlements, and policy decisions are treated as interchangeable. Teams need stable governance that separates who the subject is, what a client was delegated to request, what a resource server validated, what the application permits, and which policy engine made the decision.

This pack helps teams:

- separate authentication, OAuth tokening, and application authorization responsibilities
- distinguish OIDC claims, OAuth scopes, permissions, roles, groups, entitlements, and policy decisions
- govern PDP, PEP, PIP, PAP, policy gateway, and application-level enforcement boundaries
- compare RBAC, ABAC, PBAC, ReBAC, XACML, Cedar, OPA/Rego, OpenFGA, and custom policy surfaces
- connect downstream features, tests, claims, evidence, and releases to shared authorization governance records

## Pack Metadata

- Pack ID: `pack:authnz-policy`
- PyPI package: `authnz-policy-governance-pack`
- Import package: `authnz_policy_governance_pack`
- GitHub repository: [groupsum/authnz-policy-governance-pack](https://github.com/groupsum/authnz-policy-governance-pack)
- Reservation owner: `extension-pack:authnz-policy-governance-pack`

## Domain Focus

The pack focuses on domains where identity and authorization behavior affects security, interoperability, tenant isolation, release evidence, and product claims:

- authentication versus authorization boundaries
- OIDC ID Token and UserInfo claims
- OAuth 2.x scopes, consent, grants, access tokens, introspection, and resource-server validation
- permission naming, runtime permission checks, and permission lifecycle
- provisioned groups, roles, entitlements, and account state
- PDP, PEP, PIP, PAP, and policy gateway architecture
- RBAC, ABAC, PBAC, ReBAC, ACL, and capability-style access modeling
- XACML 3.0 vocabulary and compatibility claims
- Cedar, OPA/Rego, OpenFGA, and custom policy-as-code engines
- authorization audit, least privilege, deny paths, policy cache, revocation, and failure modes

## Authority Sources

Core identity and token authorities:

- [OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0-18.html)
- [OAuth 2.0 Authorization Framework, RFC 6749](https://www.rfc-editor.org/rfc/rfc6749)
- [OAuth 2.0 Token Introspection, RFC 7662](https://www.rfc-editor.org/rfc/rfc7662)
- [OAuth 2.0 Token Exchange, RFC 8693](https://www.rfc-editor.org/rfc/rfc8693)
- [JWT Profile for OAuth 2.0 Access Tokens, RFC 9068](https://www.rfc-editor.org/rfc/rfc9068)
- [OAuth 2.0 Security Best Current Practice, RFC 9700](https://www.rfc-editor.org/rfc/rfc9700)

Access-control and policy architecture authorities:

- [NIST SP 800-162: Guide to Attribute Based Access Control](https://csrc.nist.gov/pubs/sp/800/162/upd2/final)
- [NIST SP 800-207: Zero Trust Architecture](https://csrc.nist.gov/pubs/sp/800/207/final)
- [NIST SP 800-207A: Zero Trust Architecture Model for Access Control](https://csrc.nist.gov/pubs/sp/800/207/a/final)
- [OASIS XACML 3.0 Core Specification](https://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-os-en.html)
- [NIST RBAC Standards](https://csrc.nist.gov/projects/role-based-access-control/role-engineering-and-rbac-standards)

Policy-as-code and fine-grained authorization authorities:

- [Cedar Policy Language](https://docs.cedarpolicy.com/)
- [Open Policy Agent Rego Policy Language](https://www.openpolicyagent.org/docs/policy-language)
- [Google Zanzibar paper](https://research.google/pubs/zanzibar-googles-consistent-global-authorization-system/)
- [OpenFGA authorization modeling](https://openfga.dev/docs/modeling/getting-started)

Provisioning and identity data authorities:

- [SCIM Core Schema, RFC 7643](https://www.rfc-editor.org/rfc/rfc7643)
- [SCIM Protocol, RFC 7644](https://www.rfc-editor.org/rfc/rfc7644)

## Included ADRs

- [`adr:authentication-and-authorization-are-separate-governance-surfaces`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1000-authentication-and-authorization-are-separate-governance-surfaces.yaml) - Authentication And Authorization Are Separate Governance Surfaces
- [`adr:oidc-claims-identify-subjects-not-application-permissions`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1001-oidc-claims-identify-subjects-not-application-permissions.yaml) - OIDC Claims Identify Subjects Not Application Permissions
- [`adr:oauth-scopes-are-delegated-grants-not-complete-policy-decisions`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1002-oauth-scopes-are-delegated-grants-not-complete-policy-decisions.yaml) - OAuth Scopes Are Delegated Grants Not Complete Policy Decisions
- [`adr:access-token-claims-require-resource-server-validation`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1003-access-token-claims-require-resource-server-validation.yaml) - Access Token Claims Require Resource Server Validation
- [`adr:policy-decisions-use-explicit-pdp-pep-boundaries`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1004-policy-decisions-use-explicit-pdp-pep-boundaries.yaml) - Policy Decisions Use Explicit PDP PEP Boundaries
- [`adr:policy-inputs-use-subject-resource-action-and-context`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1005-policy-inputs-use-subject-resource-action-and-context.yaml) - Policy Inputs Use Subject Resource Action And Context
- [`adr:pip-and-attribute-sources-are-authoritative-inputs-not-hidden-logic`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1006-pip-and-attribute-sources-are-authoritative-inputs-not-hidden-logic.yaml) - PIP And Attribute Sources Are Authoritative Inputs Not Hidden Logic
- [`adr:rbac-roles-are-permission-bundles-not-policy-truth`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1007-rbac-roles-are-permission-bundles-not-policy-truth.yaml) - RBAC Roles Are Permission Bundles Not Policy Truth
- [`adr:abac-pbac-policies-own-contextual-authorization`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1008-abac-pbac-policies-own-contextual-authorization.yaml) - ABAC PBAC Policies Own Contextual Authorization
- [`adr:rebac-relationships-own-graph-based-resource-authorization`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1009-rebac-relationships-own-graph-based-resource-authorization.yaml) - ReBAC Relationships Own Graph Based Resource Authorization
- [`adr:entitlements-are-provisioned-access-facts-not-always-runtime-permissions`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1010-entitlements-are-provisioned-access-facts-not-always-runtime-permissions.yaml) - Entitlements Are Provisioned Access Facts Not Always Runtime Permissions
- [`adr:policy-as-code-engines-must-declare-language-and-evaluation-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1011-policy-as-code-engines-must-declare-language-and-evaluation-contract.yaml) - Policy As Code Engines Must Declare Language And Evaluation Contract
- [`adr:xacml-is-a-reference-architecture-not-a-required-policy-language`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1012-xacml-is-a-reference-architecture-not-a-required-policy-language.yaml) - XACML Is A Reference Architecture Not A Required Policy Language
- [`adr:policy-gateways-are-enforcement-points-not-complete-authorization-systems`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1013-policy-gateways-are-enforcement-points-not-complete-authorization-systems.yaml) - Policy Gateways Are Enforcement Points Not Complete Authorization Systems
- [`adr:deny-paths-and-least-privilege-are-release-gated-evidence`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/adr/ADR-1014-deny-paths-and-least-privilege-are-release-gated-evidence.yaml) - Deny Paths And Least Privilege Are Release Gated Evidence

## Included SPECs

- [`spc:authn-authz-boundary-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2000-authn-authz-boundary-contract.yaml) - AuthN AuthZ Boundary Contract
- [`spc:oidc-id-token-and-userinfo-claims-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2001-oidc-id-token-and-userinfo-claims-contract.yaml) - OIDC ID Token And UserInfo Claims Contract
- [`spc:oauth-scope-consent-and-grant-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2002-oauth-scope-consent-and-grant-contract.yaml) - OAuth Scope Consent And Grant Contract
- [`spc:oauth-access-token-validation-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2003-oauth-access-token-validation-contract.yaml) - OAuth Access Token Validation Contract
- [`spc:permission-taxonomy-and-naming-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2004-permission-taxonomy-and-naming-contract.yaml) - Permission Taxonomy And Naming Contract
- [`spc:entitlement-role-and-group-provisioning-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2005-entitlement-role-and-group-provisioning-contract.yaml) - Entitlement Role And Group Provisioning Contract
- [`spc:pdp-pep-pip-pap-architecture-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2006-pdp-pep-pip-pap-architecture-contract.yaml) - PDP PEP PIP PAP Architecture Contract
- [`spc:policy-decision-request-response-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2007-policy-decision-request-response-contract.yaml) - Policy Decision Request Response Contract
- [`spc:abac-pbac-policy-input-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2008-abac-pbac-policy-input-contract.yaml) - ABAC PBAC Policy Input Contract
- [`spc:rbac-role-permission-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2009-rbac-role-permission-contract.yaml) - RBAC Role Permission Contract
- [`spc:rebac-relationship-authorization-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2010-rebac-relationship-authorization-contract.yaml) - ReBAC Relationship Authorization Contract
- [`spc:policy-as-code-authoring-and-review-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2011-policy-as-code-authoring-and-review-contract.yaml) - Policy As Code Authoring And Review Contract
- [`spc:cedar-policy-language-boundary-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2012-cedar-policy-language-boundary-contract.yaml) - Cedar Policy Language Boundary Contract
- [`spc:opa-rego-policy-language-boundary-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2013-opa-rego-policy-language-boundary-contract.yaml) - OPA Rego Policy Language Boundary Contract
- [`spc:xacml-compatibility-and-vocabulary-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2014-xacml-compatibility-and-vocabulary-contract.yaml) - XACML Compatibility And Vocabulary Contract
- [`spc:policy-gateway-enforcement-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2015-policy-gateway-enforcement-contract.yaml) - Policy Gateway Enforcement Contract
- [`spc:authorization-audit-and-evidence-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2016-authorization-audit-and-evidence-contract.yaml) - Authorization Audit And Evidence Contract
- [`spc:least-privilege-and-negative-path-test-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2017-least-privilege-and-negative-path-test-contract.yaml) - Least Privilege And Negative Path Test Contract
- [`spc:token-to-policy-context-mapping-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2018-token-to-policy-context-mapping-contract.yaml) - Token To Policy Context Mapping Contract
- [`spc:authorization-failure-mode-and-cache-contract`](https://github.com/groupsum/authnz-policy-governance-pack/blob/master/src/authnz_policy_governance_pack/templates/specs/SPEC-2019-authorization-failure-mode-and-cache-contract.yaml) - Authorization Failure Mode And Cache Contract

## Install With uv

Install the pack into a project environment:

```bash
uv add authnz-policy-governance-pack
```

Install it alongside the SSOT Registry CLI:

```bash
uv add ssot-registry authnz-policy-governance-pack
```

Run without adding dependencies to a project:

```bash
uvx --from ssot-registry --with authnz-policy-governance-pack ssot --help
```

## Install With The SSOT Registry Pack CLI

Pack-enabled SSOT Registry environments can inspect, preflight, and synchronize packs through the pack command surface:

```bash
uv run ssot pack inspect authnz_policy_governance_pack
uv run ssot pack preflight . authnz_policy_governance_pack --all
uv run ssot pack sync . authnz_policy_governance_pack --all --trust --yes
```

## Use With The SSOT Registry CLI

After the pack is installed in the same environment as `ssot-registry`, validate the synchronized governance surface:

```bash
uv run ssot validate .
uv run ssot adr list .
uv run ssot spec list .
uv run ssot spec get . --id spc:pack.authnz-policy.authn-authz-boundary-contract
```

Use the IDs from this pack when linking project features, tests, claims, and release evidence in your local `.ssot` registry.

## Programmatic Usage

```python
from authnz_policy_governance_pack import load_document_manifest, read_packaged_document_text

adr_manifest = load_document_manifest("adr")
spec_manifest = load_document_manifest("spec")

print(adr_manifest[0]["id"])
print(spec_manifest[0]["id"])

text = read_packaged_document_text("spec", "SPEC-2000-authn-authz-boundary-contract.yaml")
print(text[:120])
```

## Resources

- GitHub repository: [groupsum/authnz-policy-governance-pack](https://github.com/groupsum/authnz-policy-governance-pack)
- PyPI package: [authnz-policy-governance-pack](https://pypi.org/project/authnz-policy-governance-pack/)
- SSOT Registry: [ssot-registry](https://pypi.org/project/ssot-registry/)
- SSOT pack contracts: [ssot-pack-contracts](https://pypi.org/project/ssot-pack-contracts/)
