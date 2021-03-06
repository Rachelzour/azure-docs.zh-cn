---
title: 教程：Azure Active Directory 与 Voyance 集成 | Microsoft 文档
description: 了解如何在 Azure Active Directory 和 Voyance 之间配置单一登录。
services: active-directory
documentationCenter: na
author: jeevansd
manager: mtillman
ms.reviewer: joflore
ms.assetid: 539dc1f9-64c9-4dce-b259-2b0b49dcf857
ms.service: active-directory
ms.component: saas-app-tutorial
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 07/16/2017
ms.author: jeedes
ms.openlocfilehash: ce72fb75729574c9645025459b67fd3eab597bb1
ms.sourcegitcommit: 1d850f6cae47261eacdb7604a9f17edc6626ae4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/02/2018
ms.locfileid: "39432171"
---
# <a name="tutorial-azure-active-directory-integration-with-voyance"></a>教程：Azure Active Directory 与 Voyance 集成

在本教程中，了解如何将 Voyance 与 Azure Active Directory (Azure AD) 集成。

将 Voyance 与 Azure AD 集成提供以下优势：

- 可在 Azure AD 中控制谁有权访问 Voyance
- 可以让用户使用其 Azure AD 帐户自动登录到 Voyance（单一登录）
- 可以在一个中心位置（即 Azure 门户）管理帐户

如需了解有关 SaaS 应用与 Azure AD 集成的详细信息，请参阅 [Azure Active Directory 的应用程序访问与单一登录是什么](../manage-apps/what-is-single-sign-on.md)。

## <a name="prerequisites"></a>先决条件

若要配置 Azure AD 与 Voyance 的集成，需要以下项：

- Azure AD 订阅
- 已启用 Voyance 单一登录的订阅

> [!NOTE]
> 为了测试本教程中的步骤，我们不建议使用生产环境。

测试本教程中的步骤应遵循以下建议：

