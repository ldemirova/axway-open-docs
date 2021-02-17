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

Amplify Central CLI version 0.7.0 is now available on NPM (<https://www.npmjs.com/package/@axway/amplify-central-cli/v/0.7.0>)

The CLI extension is compatible **only** with the Amplify CLI **version 1.4** (<https://www.npmjs.com/package/@axway/amplify-cli/v/1.4.0>)

**This is not yet compatible with the Axway CLI**.

The Amplify Central CLI includes the following enhancements:  

### Amplify Central WebUI

The Amplify Central WebUI is used by both the API providers and consumers to manage and consume APIs.

The Amplify Central WebUI includes the following enhancements:  

### Axway Edge Gateway / AWS / Azure Agents

To provide better visibility into your mutli-type gateway eco system, two sets of agents are provided. These agents collect data from the Gateway (API / traffic) and exposes it in Amplify Central, providing you with a global vision of your eco system from a single interface.

The agents include the following enhancements:

### Mesh governance

Amplify Central mesh governance enables you to govern and manage your APIs, public and private services, along with the hybrid environments where they are located.

Mesh governance includes the following enhancements:

## Fixed issues

The following issues were fixed in this version of Amplify Central:

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
    * Traceability agent is not reporting the App usage traffic.

* Mesh governance alpha Discovery Agents:

    * The alpha Discovery Agents do not work with the Mesh Traceability Agent.