# LAB-10 Structured Troubleshooting

## Goal

Use signaling evidence and ECSS configuration context to locate a fault without
changing unrelated settings.

## Fault Domains

1. Transport and source network.
2. IP set and SIP domain selection.
3. Subscriber identification and authentication.
4. Request-URI and allowed URI rules.
5. Routing and digit manipulation.
6. SIP trunk state and downstream response.
7. SDP negotiation and RTP media path.

## Tasks

### 1. Establish the Symptom

- Record the affected calling direction and number pattern.
- Determine whether REGISTER, INVITE or media is failing.
- Capture a timestamp and correlation identifiers.

### 2. Verify Domain Selection

- Identify the source network and its IP set.
- Confirm that the IP set maps to the intended SIP domain.
- Compare the Request-URI with domain and `allowed-ruri-list` rules.

### 3. Verify the Subscriber or Trunk

- Check registration state and authentication events.
- Confirm transport and remote endpoint state.
- Avoid interpreting every `401 Unauthorized` response as a password failure.

### 4. Trace Routing

- Normalize the called number as the platform sees it.
- Follow route selection and digit manipulation in order.
- Verify the selected trunk and the response from the next hop.

### 5. Verify Media

- Compare SDP offer and answer.
- Confirm codec agreement, media addresses and ports.
- Check RTP independently in both directions.

## Evidence Table

| Stage | Expected | Observed | Evidence |
|---|---|---|---|
| Domain selection | Intended domain selected | | Configuration / trace |
| Authentication | Subscriber or trunk accepted | | Event / SIP response |
| Routing | Expected route selected | | Route trace |
| Signaling | Dialog completes | | SIP ladder |
| Media | Bidirectional RTP | | Packet capture |

## Expected Result

The engineer can identify the failing layer, support the conclusion with evidence,
apply one scoped correction and verify the complete call again.

## Safety

Use a lab or approved maintenance window. Remove credentials, private addresses,
phone numbers and customer identifiers before sharing traces or screenshots.
