# B1CONNECT GLOBAL SAAS TRANSFORMATION PLAYBOOK
> **Target Audience:** Cheaper AI Models (GPT-4o-mini, GPT-3.5, Claude Haiku, Gemini Flash, etc.)
> **Objective:** Transform the B1connect website from Indonesian to an elite, Silicon Valley-grade global SaaS standard (similar to Stripe, Linear, Vercel, Supabase).
> **Rule for the AI Agent:** Follow the instructions step-by-step. DO NOT break Astro syntax, imports, component props, Lucide icons, or styling classes. Only replace text strings, metadata, and copy as instructed.

---

## 📌 GENERAL RULES FOR THE CHEAP AI AGENT

When you are assigned any task from this playbook:
1. **Never delete imports or change component names:** Keep all imports (`import Layout from ...`, `import Button from ...`, etc.) exactly as they are.
2. **Never change Lucide icon imports:** Only change user-visible text, labels, and metadata.
3. **Never alter CSS classes or animations:** Preserve classes like `site-container`, `app-stat-card`, `dark:...`, etc.
4. **Preserve Astro props & syntax:** Keep `{...props}`, `client:load`, frontmatter delimiters (`---`), etc.
5. **Tone of Voice:** Crisp, authoritative, enterprise-grade, high-converting tech startup copy (Stripe/Linear style). Avoid robotic translations; use idiomatic enterprise software terminology (e.g., *Bi-directional sync*, *Zero latency*, *Sub-second throughput*, *At-rest encryption*, *Multi-tenant isolation*).

---

# 📦 BATCH 1: GLOBAL CONFIG & SYSTEM LAYOUT

### Task 1.1: `src/layouts/Layout.astro`
* **Goal:** Set HTML document language to English.
* **Line 27:**
  - **FIND:**
    ```astro
    <html lang="id">
    ```
  - **REPLACE WITH:**
    ```astro
    <html lang="en">
    ```

---

### Task 1.2: `src/config/site.js`
* **Goal:** Update global metadata, OpenGraph descriptions, and SEO tags to global English.
* **Replace `meta` object with:**
  ```javascript
  meta: {
    title: "B1connect — Enterprise Shopify × SAP Business One Integration",
    description: "Enterprise-grade multi-tenant middleware delivering real-time, automated bidirectional synchronization for products, multi-warehouse inventory, pricing, and sales orders.",
    keywords: "shopify sap integration, sap business one, shopify middleware, erp integration, b1connect, ecommerce erp sync, sap hana shopify, b2b sap integration",
    image: `${SITE_URL}/og.jpg`,
    twitterHandle: "@b1connect",
  },
  ```

---

### Task 1.3: `src/components/sections/Header.astro`
* **Goal:** Translate mobile and desktop CTA buttons.
* **Lines 139 & 148:**
  - **FIND:**
    ```astro
    Hubungi Kami
    ```
  - **REPLACE WITH:**
    ```astro
    Book a Demo
    ```

---

### Task 1.4: `src/components/sections/Footer.astro`
* **Goal:** Translate footer tagline and copyright note.
* **Line 38 (Tagline):**
  - **FIND:**
    ```astro
    Middleware integrasi Shopify × SAP Business One otomatis, aman, dan siap pakai untuk bisnis Anda.
    ```
  - **REPLACE WITH:**
    ```astro
    Enterprise-grade middleware delivering zero-latency bidirectional synchronization between Shopify and SAP Business One.
    ```
* **Line 107 (Copyright):**
  - **FIND:**
    ```astro
    Hak Cipta Dilindungi.
    ```
  - **REPLACE WITH:**
    ```astro
    All rights reserved.
    ```

---

# 📦 BATCH 2: HOMEPAGE & HERO SECTION

### Task 2.1: `src/components/home/HeroSection.astro`
* **Goal:** Elevate hero headline, value proposition, and CTA buttons.
* **Update the following strings:**
  1. **Hero Title (around line 43):**
     - **OLD:** `"Hubungkan Shopify dengan SAP Business One. Tanpa Rumit."`
     - **NEW:** `"Seamless Shopify & SAP Business One Integration. Automated at Scale."`
  2. **Hero Subtitle (around line 54):**
     - **OLD:** `"Middleware multi-tenant untuk sinkronisasi otomatis master produk, inventory stok, harga, dan order secara real-time. Aman, scalable, dan siap deploy dalam hitungan jam."`
     - **NEW:** `"Enterprise multi-tenant middleware delivering zero-latency bidirectional synchronization for products, multi-warehouse inventory, pricing, and sales orders. Secure, highly resilient, and deployed in hours."`
  3. **Buttons (around line 70-75):**
     - **OLD:**
       ```astro
       <Button url="/contact" type="fill">
         Mulai Integrasi <ArrowRight size={16} class="ml-1" />
       </Button>
       <Button url="/features">
         Lihat Fitur Lengkap
       </Button>
       ```
     - **NEW:**
       ```astro
       <Button url="/contact" type="fill">
         Start Free Trial <ArrowRight size={16} class="ml-1" />
       </Button>
       <Button url="/features">
         Explore Features
       </Button>
       ```

---

### Task 2.2: `src/pages/index.astro`
* **Goal:** Replace all Indonesian homepage data arrays, section headers, mock tables, and final CTA.

#### 1. Replace `faqItems` array:
```javascript
const faqItems = [
  {
    question: "Does B1connect support multi-tenant architecture for multiple Shopify stores?",
    answer: "Yes. B1connect is architected with native multi-tenancy. You can connect and manage multiple Shopify storefronts—such as regional branches, sub-brands, or subsidiary brands—orchestrated into a single SAP Business One instance."
  },
  {
    question: "What core data points are synchronized between Shopify and SAP B1?",
    answer: "B1connect synchronizes 5 mission-critical data pipelines: Item Master catalog, Multi-Warehouse Inventory Stock, Price Lists & Currencies, Sales Orders (ORDR documents), and Business Partner (Customer) accounts via instant webhooks and intelligent polling."
  },
  {
    question: "How are our SAP database credentials and tokens secured?",
    answer: "Security is non-negotiable. All SAP Service Layer credentials and Shopify access tokens are encrypted at-rest using AES-256-GCM. Webhooks are cryptographically authenticated via constant-time HMAC-SHA256 signatures, and sessions use JWT."
  },
  {
    question: "Does it support both On-Premise and Cloud SAP B1 (SQL Server & HANA)?",
    answer: "Yes. B1connect interfaces strictly through the official SAP Business One Service Layer REST API, providing native support for on-premise servers, cloud instances, Microsoft SQL Server, and SAP HANA databases."
  },
  {
    question: "How long does deployment and onboarding take?",
    answer: "For merchants with active SAP B1 Service Layer access, typical onboarding takes less than 24-48 hours: install the app, map field attributes via the guided wizard, and execute end-to-end sandbox test transactions."
  },
  {
    question: "Does B1connect require custom add-ons or modifications inside core SAP?",
    answer: "No. B1connect does not require invasive core add-ons or stored-procedure overrides. By leveraging the standard official Service Layer, your ERP remains 100% compliant and fully upgrade-safe for future SAP patches."
  },
];
```

