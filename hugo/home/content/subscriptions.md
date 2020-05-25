---
title: SolarNetwork subscriptions
date: 2020-05-20
publishdate: 2020-06-01
type: about
markup: "mmark"
---
{{% section  title="SolarNetwork subscriptions" %}}
SolarNetwork Foundation offers subscriptions to the
[SolarNetwork](https://data.solarnetwork.net/solaruser/) platform which are based on the amount of
data collected into and queried out of the platform. By subscribing to SolarNetwork not only are
you supporting our mission to provide tools to help educate people about renewable energy and 
operate renewable energy assets, you gain access to the following SolarNetwork features:

{.table .uk-table .uk-table-divider}
| Feature          | Description |
|------------------|-------------|
| Priority support | Support straight from the SolarNetwork experts. |
| Bulk import      | Import CSV data into SolarNetwork. |
| Bulk export      | Export CSV data out of SolarNetwork, on an automated schedule or as a one-off. |
| OCPP integration | Integrate electric vehicle charging stations with your SolarNetwork account via the Open Charge Point Protocol from the [Open Charge Alliance](https://www.openchargealliance.org/). |

Other subscriber-only features will be added over time. Want to sign up? Email us at 
info@solarnetwork.net and we would be happy to help you get started.

## SolarNetwork terminology
To understand the SolarNetwork subscription costs, the following terms are used:

{.table .uk-table .uk-table-divider}
| Term         | Definition |
|--------------|------------|
| **Account**  | A means to access SolarNetwork services based on registering a unique email address. |
| **Node**     | A device that collects data for an account. Any number of nodes may be associated with an account. Each node is assigned a unique identifier by SolarNetwork. |
| **Source**   | A unique identifier for  a stream of data captured by a node. Often a source denotes a hardware device that a node is collecting data from. Sources are given short textual identifiers by node administrators, and can be organized using slashes into meaningful hierarchies. For example _/home/weather_ might be used for a weather station source. 
| **Datum**    | A timestamped sample of data specific to a source and uploaded to SolarNetwork. |
| **Property** | A uniquely named measurement captured in a datum. Each datum can have any number of properties within it. For example _temperature: 20℃_ and _wind speed: 20 km/hr_ might be captured in a datum from a weather station source. |

## Subscription pricing

Here are the new pricing tiers for the subscriptions SolarNetwork Foundation offers. Keep in mind
that subscriptions are billed _per month per node_ so tiers are applied at the node level, not at
the SolarNetwork account level:

{.table .uk-table .uk-table-divider}
|                   | Tier 1             | Tier 2             | Tier 3             | Tier 4             |
|-------------------|--------------------|--------------------|--------------------|--------------------|
| Tier start        | 1                  | 50,000             | 400,000            | 1,000,000          |
| Properties posted | $9 / million       | $6 / million       | $4 / million       | $2 / million       |
| Datum queried     | $2 / million       | $1 / million       | $0.50 / million    | $0.20 / million    |
| Datum stored^†^   | $0.40 / million    | $0.20 / million    | $0.05 / million    | $0.006 / million   |

^†^ Datum stored costs calculated _per day_ and aggregated per bill.

{{% /section %}}
{{% section  title="Subscription details" style="primary" %}}
## Properties posted

This price is calculated from the number of properties posted into SolarNetwork over the billing period.

## Datum queried

This price is calculated from the number of datum returned from any SolarNetwork API query that
returns datum over the billing period. For API calls that return paged results (e.g. results 1 - 100
of 10,000, then results 101 - 200, and so on) only the number of datum returned in each page
response count towards the total. If a query requests aggregate values, only the number of aggregate
datum returned count towards the total. For example, requesting hourly aggregated datum given 1,000
raw datum that span 24 hours would return 24 datum that count towards the total.

## Datum stored

This price is calculated from the total number of datum stored in SolarNetwork on each day over the
billing period. As nodes post datum, this value grows. SolarNetwork also stores rolled-up aggregate
datum derived from the raw datum—at hourly, daily, and monthly aggregate levels. Each of these
aggregate datum are counted in this total as well.
{{% /section %}}
{{% section  title="Examples" style="secondary" %}}
The following sections illustrate how the SolarNetwork subscription costs are calculated.

## Properties posted

A node collects temperature and wind speed properties from a single weather station
source once per minute. Over one 30-day month that would equate to:

1 _source_ × 2 _properties_ × 60 _minutes_ × 24 _hours_ × 30 _days_ = **86,400** properties

{.table .uk-table .uk-table-divider}
| Tier      | Calculation | Cost |
|-----------|-------------|------|
| 1         | 50,000 × $9 ÷ 1,000,000 | $0.45 |
| 2         | 36,400 × $6 ÷ 1,000,000 | $0.22 |
| **Total** |  | **$0.67** |

## Datum queried

The following example builds off the **Properties Posted** example above, in which 1 datum is posted
every minute. A script requests the following datum:

{.table .uk-table .uk-table-divider}
| Query | Result Count | Schedule |
|-------|--------------|----------|
| all datum for the past month, aggregated daily | 30 | every hour |
| all datum for the past 2 hours | 120 | 6 times per hour | 
| all datum for the past 24 hours, aggregated hourly | 24 | every hour |
| most recently available datum | 1 | every minute |

Over the course of a 30 day month that would equate to:

(30 daily + (120 datum × 6) + 24 hourly + 60 most recent) × 24 hours × 30 days = **600,480** datum

{.table .uk-table .uk-table-divider}
| Tier      | Calculation | Cost |
|-----------|-------------|------|
| 1         | 50,000 × $2 ÷ 1,000,000 | $0.10 |
| 2         | 350,000 × $1 ÷ 1,000,000 | $0.35 |
| 3         | 200,480 × $0.50 ÷ 1,000,000 | $0.10 |
| **Total** |  | **$0.55** |

## Datum stored

The following example builds off the **Properties Posted** example above, in which 1 datum is posted
every minute. A node has been running for a year and has 525,600 raw, 8,760 hourly aggregate, 365
daily aggregate, and 12 monthly aggregate datum stored in SolarNetwork, for a total of 534,737. Each
day the number of new datum stored would equate to:

(((60 datum per minute + 1 hourly aggregate datum) × 24 hours) + 1 daily aggregate datum = 1,465 datum

Over the course of the next 30 day month the datum storage cost would equate to:

for _d_ = 1..30: _d_ = _d~prev~_ + 534,737 + (_d_ × 1,465) = **16,723,335** datum

{.table .uk-table .uk-table-divider}
| Tier      | Calculation | Cost |
|-----------|-------------|------|
| 1         | 50,000 × $0.40 ÷ 1,000,000 | $0.02 |
| 2         | 350,000 × $0.20 ÷ 1,000,000 | $0.07 |
| 3         | 600,000 × $0.05 ÷ 1,000,000 | $0.03 |
| 4         | 15,723,335 × $0.006 ÷ 1,000,000 | $0.09 |
| **Total** |  | **$0.21** |

## Overall cost

The overall monthly subscription cost for properties posted, datum queried, and datum stored for the
previous examples would be:

{.table .uk-table .uk-table-divider}
| Subscription | Cost |
|--------------|------|
| Properties posted | $0.67 |
| Datum queried     | $0.55 |
| Datum stored      | $0.21 |
| **Total**         | **$1.43** |



{{% /section %}}
