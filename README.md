# FIWARE Data Spaces

## Overview

Data Spaces constitute one of the pillars of the European Strategy for Data. A Data Space is defined as a governance-based ecosystem that facilitates the creation of value around the use of data access, processing, presentation, and interpretation services, while preserving trust among the parties, the sovereignty of each participant, and an agile and seamless experience in carrying out the processes associated with the provision, publication, discovery, contracting, and use of data and data services.

## Basic Concepts

### Products, Services and Resources

Any participant in a data space may act in the role of product provider, product consumer, or both. A product comprises a set of data services: services accessible through APIs (Application Programming Interfaces) at specific internet endpoints that enable access to or processing of data (including services whose invocation entails the execution of actions), or end-user application services that, through web tools (dashboards, maps, VR-based interfaces, natural-language chatbots based on generative AI, etc.), facilitate the management, visualization, and interpretation of data, as well as the invocation of processing services, by end users. The services linked to a given product may require the provisioning of resources for their execution, both in the cloud (e.g., compute and storage capacity) and in the field (e.g., gateways, devices). Some of these resources (e.g., devices) may need to be provisioned by each of the organizations that has acquired the right to consume the services.

The complexity of the products provided in a data space can vary over a very wide range, from simple products comprising access to a specific dataset to sophisticated products corresponding to complete systems that implement multiple data access or data processing services via APIs, as well as applications intended for end users that facilitate access to, processing, visualization, or interpretation of data.

Thus, for example, within a data space for the agri-food sector, we may have products that simply offer access to weather data or historical data related to a farm's use of pesticides, but also sophisticated products such as a complete irrigation management system for citrus farms or a fruit growth monitoring system. Each of these systems may cover a broad set of services accessible via APIs (both for access to current and historical measurement data, and for access to predictions regarding the ideal time for irrigation or fruit harvesting) or linked to applications (dashboards, monitoring maps, prediction maps, chatbots, etc.) that facilitate the management, visualization, and interpretation of data, as well as the invocation of processing services, by end users, while taking into account the need to provision resources both in the cloud (space for storing data linked to each consumer farm) and in the field (devices for detecting moisture measurements in an irrigation system and fruit quality/size in a fruit growth monitoring system, etc.).

### Decentralized Architecture

