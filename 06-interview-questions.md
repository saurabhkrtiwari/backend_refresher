# Interview Questions for Senior Roles

## Technical Architecture Questions

### High-Level Design (HLD)

1. **Design an e-commerce order management system**
   - Components: Order Service, Inventory Service, Payment Service, Notification Service
   - Data consistency patterns (Saga, TCC, Outbox)
   - API design between services
   - Database choice per service
   - Deployment strategy (Kubernetes, service mesh)

2. **Microservices vs Monolith trade-offs**
   - When to choose each
   - Organizational alignment (Conway's Law)
   - Deployment complexity vs modularity
   - Data consistency challenges

3. **Service discovery and API gateway**
   - Eureka vs Consul vs Kubernetes DNS
   - API gateway patterns (Spring Cloud Gateway, Kong, Envoy)
   - Route filtering, rate limiting, authentication
   - Circuit breaker patterns (Resilience4j)

### Low-Level Design (LLD)

4. **Design the `Order` aggregate with proper invariants**
   - Order states: CREATED, CONFIRMED, PAID, SHIPPED, DELIVERED, CANCELLED
   - Domain events: OrderCreated, PaymentCompleted, OrderShipped
   - Aggregate root boundaries
   - Repository design

5. **JPA Entity optimization**
   - `@EntityGraph` vs `JOIN FETCH` vs Lazy vs Eager
   - `@BatchSize` for collections
   - Identify and fix N+1 problem in provided code
   - Query performance tuning strategies

6. **Concurrent access and consistency**
   - `@Transactional` isolation levels
   - Optimistic locking with `@Version`
   - Pessimistic locking with `LockModeType`
   - Deadlock prevention

## System Design Scenarios

7. **High-throughput notification system**
   - 10,000 requests/second
   - Fan-out to multiple channels (email, SMS, push)
   - Retry and dead-letter queue strategy
   - Rate limiting per channel

8. **Real-time search with Elasticsearch**
   - Index mapping strategy
   - Analyzers and tokenizers
   - Replica shard planning
   - Near real-time search considerations

9. **Cache invalidation strategy**
   - Time-based vs event-driven invalidation
   - Cache stampede prevention
   - Distributed cache consistency

## Cloud & DevOps Questions

10. **EKS OOM killer scenario**
    - How would you diagnose `OOMKilled` in production?
    - GC tuning approach: G1GC flags and monitoring
    - Container resource requests/limits best practices
    - Memory profiling in Kubernetes

11. **CI/CD pipeline design**
    - Build time optimization (Maven/Gradle cache)
    - Test isolation and parallel execution
    - Artifact promotion (dev → test → prod)
    - Rollback strategy on failed deployment

12. **Observability strategy**
    - Distributed tracing across 5+ microservices
    - Log correlation with MDC/Correlation-ID
    - Metrics dashboards for SRE team
    - Alerting on SLA/SLO breaches

## Architecture & Leadership Questions

13. **Technical debt assessment and remediation**
    - How do you measure technical debt?
    - Prioritizing debt paydown vs feature delivery
    - Refactoring strategy without breaking changes
    - Documenting architecture decisions (ADR)

14. **Mentoring and code review process**
    - What makes an effective code review?
    - Onboarding new engineers to the codebase
    - Knowledge sharing practices (tech talks, pairing)
    - Handling disagreement in technical decisions

15. **Architecture decision records (ADRs)**
    - When and how to document ADRs
    - ADR template and repository structure
    - Review and approval process for ADRs
    - Keeping ADRs current as system evolves

16. **Multi-tenant architecture design**
    - Tenant isolation levels (database vs schema vs discriminator)
    - Tenant ID resolution from requests
    - Data privacy and compliance considerations
    - Onboarding new tenants programmatically

17. **Graceful degradation and fault tolerance**
    - Circuit breaker patterns and thresholds
    - Fallback strategies per downstream dependency
    - Bulkhead isolation
    - Graceful shutdown sequences

18. **Database migration strategy**
    - Blue-green deployment for schema changes
    - Backward-compatible API changes
    - Data migration tools (Flyway, Liquibase)
    - Rollback plan considerations

---
*File created: 02-11-2026*
*Target roles: Tech Lead, Lead Engineer, Technical Architect, Solution Architect*