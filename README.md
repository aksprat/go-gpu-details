# DigitalOcean GPU Infrastructure Reference

A single-page internal reference for DigitalOcean's GPU infrastructure — covering SKUs, specs, pricing, networking, regions, data centers, inference products, and roadmap. Deployed as a static site on DigitalOcean App Platform.

## Overview

This project is a self-contained `index.html` page that serves as an internal one-stop shop for DigitalOcean GPU details. It is kept up to date with the latest GPU product information and is sourced from official DO docs and internal communications.

## Contents

The reference is organized into eight tabbed sections:

| Tab | Description |
|-----|-------------|
| **SKU & Specs** | Full spec sheets for every GPU Droplet SKU (NVIDIA and AMD), including VRAM, vCPU, RAM, disk, size slugs, virtualization type, and availability status |
| **Pricing** | On-demand hourly/monthly rates, 12-month contract pricing, and inference product pricing |
| **Networking** | Per-SKU networking details: intra-node interconnects (NVLink / Infinity Fabric), inter-node RoCEv2 fabric bandwidth, NIC models, and host Ethernet |
| **Regions** | GPU SKU availability by DigitalOcean region, cluster size limits, SLA, and spin-up times |
| **Data Centers** | Details on each GPU-capable data center (ATL1, RIC1, NYC2, TOR1, SFO2/3, NYC1, MEM1) |
| **Inference Products** | Serverless Inference, Dedicated Inference, Inference Hub, and GPU Droplets — status, pricing model, supported GPUs, and key features |
| **Roadmap** | Upcoming GPU SKUs and features with estimated timelines (B300 multi-node, MI355X, on-demand expansions, etc.) |
| **Quick Reference** | Condensed pricing cheat-sheet, architecture facts, key links, and open engineering follow-ups |

## GPU SKUs Covered

**NVIDIA**
- RTX 4000 Ada (1×, 20 GB VRAM)
- L40S (1×, 48 GB VRAM)
- RTX 6000 Ada (1×, 48 GB VRAM)
- H100 SXM5 (1× and 8×, up to 640 GB VRAM)
- H200 SXM5 (1× and 8×, up to 1,128 GB VRAM)
- B300 / Blackwell (1× and 8×, up to 2,304 GB HBM3e — Contract)

**AMD**
- MI300X (1× and 8×, up to 1,536 GB HBM3)
- MI325X (8×, 2,048 GB — Contract)
- MI350X (8×, 2,304 GB — Contract)
- MI355X (8×, ~2,304 GB — Coming Q3 2026)

## Deployment

The site is deployed as a static site on DigitalOcean App Platform using the configuration in [`.do/app.yaml`](.do/app.yaml). The `index.html` at the repository root is served directly.

```yaml
name: go-gpu-details
static_sites:
  - name: go-gpu-details
    source_dir: /
    index_document: index.html
```

## Data Sources

Pricing is validated against the [DigitalOcean Droplet Pricing Docs](https://docs.digitalocean.com/products/droplets/details/pricing/) and the [GPU Droplets Pricing Page](https://www.digitalocean.com/pricing/gpu-droplets). Specs and roadmap items are sourced from official DO documentation and internal announcements. Last updated: **May 2026**.

> **Note:** Roadmap items (⚡) are indicative and subject to change. Confirm current status with Product/Capacity before sharing externally.