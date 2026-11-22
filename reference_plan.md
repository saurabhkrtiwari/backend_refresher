# Spring Refresher Plan

Based on reference materials and career transition goals.

## Reference Materials Available

| File | Size | Author/Source | Focus |
|---|---|---|---|
| `Somnath Musib - Spring Boot in Practice (2022)` | 39.8 MB | Manning Publications | Practical patterns, best practices, real-world scenarios |
| `spring-6.pdf` | 29.4 MB | Likely Spring Framework 6 | New features, Java 17+, Spring Framework 6 changes |

---

## Refresher Plan Structure

### Phase 1: Core Spring Boot Fundamentals (3-4 days)
**Goal:** Solidify IoC, DI, auto-configuration, starters — map to your migration experience.

| Topic | Reference | MD File | Key Concepts |
|---|---|---|---|
| Spring Container & Bean lifecycle | Ch. 1-2 of *Spring Boot in Practice* | `01-core-spring-boot.md` | BeanFactory, ApplicationContext, scopes, init/destroy methods |
| Dependency Injection patterns | Ch. 3 | `01-core-spring-boot.md` | Constructor vs setter vs field injection, circular dependency resolution |
| Auto-configuration mechanics | Ch. 4-5 | `01-core-spring-boot.md` | `@Conditional` hierarchy, AutoConfigurationImportSelector, META-INF/spring.factories |
| Starter dependencies | Ch. 6 | `01-core-spring-boot.md` | How starters work, transitive dependencies, custom starter creation |
| **Mermaid: Bean Lifecycle** | — | `01-core-spring-boot.md` | See diagram below |

---

### Phase 2: Advanced Spring Boot & APIs (3-4 days)
**Goal:** Web layer, data access, security — connect to your microservices & REST API experience.

| Topic | Reference | MD File | Key Concepts |
|---|---|---|---|
| Spring MVC & REST controllers | Ch. 7-8 | `02-advanced-spring-boot.md` | @RestController, @RequestMapping, @PathVariable, @RequestBody, exception handling |
| Spring WebFlux (reactive) | Ch. 9 | `02-advanced-spring-boot.md` | Mono/Flux, Project Reactor, non-blocking, when to choose WebFlux vs MVC |
| Spring Data JPA tuning | Ch. 10-11 | `02-advanced-spring-boot.md` | EntityGraph, @Query, pagination optimization, N+1 problem, @Modifying |
| Spring Security 6 | Ch. 12-14 | `02-advanced-spring-boot.md` | JWT, OAuth2, @EnableMethodSecurity, filter chain, method-level security |
| **Mermaid: REST API Design** | — | `03-microservices-architecture.md` | See existing diagram |

---

### Phase 3: Microservices & Architecture (3-4 days)
**Goal:** Service design, patterns, distributed systems — map to your EKS migration & distributed sessions.

| Topic | Reference | MD File | Key Concepts |
|---|---|---|---|
| Service discovery | Ch. 15-16 | `03-microservices-architecture.md` | Eureka, Consul, Kubernetes DNS, self-registration |
| Distributed sessions with Redis | Ch. 17 | `03-microservices-architecture.md` | Spring Session, Redis-backed session, cookie management |
| Event-driven workflows | Ch. 18-19 | `03-microservices-architecture.md` | Spring Cloud Stream, @EnableBinding, Publisher/Consumer, DLQ |
| Multi-tenancy patterns | Ch. 20 | `03-microservices-architecture.md` | Database-per-tenant, schema-per-tenant, discriminator column, CurrentTenantIdentifierResolver |
| **Mermaid: Multi-tenancy** | — | `03-microservices-architecture.md` | See existing diagram |

---

### Phase 4: Cloud, DevOps & Performance (3-4 days)
**Goal:** EKS deployment, tuning, observability — directly map to your production incidents.

