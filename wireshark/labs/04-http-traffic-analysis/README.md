# Lab 04: HTTP Traffic Analysis

## Status

Planned

## Objective

Analyze HTTP requests and responses captured in a controlled
environment, identifying methods, status codes, headers, and
transmitted content. The lab also aims to demonstrate, in practice,
the risks of unencrypted HTTP traffic.

## Concepts covered

- HTTP protocol (Hypertext Transfer Protocol).
- HTTP methods (GET, POST, among others).
- HTTP status codes (2xx, 3xx, 4xx, 5xx).
- Relevant HTTP headers (`Host`, `User-Agent`, `Content-Type`,
  `Authorization`, `Cookie`).
- Risks of transmitting data in plain text.
- Difference between HTTP and HTTPS/TLS (conceptual).

## Environment

- Operating system: `<fill in>`
- Wireshark version: `<fill in>`
- Network interface: `<fill in>`
- Topology: `<fill in>`
- Virtual machines: `<fill in>`
- Auxiliary tools: `<fill in>`

## Scenario

`<Describe the scenario used to generate the HTTP traffic, for
example, requests made to a lab web server with fictitious content and
credentials.>`

## Procedure

`<Describe, step by step, how the capture was performed and which HTTP
requests were generated during the lab.>`

## Filters used

### Capture filters

```text
tcp port 80
```

### Display filters

```text
http
http.request
http.response
http.request.method == "GET"
http.request.method == "POST"
http.response.code >= 400
```

## Packet analysis

`<Document here the relevant packets observed during the actual
execution of the lab: relevant requests and responses, methods used,
status codes, and observed headers.>`

## Evidence

`<Add anonymized screenshots in screenshots/ and reference the
corresponding capture files in captures/ once the lab is performed.>`

## Key findings

`<Fill in after the lab is performed.>`

## Indicators of suspicious behavior

`<Fill in, if applicable, after the lab is performed.>`

## Mitigations or recommendations

`<Fill in, if applicable, after the lab is performed — for example, a
recommendation to use HTTPS/TLS for any traffic involving sensitive
data.>`

## Conclusion

`<Fill in after the lab is performed.>`

## References

- [RFC 9110 — HTTP Semantics](https://www.rfc-editor.org/rfc/rfc9110)
- [Official Wireshark documentation](https://www.wireshark.org/docs/)
- [docs/wireshark-display-filters.md](../../docs/wireshark-display-filters.md)

---

> ⚠️ **Warning**: this lab must be performed exclusively in a
> controlled environment, using fictitious credentials and data.
> **Real credentials, cookies, and tokens must never be published** in
> captures, screenshots, or this documentation. See
> [docs/packet-capture-safety.md](../../docs/packet-capture-safety.md).
