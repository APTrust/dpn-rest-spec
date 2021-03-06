## DPN REST API

### Client Authorization

The API server MUST implement token based authorization in the header of each request and MUST limit access to all returns to Authorized user tokens in addition to any other restrictions on views or returns.

    Authorization: token <token key>

for example:

    Authorization: token b35bc6a16ed0e7627fbf39114e0a97d005839200

This token MUST be issued by each API server.

### Definition of User Roles

Throughout this document several user roles are references and they are defined here as a general guide but do not require a specific implementation in the API.  It serves only to define the desired behavior of various returns to provide proper data security or facilitate aggregate reporting or auditing.

**Authorized User**: Refers to a user that has a valid API token and is entitled to a base level of information from the API without concern for user context.

**API User**:  Refers to an authorized user that would need to operate in the context of another node in the federation and would be limited to updating and viewing data as it relates to transactions with its own node.

**API Admin**: Refers to an authorized user that would need to operate in the context of being able to create, update or view system records to initiate transactions with other nodes in the system.  Typically this will only be a local administrative api client.

**Superuser**:  Refers to authorizes users, typically in the API Admin group that need to be able to view all data, regardless of node assignment.

# Additional Security Considerations

Any API server MUST use https for all requests and is assumed to have explicit Firewall rules configured for each individual server/client required.