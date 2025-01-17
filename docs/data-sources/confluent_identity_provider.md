---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "confluent_identity_provider Data Source - terraform-provider-confluent"
subcategory: ""
description: |-
  
---

# confluent_identity_provider Data Source

[![Limited Availability](https://img.shields.io/badge/Lifecycle%20Stage-Limited%20Availability-%2300afba)](https://docs.confluent.io/cloud/current/api.html#section/Versioning/API-Lifecycle-Policy) [![Request Access To OAuth API](https://img.shields.io/badge/-Request%20Access%20To%20OAuth%20API-%23bc8540)](mailto:ccloud-api-access+iam-v2-closed-preview@confluent.io?subject=Request%20to%20join%20OAuth%20API%20Closed%20Preview&body=I%E2%80%99d%20like%20to%20join%20the%20Confluent%20Cloud%20API%20Closed%20Preview%20for%20iam/v2%20to%20provide%20early%20feedback%21%20My%20Cloud%20Organization%20ID%20is%20%3Cretrieve%20from%20https%3A//confluent.cloud/settings/billing/payment%3E.)

`confluent_identity_provider` describes an Identity Provider data source.

## Example Usage

```terraform
data "confluent_identity_provider" "example_using_id" {
  id = "op-abc123"
}

output "example_using_id" {
  value = data.confluent_identity_provider.example_using_id
}

data "confluent_identity_provider" "example_using_name" {
  display_name = "My OIDC Provider: Azure AD"
}

output "example_using_name" {
  value = data.confluent_identity_provider.example_using_name
}
```

<!-- schema generated by tfplugindocs -->
## Argument Reference

The following arguments are supported (specify either `id` or `display_name`, not both):

- `id` - (Optional String) The ID of the Identity Provider, for example, `op-abc123`.
- `display_name` - (Optional String) A human-readable name for the Identity Provider.

-> **Note:** Exactly one from the `id` and `display_name` attributes must be specified.

## Attributes Reference

The following attributes are exported:

- `id` - (Required String) The ID of the Identity Provider, for example, `op-abc123`.
- `display_name` - (Required String) A human-readable name for the Identity Provider.
- `description` - (Required String) A description for the Identity Provider.
- `issuer` - (Required String) A publicly reachable issuer URI for the Identity Provider. The unique issuer URI string represents the entity for issuing tokens.
- `jwks_uri` - (Required String) A publicly reachable JSON Web Key Set (JWKS) URI for the Identity Provider. A JSON Web Key Set (JWKS) provides a set of keys containing the public keys used to verify any JSON Web Token (JWT) issued by your OAuth 2.0 identity provider.
