---
title: Azure 安全中心安全策略可以作为 Azure 策略的一部分进行设置并在安全中心查看 | Microsoft Docs
description: 本文档介绍如何在 Azure Policy 中设置策略或在 Azure 安全中心查看策略。
services: security-center
documentationcenter: na
author: rkarlin
manager: mbaldwin
editor: ''
ms.assetid: cd906856-f4f9-4ddc-9249-c998386f4085
ms.service: security-center
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/25/2018
ms.author: rkarlin
ms.openlocfilehash: 330b66e64484417e50f39c35cf90a6fd62b1e888
ms.sourcegitcommit: 922f7a8b75e9e15a17e904cc941bdfb0f32dc153
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2018
ms.locfileid: "52334663"
---
# <a name="view-security-policies"></a>查看安全策略

本文介绍如何配置安全策略，以及如何在安全中心查看这些策略。 Azure 安全中心会自动在每个载入的订阅上分配其[内置安全策略](security-center-policy-definitions.md)。 可以在 [Azure Policy](../azure-policy/azure-policy-introduction.md) 中配置这些策略，由此也可跨管理组和跨多个订阅设置策略。

有关如何使用 PowerShell 设置策略的说明，请参阅[快速入门：使用 Azure RM PowerShell 模块创建策略分配以识别不合规资源](../azure-policy/assign-policy-definition-ps.md)。



## <a name="what-are-security-policies"></a>什么是安全策略？
安全策略定义了工作负载的相应配置，有助于确保用户遵守公司或法规方面的安全要求。 在 Azure Policy 中，可定义 Azure 订阅策略，并根据工作负载类型或数据机密性进行量身定制。 例如，使用受管制数据（如个人身份信息）的应用程序可能需要比其他工作负载更高级别的安全性。 若要跨订阅或管理组设置策略，请在 [Azure Policy](../azure-policy/azure-policy-introduction.md) 中进行设置。



安全策略驱动在 Azure 安全中心获得的安全建议。 可以使用它们监视符合性以帮助识别潜在漏洞和缓解威胁。 若要详细了解如何确定适合你的选项，请参阅[内置安全性策略](security-center-policy-definitions.md)列表。

### <a name="management-groups"></a>管理组
如果你的组织有多个订阅，则可能需要一种方法来高效地管理这些订阅的访问权限、策略和符合性。 Azure 管理组提供订阅上的作用域级别。 可将订阅组织到名为“管理组”的容器中，并将管理策略应用到管理组。 管理组中的所有订阅都将自动继承应用于管理组的策略。 为每个目录指定了一个称为“根”管理组的顶级管理组。 此根管理组内置在层次结构中，包含其所有下级管理组和订阅。 此根管理组允许在目录级别应用全局策略和 RBAC 分配。 若要设置用于 Azure 安全中心的管理组，请按照[为 Azure 安全中心实现租户级可见性](security-center-management-groups.md)中的说明进行操作。

