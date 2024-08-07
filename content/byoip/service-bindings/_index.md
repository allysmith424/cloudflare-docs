---
title: Service bindings
pcx_content_type: concept
weight: 6
---

# IP address service bindings

Within IP address management, service binding refers to the association of an IP (or a range of IPs) to specific Cloudflare services.

## Scope

Currently, if you have BYOIP configured with [Magic Transit](/magic-transit/), you can use the [service binding](/api/operations/ip-address-management-service-bindings-list-service-bindings) endpoints to add CDN or Spectrum capabilities on top of Magic Transit.

### CDN (Cache)

Adding the CDN service binding ensures that any HTTP requests received via designated IPs are directed into the CDN pipeline for [Layer 7 processing](/fundamentals/concepts/how-cloudflare-works/#how-cloudflare-works-as-a-reverse-proxy) as they land on the Cloudflare network.

Refer to [Use BYOIP with Magic Transit and CDN](/byoip/service-bindings/magic-transit-with-cdn/) to learn how to set this up.

### Spectrum

Adding [Spectrum](/spectrum/) allows you benefit from Cloudflare security and performance for Layer 4 traffic.

## API

Service binding operations are currently only available via API. You can find all endpoints and their specifications in the [Cloudflare API documentation](/api/operations/ip-address-management-service-bindings-list-service-bindings).

## Limitations

* It is currently not possible to use both Spectrum and CDN together with the Magic Transit service. You must choose one or the other when upgrading your IPs.
* You must keep Magic Transit as a common base service, spanning all addresses in your prefix.
* Once a service binding is created, its propagation across the Cloudflare network will take four to six hours to complete.