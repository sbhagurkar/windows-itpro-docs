---
title: Example Windows Defender Application Control (WDAC) base policies (Windows)
description: When creating a WDAC policy for an organization, start from one of the many available example base policies.
keywords: security, malware
ms.topic: article
ms.assetid: 8d6e0474-c475-411b-b095-1c61adb2bdbb
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
ms.collection: M365-security-compliance
author: jsuther1974
ms.reviewer: jogeurte
ms.author: dansimp
manager: dansimp
ms.date: 08/05/2022
ms.technology: windows-sec
---

# Windows Defender Application Control (WDAC) example base policies

**Applies to:**

- Windows 10
- Windows 11
- Windows Server 2016 and above

>[!NOTE]
>Some capabilities of Windows Defender Application Control (WDAC) are only available on specific Windows versions. Learn more about the [Windows Defender Application Control feature availability](feature-availability.md).

When you create policies for use with Windows Defender Application Control (WDAC), start from an existing base policy and then add or remove rules to build your own custom policy. Windows includes several example policies that can be used, or organizations that use the Device Guard Signing Service can download a starter policy from that service.

## Example Base Policies

| **Example Base Policy** | **Description** | **Where it can be found** |
|----------------------------|---------------------------------------------------------------|--------|
| **DefaultWindows.xml** | This example policy is available in both audit and enforced mode. It includes rules to allow Windows, third-party hardware and software kernel drivers, and Windows Store apps. Used as the basis for all [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) policies. | %OSDrive%\Windows\schemas\CodeIntegrity\ExamplePolicies |
| **AllowMicrosoft.xml** | This example policy is available in audit mode. It includes the rules from DefaultWindows and adds rules to trust apps signed by the Microsoft product root certificate. | %OSDrive%\Windows\schemas\CodeIntegrity\ExamplePolicies |
| **AllowAll.xml** | This example policy is useful when creating a blocklist. All block policies should include rules allowing all other code to run and then add the DENY rules for your organization's needs. | %OSDrive%\Windows\schemas\CodeIntegrity\ExamplePolicies |
| **AllowAll_EnableHVCI.xml** | This example policy can be used to enable [memory integrity](https://support.microsoft.com/windows/core-isolation-e30ed737-17d8-42f3-a2a9-87521df09b78) (also known as hypervisor-protected code integrity) using Windows Defender Application Control. | %OSDrive%\Windows\schemas\CodeIntegrity\ExamplePolicies |
| **DenyAllAudit.xml** | ***Warning: May cause long boot time on Windows Server 2019.*** Only deploy this example policy in audit mode to track all binaries running on critical systems or to meet regulatory requirements. | %OSDrive%\Windows\schemas\CodeIntegrity\ExamplePolicies |
| **Device Guard Signing Service (DGSS) DefaultPolicy.xml** | This example policy is available in audit mode. It includes the rules from DefaultWindows and adds rules to trust apps signed with your organization-specific certificates issued by the DGSS. | [Device Guard Signing Service NuGet Package](https://www.nuget.org/packages/Microsoft.Acs.Dgss.Client) |
| **MEM Configuration Manager** | Customers who use Configuration Manager can deploy a policy with Configuration Manager's built-in WDAC integration, and then use the generated policy XML as an example base policy. | %OSDrive%\Windows\CCM\DeviceGuard on a managed endpoint |
| **SmartAppControl.xml** | This example policy includes rules based on [Smart App Control](https://support.microsoft.com/topic/what-is-smart-app-control-285ea03d-fa88-4d56-882e-6698afdb7003) that are well-suited for lightly managed systems. This policy includes a rule that is unsupported for enterprise WDAC policies and must be removed. For more information about using this example policy, see [Create a custom base policy using an example WDAC base policy](create-wdac-policy-for-lightly-managed-devices.md#create-a-custom-base-policy-using-an-example-wdac-base-policy)). | %OSDrive%\Windows\schemas\CodeIntegrity\ExamplePolicies |
