# ECSS-10 Architecture and Procurement Review

## Purpose

This checklist turns a high-level ECSS-10 requirement into an architecture that can
be sized, reviewed and tested. It intentionally avoids deployment-specific values.

## Interfaces and Interworking

- Define SIP access, SIP trunks and any SIP-I interworking separately.
- Document every external PBX, carrier, SBC and media gateway boundary.
- Record transport, addressing, authentication and number-format assumptions.
- Identify where signaling and media are anchored.

## Session Border Control

Review topology hiding, access control, normalization, media anchoring, NAT traversal,
rate limits and failure behavior. Clarify which functions belong to ECSS and which
belong to a dedicated SBC.

## High Availability

Document component redundancy, state synchronization, recovery targets and failure
domains. A diagram should show what happens to registration, active calls and new
calls during each planned failure test.

## Routing

- Subscriber and domain selection.
- Inbound and outbound route order.
- Digit normalization and presentation.
- Failover destinations and loop prevention.
- Emergency and restricted destinations where applicable.

## Monitoring

Define health checks, alarms, logs, CDRs and signaling/media capture points. Include
time synchronization and a retention policy so events can be correlated across nodes.

## Conference and Media Services

Estimate concurrent participants, codecs, transcoding, announcements and recording
requirements. Conference capacity should be calculated separately from ordinary
point-to-point calls.

## Scaling Inputs

- Registered subscribers.
- Busy-hour call attempts.
- Concurrent sessions.
- Transactions per second during peaks.
- Concurrent conference participants.
- Codec and transcoding mix.
- Growth horizon and resilience margin.

## Procurement Deliverables

1. Logical and physical architecture diagrams.
2. Interface and responsibility matrix.
3. Traffic assumptions and capacity calculation.
4. Hardware and licensing bill of materials.
5. High-availability and disaster-recovery behavior.
6. Monitoring and support requirements.
7. Acceptance-test plan with measurable pass criteria.

## Review Principle

Every capacity or licensing line must trace back to a traffic assumption, interface
requirement or availability target. Unverified assumptions remain explicit open items.
