# Passport (passport-parking)

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