> [!NOTE]
> 务必要了解管理组和订阅的层次结构。 请参阅[使用 Azure 管理组来组织资源](../governance/management-groups/index.md#root-management-group-for-each-directory)来了解有关管理组、根管理和管理组访问权限的详细信息。
>

## <a name="how-security-policies-work"></a>安全策略工作原理
安全中心自动为每个 Azure 订阅创建默认的安全策略。 可以在 Azure Policy 内编辑策略，执行以下操作：
- 创建新的策略定义。
- 跨管理组和订阅分配策略，这些管理组和订阅可以代表整个组织，或者组织中的某个业务部门。
- 监视策略符合性。

有关 Azure Policy 的详细信息，请参阅[创建和管理策略以强制实施符合性](../azure-policy/create-manage-policy.md)。

Azure Policy 由以下组件构成：

- “策略”是一项规则。
- “计划”是一个策略集合。
- “分配”是将计划或策略应用于特定的范围（管理组、订阅或资源组）。

资源将根据分配给它的策略进行评估，并且将根据资源符合的策略数收到符合率。

## <a name="who-can-edit-security-policies"></a>谁可以编辑安全策略？
安全中心使用基于角色的访问控制 (RBAC)，提供可以分配给 Azure 中用户、组和服务的内置角色。 用户打开安全中心时，只能看到其有权访问的资源的相关信息。 这意味着，向用户分配了资源所属的订阅或资源组的“所有者”、“参与者”或“读者”角色。 除这些角色外，还有两个特定的安全中心角色：

- 安全读者：有权查看安全中心，包括建议、警报、策略和运行状况，但无法进行更改。
- 安全管理员：拥有与安全读者相同的查看权限，不同之处在于该角色有权更新安全策略、拒绝建议和关闭警报。

## <a name="edit-security-policies"></a>编辑安全策略
可以在 [Azure Policy](../governance/policy/tutorials/create-and-manage.md) 中为每个 Azure 订阅和管理组编辑默认的安全策略。 若要修改安全策略，你必须是该订阅或包含型管理组的所有者、参与者或安全管理员。

有关如何在 Azure Policy 中编辑安全策略的说明，请参阅[创建和管理策略以强制实施符合性](../governance/policy/tutorials/create-and-manage.md)。

## <a name="view-security-policies"></a>查看安全策略

要在安全中心内查看安全策略，请执行以下操作：

1. 在“安全中心”仪表板中，选择“安全策略”。

    ![“策略管理”窗格](./media/security-center-policies/security-center-policy-mgt.png)

  在“策略管理”屏幕中，可以看到管理组数、订阅数、工作区数以及管理组结构。

  > [!NOTE]
  > - “安全中心”仪表板在“订阅覆盖范围”下显示的订阅数可能会高于在“策略管理”下显示的订阅数。 订阅覆盖范围显示标准订阅、免费订阅和“未覆盖”订阅的数量。 “未覆盖”订阅未启用“安全中心”，并且不会显示在“策略管理”下。
  >

  表中的列显示了：

 - **策略计划分配** – 分配给订阅或管理组的“安全中心”[内置策略](security-center-policy-definitions.md)和计划。
 - **符合性** – 管理组、订阅或工作区的总体符合性得分。 得分是各个分配的加权平均值。 加权平均值取决于单个分配中的策略数以及该分配应用于的资源数。

 例如，如果订阅有两台 VM 和一个分配有五个策略的计划，则订阅中有 10 项评估。 如果其中一台 VM 不符合其中的两个策略，则订阅的分配的总体符合性得分为 80%。

 - **覆盖范围** – 标识管理组、订阅或工作区在其上运行的定价层：免费或标准。  若要详细了解安全中心的定价层，请参阅[定价](security-center-pricing.md)。
 - **设置** – 订阅有“编辑设置”链接。 选择“编辑设置”，可为每个订阅或管理组更新[安全中心设置](security-center-policies-overview.md)。

2. 选择想要查看其策略的订阅或管理组。

  - “安全策略”屏幕反映在所选订阅或管理组上分配的策略所执行的操作。
  - 在顶部，使用提供的链接打开适用于订阅或管理组的每个策略“分配”。 可以使用链接访问分配以及编辑或禁用策略。 例如，如果发现特定策略分配有效地拒绝终结点保护，则可以使用该链接访问策略以及辑或禁用它。
  - 在策略列表中，可以看到策略有效应用于订阅或管理组。 这意味着将考虑适用于该范围的每个策略的设置，并提供策略所执行操作的累计效果。 例如，如果一个分配禁用此策略，而另一个设置为 AuditIfNotExist，则累计效果适用于 AuditIfNotExist。 更积极的效果始终优先。
  - 策略效果可以是：追加、审核、AuditIfNotExists、拒绝、DeployIfNotExists 和禁用。 有关如何应用效果的详细信息，请参阅[了解策略效果](../governance/policy/concepts/effects.md)。

   ![策略屏幕](./media/security-center-policies/policy-screen.png)

> [!NOTE]
> - 查看已分配的策略时，可以看到多个分配并且可以看到每个分配如何自行配置。

## <a name="next-steps"></a>后续步骤
本文中已经介绍了如何在安全中心配置安全策略。 若要详细了解安全中心，请参阅以下文章：

* [Azure 安全中心规划和操作指南](security-center-planning-and-operations-guide.md)：学习如何规划和了解有关 Azure 安全中心的设计注意事项。
* [Azure 安全中心的安全性运行状况监视](security-center-monitoring.md)：了解如何监视 Azure 资源的运行状况。
* [管理和响应 Azure 安全中心的安全警报](security-center-managing-and-responding-alerts.md)：了解如何管理和响应安全警报。
* [通过 Azure 安全中心监视合作伙伴解决方案](security-center-partner-solutions.md)：了解如何监视合作伙伴解决方案的运行状态。
* [为 Azure 安全中心实现租户级可见性](security-center-management-groups.md)：了解如何为 Azure 安全中心设置管理组。
* [Azure 安全中心常见问题解答](security-center-faq.md)：获取有关使用服务的常见问题的答案。
* [Azure 安全性博客](https://blogs.msdn.com/b/azuresecurity/):.查找关于 Azure 安全性及合规性的博客文章

若要了解有关 Azure Policy 的详细信息，请参阅[什么是 Azure Policy？](../azure-policy/azure-policy-introduction.md)