Consumers of products within a data space (i.e., consumers of the services linked to those products) may be organizations or users/agents within those organizations. Users/agents may be natural persons (for example, the organization's staff or its customers), devices (including not only sensors/actuators but also robots), or software systems/agents (including AI agents) operating within the organization. These users have an identity within the organization that distinguishes them from other users.

One principle that must be preserved within data spaces is sovereignty in the management of user/agent identities by the organizations that acquire the right to use the services associated with products offered in the data space. They should not be forced to register the identity of the users/agents linked to their organizations in any user management system associated with the products of providers whose services they use. Such users/agents must be able to consume the services linked to any product offered in the data space by disclosing only those attributes (credentials) required for access to the services to be authorized.

To meet this requirement of sovereignty in the management of users/agents, data spaces must rely on technologies that support decentralized identity management based on verifiable credentials. The following figure illustrates the entities (which map to components or systems) involved in a management system of this nature, and the interactions between them. On the one hand, users employ components that act as Holders and store the Verifiable Credentials (VCs) that entities known as Issuers assign to them. In the case of natural persons, the component that acts as Holder is implemented as an electronic wallet (digital wallet). When authenticating against a system, a component called a Verifier within that system will request from the Holder component certain VCs required for access to the system. Once the Holder sends them, the Verifier component will verify that the VCs sent have been issued by an Issuer entity that is recognized as a trusted issuing entity for such VCs. To do this, it will confirm that the identifier of the entity that issued the presented VCs is included in the registry of entities recognized as being able to issue those VCs.

![Verifiable Credentials Triangle](./img/triangle.png)

The definition of any product that a provider offers in the data space will include the authorization policies governing access by organizations or by users within organizations to the data services linked to the product. These policies will be formulated on the basis of verifiable credentials and the roles/claims included in those credentials that, by definition, the product envisages potential users possessing, and on the basis of which the services behave. In this regard, an organization acquiring the rights to use the services linked to a given product will mean that the organization becomes recognized, by the product provider, as a trusted issuer of certain credentials and roles/claims defined for the product. The authorization policies defined for a product may, in turn, contemplate users/agents that possess other types of credentials and global roles/claims issued by entities recognized as globally trusted issuers within the data space for those credentials, including those roles/claims.

Thus, for example, a product that implements a system providing a solution aimed at agricultural holdings will contemplate different authorization policies depending on the credentials of the end users connecting to the system: credentials for the farm manager, for the farmers employed on that farm, or for inspectors accredited by the competent authorities to carry out auditing tasks. It may also contemplate authorization for access from devices, for example devices connected to the land (e.g., a moisture sensor) or devices that measure fruit quality parameters and inject data into the system. When a given farm acquires the right to use the product (i.e., contracts it), the farm's administrators will issue verifiable credentials for the different categories of employees (manager, operator, etc.) as well as for the devices deployed in the field. Inspectors working for the competent authority, on the other hand, will have credentials issued by that authority. All these users will connect to the services linked to the product in order to carry out the corresponding operations according to the established authorization policies.

This model makes it easier for users of an organization consuming services linked to products in the data space to authenticate against various products in the data space in the same way, regardless of where each of them is hosted, in a seamless manner despite the adoption of a fully distributed architecture in which each system is hosted in different clouds.

### Governance

Governance is an inherent aspect of any data space. From a technical perspective, a data space includes, as part of its governance, an agreement on which interoperability standards to adopt in several key areas:

* **Data exchange and service invocation:** which APIs, protocols, and data models to use for data exchange (access) and the invocation of services for data processing, visualization, or interpretation.
* **Trust, Identity Management, and Authorization:** which mechanisms to employ to determine trust in participants, manage identities in a decentralized way, and define the authorization policies for access to and use of data or data services that must be applied.
* **Value creation:** which mechanisms to employ for the specification of products and product offerings in the data space, as well as for the discovery and contracting of products, ensuring efficient lifecycle management.

A successful data space strategy requires reaching consensus on the interoperability standards to be adopted in each of these areas. Otherwise, the potential of data spaces to generate value would be very limited.

In addition, a data space includes other governance-related aspects such as the bylaws or rulebook that each participant commits to comply with, which will set out elements such as the legal agreements governing interaction between participants, certain operational requirements (for example, requirements that facilitate traceability/auditability of transactions in case of disputes), and the governing bodies and rules established for decision-making at the overall data space level.

## High-Level Architecture

From a global architecture perspective, a data space can be built from a series of elements:

* **Data Space Connectors**, which participating organizations in the data space must deploy in order to offer data products (a combination of data access, data transfer, data processing, or data visualization/interpretation services) and interact with participants that wish to reliably and securely consume the services associated with those products, in accordance with agreed terms and conditions.
* **Global Trust Registries**, which include, among other things, the registry of participants that have adhered to the established data space governance framework, the registry of trusted issuers of global verifiable credentials assignable to organizations, users and/or products, and the registry of adopted verifiable credential formats/schemas.
* **Intermediary systems** such as:
    * **Marketplaces**, in which product providers can publish specifications for their products (defined as a combination of data and data services), as well as offers defined around those products, and in which users can place product orders (leading to provisioning and/or activation).
    * **Data Catalog and Data Service Publishing Platforms**, that compile information about the data and data services offered by organizations and provide means for potential consumers to discover them.

Different organizations will participate in the Data Space. Some of them will act in the role of provider of data products, while other organizations (or, more precisely, users and applications associated with those organizations) will act in the role of service consumers, with the possibility that the same organization may assume both roles.

![Data Spaces Architecture](./img/agrifood.png)

## FIWARE Components for Data Spaces

<!-- This section is a draft and will be filled with detailed content later. -->

### FIWARE Data Space Connector

<!-- TODO: Detailed description of the FIWARE DSC modules, deployment model, supported standards, and API compatibility -->

### FIWARE Marketplace

<!-- TODO: Detailed description of the FIWARE BAE-based marketplace, its interaction with connectors, and the DOME project -->

## License

This project is licensed under the Apache License 2.0 — see the [LICENSE](LICENSE) file for details.
