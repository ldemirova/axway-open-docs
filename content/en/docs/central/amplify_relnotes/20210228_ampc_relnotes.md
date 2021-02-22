---
title: Amplify Central February 2021 Release Notes
linktitle: Amplify Central February 2021
weight: 90
description: Amplify Central enables the user to manage their provider /
  consumer view. For more information, see the Amplify Central documentation.
---
## New features and enhancements

The following new features and enhancements are available in this update.

### Amplify Central CLI

The Amplify Central CLI is a package for managing Amplify Central resources with a DevOps approach to API Management.

Amplify Central CLI version 0.11.0 is now available on NPM (<https://www.npmjs.com/package/@axway/amplify-central-cli/v/0.11.0>)

The CLI extension is compatible **only** with the Amplify CLI **version 1.4** (<https://www.npmjs.com/package/@axway/amplify-cli/v/1.4.0>)

**This is not yet compatible with the Axway CLI**.

The Amplify Central CLI includes the following enhancements:

* Download the Azure agents from public artifactory.

### Amplify Central WebUI

The Amplify Central WebUI is used by both the API providers and consumers to manage and consume APIs.

The Amplify Central WebUI includes the following enhancements:  

* Amplify Central web UI can now be accessed using static IP address:
    * apicentral.axway.com (US region): 3.94.245.118 / 54.208.199.251 / 3.212.78.217 / 52.202.95.208 / 107.23.176.64 / 3.225.16.120.
    * central.eu-fr.axway.com (EU region): 52.47.84.198 / 13.36.25.69	/ 35.181.21.87 / 13.36.2.143 / 13.36.52.216 / 15.236.7.112.

### Axway Edge Gateway / AWS / Azure Agents

To provide better visibility into your mutli-type gateway eco system, two sets of agents are provided. These agents collect data from the Gateway (API / traffic) and exposes it in Amplify Central, providing you with a global vision of your eco system from a single interface.

The agents include the following enhancements:

* Azure traceability agent report subscription usage (Refer to API OBserver / App usage).
* Azure traceability agent report APIs usage for only discovered APIs.
* Azure agent are publicly available.
* New try it Gateways connectivity: Apigee (<https://github.com/Axway/agents-apigee>), Kong (<https://github.com/Axway/agents-kong>), Mulesoft (<https://github.com/Axway/agents-mulesoft>) and WSO2 (<https://github.com/Axway/agents-wso2>).

### Mesh governance

Amplify Central mesh governance enables you to govern and manage your APIs, public and private services, along with the hybrid environments where they are located.

Mesh governance includes the following enhancements:

## Fixed issues

The following issues were fixed in this version of Amplify Central:

* **Consumer is unable to consume v7 discovered APIs from Amplify Central web UI**. Previously, V7 discovery agent created application without cors enabled. Now the discovery agent creates the application with '*' in javascript origin which allow the API to be consumed from any location.
* **V7 traceability agent Linux service mode broken**. Proviously, the traceability service mode was broken. Now, the service mode has been restored and the traceability agent service can be installed, started and stopped
* **Fixed IP addresses**. Previously, to access Amplify platform or Central, IP addresses were dynamic. Now, static IP addresses have been assigned to help setting up the firewall rules. More information can be found [here](/docs/central/connect-api-manager/network-traffic-apimanager/index.html#communication-ports)

## Known limitations

This version of Amplify Central has the following limitations:

* API Observer:

    * Users that are assigned the Consumer role cannot see their subscription usage on the API Observer screen.  

* Axway Edge Gateway Agents:

    * Discovery Agent only discovers APIs having PassThrough, API Key and Oauth security.
    * Discovery Agent cannot expose discovered APIs in multiple teams, so the organization structure on API Manager is lost in Amplify Central. As a result, the API provider must create the team in Amplify Platform and share the API within appropriate teams.
    * When an API is renamed on the API Manager, the Discovery Agent is not able to recognize the API name change. This results in the API displaying in Amplify Central with dual entries of both the originally discovered name and the newly changed name.
    * Traceability Agent is not working in an externally managed topology deployment.

* AWS Gateway agents:

    * Discovery Agent is working with only one AWS Region (the one used when installing the agent).
    * Discovery Agent does not associate the usage plan and API when a subscriber chooses a usage plan that is not already linked to the chosen API.

* Azure agents:

    * Discovery Agent is not managing revision and version yet.

* Mesh governance alpha Discovery Agents:

    * The alpha Discovery Agents do not work with the Mesh Traceability Agent.
