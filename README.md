# DispatchHealth

DispatchHealth delivers complex medical care in the home — same-day urgent care, hospital-alternative (hospital-at-home) care, and transitional/recovery care — across roughly 50 US metropolitan areas in partnership with nearly 40 health systems and national payers. Founded in 2013 in Denver, Colorado, it merged with Medically Home in June 2025. Its CESIA platform handles care planning, dispatching, routing, scheduling and real-time patient connectivity, and is designed to integrate with a partner health system's existing EMR.

- Website: https://www.dispatchhealth.com/
- Technology (CESIA): https://www.dispatchhealth.com/technology/
- Partners: https://www.dispatchhealth.com/partners/
- Secondary market listing: https://forgeglobal.com/dispatchhealth_stock/

## API surface

DispatchHealth publishes **no public developer portal, API documentation, or OpenAPI/GraphQL/AsyncAPI contract**. `api.dispatchhealth.com` answers HTTP 204 with an empty body to every anonymous path, and the partner (Dispatch Express) and patient (request) surfaces are interactive logins.

The one machine-readable surface found on their hosts is an **OAuth 2.1-protected MCP server** exposed by the WordPress MCP adapter on the marketing site:

- `https://www.dispatchhealth.com/.well-known/oauth-authorization-server` (RFC 8414)
- `https://www.dispatchhealth.com/.well-known/oauth-protected-resource` (RFC 9728)
- `https://www.dispatchhealth.com/wp-json/mcp/mcp-oauth-server` — `tools/list` returns 401 (auth-gated)

No A2A agent card, no security.txt, no status page, no first-party SDKs (the 21 public GitHub repos are all forks). A Drata-hosted trust center exists at `trust.dispatchhealth.com` but is behind a Cloudflare bot challenge, so its certifications could not be enumerated.
