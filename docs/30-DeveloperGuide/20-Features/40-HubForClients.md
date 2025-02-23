---
layout: default
title: Hub for Clients
parent: Features
grand_parent: Developer guide
nav_order: 40
---

# Hub for Clients (Api and Worker Feature)
This file explains what to use the the hub for client feature in your V3 project.

## Prerequisite

### Knowledge to have:
* [SignalR introduction](https://docs.microsoft.com/fr-fr/aspnet/signalr/overview/getting-started/introduction-to-signalr)

## Overview
The Web clients are connected to one Web front server using SignalR.
The server can push event to the Connected Clients.
The front are connected with the redis server.
The endpoint for this service is "HubForClients" (ie: http://localhost/[YourProjectName]/WebApi/HubForClients)

## Activation
* bianetconfig.json
In the BIANet Section add:
``` json
    "ApiFeatures": {
      "HubForClients": {
        "Activate": true
      }
    },
```
* bianetconfig.ENV.json (4 files not Development)
In the BIANet Section add:
``` json
    "ApiFeatures": {
      "HubForClients": {
        "RedisConnectionString": "[FqdnYourRedisServer]",
        "RedisChannelPrefix": "[YourProjectName]"
      }
    },
```
replace [FqdnYourRedisServer] by the FQDN of your redis server
replace [YourCompanyName] by the name of your company
replace [YourProjectName] by the name of your project
replace [ENV] by the corresponding env of the file (int, uat, prd or pra)