| Topic | Reference | MD File | Key Concepts |
|---|---|---|---|
| AWS EKS deployment | Ch. 21-23 | `04-cloud-devops.md` | kubectl, Deployments, Services, Ingress (NGINX/ALB), Argo CD GitOps |
| Docker multi-stage builds | Ch. 24 | `04-cloud-devops.md` | Optimized JRE images, -XX:MaxRAMPercentage, -XX:+UseContainerSupport |
| JVM/G1GC tuning | Ch. 25-26 | `05-performance-tuning.md` | -XX:MaxGCPauseMillis, -XX:+PrintGCDetails, OOM analysis, glibc malloc-arena |
| Query/cache optimization | Ch. 27-28 | `05-performance-tuning.md` | EXPLAIN ANALYZE, indexing, Redis caching, Caffeine, slow query detection |
| Observability with SigNoz | Ch. 29-30 | `05-performance-tuning.md` | OpenTelemetry, traces, metrics, logs, correlation IDs |
| **Mermaid: JVM Tuning Workflow** | — | `05-performance-tuning.md` | See planned diagram |

---

### Phase 5: Interview & Architectural Prep (2-3 days)
**Goal:** HLD/LLD questions, ADRs, leadership scenarios — target roles.

| Topic | Reference | MD File | Key Concepts |
|---|---|---|---|
| HLD design patterns | `06-interview-questions.md` | `06-interview-questions.md` | Order management system, microservice boundaries, data consistency |
| LLD design questions | `06-interview-questions.md` | `06-interview-questions.md` | Order aggregate, @Version optimistic locking, @EntityGraph |
| Technical debt & ADRs | `06-interview-questions.md` | `06-interview-questions.md` | ADR template, documentation, decision records |
| Leadership & mentoring scenarios | `06-interview-questions.md` | `06-interview-questions.md` | Code review process, onboarding, technical disagreements |
| **Mermaid: Architecture Decision Record** | — | `06-interview-questions.md` | See planned diagram |

---

## Integration with Existing MD Files

The 6 MD files already created are the **primary learning artifacts**. This plan:

1. **Annotates** each file with reference material chapter correlations
2. **Identifies** where Mermaid diagrams should be added/updated
3. **Maps** your real experience to each topic (already in README.md)
4. **Provides** a phased approach rather than "boil the ocean"

---

## Suggested Study cadence

| Week | Focus | Output |
|---|---|---|
| **Week 1** | Phase 1 (Core) | Complete `01-core-spring-boot.md` with all Mermaid diagrams |
| **Week 2** | Phase 2 (Advanced) | Complete `02-advanced-spring-boot.md`; add WebFlux/security diagrams |
| **Week 3** | Phase 3 (Microservices) | Complete `03-microservices-architecture.md`; expand multi-tenancy |
| **Week 4** | Phase 4 (Cloud/Perf) | Complete `04-cloud-devops.md`; add JVM tuning workflow diagram |
| **Week 5** | Phase 5 (Interview) | Review `06-interview-questions.md`; prepare 3 ADRs from experience |
| **Ongoing** | Reference back | Use Manning book for deep dives; update MD files as new insights |

---

## Your Experience Mapping Priority

Topics to emphasize based on your resume:

| Your Project | Plan Phase | MD File |
|---|---|---|
| JSF → Spring Boot migration (Java 8→17) | Phase 1 | `01-core-spring-boot.md` |
| Redis distributed sessions in EKS | Phase 3 | `03-microservices-architecture.md` |
| G1GC/OOM root-cause analysis | Phase 4 | `05-performance-tuning.md` |
| Spring Boot microservices & REST APIs | Phase 2 | `02-advanced-spring-boot.md` |
| Claude Code for feature dev | Phase 5 (note) | `06-interview-questions.md` |
| 99.9% uptime targets | Phase 4 | `05-performance-tuning.md` |
| Mentoring 5 developers | Phase 5 | `06-interview-questions.md` |

---
*Plan created: 2026-11-22*
*Based on: Somnath Musib - Spring Boot in Practice (2022, Manning) + spring-6.pdf*