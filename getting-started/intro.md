# Introduction to Superdesk

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

## Core components

* **Backend**: [Superdesk Core (Backend)](../developer-guide/core/index.md)
* **Frontend**: [Superdesk Client Core (Frontend)](../developer-guide/client/index.md)
* **Planning module** (optional): [Superdesk Planning](../developer-guide/planning/index.md)
* **Architecture**: [Architecture Overview](../developer-guide/architecture.md)

## Next Steps

* [**Install and deploy**](installation.md)
* [**Quick Start**](quick-start.md)
* [**Developer Guide**](../developer-guide/index.md)
* [**Contributing to Superdesk**](../contributing/index.md)

## Getting Help

* **GitHub Issues**: Report bugs and request features on the respective repository
* **Community**: Join our community discussions on GitHub
* **Documentation**: Explore this documentation site for detailed guides

## Contributing

We welcome contributions. See [Contributing to Superdesk](../contributing/index.md).
