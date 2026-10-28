# Cruise Guest Commerce Platform: A Reference

> How a cruise company replaced queues, paper and brand-by-brand systems with one wearable, one app and one commerce platform.

*Reference document · prepared by Debashish Patra · based on a 2016–2017 delivery*

---

## In 30 seconds

A global cruise company wanted every guest to buy, book and order anything with a tap, with no cards, cash or queues. The programme delivered three guest-facing products: **Concierge** (what to do), **Shop** (what to buy) and **Dine** (what to eat). Behind them sat a **full e-commerce platform** connecting more than 20 ship and shore systems. It launched on the first equipped ship in November 2017, followed by a phased rollout across the fleet.

## Before → After

| | Before | After |
|---|---|---|
| **Paying** | Cards and cash, a separate bill per venue | One wearable, one guest bill |
| **Ordering food** | Wait for a server, repeat your preferences | Order from your phone, TV or kiosk; it finds you |
| **Booking shows and dining** | Queue at a desk or call | Book and get a seat in the app |
| **Buying excursions, spa, merchandise** | Different counters, different systems | One catalog, one cart |
| **The systems underneath** | Each brand ran its own | One shared platform across brands |

## The three products

| Product | A guest can… | Think of it as |
|---|---|---|
| **Concierge** | Discover things to do, reserve dining and shows, get a seat | A personal assistant in your pocket |
| **Shop** | Browse and buy merchandise, photos, spa services and shore excursions | An online store that works at sea |
| **Dine** | See a digital menu, order food and drinks, set dietary preferences | Food delivery that knows where you are on the ship |

## How it fits together

```mermaid
flowchart LR
    G["Guest<br/>wears a wearable, uses the guest app"] --> C["Guest app<br/>phone · web · ship TVs · kiosks"]
    C --> P["Commerce platform<br/>catalog · cart · orders · pricing · promotions<br/>tax · gratuity · loyalty credits · entitlements"]
    P --> PAY["Payments and<br/>guest bill"]
    P --> INV["Inventory<br/>food · retail · housekeeping · boutique"]
    P --> RES["Dining and entertainment<br/>reservations and seating"]
    P --> BOOK["Booking and<br/>reservation records"]
    P --> FR["Fraud checks"]
    P --> BUS(["Event bus"])
    BUS --> CREW["Crew tasks and delivery<br/>crew app"]
```

A step-by-step walk-through of one drink order is in [docs/how-it-works.md](docs/how-it-works.md).

## What was delivered

- **Product ownership and roadmap.** One Product Owner role ran the backlog for the three products: **90+ features across 14 capabilities**, sequenced across three milestones leading to the November 2017 launch.
- **Commerce architecture and integration.** An e-commerce build on **Elastic Path**, with a thin microservice layer and an event bus. It was multilingual, multi-currency and multi-device. It integrated **20+ systems**, including payments, reservations, inventory (**CrunchTime**) and seating. This replaced siloed brand-level systems with one cross-brand platform.
- **Agile delivery and governance.** **Two-week sprints**, prioritisation and backlog governance across consulting, cruise-company and partner teams. Stakeholders from CXO to GM level stayed aligned through a requirements document traced back to business goals.

More on scope and boundaries: [docs/product-ownership.md](docs/product-ownership.md).

## Timeline

| When | Milestone |
|---|---|
| Oct–Nov 2016 | Business requirements and logical architecture agreed |
| Feb 2017 | **Pre-Cruise:** account, journey planning, check-in |
| May 2017 | **On-Board:** Shop, Dine, notifications, wayfinding |
| Aug 2017 | **Launch preparation:** testing, performance tuning, content checks |
| Nov 2017 | Launch on the first equipped ship, then a phased fleet rollout |

## By the numbers

**Delivery scope**

- 3 product lines · 90+ features · 14 capabilities
- 20+ integrated systems
- 2-week sprints

**Wider programme** (public context, separate from the commerce scope)

- A guest base of 10 million+ across the cruise company
- A network of thousands of sensors aboard each ship
- A separate online check-in product cut boarding steps from about 10 minutes to about 30 seconds

## Repo map

| File | What's in it |
|---|---|
| [docs/how-it-works.md](docs/how-it-works.md) | One order, step by step, and design choices |
| [docs/product-ownership.md](docs/product-ownership.md) | What the Product Owner role covered, and what sat with other teams |
| [docs/glossary.md](docs/glossary.md) | Plain-English definitions of every term used |

---

*A simplified reference summary. It contains no confidential client documents; the client is deliberately anonymised and internal system names are generalised. Elastic Path and CrunchTime are trademarks of their respective owners.*
