# ECSS-10 Engineering Map

## Purpose

A compact map of the platform areas encountered during practical work with ECSS-10
versions in the 3.14–3.18 range. It helps identify which layer to inspect before
changing configuration.

## Configuration and Call-Processing Areas

| Area | Engineering question |
|---|---|
| Domains | Which tenant or signaling context should process the request? |
| Subscribers | Is the endpoint provisioned, authenticated and assigned correctly? |
| IP Sets | How is the source network classified? |
| SIP profiles | Which transport and signaling behavior applies? |
| Routing | Which destination is selected after normalization? |
| Supplementary services | Which service changes the basic call behavior? |
| SIP trunks | Is the external signaling path available and interoperable? |
| SBC/SMG integration | Where are signaling, number and media boundaries? |

## Platform and Operations Areas

- **Mycelium CLI** for platform inspection and operational configuration.
- **Clusters** for node roles, service placement and availability context.
- **Call Center** for queues, agents and service-specific call distribution.
- **API** for controlled integration with external systems.
- **Web, REST and media services** as separate deployable and testable components.

## Troubleshooting Order

```text
Source network / transport
          ↓
IP Set and domain selection
          ↓
Subscriber or trunk identity
          ↓
Routing and number normalization
          ↓
Supplementary or call-center logic
          ↓
SIP dialog and SDP
          ↓
RTP media path
```

This order is a diagnostic starting point, not a claim that every ECSS call follows
one identical internal implementation path.

## Repository Boundary

- Labs and reusable platform knowledge stay in this repository.
- Sanitized incidents and deployment outcomes stay in
  [Voice Integration Projects](https://github.com/nikita-voip/voice-integration-projects).
- Customer commands, addresses, licenses and proprietary configuration are not
  published.
