# intro

Welcome to the Superdesk documentation! Superdesk is an open-source headless CMS designed for newsrooms, providing end-to-end news creation, production, and publishing capabilities.

## What is Superdesk?

Superdesk is a comprehensive news management system that enables journalists and editors to create, collaborate on, and publish news content across multiple channels. It provides a modern, web-based interface with powerful features for newsrooms of all sizes.

## Architecture Overview

Superdesk consists of multiple components working together:

```
┌─────────────────────────────────────────────────────────┐
│                    Superdesk System                     │
├─────────────────────────────────────────────────────────┤
│                                                         │
│  ┌──────────────────┐      ┌──────────────────┐       │
│  │  Client (React)  │ ◄──► │  Backend (Flask) │       │
│  │ superdesk-client │      │  superdesk-core  │       │
│  └──────────────────┘      └──────────────────┘       │
│                                    │                    │
│                                    ▼                    │
│                            ┌──────────────┐            │
│                            │   MongoDB    │            │
│                            └──────────────┘            │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

## Key Repositories

### [superdesk-core](https://github.com/superdesk/superdesk-core)

The Python/Flask backend providing the REST API, business logic, and data persistence. This is the core server component that handles:

* Content management and storage
* User authentication and authorization
* Workflow management
* Publishing and distribution
* Media handling

### [superdesk-client-core](https://github.com/superdesk/superdesk-client-core)

The TypeScript/React frontend providing the user interface. This includes:

* Rich text editor
* Desk and workspace management
* Search and filtering
* Content preview and publishing
* User management interface

### [superdesk-planning](https://github.com/superdesk/superdesk-planning)

Planning and assignments module that extends Superdesk with:

* Event management
* Planning items
* Assignment workflows
* Coverage tracking
* Calendar views

### [superdesk](https://github.com/superdesk/superdesk)

The main deployment repository that brings together all components:

* Docker configurations
* Deployment scripts
* Environment setup
* Integration configurations

## Quick Start

{% stepper %}
{% step %}
### Using Docker (Recommended)

```bash
# Clone the main repository
git clone https://github.com/superdesk/superdesk.git
cd superdesk

# Start with Docker Compose
docker-compose up
```
{% endstep %}

{% step %}
### Development Setup

For development, you'll need to set up both the backend and frontend.

```bash
# Backend (superdesk-core)
cd superdesk-core
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python manage.py app:initialize_data
python manage.py app:run
```

```bash
# Frontend (superdesk-client-core)
cd superdesk-client-core
npm install
npm start
```
{% endstep %}
{% endstepper %}

## Next Steps

* [**Installation Guide**](/broken/pages/124e716c9a2820ef4ea55a1b81e890f4091d7822) - Detailed installation instructions
* [**Quick Start Guide**](/broken/pages/1886a01b2022d9329ea3e88e5cf549dc1a9e7922) - Get up and running quickly
* [**Developer Guide**](file:///docs/developer-guide/architecture) - Learn about the architecture
* [**User Guide**](file:///docs/user-guide) - Learn how to use Superdesk

## Getting Help

* **GitHub Issues**: Report bugs and request features on the respective repository
* **Community**: Join our community discussions on GitHub
* **Documentation**: Explore this documentation site for detailed guides

## Contributing

We welcome contributions! Please see our [Contributing Guide](file:///docs/contributing) to learn how you can help improve Superdesk.
