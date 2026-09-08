# VPN Service — Master Feature Roadmap

## Product Goal

Build a production-grade commercial VPN service where the Phase 1 MVP is intentionally limited in features but uses an architecture, data model, APIs, security model, and infrastructure foundation that can scale into the complete product without major rewrites.

> **Architecture principle:** Build the MVP small in features, but not small in architecture.

---

# Phase 1 — Production MVP

## 1. Customer Mobile App

- User registration
- Login/logout
- Email verification
- Password reset
- Basic account/profile
- VPN server/location list
- Country selection
- Connect/disconnect
- Connection status
- Connection error handling
- Basic connection statistics
- Current VPN IP display
- Basic settings
- App version/update information
- Privacy policy
- Terms of service
- Support/contact entry point

### Platform

- Android
- iOS

### VPN Protocol

- WireGuard

---

## 2. Authentication & Identity

- User accounts
- Secure password hashing
- Access/refresh token model
- Email verification
- Password reset
- Session management
- Device registration
- Device revocation
- Basic RBAC foundation

The identity architecture should be designed so that future features such as 2FA, social login, SSO, organizations, and business accounts can be added without redesigning authentication.

---

## 3. VPN Control Plane

The backend acts as the VPN control plane and does not carry normal user VPN traffic.

Responsibilities:

- VPN location management
- VPN server management
- Device registration
- WireGuard peer management
- VPN configuration generation
- VPN IP allocation
- Server selection
- Session creation
- Session termination
- Access authorization
- Subscription entitlement validation
- Configuration revocation

---

## 4. VPN Infrastructure

Initial infrastructure:

- WireGuard VPN servers
- 2–3 initial countries/locations
- One or more servers per location
- Linux-based VPN servers
- Firewall configuration
- NAT
- Routing
- DNS configuration
- IPv4 support
- Basic IPv6 strategy
- Server health checks
- Server registration with control plane

The server architecture should support future expansion to hundreds/thousands of servers.

---

## 5. Backend / API

### Recommended Stack

- Node.js
- TypeScript
- NestJS
- PostgreSQL
- Redis

### Initial Backend Modules

- Auth
- Users
- Devices
- VPN locations
- VPN servers
- VPN configurations
- VPN sessions
- Subscriptions
- Payments
- Notifications
- Admin
- Audit logs

---

## 6. Database

### Initial Core Entities

- users
- user_sessions
- devices
- vpn_locations
- vpn_servers
- vpn_server_metrics
- vpn_peers
- vpn_ip_pools
- vpn_ip_allocations
- vpn_sessions
- plans
- subscriptions
- payments
- payment_events
- admin_users
- audit_logs

Database design should use extensible relationships rather than hard-coded countries, servers, protocols, or plans.

---

## 7. Payments & Subscriptions

### MVP

- Monthly subscription
- Annual subscription
- Payment checkout
- Subscription activation
- Subscription expiration
- Cancellation
- Payment webhook processing
- Failed payment handling
- Basic refund handling
- Invoice/receipt support

### Potential Providers

- Stripe
- Razorpay or another India-focused provider

The subscription system should be provider-agnostic so additional payment providers can be added later.

---

## 8. Admin Panel

### MVP Admin Modules

- Dashboard
- Users
- User devices
- VPN locations
- VPN servers
- Active sessions
- Plans
- Subscriptions
- Payments
- Basic system logs
- Basic audit logs

### Admin Capabilities

- Add/remove locations
- Register servers
- Enable/disable servers
- View server health
- View active sessions
- Manage plans
- View subscriptions
- Manage users

---

## 9. Monitoring & Operations

### MVP

- Server health monitoring
- API health monitoring
- CPU/RAM monitoring
- Basic bandwidth monitoring
- Active VPN session monitoring
- Error monitoring
- Application logs
- Audit logs
- Basic alerts

### Foundation For

- Prometheus
- Grafana
- Centralized logging
- Automated alerting

---

## 10. Security & Privacy Foundation