#### 2. Replace `features` array:
```javascript
const features = [
  {
    icon: "/assets/icon/structure.png",
    title: "Bidirectional Synchronization",
    desc: "Products, stock levels, and price lists flow seamlessly from SAP B1 to Shopify. Customer checkouts and sales orders flow back into SAP B1 instantly with zero manual entry."
  },
  {
    icon: "/assets/icon/motion.png",
    title: "Enterprise-Grade Security",
    desc: "AES-256-GCM encryption for all secrets at rest. Constant-time HMAC-SHA256 signature verification for Shopify webhooks and JWT-authenticated session tokens."
  },
  {
    icon: "/assets/icon/components.png",
    title: "True Multi-Tenant Engine",
    desc: "A single middleware cluster powers multiple Shopify storefronts and warehouse centers. Complete tenant isolation guarantees zero data leakage."
  },
  {
    icon: "/assets/icon/customize.png",
    title: "Flexible Field Mapping",
    desc: "Configurable mapping for ItemCode to SKU, product attributes, Units of Measure (UoM), and warehouse routing rules without altering backend source code."
  },
  {
    icon: "/assets/icon/document.png",
    title: "Audit Trail & Live Monitoring",
    desc: "Granular telemetry logs for every sync event. Inspect transaction payloads, detect discrepancies with proactive alerts, and trigger instant re-syncs."
  },
  {
    icon: "/assets/icon/fast.png",
    title: "High-Performance Engine",
    desc: "Built on .NET 10, Redis caching, and Hangfire background queues to orchestrate tens of thousands of SKUs and orders with sub-second latency."
  },
];
```

#### 3. Replace `problems` array:
```javascript
const problems = [
  {
    icon: "/assets/icon/clock.png",
    title: "Manual data entry wastes hours and causes errors",
    desc: "Re-keying customer orders from Shopify into SAP B1 by hand drains hundreds of team hours and inevitably leads to costly typos and misplaced shipments."
  },
  {
    icon: "/assets/icon/battery.png",
    title: "Desynchronized inventory leads to painful overselling",
    desc: "When warehouse stock sells out physically but still displays as available on Shopify, angry customer cancellations and negative store reviews follow."
  },
  {
    icon: "/assets/icon/bell.png",
    title: "Pricing updates in SAP lag behind storefronts",
    desc: "Manual updates across multiple storefronts cause delays when ERP price matrices change, quietly eroding business profit margins on every order."
  },
];
```

#### 4. Replace `useCases` array:
```javascript
const useCases = [
  { icon: ShoppingBag, label: "Retail & DTC", desc: "Omnichannel Shopify stores connected to SAP B1 fulfillment" },
  { icon: Factory, label: "Manufacturing", desc: "Direct sales fulfilled straight from factory warehouse floors" },
  { icon: Package, label: "B2B Wholesale & Distributors", desc: "High-volume order streams pushed directly into ERP ledgers" },
  { icon: Globe, label: "Multi-Brand Portfolios", desc: "Manage multiple regional Shopify storefronts in one hub" },
  { icon: Boxes, label: "High-SKU Catalogs", desc: "Tens of thousands of SKUs requiring strict stock accuracy" },
  { icon: ShieldCheck, label: "SAP & ERP Consultancies", desc: "Turnkey, dependable integration accelerator for SAP clients" },
];
```

#### 5. Replace `pipelines` array:
```javascript
const pipelines = [
  { title: "Product Master", direction: "SAP → Shopify", icon: Package, desc: "ItemCode, title, categories, barcodes, and rich descriptions." },
  { title: "Inventory Stock", direction: "SAP → Shopify", icon: Boxes, desc: "Real-time stock level synchronization across multi-warehouse locations." },
  { title: "Price Lists", direction: "SAP → Shopify", icon: Tag, desc: "Multi-currency price lists, tier pricing, and promotional catalogs." },
  { title: "Sales Orders", direction: "Shopify → SAP", icon: ShoppingBag, desc: "Instantly creates compliant ORDR / ODLN documents with line items." },
  { title: "Customer Records", direction: "Shopify ↔ SAP", icon: Users, desc: "Automatic Business Partner (BP) matching and record generation." },
];
```

#### 6. Replace In-Page Section Titles & Table Mockup:
* **Ecosystem Strip Header (line 142):**
  - `"Trusted by Modern ERP & E-Commerce Ecosystems"`
* **Problem Section Header (line 157):**
  - `title="Operational Bottlenecks Without Automated Integration"`
  - `description="Managing Shopify storefronts and SAP B1 ERP in silos cripples your team's operational throughput."`
* **Solution Section Header (lines 186-189):**
  - `<h2>Bidirectional Synchronization Architecture</h2>`
  - `<p>B1connect bridges Shopify with SAP Business One via official Service Layer APIs. All critical commerce data flows automatically without altering core SAP logic.</p>`
* **Features Grid Header (line 225):**
  - `title="Engineered for Scalability and High Throughput"`
  - `description="A modern middleware foundation delivering enterprise stability, cryptographic security, and intuitive configuration."`
* **Dashboard Preview Header (lines 258-260):**
  - `title="Real-Time Sync Observability & Event Stream"`
  - `description="Monitor order cycles, inventory mutations, and SAP B1 Service Layer health metrics transparently from a unified control plane."`