- 除非必要，请勿使用生产环境。
- 如果没有 Azure AD 试用环境，可以[获取一个月的试用版](https://azure.microsoft.com/pricing/free-trial/)。

## <a name="scenario-description"></a>方案描述
在本教程中，将在测试环境中测试 Azure AD 单一登录。 本教程中概述的方案包括两个主要构建基块：

1. 从库中添加 Voyance
1. 配置和测试 Azure AD 单一登录

## <a name="adding-voyance-from-the-gallery"></a>从库中添加 Voyance
要配置 Voyance 与 Azure AD 的集成，需要从库中将 Voyance 添加到托管 SaaS 应用列表。

**若要从库中添加 Voyance，请执行以下步骤：**

1. 在 **[Azure 门户](https://portal.azure.com)** 的左侧导航面板中，单击“Azure Active Directory”图标。 

    ![“Azure Active Directory”按钮][1]

1. 导航到“企业应用程序”。 然后转到“所有应用程序”。

    ![“企业应用程序”边栏选项卡][2]
    
1. 若要添加新应用程序，请单击对话框顶部的“新建应用程序”按钮。

    ![“新建应用程序”按钮][3]

1. 在搜索框中键入“Voyance”，在结果面板中选择“Voyance”，然后单击“添加”按钮添加该应用程序。

    ![结果列表中的 Voyance](./media/voyance-tutorial/tutorial_voyance_addfromgallery.png)

## <a name="configure-and-test-azure-ad-single-sign-on"></a>配置和测试 Azure AD 单一登录

在本部分中，将基于名为“Britta Simon”的测试用户使用 Voyance 配置和测试 Azure AD 单一登录。

若要运行单一登录，Azure AD 需要知道与 Azure AD 用户相对应的 Voyance 用户。 换句话说，需要在 Azure AD 用户与 Voyance 中相关用户之间建立链接关系。

可通过将 Azure AD 中“用户名”的值指定为 Voyance 中“用户名”的值来建立链接关系。

若要配置和测试 Voyance 的 Azure AD 单一登录，需要完成以下构建基块：

1. **[配置 Azure AD 单一登录](#configure-azure-ad-single-sign-on)** - 使用户能够使用此功能。
1. **[创建 Azure AD 测试用户](#create-an-azure-ad-test-user)** - 使用 Britta Simon 测试 Azure AD 单一登录。
1. **[创建 Voyance 测试用户](#create-a-voyance-test-user)** - 在 Voyance 中创建 Britta Simon 的对应用户，并将其链接到该用户的 Azure AD 表示形式。
1. **[分配 Azure AD 测试用户](#assign-the-azure-ad-test-user)** - 使 Britta Simon 能够使用 Azure AD 单一登录。
1. **[测试单一登录](#test-single-sign-on)** - 验证配置是否正常工作。

### <a name="configure-azure-ad-single-sign-on"></a>配置 Azure AD 单一登录

在本部分中，在 Azure 门户中启用 Azure AD 单一登录，并在 Voyance 应用程序中配置单一登录。

**若要配置 Voyance 的 Azure AD 单一登录，请执行以下步骤：**

1. 在 Azure 门户中的“Voyance”应用程序集成页上，单击“单一登录”。

    ![配置单一登录链接][4]

1. 在“单一登录”对话框中，选择“基于 SAML 的单一登录”作为“模式”以启用单一登录。
 
    ![“单一登录”对话框](./media/voyance-tutorial/tutorial_voyance_samlbase.png)

1. 在“Voyance 域和 URL”部分中，如果要在“IDP”发起的模式下配置应用程序，请执行以下步骤：

    ![IDP 的 Voyance 域和 URL 单一登录信息](./media/voyance-tutorial/tutorial_voyance_url1.png)

    a. 在“标识符”文本框中，使用以下模式键入 URL：`https://<companyname>.nyansa.com`

    b. 在 **“回复 URL”** 文本框中，使用以下模式键入 URL：`https://<companyname>.nyansa.com/saml/create/`

1. 如果要在 SP 发起的模式下配置应用程序，请选中“显示高级 URL 设置”，并执行以下步骤：

    ![SP 的 Voyance 域和 URL 单一登录信息](./media/voyance-tutorial/tutorial_voyance_url2.png)

    在“登录 URL”文本框中，使用以下模式键入 URL： `https://<companyname>.nyansa.com/`
     
    > [!NOTE] 
    > 这些不是实际值。 请使用实际的“标识符”、“回复 URL”和“登录 URL”更新这些值。 请联系 [Voyance 客户支持团队](mailto:support@nyansa.com)，获取这些值。 

1. 在“SAML 签名证书”部分中，单击“证书(base64)”，并在计算机上保存证书文件。

    ![证书下载链接](./media/voyance-tutorial/tutorial_voyance_certificate.png) 

1. 单击“保存”按钮。

    ![配置单一登录“保存”按钮](./media/voyance-tutorial/tutorial_general_400.png)
    
1. 在“Voyance 配置”部分，单击“配置 Voyance”打开“配置登录”窗口。 从“快速参考”部分中复制“SAML 单一登录服务 URL”

    ![Voyance 配置](./media/voyance-tutorial/tutorial_voyance_configure.png) 

1. 在另一个 Web 浏览器窗口中，以管理员身份登录 Voyance 租户。

1. 转到导航栏的右上角，单击称为“Acme University”的下拉列表。
    
    ![在应用端配置单一登录（Acme University）](./media/voyance-tutorial/tutorial_voyance_001.png) 

1. 单击“管理员设置”。

    ![在应用端配置单一登录（管理员设置）](./media/voyance-tutorial/tutorial_voyance_002.png)

1. 单击“用户访问”选项卡。

    ![在应用端配置单一登录（用户权限）](./media/voyance-tutorial/tutorial_voyance_003.png)

1. 单击“已禁用 SSO”按钮，使用 SAML 2.0 将 Azure AD 配置为 IdP。

    ![在应用端配置单一登录（“已禁用 SSO”按钮）](./media/voyance-tutorial/tutorial_voyance_004.png)

1. 转到“SAML v2”部分，并执行以下步骤：

    ![在应用端配置单一登录（SAML v2）](./media/voyance-tutorial/tutorial_voyance_005.png)
    
    a. 选择“启用”。
    
    b. 将从 Azure 门户复制的“SAML 单一登录服务 URL”粘贴到“IdP 登录 URL”文本框中。

    c. 在记事本中打开下载的 Base64 编码证书，将其内容复制到剪贴板，并粘贴到“IdP 证书”文本框中。
    
    d. 单击“ **保存**”。

> [!TIP]
> 之后在设置应用时，就可以在 [Azure 门户](https://portal.azure.com)中阅读这些说明的简明版本了！  从“Active Directory”>“企业应用程序”部分添加此应用后，只需单击“单一登录”选项卡，即可通过底部的“配置”部分访问嵌入式文档。 可在此处阅读有关嵌入式文档功能的详细信息：[ Azure AD 嵌入式文档]( https://go.microsoft.com/fwlink/?linkid=845985)


### <a name="create-an-azure-ad-test-user"></a>创建 Azure AD 测试用户

本部分的目的是在 Azure 门户中创建名为 Britta Simon 的测试用户。

![创建 Azure AD 测试用户][100]

**若要在 Azure AD 中创建测试用户，请执行以下步骤：**

1. 在 **Azure 门户**的左侧导航窗格中，单击“Azure Active Directory”图标。

    ![“Azure Active Directory”按钮](./media/voyance-tutorial/create_aaduser_01.png) 

1. 若要显示用户列表，请转到“用户和组”，单击“所有用户”。
    
    ![“用户和组”以及“所有用户”链接](./media/voyance-tutorial/create_aaduser_02.png) 

1. 若要打开“用户”对话框，请在对话框顶部单击“添加”。
 
    ![“添加”按钮](./media/voyance-tutorial/create_aaduser_03.png) 

1. 在“用户”对话框页上，执行以下步骤：
 
    ![“用户”对话框](./media/voyance-tutorial/create_aaduser_04.png) 

    a. 在“名称”文本框中，键入 **BrittaSimon**。

    b. 在“用户名”文本框中，键入 BrittaSimon 的“电子邮件地址”。

    c. 选择“显示密码”并记下“密码”的值。

    d. 单击“创建”。
 
### <a name="create-a-voyance-test-user"></a>创建 Voyance 测试用户

本部分的目的是在 Voyance 中创建名为“Britta Simon”的用户。 Voyance 支持在默认情况下启用的实时预配。 此部分不存在任何操作项。 尝试访问 Voyance 期间，如果该用户尚不存在，则将创建一个新用户。

>[!NOTE]
>如果需要手动创建用户，则需联系 [Voyance 支持团队](maiLto:support@nyansa.com)。

### <a name="assign-the-azure-ad-test-user"></a>分配 Azure AD 测试用户

在本部分中，通过授予 Britta Simon 访问 Voyance 的权限，允许使用 Azure 单一登录。

![分配用户角色][200]

**要将 Britta Simon 分配到 Voyance，请执行以下步骤：**

1. 在 Azure 门户中打开应用程序视图，导航到目录视图，接着转到“企业应用程序”，并单击“所有应用程序”。

    ![分配用户][201] 

1. 在应用程序列表中，选择“Voyance”。

    ![应用程序列表中的 Voyance 链接](./media/voyance-tutorial/tutorial_voyance_app.png) 

1. 在左侧菜单中，单击“用户和组”。

    ![“用户和组”链接][202]

1. 单击“添加”按钮。 然后在“添加分配”对话框中选择“用户和组”。

    ![“添加分配”窗格][203]

1. 在“用户和组”对话框的“用户”列表中，选择“Britta Simon”。

1. 在“用户和组”对话框中单击“选择”按钮。

1. 在“添加分配”对话框中单击“分配”按钮。
    
### <a name="test-single-sign-on"></a>测试单一登录

在本部分中，使用访问面板测试 Azure AD 单一登录配置。

单击访问面板中的“Voyance”磁贴时，用户应自动登录到 Voyance 应用程序。

## <a name="additional-resources"></a>其他资源

* [有关如何将 SaaS 应用与 Azure Active Directory 集成的教程列表](tutorial-list.md)
* [什么是使用 Azure Active Directory 的应用程序访问和单一登录？](../manage-apps/what-is-single-sign-on.md)

<!--Image references-->

[1]: ./media/voyance-tutorial/tutorial_general_01.png
[2]: ./media/voyance-tutorial/tutorial_general_02.png
[3]: ./media/voyance-tutorial/tutorial_general_03.png
[4]: ./media/voyance-tutorial/tutorial_general_04.png

[100]: ./media/voyance-tutorial/tutorial_general_100.png

[200]: ./media/voyance-tutorial/tutorial_general_200.png
[201]: ./media/voyance-tutorial/tutorial_general_201.png
[202]: ./media/voyance-tutorial/tutorial_general_202.png
[203]: ./media/voyance-tutorial/tutorial_general_203.png

