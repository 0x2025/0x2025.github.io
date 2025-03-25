---
title: Scale Millions of Users with Strapi
date: 2025-03-18
tags:
    - software_development
    - strapi
categories:
    - builder
    - build fast
keywords:
    - software_development
    - strapi
---
# What?

We built an Instagram Reel-like application with like/share/comment features serving millions of users in less than 6 months using Strapi. Here's our journey and challenges.

# Why Strapi?

Strapi is a headless CMS with an intuitive UI and simple setup. It provides everything needed out-of-the-box:
- HTTP Server
- Authentication & Authorization
- Role-based permissions
- Database Management
- Migrations
- REST API

# Architecture

Our architecture splits into two parts:
1. A CMS (Strapi)
2. Microservices (handling listing, interactions, search)

We use Kafka as the central hub for data replication between CMS and microservices, following an event-driven architecture. Each service operates independently, eliminating single points of failure.

# Challenges

## Limited Admin Portal UI Customization
Strapi's design language is strict. Custom features like tabbed listing pages require building new pages without reusing Strapi components.

## Document Service Performance Trade-offs
Strapi's Document Service manages relationships, content lifecycle, and audit logs automatically. However, this impacts performance at scale. We solved this by using Knex directly for high-traffic parts.

## Implementing CQRS
Strapi doesn't natively support Command Query Responsibility Segregation (CQRS). We implemented it by:
1. Creating a new @strapi/database instance
2. Reusing metadata from the original database
3. Disabling migrations for read database

Example code:
```typescript
// register method (index.ts)
const db = new Database(strapi.config.get('database.read'));
strapi.add('readDb', db);

// bootstrap method (index.ts)
const db = strapi.get('readDb');
db.metadata = strapi.db.metadata;

// Usage
const db = strapi.get('readDb');
db.query('api:restaurants.restaurants').find(...);
```

## Database Schema Constraints
Strapi creates default fields (id, documentId, publishedAt) with fixed configurations. We used custom migration scripts to modify field properties when needed.

# Conclusion

Strapi accelerated our development by providing essential features out-of-the-box. Despite customization limitations, understanding the "Strapi way" allows efficient development, including building custom UIs using its headless capabilities.
