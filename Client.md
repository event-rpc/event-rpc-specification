# Client requirements and expectations

The purpose of the client is twofold, it should synchronize the local state with the server, and it should dispatch commands to the server. To ensure a good user experience, a client must:

#### Functional requirements

-   [ ] Enable user to subscribe to an entity (as outlined in the (API Specification)[./API.md])
-   [ ] Enable user to react to state and event updates as they are received
-   [ ] Enable user to send a command to the server
-   [ ] Enable user to react to the command result

#### Technical requirements

-   [ ] Store subscribed entities locally, and available even offline
    -   A user should be able to access the version of an entity, timestamp of the last processed by entity update (in case of an `event`, this would be the event creation timestamp)
-   [ ] Ensure the device running the client is not overwhelmed by the load introduced through a websocket connection
-   [ ] Work with at least the native websocket client
-   [ ] Provide flexibility (within reason) in choice of state storage solutions
-   [ ] Ensure the state is never stored in a manner where it can be easily accessed by other processes, websites or apps

> The client should not implement the websocket protocol, manage the connection or handle auth, these should all be external concerns that the native ecosystem should handle. Instead, the client should enable easy setup and integration of these external concerns. This may be done through polymorphism, templates, code generation and other similar means.
>
> The resulting library should therefore fit into the ecosystem and be interoperable