- TLS everywhere
- Secure authentication
- Secure secret management
- WireGuard key management
- Least-privilege access
- Firewall rules
- Admin RBAC
- Audit logging
- Secure configuration storage
- Basic abuse prevention
- Account deletion
- Privacy policy
- Terms of service
- Data retention policy

The privacy model should be defined before collecting analytics or connection data.

---

## 11. DevOps

- Docker
- GitHub Actions
- CI/CD
- Development environment
- Staging environment
- Production environment
- Infrastructure configuration
- Automated tests
- Database migrations
- Environment/secret management
- Deployment process
- Backup strategy
- Basic disaster recovery plan

---

# Phase 2 — Core VPN Product

## Mobile

- Quick Connect
- Fastest server
- Recommended server
- Favorite locations
- Recent locations
- Auto-connect
- Reconnect handling
- Kill switch
- Split tunneling
- DNS leak protection
- IPv6 leak protection
- Network-change handling
- Wi-Fi/mobile-data rules
- Connection notifications
- Better connection diagnostics

## VPN Infrastructure

- Multiple servers per location
- Server pools
- Server load measurement
- Automatic server selection
- Load-aware routing
- Server capacity management
- Automated health checks
- Server draining
- Improved DNS infrastructure
- IPv6 support

## Backend

- Server selection engine
- Load balancing logic
- Connection policy engine
- Device limits
- Concurrent connection limits
- Advanced session management
- Feature flags
- Configuration versioning

## Admin

- Real-time server status
- Server load
- Bandwidth monitoring
- Session monitoring
- Server capacity
- Location management
- Feature flags
- User connection diagnostics

---

# Phase 3 — Advanced Privacy & Networking

## VPN Protocols

- OpenVPN
- Additional protocol support where commercially justified
- Protocol selection
- Automatic protocol selection

## Advanced Networking

- Multi-hop / Double VPN
- Advanced routing
- Custom DNS
- DNS filtering
- IP rotation
- Dedicated IP architecture
- Specialized server pools
- Obfuscated connections
- Connection fallback strategies

## Privacy & Security

- Advanced leak protection
- Enhanced privacy controls
- Privacy-preserving telemetry
- Stronger key rotation
- Improved abuse detection
- Security event monitoring
- Optional tracker blocking
- Optional malicious-domain blocking

## Mobile/Desktop UX

- Protocol selection
- Advanced connection settings
- Custom DNS
- Multi-hop configuration
- Specialized server selection

---

# Phase 4 — Full Multi-Platform VPN Platform

## Applications

- Android
- iOS
- Windows
- macOS
- Linux
- Browser extensions
- Router configuration/support

## Account

- Multiple simultaneous devices
- Device groups
- Device naming
- Device management
- Family plans
- Household management

## Business VPN

- Organization accounts
- Team members
- Team administration
- Business plans
- Central billing
- Device policies
- Connection policies
- Organization-level access controls

## Dedicated IP

- Dedicated IP purchase
- Dedicated IP assignment
- Dedicated IP management
- Dedicated IP lifecycle

## Customer Portal

- Account dashboard
- Subscription management
- Payment history
- Invoice downloads
- Device management
- Security settings
- Support

---

# Phase 5 — Global Scale & Infrastructure Automation

## Infrastructure

- Automated server provisioning
- Infrastructure-as-code
- Global server orchestration
- Automated server deployment
- Automated WireGuard configuration
- Server replacement
- Server retirement
- Capacity planning
- Geographic expansion
- Automated scaling

## Reliability

- High availability
- Multi-region control plane
- Database replication strategy
- Redis high availability
- Disaster recovery
- Backup automation
- Failover
- Incident management
- Service-level monitoring

## Observability

- Prometheus
- Grafana
- Centralized logs
- Distributed tracing
- Advanced metrics
- Automated alerts
- Capacity dashboards
- SLO/SLI monitoring

## Security

