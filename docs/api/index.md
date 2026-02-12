# index

Welcome to the Superdesk API Reference documentation. This section provides comprehensive API documentation for all Superdesk components.

## Overview

Superdesk provides RESTful APIs for all its components. The APIs follow standard REST principles with JSON payloads and use HTTP methods (GET, POST, PATCH, DELETE) for CRUD operations.

## API Documentation

View the complete API documentation using our interactive API Explorer:

### Core APIs

[**Superdesk Core API (Rundowns) →**](file:///api/superdesk-core-direct/)

* Rundown management for broadcast workflows
* Shows, templates, and rundown items

[**Superdesk Production API →**](file:///api/production-api/)

* Stable, versioned endpoints for third-party integrations
* Content items, assignments, planning, events, and more
* JWT authentication for secure access

The API Explorer provides:

* ✅ **Single-page view** - All endpoints on one scrollable page
* ✅ **Interactive navigation** - Left sidebar menu with endpoint list
* ✅ **Direct rendering** - No generated files, updates immediately when spec changes
* ✅ **Clean interface** - Professional Redoc design integrated with Docusaurus
* ✅ **Try it out** - Test API endpoints directly from the documentation

## Available APIs

### Superdesk Core API

The Superdesk Core backend provides the main REST API for content management, workflow, and publishing.

Base URL: `https://your-superdesk-instance.com/api`

Authentication: Session-based or token-based authentication

Key endpoints:

* `/archive` - Content management
* `/desks` - Desk management
* `/users` - User management
* `/publish` - Publishing operations
* `/search` - Content search

### Superdesk Production API

Production API server provides **stable and versioned endpoints** for third-party apps to consume news content from Superdesk.

Base URL: `https://your-superdesk-instance.com/prodapi/v1`

Authentication: JWT token authentication (Bearer token)

Current Version: v1

Key features:

* Uses the same DB and Elasticsearch index as main Superdesk app
* Versioned endpoints for non-breaking API changes
* HATEOAS links for resource relationships
* Elasticsearch and MongoDB query support

Key endpoints:

* `/items` - Content items with search
* `/assignments` - Assignment management
* `/planning` - Planning items
* `/events` - Calendar events
* `/desks` - Editorial desks
* `/users` - System users
* `/contacts` - Contact information
* `/assets` - Media assets

### Superdesk Planning API

The Planning module extends the core API with event and planning management.

Base URL: `https://your-superdesk-instance.com/api`

Key endpoints:

* `/events` - Event management
* `/planning` - Planning items
* `/assignments` - Assignment management
* `/coverage` - Coverage tracking

## OpenAPI Specifications

Full OpenAPI 3.0 specifications are available for:

* **Superdesk Core API (Rundowns)** - `static/openapi/superdesk-core.yaml`
* **Superdesk Production API** - `static/openapi/superdesk-production-api.yaml`

## API Authentication

### Session Authentication

Standard session-based authentication using cookies:

{% code title="Login (curl)" %}
```bash
# Login
curl -X POST https://your-instance.com/api/auth \
  -H "Content-Type: application/json" \
  -d '{
    "username": "admin",
    "password": "password"
  }'
```
{% endcode %}

### Token Authentication (Core API)

API token authentication for integrations:

{% code title="Use API token in header (curl)" %}
```bash
# Use API token in header
curl -X GET https://your-instance.com/api/archive \
  -H "Authorization: Bearer YOUR_API_TOKEN"
```
{% endcode %}

### JWT Authentication (Production API)

Production API uses JWT token authentication. Third-party apps must retrieve token using AuthServer:

{% code title="Query Production API with JWT (bash)" %}
```bash
export PRODAPI=http://127.0.0.1:5500/prodapi/v1
export JWT_TOKEN=your.jwt.token
export FILTER='source={"query":{"filtered":{"filter":{"terms":{"type":["text"]}}}}}'

curl -g -i $PRODAPI/items?$FILTER \
  -H "Authorization: Bearer $JWT_TOKEN"
```
{% endcode %}

## Common Patterns

### Pagination

List endpoints support pagination:

{% code title="Pagination example (HTTP)" %}
```bash
GET /api/archive?page=1&max_results=25
```
{% endcode %}

### Filtering

Use MongoDB query syntax for filtering:

{% code title="Filtering example (HTTP)" %}
```bash
GET /api/archive?where={"type":"text","urgency":{"$gte":3}}
```
{% endcode %}

### Sorting

Sort results using the `sort` parameter:

{% code title="Sorting example (HTTP)" %}
```bash
GET /api/archive?sort=-versioncreated
```
{% endcode %}

### Embedded Resources

Include related resources using `embedded`:

{% code title="Embedded resources example (HTTP)" %}
```bash
GET /api/archive?embedded={"user":1}
```
{% endcode %}

### ETags

Update operations require ETags for optimistic locking:

{% code title="ETag example (HTTP)" %}
```bash
PATCH /api/archive/123
If-Match: "etag-value"
```
{% endcode %}

## Error Handling

API errors follow standard HTTP status codes:

* `200 OK` - Success
* `201 Created` - Resource created
* `400 Bad Request` - Invalid request
* `401 Unauthorized` - Authentication required
* `403 Forbidden` - Permission denied
* `404 Not Found` - Resource not found
* `409 Conflict` - Conflict (e.g., ETag mismatch)
* `422 Unprocessable Entity` - Validation error
* `500 Internal Server Error` - Server error

Error response format:

{% code title="Error response (JSON)" %}
```json
{
  "_status": "ERR",
  "_error": {
    "code": 400,
    "message": "Validation failed"
  },
  "_issues": {
    "headline": "required field"
  }
}
```
{% endcode %}

## Rate Limiting

API requests may be rate-limited. Check response headers:

* `X-RateLimit-Limit` - Maximum requests per window
* `X-RateLimit-Remaining` - Remaining requests
* `X-RateLimit-Reset` - Time when limit resets

## Examples

### Create an Article

{% code title="Create an article (curl)" %}
```bash
curl -X POST https://your-instance.com/api/archive \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -d '{
    "headline": "Breaking News",
    "body_html": "<p>Story content here</p>",
    "type": "text",
    "urgency": 1
  }'
```
{% endcode %}

### Update an Article

{% code title="Update an article (curl)" %}
```bash
curl -X PATCH https://your-instance.com/api/archive/abc123 \
  -H "Content-Type: application/json" \
  -H "If-Match: \"etag-value\"" \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -d '{
    "headline": "Updated Headline"
  }'
```
{% endcode %}

### Search Articles

{% code title="Search articles (curl)" %}
```bash
curl -X GET https://your-instance.com/api/archive \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -G \
  --data-urlencode 'where={"type":"text"}' \
  --data-urlencode 'sort=-versioncreated' \
  --data-urlencode 'max_results=10'
```
{% endcode %}

### Publish an Article

{% code title="Publish an article (curl)" %}
```bash
curl -X POST https://your-instance.com/api/publish \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -d '{
    "item_id": "abc123",
    "desk": "sports",
    "stage": "published"
  }'
```
{% endcode %}

### Query Production API Items

{% code title="Get all packages (curl)" %}
```bash
# Get all packages
curl -g "$PRODAPI/items?source={\"query\":{\"filtered\":{\"filter\":{\"terms\":{\"type\":[\"composite\"]}}}}}" \
  -H "Authorization: Bearer $JWT_TOKEN"
```
{% endcode %}

{% code title="Filter by desk (curl)" %}
```bash
# Filter by desk
curl -g "$PRODAPI/items?source={\"query\":{\"filtered\":{\"filter\":{\"terms\":{\"task.desk\":[\"5c489481405ecc015e5e10bc\"]}}}}}" \
  -H "Authorization: Bearer $JWT_TOKEN"
```
{% endcode %}

{% code title="Filter by assignment (curl)" %}
```bash
# Filter by assignment
curl -g "$PRODAPI/items?source={\"query\":{\"bool\":{\"must\":{\"terms\":{\"assignment_id\":[\"60e403bc8361feb5664719b1\"]}}}}}" \
  -H "Authorization: Bearer $JWT_TOKEN"
```
{% endcode %}

## WebSocket API

For real-time updates, Superdesk uses WebSockets:

{% code title="WebSocket example (JavaScript)" %}
```javascript
const ws = new WebSocket('wss://your-instance.com/ws');

ws.onmessage = (event) => {
  const data = JSON.parse(event.data);
  console.log('Received update:', data);
};
```
{% endcode %}

## Next Steps

* [Developer Guide](file:///docs/developer-guide/architecture) - Understand the architecture
* [Core Backend Documentation](file:///docs/developer-guide/core) - Learn about the backend
* [Client Frontend Documentation](file:///docs/developer-guide/client) - Learn about the frontend
* [Contributing](file:///docs/contributing) - Help improve the API

## Resources

* [Eve Framework Documentation](https://docs.python-eve.org/) - Backend framework
* [OpenAPI Specification](https://swagger.io/specification/) - API spec format
* [REST API Best Practices](https://restfulapi.net/) - REST principles
* [Production API Documentation](https://superdesk.readthedocs.io/en/latest/production_api.html) - Original documentation
