---
sidebar_position: 1
---

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

* **Backend**: [Superdesk Core (Backend)](index-2/index-1.md)
* **Frontend**: [Superdesk Client Core (Frontend)](index-2/index.md)
* **Planning module** (optional): [Superdesk Planning](index-2/index-2.md)
* **Architecture**: [Architecture Overview](index-2/architecture.md)

## Next Steps

* [**Install and deploy**](installation.md)
* [**Quick Start**](index-2/quick-start.md)
* [**Developer Guide**](index-2/)
* [**Contributing to Superdesk**](index-1.md)

## Getting Help

* **GitHub Issues**: Report bugs and request features on the respective repository
* **Community**: Join our community discussions on GitHub
* **Documentation**: Explore this documentation site for detailed guides

## Contributing

We welcome contributions. See [Contributing to Superdesk](index-1.md).