* **Dashboard Mockup UI strings (lines 325-360):**
  - `Arah Aliran` ➔ `Direction`
  - `Latensi` ➔ `Latency`
  - Mock Table items:
    - `"Order #SH-10492 — Sales Order" | "Shopify → SAP B1" | "Success" | "0.4s"`
    - `"SKU-98402 — Stock Adjustment (WH-01)" | "SAP B1 → Shopify" | "Updated" | "0.6s"`
    - `"Order #SH-10491 — Sales Order" | "Shopify → SAP B1" | "Success" | "0.5s"`
    - `"PRC-MATRIX — Price Tier Matrix" | "SAP B1 → Shopify" | "Synced" | "0.8s"`
  - Note beneath mockup: `"Real-time telemetry with comprehensive audit logging and automated exponential-backoff retry policies."`
* **Use Cases Header (line 367):**
  - `title="Purpose-Built for Modern Commerce Models"`
  - `description="Whether you run high-growth DTC brands, multi-warehouse B2B distribution networks, or SAP consulting practices."`
* **Tech Stack Architecture Header (line 393):**
  - `title="Cloud-Native, Resilient Technology Foundation"`
  - `description="A proven tech stack guaranteeing data consistency, fault tolerance, and uninterrupted transaction throughput."`
* **Pricing & FAQ Headers (lines 403, 411, 417):**
  - Pricing: `title="Flexible Integration Plans"` | `description="Transparent pricing designed to scale effortlessly with your transaction volume."`
  - FAQ: `title="Frequently Asked Questions"`
  - Blog: `title="Integration Insights & Technical Articles"`
* **Final CTA Section (lines 424-435):**
  - Heading: `"Ready to Automate Your Shopify × SAP B1 Operations?"`
  - Subtitle: `"Contact our engineering team today for a live demo, architecture mapping, and seamless technical onboarding."`
  - Buttons:
    - `"Book a Technical Demo"` (url `/contact`)
    - `"Explore All Features"` (url `/features`)

---

# 📦 BATCH 3: FEATURES & HOW IT WORKS PAGES

### Task 3.1: `src/pages/features.astro`
* **Goal:** Full translation of feature modules, technical bullet points, and code/mockup snippets.
* **Layout Meta:**
  - `title={`Complete Features — ${siteConfig.title}`}`
  - `description="Explore the 6 core modules of B1connect powering real-time, secure, and bidirectional Shopify and SAP Business One integration."`
* **Page Header:**
  - `title="Everything You Need for Enterprise Shopify × SAP Integration"`
  - `description="Engineered specifically to eliminate manual entry, prevent inventory overselling, and preserve transactional integrity in real time."`
* **Feature Modules Array (`featureModules`):**
  ```javascript
  const featureModules = [
    {
      icon: RefreshCw,
      title: "Product Master & Inventory Stock Synchronization",
      desc: "Item Masters in SAP Business One automatically publish as live products on Shopify. Multi-warehouse inventory adjustments and price list changes poll automatically every 30 seconds with zero manual CSV exports.",
      points: [
        "Automated background polling every 30 seconds",
        "Flexible attribute mapping: ItemCode → SKU, ItemName → Title, UoM conversions",
        "Multi-warehouse routing and inventory location allocation",
        "Automated Price List and currency synchronization"
      ],
      direction: "left",
      visual: "product-sync",
    },
    {
      icon: ShoppingBag,
      title: "Automated Sales Order Ingestion into SAP B1",
      desc: "Every paid checkout on Shopify is converted into a native SAP B1 Sales Order (ORDR/ODLN document) instantly via real-time webhooks without latency.",
      points: [
        "Sub-second webhooks for orders/paid and orders/create events",
        "Automatic line items, tax brackets, discounts, and shipping cost mapping",
        "Intelligent Business Partner (BP) reconciliation and customer creation",
        "Dead-letter queues and automated retries when SAP experiences peak load"
      ],
      direction: "right",
      visual: "order-sync",
    },
    {
      icon: Layers,
      title: "Native Multi-Tenancy: One Cluster for Multiple Stores",
      desc: "A true multi-tenant architecture empowers a single integration cluster to orchestrate multiple Shopify storefronts. Each merchant brand or regional branch maintains isolated configurations with 100% data privacy.",
      points: [
        "Strict database and in-memory tenant isolation",
        "Independent connections to separate SAP B1 company databases",
        "Scales effortlessly to dozens of concurrent storefronts",
        "Seamless onboarding via standard Shopify App Store OAuth"
      ],
      direction: "left",
      visual: "multi-tenant",
    },
    {
      icon: ShieldCheck,
      title: "Enterprise-Grade Cryptographic Security",
      desc: "All sensitive credentials, including Shopify private access tokens and SAP B1 Service Layer passwords, are encrypted using AES-256-GCM. Webhooks are verified using constant-time HMAC-SHA256 comparison.",
      points: [
        "AES-256-GCM encryption for all credentials stored at rest",
        "Constant-time HMAC-SHA256 signature verification for Shopify webhooks",
        "Shopify App Bridge JWT session token authentication",
        "Support for internal and self-signed SSL certificates for on-premise SAP servers"
      ],
      direction: "right",
      visual: "security",
    },
    {
      icon: SlidersHorizontal,
      title: "Guided 3-Step Setup Wizard Without Code",
      desc: "Configure the entire integration through an intuitive wizard embedded directly inside Shopify Admin. Authenticate your ERP connection, map fields, and launch auto-sync.",
      points: [
        "Step 1: Input Service Layer URL, CompanyDB, and authentication credentials",
        "Step 2: Map SKU fields, barcodes, and master price list catalogs",
        "Step 3: Map order financial accounts and default shipping warehouses",
        "Built-in Test Connection tool for immediate connectivity validation"
      ],
      direction: "left",
      visual: "wizard",
    },
    {
      icon: Activity,
      title: "Observability Dashboard & Hangfire Queue Telemetry",
      desc: "Gain complete transparency over every background job. Monitor queue throughput, inspect SAP HTTP response payloads, and track service health in real time.",
      points: [
        "Real-time sync status telemetry per connected storefront",
        "Granular transaction audit logs with full request & response payloads",
        "Integrated Hangfire dashboard for queue lifecycle management",
        "Automated health-check endpoint (/health) for uptime observability"
      ],
      direction: "right",
      visual: "dashboard",
    },
  ];
  ```
* **Interactive Visual Mockup Labels:**
  - Product Sync Mock: `"PriceList #01: $249.00"` | `"Multi-Warehouse (WH-01, WH-02)"` | `"Shopify Variant Price: $249.00 (Updated)"`
  - Setup Wizard Mock:
    - `"SAP Service Layer Connection (200 OK)"`
    - `"SKU & Master Price Field Mapping Completed"`
    - `"Configure Default Warehouse & Sales Order Ledger"`
