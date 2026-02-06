# System Design Crash Course

## Basic Concept

### Scability

-

### RAM

- RAM disappears when power is off
- ROM persists after turning off computer
- SRAM

### RESTful API

- REST is stateless
- If the API response contains a large number of info, use pagination. `/users?limit=25&offset=50`

### CI/CD

- CI requires high test coverage.
- Build tools: WebPack(JavaScript), Gradle(Java)
- CD allows feature for small set of users.

### DNS

- translate human readable domain into machine IP
- Top Level Domain Nameservers (.cn, .com, .org)
- When a website domain is hit, it goes to DNS resolver and check the cache. Then it goes to nameserver for TLD Nameservers for IP address
