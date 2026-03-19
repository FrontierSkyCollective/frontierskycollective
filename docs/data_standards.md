# Data Standards

All observations recorded by Frontier Sky Collective follow standardized metadata structures.

---

## Time Standard

All timestamps use **UTC (Coordinated Universal Time)**.

Example:

2026-03-19T02:14:23Z

---

## Observation Metadata

Each recorded event should include the following fields when possible:

- timestamp
- sensor ID
- observation node ID
- latitude
- longitude
- camera orientation (azimuth/elevation)
- environmental conditions
- nearby aircraft (if available)
- satellite pass proximity (if available)

---

## Sensor Identification Format

Sensor identifiers follow this format:

FSC-OBS-###-TYPE##

Examples:

FSC-OBS-001-CAM01  
FSC-OBS-001-SDR01  
FSC-OBS-001-ADS01

---

## Event Classification Categories

Observed events may be categorized as:

CAT-1 Aircraft  
CAT-2 Satellite  
CAT-3 Meteor  
CAT-4 Atmospheric Phenomenon  
CAT-5 Lightning or Electrical Event  
CAT-6 Unknown Aerial Object  
CAT-7 Instrument Artifact

---

## Data Preservation

Raw observational data should be preserved whenever possible.

Derived analysis files should be stored separately from original recordings.