* **Bottom CTA:**
  - Heading: `"Ready to Connect Your Shopify Storefront?"`
  - Subtitle: `"Schedule a live demonstration and discover how B1connect saves your team hundreds of manual operational hours every month."`
  - Buttons: `"Book a Live Demo"` | `"View Pricing Plans"`

---

### Task 3.2: `src/pages/how-it-works.astro`
* **Goal:** Translate the 3-step timeline, architecture diagram nodes, 2-way data flow tables, and technology highlights.
* **Layout Meta:**
  - `title={`How B1connect Works — ${siteConfig.title}`}`
  - `description="Learn how B1connect connects Shopify with SAP Business One through automated, secure middleware without modifying core SAP systems."`
* **Page Header:**
  - `title="How B1connect Works"`
  - `description="From initial setup to continuous automated bidirectional synchronization—configured in 3 simple steps without complex code."`
* **Section 1: Architecture Diagram Nodes:**
  - Badge: `"System Architecture"`
  - Title: `"The Intelligent Bridge Between Modern E-Commerce & Enterprise ERP"`
  - Node 1: `Shopify Store` ➔ Subtitle: `Front-End Storefront & Checkout`
    - `Product Catalog & Variants`
    - `Customer Checkout Orders`
    - `Webhooks: orders/paid`
  - Node 2: `B1connect Middleware` ➔ Subtitle: `Multi-Tenant Sync Engine`
    - `AES-256-GCM Secret Store`
    - `Data Normalizer & Field Mapper`
    - `Hangfire Queue & Auto-Retry`
  - Node 3: `SAP Business One` ➔ Subtitle: `Enterprise ERP & Warehousing`
    - `Service Layer REST API`
    - `Item Master & Multi-Warehouse`
    - `Sales Orders (ORDR / ODLN)`
* **Section 2: 3 Simple Steps (`steps`):**
  ```javascript
  const steps = [
    {
      number: "01",
      title: "Install & Authorize Shopify Storefront",
      desc: "Open the B1connect installation link. Through Shopify's official OAuth flow, the embedded app installs in seconds. All access tokens are securely encrypted.",
      points: [
        "Installed via official Shopify App Bridge OAuth",
        "Credentials secured with AES-256-GCM encryption",
        "Zero theme code (Liquid/JSON) modifications required"
      ]
    },
    {
      number: "02",
      title: "Configure SAP Service Layer & Field Mappings",
      desc: "Launch the guided Setup Wizard within your Shopify admin. Enter your SAP B1 Service Layer URL, CompanyDB, and service credentials. Then map your SKUs, price lists, and fulfillment centers.",
      points: [
        "Native connection via official SAP Service Layer REST API (HANA / SQL Server)",
        "Instant Test Connection feature for real-time network validation",
        "Granular mapping for items, Units of Measure (UoM), and Price Lists",
        "Support for self-signed SSL on on-premise SAP deployments"
      ]
    },
    {
      number: "03",
      title: "Activate Automated Sync & Live Monitoring",
      desc: "Enable the synchronization engine. Inventory and catalog items from your SAP warehouses appear on Shopify, while store orders automatically generate official Sales Orders in SAP.",
      points: [
        "Automated inventory polling every 30 seconds",
        "Sub-second orders/paid webhooks generating ORDR/ODLN records",
        "Real-time monitoring dashboard and telemetry audit stream"
      ]
    }
  ];
  ```
* **Section 3: Detailed Data Flow (`dataFlows`):**
  ```javascript
  const dataFlows = [
    {
      direction: "SAP Business One ➔ Shopify",
      tag: "Catalog & Inventory",
      frequency: "Automated polling every 30 seconds",
      items: [
        { name: "Item Master (OITM)", desc: "ItemCode, ItemName, descriptions, barcodes, and product media" },
        { name: "Inventory Stock (OITW)", desc: "On-hand stock levels across multiple physical warehouse facilities" },
        { name: "Price Lists (ITM1)", desc: "Tiered price matrices, multi-currency values, and promotional rates" }
      ]
    },
    {
      direction: "Shopify ➔ SAP Business One",
      tag: "Transactions & Customers",
      frequency: "Real-time webhooks (Latency < 0.5s)",
      items: [
        { name: "Sales Orders (ORDR)", desc: "Customer checkout items, quantities, taxes, discounts, and shipping" },
        { name: "Customer Master (OCRD)", desc: "Intelligent matching or automated registration of new Business Partners" },
        { name: "Delivery / Fulfillment", desc: "Fulfillment status and tracking numbers synced bi-directionally" }
      ]
    }
  ];
  ```
* **Section 4: Enterprise Tech Highlights (`techHighlights`):**
  - `.NET 10 Core` ➔ `"High-throughput compiled backend built for massive transactional loads."`
  - `PostgreSQL` ➔ `"Robust relational database featuring complete multi-tenant schema isolation."`
  - `Redis Cache` ➔ `"High-speed in-memory datastore for token idempotency and fast delta diffing."`
  - `Hangfire Worker` ➔ `"Background job orchestration with built-in dead-letter queues & auto-retries."`
  - `Docker Ready` ➔ `"Containerized architecture for rapid deployment on private VPS or public cloud."`
  - `AES-256-GCM & HMAC` ➔ `"Military-grade at-rest encryption and cryptographic webhook validation."`
* **Section 5: Bottom CTA:**
  - Heading: `"Ready to Connect Your Systems?"`
  - Subtitle: `"Book a live demonstration and implementation consultation with our senior integration engineers."`
  - Buttons: `"Schedule a Free Demo"` | `"View Pricing Plans"`

---

# 📦 BATCH 4: COMMERCIAL & CONVERSION PAGES

### Task 4.1: `src/components/sections/Pricing.astro`
* **Goal:** Globalize plan names, pricing tiers (convert from IDR to USD standard SaaS tiers), descriptions, and CTA labels.
* **Component Props default:**
  - `title = "Simple, Predictable Integration Pricing"`
  - `description = "Transparent investment plans designed to scale with your transaction volume. Upgrade or downgrade anytime."`