- Security monitoring
- Automated threat detection
- Abuse detection
- Fraud detection
- Credential protection
- Key rotation automation
- Infrastructure security scanning
- Dependency security scanning

---

# Phase 6 — Commercial & Enterprise Ecosystem

## Consumer Features

- Free plan
- Premium plans
- Family plans
- Gift subscriptions
- Referral program
- Affiliate program
- Promo codes
- Coupons
- Regional pricing
- Multi-currency
- Local payment methods
- Promotional campaigns

## Enterprise

- Enterprise VPN
- Organization management
- SSO
- SAML/OIDC
- SCIM
- Enterprise RBAC
- Organization policies
- Centralized device management
- Dedicated IP pools
- Business analytics
- Enterprise billing
- Audit reports

## Partner Platform

- Public/partner APIs
- Partner authentication
- API keys
- Usage limits
- Webhooks
- Integration platform

## Customer Support

- Help center
- Knowledge base
- Support tickets
- Live chat
- Automated troubleshooting
- Customer communication
- Status page

## Localization

- Multiple languages
- Localized apps
- Localized website
- Regional pricing
- Regional payment methods
- Regional support

---

# Cross-Phase Systems

These systems should be considered from Phase 1 even when advanced functionality is implemented later.

## Authentication

Future-compatible with:

- 2FA
- Passkeys
- Google/Apple login
- SSO
- Enterprise identity providers

## Authorization

Future-compatible with:

- Customer roles
- Admin roles
- Support roles
- Operations roles
- Enterprise organization roles
- Fine-grained permissions

## Billing

Future-compatible with:

- Multiple providers
- Multiple currencies
- Multiple plans
- Trials
- Coupons
- Family plans
- Business plans
- Enterprise billing

## VPN Server Abstraction

Do not hard-code WireGuard servers into business logic.

The architecture should abstract:

- Protocol
- Server
- Location
- Region
- Provider
- IP pool
- Capacity
- Health
- Configuration
- Server lifecycle

This allows future support for additional protocols and infrastructure providers.

## Analytics

Separate operational metrics from customer/privacy-sensitive data.

Potential future analytics:

- Product analytics
- Server performance
- Connection success rate
- Crash analytics
- Subscription analytics
- Revenue analytics
- Capacity analytics

## Notifications

Foundation for:

- Email
- Push notifications
- Payment notifications
- Subscription expiry
- Security alerts
- Service incidents
- Marketing communication

---

# Recommended Technology Direction

## Mobile

Choose one:

- React Native
- Native Android + Native iOS

The VPN tunnel integration must use the native platform VPN APIs even if the UI is built with React Native.

## Backend

- Node.js
- TypeScript
- NestJS
- REST API initially
- WebSocket where real-time functionality is required

## Database

- PostgreSQL

## Cache / Queues

- Redis
- Background job system

## VPN

- WireGuard initially
- OpenVPN later

## Admin/Web

- React
- Next.js where appropriate

## Infrastructure

- Linux
- Docker
- VPS/cloud providers
- Infrastructure-as-code as the platform grows

## CI/CD

- GitHub Actions

## Monitoring

- Prometheus
- Grafana
- Centralized logging
- Error tracking

---

# Architecture Rules for Phase 1

The MVP must NOT:

1. Hard-code countries.
2. Hard-code VPN servers.
3. Hard-code subscription plans.
4. Couple payment logic directly to one payment provider.
5. Couple business logic directly to WireGuard commands.
6. Store VPN traffic through the application backend.
7. Mix admin and customer authorization.
8. Store unnecessary user connection data.
9. Make mobile apps responsible for subscription authorization.
10. Require a database redesign when additional protocols or server providers are introduced.

---

# Product Evolution

```text
Phase 1
Production MVP
    ↓
Phase 2
Core VPN Product
    ↓
Phase 3
Advanced Privacy & Networking
    ↓
Phase 4
Full Multi-Platform Platform
    ↓
Phase 5
Global Scale & Automation
    ↓
Phase 6
Commercial & Enterprise Ecosystem
