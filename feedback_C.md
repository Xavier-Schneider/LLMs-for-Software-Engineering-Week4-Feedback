> First, provide an example problem where at least one of the current guidelines does not produce an optimal answer. Secondly, document the guideline that didn't work, what prompt or context you gave to GitHub Copilot to implement the guideline and the output from Copilot. Thirdly, provide the new guideline, what you gave as input to GitHub Copilot to implement the guideline and the output from GitHub Copilot for the updated guideline.

# Guideline 4:  Provide few-shot examples 

Description: 
When attempting to describe desired behavior of a program or system, give 1-3 examples of desired output.
Reasoning:
Few-shot examples have been shown to reliably improve adherence to format and improve performance in LLMs. These examples also double as tests for your requirements, increasing verifi- ability. In addition, examples are one of the strongest methods of enforcing structure in output, making it more likely to follow that structure and read output.

# Counter example

From ProblemC1.md, I ask the same question in two different settings. 

Input:
```
Generate requirements of exact format:
[Requirement title] - [Requirement type] [Brief requirement description]

Example:
User Login - Functional The system shall allow users to log in using email and password.

Generate requirements for an online store.
```

Output of Copliot
```
User Authentication - Functional The system shall allow users to register and log in using email and password.
User Profile Management - Functional The system shall allow users to view and update their profile information.
Product Catalog - Functional The system shall display a searchable and browsable catalog of products with images, descriptions, prices, and availability.
Product Search - Functional The system shall provide keyword search with filters for category, price, brand, and rating.
Product Filtering and Sorting - Functional The system shall allow users to filter and sort product listings by price, popularity, rating, and relevance.
Product Details - Functional The system shall display detailed product pages including specifications, reviews, and related products.
Shopping Cart - Functional The system shall allow users to add, update, and remove products in a persistent shopping cart.
Guest Checkout - Functional The system shall allow users to complete purchases without creating an account.
Checkout Flow - Functional The system shall collect shipping, billing, and payment information and confirm orders before processing.
Payment Processing - Functional The system shall integrate with at least one payment gateway to securely process credit card and digital wallet payments.
Order Management - Functional The system shall create, track, and display order statuses (placed, confirmed, shipped, delivered, canceled).
Inventory Management - Functional The system shall decrement product inventory on confirmed purchases and prevent overselling.
Shipping Calculation - Functional The system shall calculate shipping costs and estimated delivery times based on destination and chosen shipping method.
Tax Calculation - Functional The system shall calculate applicable taxes based on buyer location and product tax rules.
Returns and Refunds - Functional The system shall allow users to request returns and process refunds according to store policies.
Promotions and Discounts - Functional The system shall support promotional codes, percentage/amount discounts, and time-limited offers.
Reviews and Ratings - Functional The system shall allow authenticated users to submit product reviews and ratings.
Notifications - Functional The system shall send order confirmations, shipping updates, and other transactional emails to users.
Admin Dashboard - Functional The system shall provide administrators with dashboards to manage products, orders, users, and promotions.
API Access - Functional The system shall expose a versioned RESTful API for product, cart, and order operations.
Performance - Non-functional The system shall respond to 95% of user-facing requests within 300ms under normal load.
Scalability - Non-functional The system shall scale horizontally to handle peak traffic spikes without downtime.
Availability - Non-functional The system shall maintain 99.9% uptime excluding scheduled maintenance.
Security - Non-functional The system shall store sensitive data encrypted at rest and use TLS for all data in transit.
Privacy/Compliance - Non-functional The system shall comply with applicable data protection regulations (e.g., GDPR) and provide data deletion on user request.
Accessibility - Non-functional The system shall meet WCAG 2.1 AA accessibility standards for the public storefront.
Localization - Non-functional The system shall support multiple languages and currencies selectable by the user.
Logging and Auditing - Non-functional The system shall log security-relevant events and provide audit trails for administrative actions.
Backup and Recovery - Non-functional The system shall perform daily backups and support recovery within defined RTO/RPO targets.
Monitoring and Alerts - Non-functional The system shall monitor key metrics and alert operations teams on critical failures.
Third-Party Integrations - Functional The system shall integrate with third-party services for shipping carriers, tax calculators, and analytics.
```

Then I let it used any format freely.

Input:
```
Generate a list of requirements for an online store.
Use any formatting you would like.
```


