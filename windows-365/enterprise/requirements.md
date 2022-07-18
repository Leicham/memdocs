---
# required metadata
title: Windows 365 requirements
titleSuffix:
description: Windows 365 requirements
keywords:
author: ErikjeMS  
ms.author: erikje
manager: dougeby
ms.date: 02/08/2022
ms.topic: how-to
ms.service: cloudpc
ms.subservice:
ms.localizationpriority: high
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:

ms.reviewer: chbrinkh
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
---

# Requirements for Windows 365

To use Cloud PCs, you must meet the following requirements:

## Azure requirements

None, if you plan on provisioning Azure AD joined Cloud PCs on a Microsoft hosted network.

If you choose to provision Cloud PCs on your own network, an active Azure subscription with the following configurations is required:

- Sufficient permissions to grant Windows 365:
  - A reader role on the subscription.
  - Network contributor permissions on the resource group.
  - A network contributor role on the vNet.

## Azure Active Directory and Intune requirements

- A valid and working Intune and Azure Active Directory tenant.
- Ensure that Intune device type enrollment restrictions are set to Allow Windows (MDM) platform for corporate enrollment.
- Infrastructure configuration: If you plan on provisioning Hybrid Azure AD joined Cloud PCs, you must configure your infrastructure to automatically hybrid Azure AD join any devices that domain join to the on-premises Active Directory. This [configuration lets them be recognized and managed in the cloud](/azure/active-directory/devices/overview).
- Azure Active Directory Domain Services isn't supported because it doesn't support Hybrid Azure AD join.

## Domain requirements

None, if you plan on provisioning Azure AD joined Cloud PCs on a Microsoft hosted network.

If you choose to provision Hybrid Azure AD joined Cloud PCs, then the following configurations on your domain are required:

- If an organizational unit is specified, ensure it exists and is valid.
- An Active Directory user account with sufficient permissions to join the computer into the specified organizational unit within the Active Directory domain. If you don't specify an organizational unit, the user account must have sufficient permissions to join the computer to the Active Directory domain.
- User accounts that are assigned Cloud PCs must have a synced identity available in both Active Directory and Azure Active Directory.

## Licensing requirements

- You must have an Intune license so that you can use Intune to manage the devices.
- Users must have licenses for Windows, Intune, Azure AD, and Windows 365 to use their Cloud PC.

## Management requirements

You must use [Microsoft Endpoint Manager admin center](https://admin.microsoft.com/) to manage your Cloud PCs.

## Role and identity requirements

- Admin role: You must be an [Intune Administrator in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#intune-administrator) to provision Cloud PCs.
- User identity: Cloud PC users must be configured with [hybrid identities](/azure/active-directory/hybrid/whatis-hybrid-identity) so that they can authenticate with resources both on-premises and in the cloud.

## Supported Azure regions for Cloud PC provisioning

Windows 365 manages the capacity and availability of underlying Azure resources as part of the service. Windows 365 partners closely with Azure to select regions that meet our Windows 365 service requirements for availability and capacity. On availability, we use features like availability zones in Azure to provide in-region resiliency as built-in value to the service. You can create a virtual network or use the Microsoft hosted network for provisioning Cloud PCs in the following Azure regions:

- US Central
- US East
- US East 2
- US West 2
- US West 3
- US South central
- Asia Southeast
- Australia East
- Europe North
- Europe West
- UK South
- Canada Central
- Germany West Central
- India Central
- Japan East
- France Central

<!-- ########################## -->
## Next steps

[Review network requirements](requirements-network.md)