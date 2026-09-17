# Category Knowledge Brief — Scissor Lifts

- **Vertical:** Hire/Bulk
- **Category / Sub-category:** POWERED ACCESS / Scissor Lifts
- **Date reviewed:** 17/09/2026
- **Reviewed by:** Martin Richmond
- **Status:** In Review

---

## 1. Definition

"A scissor lift is a type of Mobile Elevated Work Platform (MEWP) designed to safely raise personnel and materials strictly in a vertical direction. It gets its name from its distinctive lifting mechanism, a stack of folding, criss-crossing metal supports in an "X" or pantograph pattern that resemble a pair of scissors as they extend and contract."

## 2. What does NOT belong here

- Mast Booms, Push Arounds or AWP's
- Boom Lifts
- Spider Booms
- Truck or Van Mounted Booms

## 3. Naming convention — description

**Rule:** `TYPE + WORKING HEIGHT + POWER SOURCE + SPECIAL FEATURE (Not Mandatory)`

**Good examples:**
- `SCISSOR 8M BATTERY NARROW AISLE`
- `SCISSOR 12M DIESEL ROUGH TERRAIN`

**Bad examples (before cleanse) → Fixed:**
- `8M SCISSOR 1932` → `SCISSOR 8M BATTERY`
- `SJ3220 SCISSOR` → `SCISSOR 8M BATTERY NARROW`

**Width Definitiona**
| Category | Imperial | Metric | Access Capabilities |
|---|---|---|---|
| Micro / Compact | up to 30" | up to 0.76m | Clears standard single doors with ease. |
| Narrow Aisle| 32" to 34" | 0.81m to 0.85m | Fits between warehouse racking, and through double doors. |
| Normal / Standard | 46" and above | 1.17m and above | Requires double doors or open space |

**Naming Validation Checklist**
- Product type included
- Size included
- Power source included
- Boom type included
- Key differentiator included
- Abbreviations removed
- Manufacturer/supplier name removed where necessary

## 3b. Naming pattern string (machine-checkable)

Same rule as above, restated in the agreed universal 4-slot order — Type of Machine / Size/Model / Power / Added Detail — so it lines up with every other category's brief and can be walked positionally by a script.

**Pattern:** `[TYPE OF MACHINE] BOOM [SIZE/MODEL] 12M [POWER] DIESEL [ADDED DETAIL] TELESCOPIC`

**Worked examples:**

| Type of Machine | Size/Model | Power | Added Detail |
|---|---|---|---|
| Boom | 12M | Hybrid | Articulated, Narrow |
| Boom | 23M | Diesel | Telescopic, Tracked |
| Boom | 12M | Electric | Articulated, Towable |

**Slot definitions for Boom Lifts:**

| Slot | Mandatory | Value type | Allowed values | Regex / format hint |
|---|---|---|---|---|
| Type of Machine | Yes | Fixed term | Boom | Match against enum |
| Size/Model | Yes | Measurement — working height | 10m–82m | `\d{1,2}M` |
| Power | Yes | Fuel/power type | Diesel / Electric / Battery / Hybrid / Hydrogen | Fixed list. Hybrid = Battery + one of Diesel/Electric/Hydrogen |
| Added Detail | No, but Boom Type within it is effectively mandatory | Free text from fixed list, boom type + optional special feature | Boom type: Articulated / Telescopic (required — classify by predominant feature if both apply). Special feature (optional, one or more): Tracked, Narrow, Towable, Negative Reach, 4 Wheel Drive, Rough Terrain | One or more allowed, order not enforced |

**Notes for script/brief use:**
- Column order is always Type of Machine → Size/Model → Power → Added Detail, matching every other category's brief.
- Boom Type (Articulated/Telescopic) is technically inside the Added Detail slot for this category but should be treated as a required sub-field within it — a Boom name missing this should still flag, even though "Added Detail" as a whole is marked optional at template level.
- Working height and platform height are related but distinct (platform height typically ~2m lower) — Size/Model in the name refers to working height specifically; platform height lives in the attributes table (section 4), not the name.

## 4. Typical attributes / spec bands

| Attribute | Mandatory | Typical range / values | Notes |
|---|---|---|---|
| Working height | Yes | 10m–82m | Common size bands used across market |
| Platform height | Yes | 8m–80m | Typically 2m lower than working height |
| Power Type | Yes | Diesel / Electric / Battery / Hybrid / Hydrogen | Hybrid would typically be Battery and then a power source that could be Diesel, Electric or Hydrogen |
| Boom Type | Yes | Articulated or Telescopic | If machine is both then class as the predominant feature (usually Telescopic) |
| Special Feature | No | Tracked, Narrow, Towable, Negative Reach, 4 Wheel Drive, Rough Terrain | Any feature that can be used to differentiate two machines with the same specifications |

## 5. Known traps / history

- Added to wrong category, in the past Plant and Access have been used. Should be Powered Access
- Sub Category can be confusing, there are a number that could be and have been used. For example Boom, Small Boom, Medium Boom, Large Boom, Specialist Boom.

## 6. Approved reference sources

Use sources in this priority order.

| Priority | Source | Purpose |
|---|---|---|
| 1 | Manufacturer Specification Sheet | Primary data |
| 2 | Supplier Product Catalogue | Secondary validation |
| 3 | HSS Website | Market comparison |
| 4 | Competitor Website | Benchmarking |

Cross-checks made this review (source — what it confirmed):

- 

## 7. Duplicate / consolidation notes

- 

## 8. Open questions / follow-ups

- 

---
*Template v2 — Project Argos*