* **Replace `plans` array with:**
  ```javascript
  const plans = [
    {
      name: "Starter",
      monthlyPrice: "$99",
      yearlyPrice: "$79",
      monthlyDescription: "Ideal for single Shopify stores establishing automated SAP B1 connectivity.",
      yearlyDescription: "Save 20% with annual billing for predictable operational cost.",
      monthlySuffix: "/ mo",
      yearlySuffix: "/ mo (billed annually)",
      features: [
        { text: "1 Connected Shopify Storefront", included: true },
        { text: "1 SAP B1 Instance (Service Layer)", included: true },
        { text: "Item Master & Price List Sync", included: true },
        { text: "Inventory Sync (5-min interval)", included: true },
        { text: "Automated Sales Order Ingestion", included: true },
        { text: "Monitoring Dashboard & Audit Logs", included: true },
        { text: "Standard Email Support (48h)", included: true },
        { text: "Multi-warehouse inventory routing", included: false },
      ],
      cta: "Start 14-Day Free Trial",
      popular: false,
      url: "/contact",
    },
    {
      name: "Business",
      monthlyPrice: "$249",
      yearlyPrice: "$199",
      monthlyDescription: "For scaling brands with high order volume or multi-warehouse fulfillment.",
      yearlyDescription: "Save 20% — sub-second webhooks, 30s polling, and multi-warehouse routing.",
      monthlySuffix: "/ mo",
      yearlySuffix: "/ mo (billed annually)",
      features: [
        { text: "Up to 5 Shopify Storefronts", included: true },
        { text: "Ultra-fast 30-second polling", included: true },
        { text: "Real-time orders/paid webhooks", included: true },
        { text: "Custom Field Mapping (UoM & Status)", included: true },
        { text: "Multi-warehouse inventory routing", included: true },
        { text: "Dead-letter queues & auto-retries", included: true },
        { text: "Priority Support (1 business day)", included: true },
        { text: "1 Technical Onboarding Session", included: true },
      ],
      cta: "Start 14-Day Free Trial",
      popular: true,
      url: "/contact",
    },
    {
      name: "Enterprise",
      monthlyPrice: "Custom",
      yearlyPrice: "Custom",
      monthlyDescription: "For enterprise organizations requiring bespoke SAP logic, on-premise hosting, and SLAs.",
      yearlyDescription: "Dedicated engine instance, 99.9% uptime SLA, and dedicated integration engineers.",
      monthlySuffix: "",
      yearlySuffix: "(annual contract)",
      features: [
        { text: "Unlimited Storefronts & Warehouses", included: true },
        { text: "Dedicated Engine & On-Premise Hosting", included: true },
        { text: "Custom SAP B1 UDFs & Custom Business Logic", included: true },
        { text: "Guaranteed 99.9% Uptime SLA", included: true },
        { text: "Unlimited Historical Audit Logs", included: true },
        { text: "Full White-Glove Implementation", included: true },
        { text: "Dedicated Engineer & 24/7 Hotline", included: true },
        { text: "Custom Enterprise NDA & Security Review", included: true },
      ],
      cta: "Contact Enterprise Sales",
      popular: false,
      url: "/contact",
    },
  ];
  ```

---

### Task 4.2: `src/pages/pricing.astro`
* **Goal:** Translate comparison table and pricing FAQ.
* **Layout Meta:**
  - `title={`Pricing & Plans — ${siteConfig.title}`}`
  - `description="Transparent, scalable pricing tiers for enterprise Shopify and SAP Business One integration."`
* **Page Header:**
  - `title="Flexible Plans Built for Every Stage of Growth"`
  - `description="Choose the right plan based on your order throughput, inventory locations, and multi-store requirements."`
* **Comparison Features Array (`comparisonFeatures`):**
  ```javascript
  const comparisonFeatures = [
    { name: "Connected Shopify Stores", starter: "1 Store", business: "Up to 5", enterprise: "Unlimited" },
    { name: "SAP B1 Service Layer Instances", starter: "1 Instance", business: "1 Instance", enterprise: "Multi-Instance" },
    { name: "Product Master & Price Sync", starter: true, business: true, enterprise: true },
    { name: "Inventory Stock Sync", starter: true, business: true, enterprise: true },
    { name: "Automated Sales Order Ingestion", starter: true, business: true, enterprise: true },
    { name: "Background Polling Interval", starter: "5 Minutes", business: "30 Seconds", enterprise: "Custom (<10s)" },
    { name: "Real-Time Order Webhooks", starter: false, business: true, enterprise: true },
    { name: "Custom Field & UoM Mapping", starter: "Basic (5 fields)", business: "Full Mapping", enterprise: "Full + Custom Logic" },
    { name: "Multi-Warehouse Inventory Routing", starter: false, business: true, enterprise: true },
    { name: "Observability & Audit Logs", starter: true, business: true, enterprise: true },
    { name: "On-Premise / Self-Hosted Option", starter: false, business: false, enterprise: true },
    { name: "Guaranteed Uptime SLA", starter: false, business: false, enterprise: "99.9%" },
    { name: "Support Level", starter: "Email (48h)", business: "Priority (1 business day)", enterprise: "Dedicated 24/7" },
    { name: "Technical Onboarding Assistance", starter: false, business: "1 Session", enterprise: "Dedicated Engineer" },
  ];
  ```
* **Comparison Table Title:** `"Full Feature Comparison"`
* **Table Headers:** `Features & Capabilities` | `Starter` | `Business` | `Enterprise`
* **Pricing FAQ Array (`faqItems`):**
  ```javascript
  const faqItems = [
    {
      question: "Is there a free trial available?",
      answer: "Yes, we offer a 14-day fully featured free trial for Starter and Business tiers. You can connect development stores and validate end-to-end sync without requiring a credit card."
    },
    {
      question: "What payment methods are supported?",
      answer: "We support major corporate credit cards, automated wire transfers, and corporate invoicing with tax invoices. Annual billing plans automatically receive a 20% discount."
    },
    {
      question: "Can we upgrade or downgrade our tier as our business scales?",
      answer: "Absolutely. You can change your plan at any time through your dashboard as your order volume surges. Upgrades take effect immediately with prorated billing adjustments."
    },
    {
      question: "What if our SAP B1 setup utilizes custom UDFs or bespoke business logic?",
      answer: "Our senior solutions engineers specialize in custom User-Defined Fields (UDF), UDTs, and complex SAP transaction workflows through our Enterprise plan. Contact sales for an architectural assessment."
    },
  ];
  ```
* **Pricing FAQ Section Title:** `"Frequently Asked Questions About Pricing"`
* **Bottom CTA:**
  - Heading: `"Need Guidance Choosing the Right Plan?"`
  - Subtitle: `"Discuss your SAP Business One deployment and storefront architecture with our technical solutions team."`
  - Buttons: `"Talk to Sales"` | `"Explore All Features"`

