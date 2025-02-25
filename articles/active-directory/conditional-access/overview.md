---
title: What is Conditional Access in Azure Active Directory?
description: Learn how Conditional Access is at the heart of the new identity-driven control plane.

services: active-directory
ms.service: active-directory
ms.subservice: conditional-access
ms.topic: overview
ms.date: 08/05/2022

ms.author: joflore
author: MicrosoftGuyJFlo
manager: amycolannino
ms.reviewer: calebb

ms.collection: M365-identity-device-management
ms.custom: contperf-fy20q4, azuread-video-2020
---
# What is Conditional Access?

The modern security perimeter now extends beyond an organization's network to include user and device identity. Organizations can use identity-driven signals as part of their access control decisions. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4MwZs]

Conditional Access brings signals together, to make decisions, and enforce organizational policies. Azure AD Conditional Access is at the heart of the new identity-driven control plane.

![Conceptual Conditional signal plus decision to get enforcement](./media/overview/conditional-access-signal-decision-enforcement.png)

Conditional Access policies at their simplest are if-then statements, if a user wants to access a resource, then they must complete an action. Example: A payroll manager wants to access the payroll application and is required to do multi-factor authentication to access it.

Administrators are faced with two primary goals:

- Empower users to be productive wherever and whenever
- Protect the organization's assets

Use Conditional Access policies to apply the right access controls when needed to keep your organization secure.

![Conceptual Conditional Access process flow](./media/overview/conditional-access-overview-how-it-works.png)

> [!IMPORTANT]
> Conditional Access policies are enforced after first-factor authentication is completed. Conditional Access isn't intended to be an organization's first line of defense for scenarios like denial-of-service (DoS) attacks, but it can use signals from these events to determine access.

## Common signals

Common signals that Conditional Access can take in to account when making a policy decision include the following signals:

- User or group membership
   - Policies can be targeted to specific users and groups giving administrators fine-grained control over access.
- IP Location information
   - Organizations can create trusted IP address ranges that can be used when making policy decisions. 
   - Administrators can specify entire countries/regions IP ranges to block or allow traffic from.
- Device
   - Users with devices of specific platforms or marked with a specific state can be used when enforcing Conditional Access policies.
   - Use filters for devices to target policies to specific devices like privileged access workstations.
- Application
   - Users attempting to access specific applications can trigger different Conditional Access policies. 
- Real-time and calculated risk detection
   - Signals integration with [Azure AD Identity Protection](../identity-protection/overview-identity-protection.md) allows Conditional Access policies to identify risky sign-in behavior. Policies can then force users to change their password, do multi-factor authentication to reduce their risk level, or block access until an administrator takes manual action.
- [Microsoft Defender for Cloud Apps](/defender-cloud-apps/what-is-defender-for-cloud-apps)
   - Enables user application access and sessions to be monitored and controlled in real time, increasing visibility and control over access to and activities done within your cloud environment.

## Common decisions

- Block access
   - Most restrictive decision
- Grant access
   - Least restrictive decision, can still require one or more of the following options:
      - Require multi-factor authentication
      - Require device to be marked as compliant
      - Require Hybrid Azure AD joined device
      - Require approved client app
      - Require app protection policy (preview)

## Commonly applied policies

Many organizations have [common access concerns that Conditional Access policies can help with](concept-conditional-access-policy-common.md) such as:

- Requiring multi-factor authentication for users with administrative roles
- Requiring multi-factor authentication for Azure management tasks
- Blocking sign-ins for users attempting to use legacy authentication protocols
- Requiring trusted locations for Azure AD Multi-Factor Authentication registration
- Blocking or granting access from specific locations
- Blocking risky sign-in behaviors
- Requiring organization-managed devices for specific applications

## License requirements

[!INCLUDE [Active Directory P1 license](../../../includes/active-directory-p1-license.md)]

Customers with [Microsoft 365 Business Premium licenses](/office365/servicedescriptions/office-365-service-descriptions-technet-library) also have access to Conditional Access features. 

Risk-based policies require access to [Identity Protection](../identity-protection/overview-identity-protection.md), which is an Azure AD P2 feature.

Other products and features that may interact with Conditional Access policies require appropriate licensing for those products and features.

## Next steps

- [Building a Conditional Access policy piece by piece](concept-conditional-access-policies.md)
- [Plan your Conditional Access deployment](plan-conditional-access.md)
- [Learn about Identity Protection](../identity-protection/overview-identity-protection.md)
- [Learn about Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)
- [Learn about Microsoft Intune](/intune/index)
