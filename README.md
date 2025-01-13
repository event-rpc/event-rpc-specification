# EventRPC Specification

The EventRPC Specification outlines the cross-language requirements and expectations for all EventRPC implementations.

## Delimitation

EventRPC is a standard that should enable its implementing client and server libraries to communicate effortlessly, in real time, and reliably. To keep the implementing libraries concise, and focused on the concern of EventRPC, the following guidelines should apply:

-   Should strive to have 0 dependencies
-   Should not implement technical concerns such as websockets, auth and other
-   Should make use of the existing ecosystem of the programming language and community
-   Should allow the user to bootstrap necessary functionality with a single action (command, line of code, etc...), and sensible, production ready defaults
-   Should conform to standards and best practices of the ecosystem in question

## Table of Contents

-   [Websocket API specification](./API.md)
-   [Client expectations](./Client.md)
-   [Server expectations](./Server.md)

## Versioning the Specification

Changes to the [specification](./specification/overview.md) are versioned according to [Semantic Versioning 2.0](https://semver.org/spec/v2.0.0.html) and described in [CHANGELOG.md](CHANGELOG.md). Layout changes are not versioned. Specific implementations of the specification should specify which version they implement.

Changes to the change process itself are not currently versioned but may be independently versioned in the future.

## License

By contributing to OpenTelemetry Specification repository, you agree that your contributions will be licensed under its [Apache 2.0 License](LICENSE).