---

### Task 4.3: `src/pages/contact.astro`
* **Goal:** Translate contact topics, channels, form inputs, placeholders, and feedback alerts.
* **Layout Meta:**
  - `title={`Contact & Sales — ${siteConfig.title}`}`
  - `description="Discuss your Shopify and SAP Business One integration needs with our technical team."`
* **Contact Topics (`contactTopics`):**
  ```javascript
  const contactTopics = [
    { value: "demo", label: "Request a Live Demo & 14-Day Trial" },
    { value: "sales", label: "Pricing & Enterprise Licensing Inquiry" },
    { value: "technical", label: "Technical Architecture / SAP Service Layer Query" },
    { value: "partnership", label: "ERP Consultancy or Reseller Partnership" },
    { value: "general", label: "General Inquiries" },
  ];
  ```
* **Expectations Array (`expectations`):**
  ```javascript
  const expectations = [
    { icon: Clock3, title: "Rapid Response", desc: "All inquiries and demo requests receive a response within 1 business day." },
    { icon: LifeBuoy, title: "Live Architecture Demo", desc: "Book an interactive session via Google Meet to walk through live product and order flows." },
    { icon: ShieldCheck, title: "Strict Confidentiality", desc: "We are glad to execute mutual NDAs prior to reviewing your internal ERP architecture." },
  ];
  ```
* **Left Column Copy (lines 50-80):**
  - Badge: `"Consulting & Sales"`
  - Heading: `"Let's Architect Your Integration."`
  - Subtitle: `"Have questions about SAP Service Layer compatibility, want to see a live demo, or need a bespoke workflow for your storefront? Our engineering team is ready to assist."`
  - Channel labels:
    - `Official Email`
    - `Direct Consultation / WhatsApp`
    - `Headquarters`
* **Form UI Strings (lines 104-203):**
  - Form Badge / Header: `"Inquiry Form"` | `"Send a Message & Request a Demo"`
  - Form Subtitle: `"Fill out the form below and our integration engineers will reach out promptly."`
  - Top Badge: `"24h Response SLA"`
  - Field 1 Label: `"Full Name"` | Placeholder: `"Jane Doe"`
  - Field 2 Label: `"Work Email"` | Placeholder: `"jane@company.com"`
  - Field 3 Label: `"Company / Brand Name"` | Placeholder: `"Acme Retail Corp"`
  - Field 4 Label: `"Phone / WhatsApp"` | Placeholder: `"+1 (555) 000-0000"`
  - Field 5 Label: `"Inquiry Topic"` | Default option: `"Select your inquiry topic"`
  - Field 6 Label: `"Project Details & Requirements"` | Placeholder: `"Tell us about your SAP B1 version (SQL/HANA), number of Shopify stores, or any specific workflow requirements..."`
  - Notice text: `"<strong class='font-semibold text-primary dark:text-primary-light'>Privacy Guaranteed:</strong> Your contact information is solely used to facilitate B1connect technical consultations."`
  - Submit Button: `"Submit Inquiry"`
  - Success Alert (line 201):
    ```html
    Thank you! Your message has been received. A B1connect integration specialist will contact you within 1 business day.
    ```

---

# 📦 BATCH 5: ABOUT, 404 & SYSTEM PAGES

### Task 5.1: `src/pages/about.astro`
* **Goal:** Modernize company vision, problem statement, values, and milestone timeline into global startup terminology.
* **Layout Meta:**
  - `title={`About Us — ${siteConfig.title}`}`
  - `description="About B1connect: Our mission is to automate the bridge between Shopify e-commerce and SAP Business One enterprise ERP."`
* **Page Header:**
  - `title="Bridging Modern Commerce with Enterprise ERP"`
  - `description="B1connect exists to eliminate manual operational friction, eliminate inventory overselling, and accelerate global business automation."`
* **Story Section (lines 53-64):**
  - Subtitle: `"Why We Built B1connect"`
  - Paragraph 1: `"Modern retail enterprises, international distributors, and high-growth brands rely on SAP Business One as their operational backbone for accounting and warehouse management, while turning to Shopify for world-class storefronts."`
  - Paragraph 2: `"Yet all too often, the gulf between these two powerful systems is still bridged by fragile manual workflows: operations staff spending hours copying order lines, exporting CSV spreadsheets, and handling customer cancellations caused by out-of-sync inventory levels."`
  - Paragraph 3: `"Building custom integrations from scratch costs tens of thousands of dollars, takes months of development, and introduces ongoing maintenance liabilities. B1connect was engineered as the solution: a turnkey, resilient, multi-tenant middleware built on official SAP Service Layer APIs that deploys in hours."`
* **Values Section (lines 70-94):**
  - Subtitle: `"Our Core Principles"`
  - Value 1: `Uncompromising Security` ➔ `"All SAP credentials and Shopify tokens are encrypted using AES-256-GCM. Strict tenant isolation ensures zero cross-merchant data leakage."`
  - Value 2: `High Availability & Resilience` ➔ `"Hangfire-backed worker queues with automated exponential backoff retries guarantee that not a single order is dropped during network surges."`
  - Value 3: `Intuitive Configuration` ➔ `"A 3-step setup wizard embedded directly into Shopify Admin connects your ERP without requiring custom scripts or invasive SAP modifications."`
  - Value 4: `Deep ERP Expertise` ➔ `"Supported by engineering teams with deep expertise in SAP Business One architecture and high-volume e-commerce scaling."`
* **Milestone Timeline (`timeline` array):**
  ```javascript
  const timeline = [
    {
      version: "v0.1",
      date: "June 2026",
      title: "Proof of Concept (PoC)",
      desc: "First working prototype: automated Item Master synchronization from SAP B1 to Shopify, eliminating 4 hours of daily manual catalog updates."
    },
    {
      version: "v0.5",
      date: "July 2026",
      title: "Multi-Tenant & Bi-Directional Engine",
      desc: "Engineered true multi-tenant architecture, sub-second webhooks for sales orders, AES-256-GCM credential encryption, and Shopify OAuth flows."
    },
    {
      version: "v1.0",
      date: "August 2026",
      title: "Production-Ready Release",
      desc: "Official enterprise release: real-time observability dashboard, Hangfire queue workers, multi-warehouse routing, and audit logs."
    },
    {
      version: "Roadmap",
      date: "Q4 2026",
      title: "Ecosystem Expansion",
      desc: "Public Shopify App Store listing, advanced Business Partner Customer Portal modules, and native Shopify Billing API integration."
    },
  ];
  ```
