# architecture

This document provides a high-level overview of Superdesk's architecture and how its components work together.

## System Architecture

Superdesk follows a modern, modular architecture with clear separation between frontend and backend:

```
┌─────────────────────────────────────────────────────────────────┐
│                         Client Layer                            │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌───────────────────────────────────────────────────────┐    │
│  │        React/TypeScript Frontend                       │    │
│  │  (superdesk-client-core + extensions)                 │    │
│  │                                                        │    │
│  │  - UI Components (React)                              │    │
│  │  - State Management (Redux)                           │    │
│  │  - API Client                                         │    │
│  │  - Extensions & Plugins                               │    │
│  └───────────────────────────────────────────────────────┘    │
│                           │ HTTP/REST                           │
└───────────────────────────┼─────────────────────────────────────┘
                            │
┌───────────────────────────┼─────────────────────────────────────┐
│                           │    Server Layer                     │
├───────────────────────────┼─────────────────────────────────────┤
│                           ▼                                     │
│  ┌───────────────────────────────────────────────────────┐    │
│  │         Flask/Python Backend                          │    │
│  │         (superdesk-core)                              │    │
│  │                                                        │    │
│  │  - REST API (Eve framework)                           │    │
│  │  - Business Logic Services                            │    │
│  │  - Workflow Engine                                    │    │
│  │  - Publishing System                                  │    │
│  │  - Media Processing                                   │    │
│  │  - Apps & Extensions                                  │    │
│  └───────────────────────────────────────────────────────┘    │
│                           │                                     │
└───────────────────────────┼─────────────────────────────────────┘
                            │
┌───────────────────────────┼─────────────────────────────────────┐
│                           │   Data Layer                        │
├───────────────────────────┼─────────────────────────────────────┤
│                           ▼                                     │
│  ┌────────────┐  ┌──────────────┐  ┌────────────┐            │
│  │  MongoDB   │  │ Elasticsearch │  │   Redis    │            │
│  │            │  │              │  │            │            │
│  │ - Content  │  │ - Search     │  │ - Cache    │            │
│  │ - Users    │  │ - Indexing   │  │ - Sessions │            │
│  │ - Metadata │  │ - Analytics  │  │ - Queues   │            │
│  └────────────┘  └──────────────┘  └────────────┘            │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

## Core Components

### Frontend (superdesk-client-core)

The frontend is built with modern web technologies:

* **React**: Component-based UI framework
* **TypeScript**: Type-safe JavaScript
* **Redux**: State management
* **RxJS**: Reactive programming for data streams
* **Webpack**: Module bundling and build system

Key features:

* Rich text editor with formatting
* Drag-and-drop interface
* Real-time updates
* Extensible plugin system
* Responsive design

### Backend (superdesk-core)

The backend is built with Python and Flask:

* **Flask**: Lightweight web framework
* **Eve**: REST API framework built on Flask
* **Celery**: Asynchronous task processing
* **Python 3.8+**: Modern Python features

Key features:

* RESTful API design
* Event-driven architecture
* Extensible app system
* Pluggable storage backends
* Multi-tenancy support

### Data Storage

#### MongoDB

Primary database for storing:

* Content items (articles, media)
* User accounts and permissions
* Desk and workflow configuration
* Publishing destinations
* Audit logs

#### Elasticsearch

Powers search and analytics:

* Full-text search
* Faceted filtering
* Aggregations and analytics
* Content indexing
* Search suggestions

#### Redis

Used for:

* Session management
* Caching
* Background job queues
* Real-time notifications
* Rate limiting

## Data Flow

### Content Creation Flow

{% stepper %}
{% step %}
### User input and frontend

User interacts with a React component which dispatches a Redux action and triggers an API call.
{% endstep %}

{% step %}
### Backend processing

Backend API validates the request and processes it via the service layer, then stores data in MongoDB.
{% endstep %}

{% step %}
### Indexing and UI update

Content is indexed in Elasticsearch. A WebSocket update triggers the UI to refresh with the new content.
{% endstep %}
{% endstepper %}

### Publishing Flow

{% stepper %}
{% step %}
### Publish request and validation

A publish request goes through workflow validation and the publishing service.
{% endstep %}

{% step %}
### Formatting and transmission

Content is formatted and transmitted to the publishing destinations, then archived.
{% endstep %}

{% step %}
### Post-publish updates

Publishing status is updated, the content is indexed in Elasticsearch, and users are notified.
{% endstep %}
{% endstepper %}

## Extension Architecture

Superdesk supports extensions at multiple levels:

### Backend Extensions

```python
# Example app structure
my_app/
├── __init__.py        # App initialization
├── service.py         # Business logic
├── resource.py        # API endpoints
└── commands.py        # CLI commands
```

### Frontend Extensions

```typescript
// Example extension structure
my-extension/
├── index.tsx          // Extension entry point
├── components/        // React components
├── services/          // API services
└── styles/            // CSS/SCSS
```

## Communication Patterns

### REST API

* Standard HTTP methods (GET, POST, PATCH, DELETE)
* JSON payloads
* ETags for concurrency control
* HATEOAS links for navigation

### WebSockets

* Real-time notifications
* Content updates
* User presence
* System alerts

### Message Queue

* Background jobs (Celery)
* Email notifications
* Media processing
* Report generation

## Security Architecture

### Authentication

* Session-based authentication
* OAuth2 support
* SAML integration
* API tokens for integrations

### Authorization

* Role-based access control (RBAC)
* Resource-level permissions
* Desk and stage restrictions
* Publishing rights management

### Data Protection

* HTTPS encryption in transit
* Database encryption at rest (optional)
* Media file encryption
* Audit logging

## Scalability Considerations

### Horizontal Scaling

* Stateless API servers
* Load-balanced frontend
* Shared session storage (Redis)
* Distributed Elasticsearch

### Performance Optimization

* Database indexing
* Query optimization
* CDN for media files
* Browser caching
* API response caching

## Module System

### Core Modules

* **Content Management**: Article creation and editing
* **Media**: Image and video handling
* **Workflow**: Desk and stage management
* **Publishing**: Multi-channel distribution
* **Search**: Advanced content discovery
* **Users**: User management and permissions

### Optional Modules

* **Planning**: Event and assignment management
* **Analytics**: Usage and performance metrics
* **Archive**: Long-term content storage
* **Monitoring**: Content monitoring and tracking

## Next Steps

Explore detailed documentation for each component:

* [Core Backend](file:///docs/developer-guide/core)
* [Client Frontend](file:///docs/developer-guide/client)
* [Planning Module](file:///docs/developer-guide/planning)

For deployment information, see the [Deployment Guide](file:///docs/deployment).
