# Ably SDK Team: Guidance on Versioning

This document outlines our approach for SDK release versioning.

There will be some SDK repositories which are yet to make a release that conforms to the requirements outlined here,
including [Release Process](releases.md#release-process) adherance, however this approach will be required for all repositories
[from **May 2022**](#policy-change-from-1-may-2022).

## Semantic Versioning

Version increments to SDKs must conform to [Semantic Versioning 2.0.0](https://semver.org/).

## Features Specification and Protocol Versioning

We will move the **Features Specification** from the **Client Library Development Guide** source code from the
[`ably/docs` repository](https://github.com/ably/docs) to the [`ably/ably-common` repository](https://github.com/ably/ably-common),
where it will be versioned alongside the core Ably service protocol definitions.

_This work is yet to be undertaken. Once it's been completed then this document will be updated to reflect that._

## Historical Context

### Retired Approach to Ably Versioning

Ably's **Client Library Development Guide** guidance on **Ably Versioning** was originally:

> Ably’s general approach to versioning is to use the [semantic versioning scheme](https://semver.org/), with a few differences that are explained in this article. The approach outlined here applies to our [client library SDKs](https://ably.com/download), our [REST API endpoints](https://docs.ably.com/rest-api), and all other public endpoints that support versioning such as [Server-Sent Events](https://docs.ably.com/sse).
>
> Our policy is that a `major.minor` version number applies to the API specification and across all versioned services and protocols. Each library implementing a given version of the API specification adopts the same major and minor versions and has patch version numbering indicating the actual library revision.
>
> Whilst we recognise this approach has some limitations – primarily around the need to synchronize version updates across multiple libraries and specifications when a breaking change is introduced into any one of them – we believe that having an independent series of version numbers for different protocols, endpoints and SDKs would make managing that very difficult for Ably and, most importantly, would be confusing for our customers. This documentation itself operates on the basis that customer-facing content shares a single version number so that customers can view the latest or, for example, switch to 1.1 across the entire site (for content that has been versioned).
>
> Further, given that the version numbers we use cover the raw HTTP API, the protocol and API spec, and the client library SDKs, features such as support for connection/request params, channel params, extras, token lengths, APIs (eg push HTTP API) vary by the API version. Stateless connections are subject to some of those constraints, even if they don’t follow the full protocol spec or the library API.
>
> As such, in the case of SSE for example, we believe that standardising on versioning means it is quite natural for a connection string for a stateless connection to include the spec version, and that will allow the system to know what features the client can be expected to understand, and might be required so that the system knows how to interpret param values that are supplied by the client. Whilst we always try to make it so that there are no incompatibilities, we have a version because we recognise that that is not always avoidable.
>
> Please note that the realtime protocol used by our SDKs is an internal protocol, and thus breaking changes do not necessitate a major version change. A major version bump is preferred for breaking changes to public APIs.

[**ADR34** (internal link)](https://ably.atlassian.net/wiki/spaces/ENG/pages/1505886246/ADR34+SDK+versioning+policy) is the architectural decision record documenting our decision to move away from this approach, with the approach going forwards being that of _"allowing our SDKs to live their own lives"_...

This retired approach is being quoted above in this document for the benefit of those interested in understanding the reasons why, prior to May 2022, it was considered the correct approach.

### Policy Change from 1 May 2022

SDK releases made from May 2022 forwards will conform to the constraints defined by [Semantic Versioning](#semantic-versioning).