* **Bottom CTA:**
  - Heading: `"Ready to Modernize Your Operations?"`
  - Subtitle: `"Contact our team today to evaluate your system architecture or schedule a direct demonstration."`
  - Buttons: `"Get in Touch"` | `"View Changelog"`

---

### Task 5.2: `src/pages/404.astro`
* **Goal:** Translate 404 error page.
* **Layout Meta:**
  - `title={`Page Not Found — ${siteConfig.title}`}`
  - `description="The page you are looking for does not exist or has been moved."`
* **Page Content:**
  - Heading: `"Page Not Found"`
  - Description: `"The link you followed may be broken, relocated, or no longer available. Please return to the homepage or reach out if you need assistance."`
  - Buttons:
    - `"Return to Home"` (url `/`)
    - `"Report Broken Link"` (url `mailto:${siteConfig.mail}?subject=Broken%20Link%20Report%20B1connect`)

---

# 📦 BATCH 6: CHANGELOG & RELEASES

### Task 6.1: `src/pages/changelog.astro`
* **Goal:** Set locale to `en-US` and translate headings.
* **Line 14:** Change locale to `"en-US"`:
  ```javascript
  function formatDate(date: Date): string {
    return date.toLocaleDateString("en-US", {
      year: "numeric",
      month: "long",
      day: "numeric",
    });
  }
  ```
* **Page Header:**
  - `title="Release Notes & Product Updates"`
  - `description="Regular improvements ensuring your Shopify and SAP Business One integration remains resilient, fast, and secure."`

---

### Task 6.2: `src/content/changelog/v1.0.0-initial-release.mdx`
```mdx
---
title: "v1.0.0 — Production Release"
publishDate: 2026-07-28
version: "v1.0.0"
description: "Initial production release of B1connect featuring native multi-tenancy, bidirectional synchronization, and enterprise-grade encryption."
---

## Key Highlights

- **Multi-Tenant Architecture**: A single integration cluster orchestrates multiple Shopify storefronts with isolated company databases and configurations.
- **Bidirectional Synchronization**: Automated Item Master & inventory flows (SAP B1 → Shopify) and instant Sales Order creation (Shopify → SAP B1 ORDR documents).
- **Enterprise-Grade Security**: At-rest AES-256-GCM encryption for credentials, constant-time HMAC-SHA256 webhook verification, and JWT session authentication.
- **High-Throughput Background Engine**: Built on .NET 10 and Hangfire with dead-letter queue resilience and automated exponential retries.
- **Self-Signed SSL Support**: Seamless connection to on-premise SAP B1 Service Layer instances with internal enterprise certificates.
- **Service Health Telemetry**: Automated health status observability via `/health`.
```

---

### Task 6.3: `src/content/changelog/v1.1.0-multi-warehouse.mdx`
```mdx
---
title: "v1.1.0 — Multi-Warehouse Routing & UoM Conversion"
publishDate: 2026-08-20
version: "v1.1.0"
description: "Enhanced multi-warehouse stock routing and flexible Unit of Measure (UoM) conversion rules."
---

## Enhancements & New Features

- **Multi-Warehouse Routing**: Map designated SAP B1 warehouse codes directly to specific Shopify fulfillment locations.
- **Flexible UoM Conversion**: Out-of-the-box support for converting composite packaging units (e.g., Case/Carton to Individual Units).
- **Redis Cache Optimization**: Accelerated catalog delta diffing by 45% during high-volume catalog sync cycles.
- **Connection Recovery**: Automatic reconnect handling when SAP Service Layer undergoes scheduled server restarts.
```

---

### Task 6.4: `src/content/changelog/v1.2.0-dashboard-analytics.mdx`
```mdx
---
title: "v1.2.0 — Live Event Stream & Diagnostic Tools"
publishDate: 2026-09-15
version: "v1.2.0"
description: "Live real-time event streaming interface and self-serve connectivity diagnostics."
---

## What's New in v1.2.0

- **Live Event Stream**: Real-time transaction observability showing sub-second sync latency directly in the monitoring UI.
- **Test Connection Diagnostics**: Validate Service Layer credentials and CompanyDB access rights from the setup wizard in real time.
- **Enhanced Error Diagnostics**: SAP B1 error responses are parsed into actionable troubleshooting recommendations.
- **SAP HANA & SQL 2022 Verification**: Full validation and certified compatibility with SAP Business One v10.0 FP 2305 and newer.
```

---

# 📦 BATCH 7: BLOG & CONTENT MARKETING

### Task 7.1: `src/pages/blog/index.astro` & `src/pages/blog/page/[page].astro`
* **Layout Meta:**
  - `title={`Blog & Engineering Insights — ${siteConfig.title}`}`
  - `description="Technical guides, architecture breakdowns, and ecosystem updates for Shopify and SAP Business One integrations."`
* **Page Header:**
  - `title="Engineering Insights & Integration Guides"`
  - `description="Technical deep dives, best practices, and release updates on connecting Shopify with SAP Business One."`

---

