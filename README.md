# DispatchHealth

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
