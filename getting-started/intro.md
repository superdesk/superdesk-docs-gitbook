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

* **Backend**: [Superdesk Core (Backend)](/broken/spaces/iQkljDhdKl4KTB0EU3WI/pages/rhbW6vEzphxtXnh15CPN)
* **Frontend**: [Superdesk Client Core (Frontend)](/broken/spaces/iQkljDhdKl4KTB0EU3WI/pages/KUfLO2S6Bf5SQu4ER3Hh)
* **Planning module** (optional): [Superdesk Planning](/broken/spaces/iQkljDhdKl4KTB0EU3WI/pages/ZwihAf6RxbAJscL0lPVr)
* **Architecture**: [Architecture Overview](/broken/spaces/iQkljDhdKl4KTB0EU3WI/pages/f368d1814bc2e57d3c73bf434486881ed50ea82f)

## Next Steps

* [**Install and deploy**](installation.md)
* [**Quick Start**](/broken/spaces/iQkljDhdKl4KTB0EU3WI/pages/LPDze84CPGj78Z1hu3GT)
* [**Developer Guide**](/broken/spaces/iQkljDhdKl4KTB0EU3WI/pages/n8TCq6Twx0douCtHFqb6)
* [**Contributing to Superdesk**](../contributing/index.md)

## Getting Help

* **GitHub Issues**: Report bugs and request features on the respective repository
* **Community**: Join our community discussions on GitHub
* **Documentation**: Explore this documentation site for detailed guides

## Contributing

We welcome contributions. See [Contributing to Superdesk](../contributing/index.md).
