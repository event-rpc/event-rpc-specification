# Server requirements and expectations

The Server runs and integrates with the event sourcing libraries, and handles the communication between the Client and the event sourcing library. The server should be as minimal as possible and integrate with the ecosystem of the language, such that the websocket management, auth, middleware and other concerns can be handled through the most common libraries and frameworks.

#### Requirements

-   [ ] Keep track of Clients state subscriptions, forward state updates, and events to the subscribed Clients
-   [ ] Keep track of the `command` execution life-cycle and ensure the `result` message is sent to the Client when execution completes
-   [ ] Integrate with the most popular event sourcing library in the ecosystem
-   [ ] Integrate with at least the most popular websocket solution in the ecosystem
-   [ ] Enable the user to define auth and other websocket connection concerns
-   [ ] Enable the user to define (middlewares)[## Middlewares] for command handling **unless** the event sourcing library integrated already offers this functionality

> The EventRPC library should never directly implement event sourcing processes, these should always use a separate system as the concern of EventRPC is only to handle the connection and state sync with Clients.

## Middlewares

A middleware entails any code that may or may not contain side-effects, that should run before a `command` is issued to the target event sourcing library. These can be used for request validation, additional data fetching, and other tasks that might need to happen before the `command` is processed.

Middlewares are particularly great for handling side-effects and filling `command` contracts with additional data that may be required for an aggregate to handle the `command`.

## Correlation IDs

Every message shared via the EventRPC websocket connection has an envelope, which contains a `correlation-id` this ID is always defined by the Client, and it is used to track the specific Clients subscriptions and commands. This ID must be returned with every message sent to the Clients, and can be a great way to keep track of all the commands and subscriptions happening in the system.