### Task 7.2: `src/content/post/memperkenalkan-b1connect/index.mdx`
```mdx
---
title: "Introducing B1connect: Enterprise Shopify × SAP Business One Integration"
description: "Why we engineered a dedicated middleware platform to bridge Shopify and SAP B1, and how it eliminates dozens of manual operational hours every week."
publishDate: 2026-07-28
read: 5
tags: ["Product", "Integration", "Shopify", "SAP B1"]
img: "/assets/article-cover.jpg"
img_alt: "B1connect Shopify and SAP Business One Integration"
featured: true
---

In modern omnichannel commerce, operational speed separates market leaders from organizations bogged down by administrative debt. Enterprises around the world rely on **SAP Business One** as their core ERP engine for inventory valuation, financials, and warehouse fulfillment, while choosing **Shopify** for world-class storefronts.

However, seamlessly bridging these two platforms has historically been fraught with complexity.

## The Traditional Dilemma: Siloed Storefronts and ERP Systems

Without automation, operations teams face relentless friction:

1. **Manual Order Re-Keying**: Operations staff re-type customer orders from Shopify into SAP B1, inviting costly human errors and shipment delays.
2. **Lagging Inventory Updates**: Stock depleted in physical warehouses takes hours to reflect on Shopify, triggering painful overselling and cancellations.
3. **Price Discrepancies**: Changes to SAP Price Lists take days to propagate across online sales channels, quietly eroding profit margins.

Custom point-to-point integrations often require tens of thousands of dollars in consulting fees, take months to deliver, and break with every major API update.

## Enter B1connect: Purpose-Built Integration Middleware

**B1connect** was created to bridge this divide. We engineered a resilient, multi-tenant middleware platform that connects Shopify directly to the official SAP Business One Service Layer.

### Why Teams Choose B1connect:

- **Automated Bidirectional Sync**: Master items and multi-warehouse stock levels flow from SAP to Shopify every 30 seconds. Orders from Shopify generate official SAP Sales Orders in real time via sub-second webhooks.
- **Native Multi-Tenancy**: A single cluster manages multiple storefronts and regional warehouses with strict database and credential isolation.
- **Enterprise-Grade Security**: Sensitive secrets are encrypted at rest with **AES-256-GCM**, and webhooks are validated using constant-time **HMAC-SHA256** signatures.
- **Fast Setup, Zero Core Modifications**: By leveraging the standard Service Layer, your SAP ERP database remains pristine and upgrade-safe.

With B1connect, your team can focus on scaling customer acquisition while your core operations run reliably in the background 24/7.
```

---

### Task 7.3: `src/content/post/cara-kerja-sinkronisasi-shopify-sap/index.mdx`
```mdx
---
title: "Under the Hood: How B1connect Synchronizes Shopify and SAP B1"
description: "A technical architectural review of background polling workers, webhook ingestion pipelines, and field mapping inside B1connect."
publishDate: 2026-08-15
read: 6
tags: ["Technical", "Architecture", "Synchronization"]
img: "/assets/article-cover.jpg"
img_alt: "B1connect Synchronization Architecture"
featured: false
---

Behind B1connect's intuitive user interface lies a high-throughput backend architecture engineered for speed, resilience, and strict transactional consistency. This article details how data flows between Shopify and SAP Business One under the hood.

## 1. Master Item & Inventory Pipeline (SAP ➔ Shopify)

Product catalog data and physical warehouse stock originate from SAP Business One as the authoritative single source of truth.

- **Intelligent Polling**: Background Hangfire workers query the SAP B1 Service Layer every 30 seconds.
- **Delta Change Detection**: The engine inspects `UpdateDate` and `UpdateTime` timestamps on `OITM` (Item Master) and `OITW` (Item Warehouse) tables against Redis caches, ensuring only mutated records are processed.
- **Attribute Mapping**: SAP attributes (`ItemCode`, `ItemName`, `SalUnitMsr`, and barcodes) are mapped automatically into Shopify Product and Variant schema definitions.
- **Multi-Warehouse Routing**: Quantities from designated SAP warehouse codes are aggregated or mapped directly into specific Shopify fulfillment locations.

## 2. Sales Order Ingestion Pipeline (Shopify ➔ SAP B1)

When a customer completes a checkout order on Shopify:

- **Webhook Event**: Shopify issues an instant `orders/paid` webhook payload to B1connect's secure ingestion endpoint.
- **Cryptographic Verification**: B1connect calculates HMAC signatures using the application's shared secret and executes a constant-time comparison against `X-Shopify-Hmac-Sha256` to prevent timing attacks.
- **Business Partner Reconciliation**: The engine matches the customer against SAP Business Partners (`OCRD`) by email or unique ID, automatically generating new accounts when needed.
- **Document Generation**: An official Sales Order (`ORDR`) document is created via the Service Layer complete with line items, tax rates, discounts, and shipping lines.
- **Dead-Letter Queue Resilience**: If the SAP server is temporarily under maintenance, Hangfire places the payload into an exponential-backoff queue, ensuring zero lost transactions.

This architecture ensures your commerce infrastructure operates without interruption or manual friction.
```

---

### Task 7.4: `src/content/post/keamanan-data-middleware-erp/index.mdx`
```mdx
---
title: "Enterprise Security Architecture: AES-256-GCM & HMAC Validation"
description: "How B1connect safeguards SAP B1 database credentials and Shopify access tokens using industry-standard cryptography and multi-tenant isolation."
publishDate: 2026-09-01
read: 4
tags: ["Security", "Encryption", "Enterprise"]
img: "/assets/article-cover.jpg"
img_alt: "B1connect Enterprise Data Security"
featured: false
---

When connecting an enterprise ERP system with cloud commerce platforms, data security is not an optional feature—it is a critical prerequisite. SAP Business One holds an enterprise's most confidential assets: financial ledgers, wholesale pricing tiers, margin data, and customer records.

At B1connect, we apply *Security by Design* across every layer of our architecture.

## 1. At-Rest Credential Encryption (AES-256-GCM)

SAP Service Layer credentials and private Shopify Access Tokens are never stored in plain text.

- We utilize **AES-256-GCM (Galois/Counter Mode)**, a gold-standard authenticated symmetric cipher trusted by global financial institutions.
- GCM provides dual guarantees: **confidentiality** and **cryptographic authenticity**, ensuring that ciphertext cannot be altered undetected.

## 2. Cryptographic Webhook Validation (HMAC-SHA256)

Every order webhook originating from Shopify must be proven authentic before processing:

- B1connect computes an HMAC digest of the raw payload using the app's shared secret.
- Verification is conducted via a constant-time equality check, eliminating side-channel timing attack vulnerabilities.

## 3. Multi-Tenant Data Isolation

In a multi-tenant environment orchestrating multiple merchant storefronts:

- Each tenant's configurations, credentials, and encryption keys are strictly partitioned.
- Database access policies enforce complete query isolation, guaranteeing that zero data leakage occurs between connected storefronts.

With these safeguards, your organization can harness the speed of cloud automation while maintaining strict compliance with enterprise security requirements.
```

---

## 🛠 VERIFICATION & TESTING CHECKLIST FOR THE AI AGENT

Once all batches are applied:
1. Run `npm run build` or `npx astro check` to verify that there are zero TypeScript, JSX, or markdown parsing errors.
2. Check that all URLs and routes (`/features`, `/how-it-works`, `/pricing`, `/about`, `/contact`, `/blog`, `/changelog`) render with English titles and copy.
3. Verify that the mobile hamburger menu and desktop headers display `Book a Demo`.
4. Ensure dark/light mode toggle and interactive animations continue to operate smoothly.
