# Awesome-Mobile-Analytics-KPI-Dashboard

# Awesome Mobile Analytics & KPI Dashboard

> A curated list of top Mobile Analytics and KPI Dashboard platforms — both SaaS/Hosted commercial solutions and open-source alternatives for tracking product metrics, visualizing KPIs, and understanding user behavior in mobile applications.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Mixpanel](#mixpanel)
  - [Amplitude](#amplitude)
  - [Zoho Apptics](#zoho-apptics)
  - [Datadog Mobile RUM](#datadog-mobile-rum)
  - [UXCam](#uxcam)
- [Open-Source Software](#-open-source-software)
  - [OpenPanel](#openpanel)
  - [PostHog](#posthog)
  - [nilalytics](#nilalytics)
  - [Umami (via umami_flutter)](#umami-via-umami_flutter)
  - [Lens](#lens)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Mobile Analytics and KPI Dashboard platforms. These are not open-source but are included as reference points for feature comparison.

### Mixpanel
**Type:** Event-based product analytics with funnel and retention analysis
Mixpanel is built for product teams wanting self-serve analytics without SQL, with strong funnel analysis, retention curves, and user segmentation [citation:7]. It added session replay for mobile in 2025 and offers a free tier up to **20 million events/month** [citation:7]. The platform has **8.33% market share** in mobile analytics with **53,522 customers** globally [citation:4]. **Trade-off:** It is purely analytics-focused—no infrastructure features like crash reporting or push notifications [citation:7].

### Amplitude
**Type:** Product analytics with predictive modeling
Amplitude offers similar capabilities to Mixpanel but is stronger on predictive analytics and cohort modeling, with its "Predict" feature using ML to score which users are likely to convert or churn [citation:7]. It holds **5.68% market share** with **36,496 customers** [citation:4]. The free starter plan covers up to **10 million events/month** [citation:7]. **Best for:** Data-heavy product teams with data scientists who want to build predictive models on behavioral data.

### Zoho Apptics
**Type:** End-to-end product analytics with native iOS app
Zoho Apptics provides insights into app usage, health, performance, and engagement across mobile, web, and desktop apps, with a **native iOS app** for accessing KPIs on the go [citation:1]. Key mobile KPIs include app health (crashes, sessions), adoption (new devices, unique active devices, opt-in/opt-out devices), and engagement (sessions, screens, events, APIs) [citation:1]. It includes real-time crash reporting, in-app feedback, and **AI insights using Apple's on-device foundation models** for private analytics summaries [citation:1]. **Best for:** Teams already in the Zoho ecosystem wanting a privacy-focused analytics suite with a native mobile dashboard app.

### Datadog Mobile RUM
**Type:** Real User Monitoring tied to backend traces
Datadog RUM provides mobile real user monitoring that correlates frontend mobile performance with backend traces, making it the strongest choice for teams already using Datadog for APM [citation:12]. It supports mobile-first frameworks including React Native and captures session replays alongside performance data [citation:12]. **Best for:** Teams needing backend correlation and already invested in Datadog's observability stack.

### UXCam
**Type:** Mobile product analytics with AI analyst and session replay
UXCam records every session automatically without manual event tagging, capturing screens, taps, swipes, scrolls, and crashes [citation:9]. Its **Tara AI analyst** answers plain-language questions like "Why did checkout completion drop?" with numbers and linked session replays [citation:9]. It offers funnels, retention, segments, and KPI dashboards, with masking running in the SDK so sensitive content never leaves the device [citation:9]. It processes **100B+ data points monthly** and is SOC 2 Type II audited [citation:9]. **Best for:** Teams wanting session replay and AI-driven insights without manual event instrumentation.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Mobile Analytics and KPI Dashboard tools. The open-source ecosystem spans **Mixpanel alternatives with mobile SDKs**, **OTel-native lakehouse analytics**, **privacy-first Flutter packages**, and **YAML-driven KPI dashboards**.

### OpenPanel
**Stack:** ClickHouse / PostgreSQL / Redis / Docker | **License:** Open Source (self-hostable)
OpenPanel is an open-source product and web analytics platform positioned as a **Mixpanel and Amplitude alternative** [citation:8]. Key characteristics:
- **Mobile SDKs**: React Native, iOS, and Android SDKs for tracking events from mobile apps [citation:8]
- **Real-time dashboards**: Funnels, retention, user profiles, and sessions [citation:8]
- **Cookieless option**: Can run without cookies for privacy-conscious deployments [citation:8]
- **Self-hosted architecture**: Three apps (API, dashboard, worker) with ClickHouse for events, PostgreSQL for users/projects, and Redis for queues [citation:8]
- **Deployment**: Railway template available that creates admin account, closes sign-up, and pins login cookies to your domain [citation:8]

**Trade-off:** Self-hosting requires managing ClickHouse, PostgreSQL, and Redis—the seven services idle at approximately 1.7 GB of RAM [citation:8]. **Best for:** Teams wanting a self-hosted Mixpanel alternative with native mobile SDKs and ClickHouse-backed real-time analytics, accepting the infrastructure overhead.

### PostHog
**Stack:** TypeScript / ClickHouse / PostgreSQL | **License:** Apache-2.0 (core)
PostHog bundles product analytics, feature flags, session replay, error tracking, and experiments in one SDK, with a **first-class React Native SDK** [citation:12]. It has the **best free tier in 2026** at **1 million events/month** including replay and flags, and can be self-hosted or used via cloud [citation:12]. The decision rubric in a 2026 RUM comparison recommends PostHog when "one product analytics tool, OSS preferred" is the priority [citation:12]. **Trade-off:** Self-hosting is heavy (ClickHouse, PostgreSQL, Redis) and the team steers most users to cloud. **Best for:** Teams wanting an all-in-one open-source analytics platform with mobile SDK support and a generous free tier.

### nilalytics
**Stack:** Python / DuckDB / OpenTelemetry / DuckLake | **License:** Apache-2.0
nilalytics is a **batteries-included, OpenTelemetry-native** analytics platform for web and mobile that runs entirely on your own object storage [citation:2]. Key characteristics:
- **Mobile support**: Collects events, errors, and performance data via **OpenTelemetry SDKs** (mobile + server) [citation:2]
- **No warehouse, no per-event fees**: Stores data in a DuckLake lakehouse on S3, MinIO, GCS, Cloudflare R2, or Azure [citation:2]
- **Built-in analytics**: Funnels, retention, errors, traces, metrics, and cross-device identity [citation:2]
- **Secure by default**: Token-authenticated ingest and read-only query authorization [citation:2]
- **Sub-second reads**: Via DuckDB's Quack protocol [citation:2]

**Trade-off:** It is a newer project with a Python-based stack—you need object storage and familiarity with OTel concepts. **Best for:** Teams wanting OpenTelemetry-native mobile analytics with data staying entirely in their own object storage and no per-event pricing.

### Umami (via umami_flutter)
**Stack:** Flutter package / Umami server | **License:** MIT (package) / Umami open-source
umami_flutter is a lightweight, privacy-focused Flutter package that connects to a self-hosted **Umami** analytics server, positioned as an open-source alternative to Firebase Analytics [citation:5]. Key characteristics:
- **Privacy-first**: No cookies, no PII, no third-party data sharing—GDPR/CCPA friendly without consent banners [citation:5]
- **Non-blocking**: Events tracked before initialization are queued and flushed automatically [citation:5]
- **Automatic device info**: Collects device ID, locale, and screen resolution [citation:5]
- **Tiny footprint**: ~9 KB compressed, with minimal dependencies [citation:5]
- **Multi-platform**: Android, iOS, macOS, and Windows [citation:5]

**Trade-off:** It tracks screen views and custom events but **drops events when offline** (no queuing) and does not provide user identity tracking [citation:5]. It is a lightweight event tracker rather than a full KPI dashboard. **Best for:** Flutter developers wanting simple, privacy-respecting event tracking with self-hosted Umami, accepting the limited analytics depth.

### Lens
**Stack:** Python / YAML / React | **License:** Open Source (PyPI)
Lens is a YAML-driven analytics dashboarding library that generates a full React dashboard from a config file [citation:3]. Key characteristics:
- **KPI widgets**: With trend indicators, formatting, and compact numbers [citation:3]
- **Charts and tables**: Bar, line, area, pie, donut, horizontal bar, combo via ApexCharts, plus data tables with pagination and CSV export [citation:3]
- **Filters**: Dropdown, date range, text search, number range, toggle [citation:3]
- **Security**: Read-only queries, parameterized SQL, no raw SQL on the client [citation:3]
- **Deployment**: `lens serve dashboard.yaml` starts the dashboard instantly [citation:3]

**Trade-off:** It is a **dashboarding library** rather than an analytics backend—you must supply the SQL queries and data pipeline yourself. It has no built-in mobile SDK. **Best for:** Developers wanting a quick, YAML-configured KPI dashboard UI that connects to their own database, accepting that event collection must be handled separately.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Mobile SDK | Self-Hosted | KPI Dashboard | Best For |
|----------|---------|-------|------------|-------------|---------------|----------|
| **Mixpanel** | Proprietary | Cloud | ✅ React Native | ❌ | ✅ Funnels/retention | Product-led teams |
| **Amplitude** | Proprietary | Cloud | ✅ React Native | ❌ | ✅ Predictive | Data-heavy teams |
| **Zoho Apptics** | Proprietary | Cloud | ✅ Native iOS app | ❌ | ✅ On-the-go KPIs | Zoho ecosystem |
| **UXCam** | Proprietary | Cloud | ✅ iOS/Android | ❌ | ✅ AI analyst | Session replay + AI |
| **OpenPanel** | Open Source | ClickHouse/Postgres | ✅ iOS/Android/RN | ✅ | ✅ Funnels/retention | Self-hosted Mixpanel alt |
| **PostHog** | Apache-2.0 | ClickHouse/Postgres | ✅ React Native | ✅ (Heavy) | ✅ All-in-one | OSS all-in-one |
| **nilalytics** | Apache-2.0 | DuckDB/OTel | ✅ OTel SDKs | ✅ (Object storage) | ✅ Funnels/retention | OTel-native lakehouse |
| **umami_flutter** | MIT | Flutter/Umami | ✅ Flutter | ✅ (Umami) | ❌ (Events only) | Privacy-first Flutter |
| **Lens** | Open Source | Python/YAML/React | ❌ | ✅ (Library) | ✅ YAML-driven | Quick KPI dashboard UI |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Mobile Analytics or KPI Dashboard tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source.

**Note on the open-source ecosystem:** The open-source landscape for **mobile analytics** is **growing but fragmented**. **PostHog** is the most complete all-in-one option with a first-class React Native SDK and the best free tier, though self-hosting is heavy [citation:12]. **OpenPanel** is the most direct Mixpanel alternative, with native iOS/Android/React Native SDKs and ClickHouse-backed funnels and retention, deployable via Railway [citation:8]. **nilalytics** takes a fundamentally different approach—OpenTelemetry-native, storing everything in your own object storage with no per-event fees [citation:2]. For Flutter developers, **umami_flutter** offers privacy-first event tracking but lacks KPI dashboards and offline queuing [citation:5]. **Lens** fills the dashboarding layer for teams that already have a database and want a quick YAML-configured KPI UI [citation:3]. No single open-source project fully replicates Mixpanel's funnel depth combined with Zoho Apptics' native mobile dashboard experience, but OpenPanel and PostHog cover the core mobile analytics workflow comprehensively.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
