# Rooftop poster — Rick Hendrick Chevrolet Norfolk

One-screen view of demand. Detail lives in [marketing-leads-map.md](./marketing-leads-map.md).

```mermaid
flowchart TB
  subgraph GEO ["Market: Hampton Roads"]
    VB["Virginia Beach demand"]
    NF["Norfolk rooftop · 6252 E VA Beach Blvd"]
    MIL["NAS Norfolk · Oceana · Langley · shipyards"]
    COMP["Priority Chevy Chesapeake · RK Chevy VB"]
  end

  VB --> NF
  MIL --> NF
  COMP -.->|"steal ROs and sales"| NF

  subgraph FIXED ["Fixed ops — start here"]
    APPT["serviceapptform"]
    COUP["serviceandpartsspecials"]
    SEO["service-and-parts-tips SEO"]
    ADV["Named advisors = moat"]
    TOW["Tow-in / no-appt = 1-star risk"]
  end

  subgraph VAR ["Variable ops"]
    NEW["New: Silverado Tahoe Equinox Corvette EV"]
    USED["Used: ~500 mixed-make units on 3P sites"]
    TRADE["Gubagoo 10-second trade"]
    FI["Credit app · GM Financial · military"]
  end

  subgraph ADJ ["Adjacent P&Ls"]
    COLL["Collision · Carwise/CCC photo estimate · C8 cert · Sunbit"]
    FLEET["Commercial · Work Truck Solutions · EZOrder · 300-1588 / 760-8103"]
    PARTS["GM OE / ACDelco counter"]
    EV["Free public L2 charge · ops inconsistency"]
  end

  NF --> FIXED
  NF --> VAR
  NF --> ADJ

  APPT --> ADV
  COUP --> APPT
  SEO --> APPT
  TOW --> ADV
  ADV -->|"MPI / wait lounge"| NEW
  COLL -->|"total loss"| NEW
  TRADE --> FI
  NEW --> APPT
```

## Capture objects to wire first

| Priority | Object | Why |
|---|---|---|
| 1 | `/service/serviceapptform/` | Highest-frequency lead; corporate UTM already exists |
| 2 | Service Google/Waze number `(757) 544-9732` vs site pool `(757) 271-1678` | Attribution is currently soup |
| 3 | Cadillac form leak on Chevy local listings | Demand handed to sister store |
| 4 | Gubagoo chat + 10-second trade | Occupies the on-site conversation slot |
| 5 | Collision Carwise/CCC photo estimate + `(757) 455-4505` | Insurance inbound; Shop Assistant already exists — orchestrate, don’t duplicate |
| 6 | CarGurus / iSeeCars listing completeness | 64% valid price+photo+miles |
| 7 | Work Truck Solutions EZOrder + two fleet phones | B2B is a different CRM object |
| 8 | Marketplace + DealerRater + GBP replies | Shared-queue replies already misfire |
| 9 | Google 4.7 / 9,506 vs Yelp ~2.3 / 165 | Review gating is working for Google and failing on Yelp |
| 10 | Wholesale parts (real desk, no public portal) + GM Accessories BAC 164265 | Invisible B2B capture |
| 11 | Get E-Price / Fast Pass / `/bad-credit-car-loans/` vs expired 0% APR banners | Finance-contingent price + stale offers = compliance risk for any bot |

## Do not build yet

A second CRM, a second chatbot, or blast campaigns. Hendrick already has Dealer Inspire, Gubagoo, and a corporate Snowflake Customer 360. The store needs an operating picture on top of those, starting with Service SLAs and listing hygiene.
