# Passport (passport-parking)

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

Passport (Passport Labs) is a mobility management platform for cities, universities, and agencies, covering digital parking payments, enforcement, permits, and curbside management, and is used by 800+ agencies. Passport runs a partner developer program at [developer.passportinc.com](https://developer.passportinc.com/) whose REST APIs let parking apps, navigation apps, in-car infotainment, and mobility/POS systems create and stop parking sessions, quote and determine rates, bulk-export the parking environment (zones, spaces, rules), receive parking event schemas, and manage enforcement immobilizations. Rates and rules are configured once by Passport's customers and pushed to payment providers via API. No SDK is required.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/passport-parking/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/passport-parking/refs/heads/main/apis.yml)

## Access model (read this first)

Passport's API is **partner / agency-gated**, not open self-serve:

- The developer documentation at `developer.passportinc.com` is **public to read**, but the APIs **cannot be called anonymously**.
- Access is restricted to **authenticated applications**. Partners register their application and are issued **OAuth client credentials** by Passport's identity provider; every API call must be authenticated.
- You typically reach the APIs by **becoming a Passport partner** (parking app, navigation, automotive, MaaS, payments, or POS), which unlocks Passport's database of city rules, rates, and restrictions across hundreds of cities.
- **Commercial terms are partnership / agency-contract based.** There is no publicly listed self-serve API pricing; the [Partnerships](https://www.passportinc.com/resources/partnerships/) page is the access and pricing front door.

Because the reference portal is client-rendered and the concrete endpoints, request/response shapes, and base host sit behind the partner-gated experience, this entry **lists the real, documented API sections with their real reference URLs but does not fabricate an OpenAPI definition, exact endpoint paths, or a base URL**. Endpoints are marked as modeled in `review.yml` (`endpointsModeled: true`).

## Tags

- Parking
- Mobility
- Smart Cities
- Payments
- Enforcement
- Curbside Management
- Transportation

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### Passport Parking Sessions and Quotes API

Quote, create, and stop parking sessions on behalf of a driver in a Passport-managed zone - the core surface behind facilitating a paid parking session from a parking app, navigation app, or in-car experience. Includes quoting the price for a duration and stopping a session early with support for partial refunds in eligible zones.

- **Human URL:** [Create a parking session](https://developer.passportinc.com/docs/parking-sessions-quotes/13a733cdcae7c-create-a-parking-session)
- **Also:** [Stop a parking session](https://developer.passportinc.com/docs/parking-sessions-quotes/y8i8yj7mfx4vr-stop-a-parking-session)

### Passport Parking Rates API

Determine the parking rate for a location and duration. Rates are defined uniquely by each Passport customer (city, university, or operator) and vary by location, time, and rules, giving partners a single source of truth for what a driver should be charged before starting a session.

- **Human URL:** [Rates API](https://developer.passportinc.com/docs/parking-rates/YXBpOjI1OTk0NTg0)

### Passport Parking Environment Export API

Bulk export of the parking environment. Returns a single-use URL to download a JSON file describing zones, zone numbers, geolocation (latitude and longitude), and associated rules and restrictions for the cities a partner is authorized to serve - the block-by-block data used to map and price parking.

- **Human URL:** [Environment Export API](https://developer.passportinc.com/docs/parking-bulk-export/b3A6MjU5OTIzNjY)

### Passport Parking Event Schemas

Versioned JSON schemas for the parking events Passport emits to partners (for example a `parking_session_started` event, v3.0.0). These are server-to-endpoint webhook-style event payloads that let partner systems react to session lifecycle changes; there is no WebSocket transport.

- **Human URL:** [Parking event schemas](https://developer.passportinc.com/docs/parking-event-schemas/f7f18f6220972)

### Passport Immobilizations API

Manage enforcement immobilizations (vehicle boots) - for example updating an existing immobilization record - as part of Passport's digital parking enforcement and compliance workflow. Part of the broader enforcement and citations product surface.

- **Human URL:** [Immobilizations API](https://developer.passportinc.com/docs/immobilizations/ac6df0372e30f-update-an-existing-immobilization)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/passport-labs)
- [Website](https://www.passportinc.com)
- [Documentation](https://developer.passportinc.com/)
- [Plans / Partnerships](https://www.passportinc.com/resources/partnerships/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