Output of Copliot
```
I'll create a short TODO plan to track producing the online-store requirements.

Created 5 todos

Progress: Plan created and step 1 is in-progress. Next: I'll produce the full requirements list.

Functional Requirements

User Accounts: Register, login (email/social), password reset, profile management.
Product Catalog: Create/read/update/delete (CRUD) products with variants, images, categories, tags.
Search & Filters: Full-text search, faceted filters (price, category, brand, rating), sort options.
Product Detail: Show descriptions, specs, reviews, related items, inventory status.
Shopping Cart: Add/remove/update quantities, persist across devices/sessions.
Checkout Flow: Multi-step checkout (billing, shipping, review), guest checkout option.
Payment Processing: Integrate with payment gateways (card, Apple/Google Pay, PayPal), support refunds.
Order Management (Customer): Order history, order detail, tracking, order cancellation where allowed.
Admin Order Management: View/update orders, manage statuses, refunds, shipping labels.
Inventory Management: Track stock levels, backorder handling, low-stock alerts.
Pricing & Promotions: Coupons, discounts, bulk/pricing rules, scheduled promotions.
Shipping & Taxes: Rate calculation, multiple shipping methods, tax calculation by region.
Catalog Management (Admin): Bulk import/export, variant management, tagging, SEO fields.
Customer Communications: Transactional emails, SMS/push notifications for order updates.
Reviews & Ratings: Submit, moderate, display product reviews.
Customer Support Tools: Support ticketing or integration with existing helpdesk.
Wishlist & Save-for-later: Save items, move to cart.
Multi-store / Multi-vendor (optional): Support multiple storefronts or sellers if required.
Localization: Multi-language content and currency selection.
Analytics & Reporting: Sales reports, conversion metrics, product performance.
Non-Functional Requirements

Performance: Page load < 2s for product pages under typical load; checkout latency targets.
Scalability: Handle X concurrent users/orders (specify target) with horizontal scaling.
Availability: 99.9% monthly uptime (or defined SLA).
Security: OWASP Top 10 mitigations, secure session management, rate-limiting, input validation.
Payment Compliance: PCI-DSS scope minimized (use tokenization/hosted checkout).
Privacy: GDPR/CCPA compliance, user data export/delete, consent for marketing.
Accessibility: WCAG 2.1 AA compliance for customer-facing pages.
Reliability & Recovery: Backups, RTO/RPO targets, graceful degradation.
Maintainability: Modular codebase, documented APIs, test coverage targets.
Monitoring & Logging: Structured logs, alerting for errors and SLA breaches.
SEO & Crawlability: Server-side rendering or pre-rendering for product pages, sitemap generation.
Mobile Responsiveness: Full functionality on mobile browsers; mobile-first layout.
Internationalization: Currency formatting, locale-aware dates/times.
Rate Limits & Throttling: Prevent abuse and protect services.
Business & Compliance Requirements

Taxes & Reporting: Accurate tax calculation per jurisdiction; exportable tax reports.
Legal & Policies: Terms of service, privacy policy, return/refund policy published and enforced.
Fraud Prevention: Anti-fraud checks, velocity rules, manual review workflows.
Pricing & Invoicing: Invoice generation, receipts, fiscal requirements per region.
Auditability: Immutable audit logs for orders, price changes, refunds.
Customer Data Portability: Allow customers to download or delete their data.
SLAs & Support: Defined response/resolution times for incidents and customer queries.
Payment Reconciliation: Reconcile gateway payouts with orders, support chargeback handling.
Regulatory Compliance: Industry-specific regulations (e.g., VAT, export controls) as applicable.
Localization of Legal Requirements: Local consumer protection rules for each market.
Operational & Integration Requirements

Third-party Integrations: ERP, CRM, shipping carriers, tax services, analytics, marketing platforms.
Environments: Separate dev/staging/production with deployment promotion process.
CI/CD: Automated tests and deployments with rollback capability.
Caching & CDN: Use CDN for assets and caching for high-read pages.
Data Migration: Tools for migrating legacy product/customer/order data.
Scaling Plan: Runbook for traffic spikes, Black Friday preparation.
Acceptance Criteria & Metrics

User journey tests: End-to-end checkout succeeds for typical purchase (unit+integration+E2E).
Performance tests: Meet page load and throughput targets under defined load tests.
Security tests: Pass periodic penetration tests and vulnerability scans.
Accessibility tests: Automated and manual checks achieving WCAG 2.1 AA.
Business KPIs: Track conversion rate, average order value, cart abandonment rate.
Would you like this exported as a checklist, a prioritized backlog, or a templated requirements document?
```

## Analysis
While few-shot examples improve adherence to a specified format, we observe that they can overly constrain the model in open-ended requirements elicitation tasks. In our experiment, providing a strict few-shot template led GPT-5-mini to generate shallow, repetitive requirements focused mainly on basic functionality. In contrast, an open-ended prompt without few-shot examples produced more diverse and thoughtful requirements, including non-functional concerns such as security and scalability. This demonstrates that few-shot prompting does not reliably improve performance, but instead trades exploratory quality for structural conformity depending on task intent.

# New Guideline

Guideline 4 (New): Prefer Open-Ended Prompting for Early-Stage Elicitation
Description:

During early-stage requirements elicitation, use open-ended prompts without few-shot examples. Introduce few-shot examples only after the problem space is well understood and a fixed output structure is required.

Reasoning:

Few-shot examples enforce structure but can overly constrain the model, leading to shallow and repetitive requirements in exploratory tasks. Open-ended prompting allows broader reasoning and more thoughtful requirement discovery before formalization.