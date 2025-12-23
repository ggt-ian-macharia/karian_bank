# Core Banking API - Learning Project

## Overview

A production-grade core banking API built with Node.js, Express, PostgreSQL, and Prisma to demonstrate enterprise-level software engineering practices including:

- ✅ **Multi-tenancy** (Database-per-tenant architecture)
- ✅ **Idempotency** (Prevent duplicate transactions)
- ✅ **API Rate Limiting** (DoS protection)
- ✅ **Pagination** (Cursor and offset-based)
- ✅ **Reports** (PDF and Excel generation)
- ✅ **Security** (JWT, RBAC, encryption, audit logging)
- ✅ **Performance** (Caching, query optimization, indexing)
- ✅ **Maintainability** (Layered architecture, dependency injection, DTOs)
- ✅ **Double-Entry Bookkeeping** (Financial accuracy)
- ✅ **Batch Processing** (Scheduled jobs and bulk operations)

---

## Documentation

All comprehensive documentation is available in the `docs/` directory:

### Requirements
- [Functional Requirements](docs/requirements/functional-requirements.md) - Core banking features and modules
- [Non-Functional Requirements](docs/requirements/non-functional-requirements.md) - Performance, security, scalability

### Architecture
- [System Design](docs/architecture/system-design.md) - High-level architecture and design patterns
- [Database Design](docs/architecture/database-design.md) - Multi-tenancy database strategy and schemas
- [Folder Structure](docs/architecture/folder-structure.md) - Project organization and layer responsibilities

### Best Practices
- [Idempotency](docs/best-practices/idempotency.md) - Preventing duplicate transactions
- More guides coming soon (Security, Performance, Rate Limiting, etc.)

### Implementation
- [Implementation Roadmap](docs/implementation-roadmap.md) - Phased development plan (14 weeks)

---

## Quick Start

### Prerequisites

- **Node.js** v20+ LTS
- **PostgreSQL** 15+
- **Redis** (for caching and rate limiting)
- **npm** or **yarn**

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd karian_bank

# Install dependencies
npm install

# Copy environment variables
cp .env.example .env

# Edit .env with your configuration
# Set up master and tenant database URLs

# Run database migrations
npx prisma migrate dev --schema=./prisma/master.prisma
npx prisma migrate dev --schema=./prisma/tenant.prisma

# Seed databases (optional)
npm run seed

# Start development server
npm run dev
```

---

## Technology Stack

### Backend
- **Runtime**: Node.js v20+ LTS
- **Framework**: Express.js
- **Language**: TypeScript
- **ORM**: Prisma
- **Database**: PostgreSQL 15+
- **Cache**: Redis
- **Queue**: Bull (Redis-based)

### Security
- **Authentication**: JWT (jsonwebtoken)
- **Password Hashing**: bcrypt
- **Security Headers**: Helmet.js
- **Rate Limiting**: express-rate-limit

### Validation & DTOs
- **Validation**: Joi / Zod
- **Sanitization**: express-validator

### Testing
- **Framework**: Jest with ts-jest
- **API Testing**: Supertest
- **Coverage**: jest --coverage

### Documentation
- **API Docs**: Swagger/OpenAPI
- **Code Docs**: JSDoc

### Reporting
- **PDF**: PDFKit
- **Excel**: ExcelJS

### Logging & Monitoring
- **Logging**: Winston / Pino
- **Metrics**: Prometheus (prom-client)

---

## Project Structure

```
karian_bank/
├── src/
│   ├── api/                    # API layer (routes, controllers, middleware)
│   ├── services/               # Business logic
│   ├── repositories/           # Data access layer
│   ├── utils/                  # Utilities (logger, errors, etc.)
│   ├── config/                 # Configuration
│   ├── lib/                    # Third-party integrations
│   └── jobs/                   # Scheduled jobs
├── prisma/
│   ├── master.prisma           # Master database schema
│   ├── tenant.prisma           # Tenant database schema
│   └── migrations/             # Database migrations
├── tests/
│   ├── unit/                   # Unit tests
│   ├── integration/            # Integration tests
│   └── e2e/                    # End-to-end tests
├── docs/                       # Documentation
├── scripts/                    # Utility scripts
└── server.js                   # Application entry point
```

See [Folder Structure](docs/architecture/folder-structure.md) for detailed explanation.

---

## Core Features

### Phase 1: Foundation (Completed: ⬜)
- [ ] Multi-tenant architecture
- [ ] Authentication & Authorization (JWT + RBAC)
- [ ] User management
- [ ] Core utilities and middleware

### Phase 2: Core Banking (Completed: ⬜)
- [ ] Customer management (KYC)
- [ ] Account management (Savings, Checking, Fixed Deposit)
- [ ] Transaction processing (Deposit, Withdrawal, Transfer)
- [ ] Double-entry ledger system

### Phase 3: Advanced Features (Completed: ⬜)
- [ ] Idempotency for transactions
- [ ] Rate limiting
- [ ] Pagination (cursor and offset-based)
- [ ] PDF and Excel reports
- [ ] Batch processing
- [ ] Payment gateway integration (simulated)

### Phase 4: Security & Compliance (Completed: ⬜)
- [ ] Comprehensive audit logging
- [ ] Data encryption
- [ ] Compliance features (GDPR)
- [ ] Security monitoring

---

## Testing

```bash
# Run all tests
npm test

