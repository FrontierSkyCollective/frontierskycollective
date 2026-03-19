# Phase 1 Observatory Architecture
Frontier Sky Collective

Document Version: 0.1  
Status: Planning  
Observation Node: FSC-OBS-001

---

# 1. Overview

Phase 1 establishes the **Minimum Viable Observation Node (MVON)** for Frontier Sky Collective.

The goal is to deploy a multi-sensor monitoring station capable of collecting synchronized data across multiple observational channels:

- optical sky monitoring
- aircraft tracking
- radio frequency monitoring
- environmental telemetry

This multi-source approach allows events to be cross-referenced against known aerial and atmospheric activity.

The initial node will be designated:

FSC-OBS-001

Location: Canton, Michigan, USA.

---

# 2. System Design Philosophy

The Phase 1 architecture follows several guiding principles:

• Use affordable, widely available hardware  
• Prefer open-source software when possible  
• Preserve raw observational data  
• Maintain reproducible system configurations  
• Allow modular upgrades without redesign

The system is designed so that additional sensors or nodes can be integrated later.

---

# 3. System Architecture

High level architecture:

Sensors  
↓  
Local Capture Systems  
↓  
Local Storage  
↓  
Event Detection  
↓  
Workflow Automation (n8n)  
↓  
Data Indexing and Reporting

Primary processing will occur on local systems within the Frontier Sky Collective home lab environment.

---

# 4. Hardware Components

## 4.1 Optical Sky Monitoring System

Primary purpose:

Continuous monitoring of the night sky for visible aerial phenomena.

Proposed hardware:

Compute Platform  
Raspberry Pi 5 (8GB recommended)

Camera Module  
Raspberry Pi Camera Module 3 (NoIR preferred for low-light performance)

Lens  
Wide angle lens (approximately 120°–160° field of view)

Mounting  
Weatherproof outdoor enclosure with clear optical dome or window.

Storage  
Local SSD connected via USB or network storage via home lab server.

Operational mode:

Continuous night recording or motion-triggered capture depending on software configuration.

---

## 4.2 ADS-B Aircraft Tracking

Purpose:

Receive aircraft transponder signals to identify aircraft near the observation site.

Proposed hardware:

RTL-SDR v3 or equivalent SDR receiver

1090 MHz ADS-B antenna  
(outdoor mounted if possible)

Compute platform:

Either Raspberry Pi system or existing home lab server.

Software candidates:

dump1090  
tar1090  
piaware

Collected data will be used to cross-reference observed aerial events.

---

## 4.3 Radio Frequency Monitoring (SDR)

Purpose:

Monitor portions of the radio spectrum for unusual transmissions or activity that may correlate with observed events.

Proposed hardware:

RTL-SDR v3 receiver (initial system)

Future upgrade path:

Airspy SDR or similar higher sensitivity receiver.

Antennas:

General purpose broadband antenna for initial experimentation.

Software candidates:

rtl_power  
gqrx  
sdrangel

Data products may include:

waterfall recordings  
spectrum scans  
signal detection logs

---

## 4.4 Environmental Monitoring

Purpose:

Provide environmental context for observations.

Potential hardware:

temperature sensor  
humidity sensor  
barometric pressure sensor  
wind measurement (optional)

Example platforms:

BME280 sensor module  
or small weather station integrated with Raspberry Pi.

Environmental data allows correlation between observations and atmospheric conditions.

---

# 5. Compute Infrastructure

Initial compute nodes:

Observation Node Processor  
Raspberry Pi 5

Home Lab Server  
existing home lab infrastructure for storage and analysis.

Responsibilities:

Raspberry Pi

• sensor control  
• image capture  
• SDR capture  
• initial data tagging

Home Lab

• long term storage  
• automated workflows  
• event detection analysis  
• reporting

---

# 6. Software Architecture

The software stack will consist primarily of open-source tools.

Core components include:

Operating System  
Linux (Raspberry Pi OS or Debian)

Camera Capture Software  
libcamera  
motion  
or custom capture scripts

ADS-B Software  
dump1090 or equivalent

SDR Tools  
rtl_power  
gqrx  
sdrangel

Automation Platform  
n8n (running on home lab server)

n8n will be used for:

• event pipeline automation  
• metadata enrichment  
• report generation  
• data tagging workflows

---

# 7. Data Storage

Raw data types expected:

image or video recordings  
ADS-B logs  
radio spectrum logs  
environmental telemetry

Primary storage strategy:

local capture → home lab storage system

Recommended structure:

/observatory_data/
   optical/
   adsb/
   rf/
   environmental/

Data retention policies may evolve as the dataset grows.

---

# 8. Event Detection Strategy

Initial detection methods may include:

motion detection within sky camera footage  
bright object detection  
scheduled satellite pass correlation  
ADS-B proximity alerts

Future development may include machine learning assisted classification.

---

# 9. External Data Sources

Observation data may be cross-referenced against public databases including:

OpenSky Network  
CelesTrak satellite catalog  
American Meteor Society meteor reports  
public weather datasets

These sources help eliminate conventional explanations for observed phenomena.

---

# 10. Future Expansion

Potential upgrades include:

all-sky camera systems  
radio telescope receiver systems  
automated telescope mount  
additional observation nodes

The architecture is intentionally modular to support expansion.

---

# 11. Document Status

This document represents the **initial Phase 1 architecture plan**.

Hardware selection and software configuration may evolve as testing begins.
