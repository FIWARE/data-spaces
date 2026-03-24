# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **documentation-only repository** for FIWARE Data Spaces. It contains conceptual and architectural documentation describing Data Spaces, the FIWARE Data Space Connector (DSC), and the FIWARE Marketplace. There is no application code, build system, or test suite.

## Repository Structure

- `a.md` / `b.md` — Main documentation files covering Data Space concepts, architecture, the FIWARE DSC, and the FIWARE Marketplace. These are two variants of overlapping content (b.md focuses on overview/concepts; a.md adds detailed FIWARE component descriptions).
- `img/` — Diagrams referenced from the markdown files (triangle.png, agrifood.png, overview.png).
- `README.md` — Project readme (currently empty).
- `LICENSE` — Apache 2.0.

## Domain Context

Key domain concepts that appear throughout the documents:

- **Data Space Connector (DSC):** Modular software stack organizations deploy to offer/consume data products. Includes authentication, authorization, catalog, contract/lifecycle management, DSP compatibility, logging, monitoring, and remote attestation modules.
- **Verifiable Credentials (VCs):** Decentralized identity mechanism — issuers, holders (wallets), verifiers, trust registries. Central to the sovereignty model.
- **Products and Offerings:** A product bundles data access services, processing services, and/or visualization services. Products are published in marketplaces and contracted via TM Forum Open APIs.
- **Reference standards:** W3C DIDs, W3C VCs, OpenID OID4VC (SIOPv2, OID4VP), EBSI Trusted Issuers Registry, TM Forum Open APIs, DCATv3, W3C ODRL, Gaia-X ODRL VC profile, Eclipse/IDSA Dataspace Protocol (DSP).
- **FIWARE BAE (Business Application Ecosystem):** Open-source marketplace implementation adopted by the EU DOME project.