# Run unit tests only
npm run test:unit

# Run integration tests
npm run test:integration

# Run with coverage
npm run test:coverage

# Run specific test file
npm test -- tests/unit/services/transaction.service.test.js
```

---

## API Documentation

Once the server is running, API documentation is available at:

```
http://localhost:3000/api-docs
```

---

## Environment Variables

See `.env.example` for all required environment variables:

```bash
# Application
NODE_ENV=development
PORT=3000

# Master Database
MASTER_DATABASE_URL=postgresql://user:password@localhost:5432/master_db

# Tenant Database (template)
TENANT_DATABASE_URL=postgresql://user:password@localhost:5432/tenant_db

# JWT
JWT_SECRET=your-secret-key
JWT_EXPIRES_IN=15m

# Redis
REDIS_HOST=localhost
REDIS_PORT=6379

# ... and more
```

---

## Development Scripts

```bash
# Start development server with hot reload
npm run dev

# Run linting
npm run lint

# Format code
npm run format

# Run database migrations
npm run migrate

# Seed database
npm run seed

# Generate Prisma client
npm run prisma:generate
```

---

## Learning Outcomes

By completing this project, you will learn:

1. **Architecture Patterns**
   - Layered architecture
   - Repository pattern
   - Service layer pattern
   - Dependency injection

2. **Advanced Concepts**
   - Multi-tenancy (database-per-tenant)
   - Idempotency
   - Double-entry bookkeeping
   - Optimistic locking
   - Rate limiting
   - Pagination strategies

3. **Security**
   - JWT authentication
   - RBAC authorization
   - Password hashing
   - Data encryption
   - Audit logging

4. **Performance**
   - Database indexing
   - Query optimization
   - Caching strategies
   - Connection pooling

5. **Best Practices**
   - Separation of concerns
   - DTOs and validation
   - Error handling
   - Testing strategies
   - API design

---

## Roadmap

See [Implementation Roadmap](docs/implementation-roadmap.md) for the complete 14-week development plan.

**Current Phase**: Phase 1 - Foundation & Setup

---

## Contributing

This is a learning project. Feel free to:
- Experiment with different approaches
- Add new features
- Improve existing code
- Document your learnings

---

## License

This project is for educational purposes.

---

## Acknowledgments

Built to learn enterprise-level software engineering practices in:
- Multi-tenancy
- Idempotency
- Security
- Performance optimization
- Maintainable architecture

---

## Support

For questions or clarifications, refer to the comprehensive documentation in the `docs/` directory.

**Happy Learning!**
