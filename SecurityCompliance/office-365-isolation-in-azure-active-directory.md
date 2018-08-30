---
title: Office 365 の分離と Azure Active Directory のアクセス制御
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: Azure Active Directory 内で分離し、アクセス制御の操作方法です。'
ms.openlocfilehash: db4fa0d026c6c608f09252c65bf1e0de5354f68c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532677"
---
# <a name="isolation-and-access-control-in-azure-active-directory"></a><span data-ttu-id="acf1b-103">Azure Active Directory での分離とアクセス制御</span><span class="sxs-lookup"><span data-stu-id="acf1b-103">Isolation and Access Control in Azure Active Directory</span></span>

<span data-ttu-id="acf1b-p101">Azure Active Directory は、論理的なデータ分離による安全性の高い方法で複数のテナントをホストするために設計されました。Azure Active Directory へのアクセスは、承認、レイヤーで区切られています。Azure Active Directory では、コンテンツのアクセスできないかまたは、共同テナントによって侵害されるようにお客様のコンテンツを保護するセキュリティの境界としてテナントのコンテナーを使用しているユーザーを分離します。Azure Active Directory の認証のレイヤーでは、次の 3 つのチェックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="acf1b-p101">Azure Active Directory was designed to host multiple tenants in a highly secure way through logical data isolation. Access to Azure Active Directory is gated by an authorization layer. Azure Active Directory isolates customers using tenant containers as security boundaries to safeguard a customer's content so that the content cannot be accessed or compromised by co-tenants. Three checks are performed by Azure Active Directory's authorization layer:</span></span>
- <span data-ttu-id="acf1b-108">Azure Active Directory のテナントにアクセスするため、プリンシパルが有効ですか。</span><span class="sxs-lookup"><span data-stu-id="acf1b-108">Is the principal enabled for access to Azure Active Directory tenant?</span></span>
- <span data-ttu-id="acf1b-109">このテナントのデータにアクセスするため、プリンシパルが有効ですか。</span><span class="sxs-lookup"><span data-stu-id="acf1b-109">Is the principal enabled for access to data in this tenant?</span></span>
- <span data-ttu-id="acf1b-110">主体の役割は、要求されたデータ アクセスの種類を許可するこのテナントのですか。</span><span class="sxs-lookup"><span data-stu-id="acf1b-110">Is the principal's role in this tenant authorized for the type of data access requested?</span></span>

<span data-ttu-id="acf1b-p102">アプリケーション、ユーザー、サーバー、またはサービスにアクセスできません Azure Active Directory に適切な認証とトークンや証明書。適切な資格情報が伴わないしない場合、要求は拒否されます。</span><span class="sxs-lookup"><span data-stu-id="acf1b-p102">No application, user, server, or service can access Azure Active Directory without the proper authentication and token or certificate. Requests are rejected if they are not accompanied by proper credentials.</span></span>

<span data-ttu-id="acf1b-113">実際には、Azure Active Directory は、ポリシーとだけ所有し、テナントによって管理されているコンテナー内でアクセス許可と、自身の保護されたコンテナー内の各テナントをホストします。</span><span class="sxs-lookup"><span data-stu-id="acf1b-113">Effectively, Azure Active Directory hosts each tenant in its own protected container, with policies and permissions to and within the container solely owned and managed by the tenant.</span></span>
 
![Azure のコンテナー](media/office-365-isolation-azure-container.png)

<span data-ttu-id="acf1b-p103">テナント コンテナーという概念が深く根深いに永続的なストレージ ・ ポータルからのすべてのレイヤーにあるディレクトリ サービスで。Azure Active Directory のテナントの複数のメタデータは、同じ物理ディスクに保存されている場合にも関係がまったく存在にテナントの管理者によって指定されるディレクトリ サービスで定義されている以外のコンテナー間で。必要があります直接接続 Azure Active Directory の記憶域からの要求元のアプリケーションや承認レイヤーを経由しないでサービスです。</span><span class="sxs-lookup"><span data-stu-id="acf1b-p103">The concept of tenant containers is deeply ingrained in the directory service at all layers, from portals all the way to persistent storage. Even when multiple Azure Active Directory tenant metadata is stored on the same physical disk, there is no relationship between the containers other than what is defined by the directory service, which in turn is dictated by the tenant administrator. There can be no direct connections to Azure Active Directory storage from any requesting application or service without first going through the authorization layer.</span></span>

<span data-ttu-id="acf1b-118">次の例では、contoso 社と fabrikam 社、独立した専用のコンテナーがありが独立して、互いから分離しで区切られても、それらのコンテナーなど、サーバとストレージの同じ基になるインフラストラクチャの一部を共有する場合があります。承認とアクセス制御のレイヤーです。</span><span class="sxs-lookup"><span data-stu-id="acf1b-118">In the example below, Contoso and Fabrikam both have separate, dedicated containers, and even though those containers may share some of the same underlying infrastructure, such as servers and storage, they remain separate and isolated from each other, and gated by layers of authorization and access control.</span></span>
 
![Azure の専用コンテナー](media/office-365-isolation-azure-dedicated-containers.png)

<span data-ttu-id="acf1b-120">さらに、Azure Active Directory 内から実行可能なアプリケーションのコンポーネントがないと、1 つのテナントを強制的に他のテナントの整合性に違反、他のテナントの暗号化キーへのアクセスやサーバーからの生データを読み取ることはできません。</span><span class="sxs-lookup"><span data-stu-id="acf1b-120">In addition, there are no application components that can execute from within Azure Active Directory, and it is not possible for one tenant to forcibly breach the integrity of another tenant, access encryption keys of another tenant, or read raw data from the server.</span></span>

<span data-ttu-id="acf1b-p104">既定では、Azure Active Directory は、他のテナントのユーザーによって発行されたすべての操作を禁止します。各テナントは、クレーム ベースのアクセス コントロールを Azure Active Directory 内で論理的に分離されます。読み取りと書き込みディレクトリ データがテナントのコンテナーのスコープし、セキュリティの境界としてテナントを一緒に強制する内部の抽象レイヤーと、役割ベースのアクセス制御 (RBAC) レイヤーで区切られています。これらのレイヤーをすべてのディレクトリ データのアクセス要求が処理され、Office 365 内のすべてのアクセス要求で上記のロジックによって制限します。</span><span class="sxs-lookup"><span data-stu-id="acf1b-p104">By default, Azure Active Directory disallows all operations issued by identities in other tenants. Each tenant is logically isolated within Azure Active Directory through claims-based access controls. Reads and writes of directory data are scoped to tenant containers, and gated by an internal abstraction layer and a role-based access control (RBAC) layer, which together enforce the tenant as the security boundary. Every directory data access request is processed by these layers and every access request in Office 365 is policed by the logic above.</span></span>

<span data-ttu-id="acf1b-p105">Azure Active Directory には、北アメリカ、米国政府、欧州連合 (ドイツ)、および World Wide のパーティションがあります。テナントは、1 つのパーティションに存在して、パーティションは、複数のテナントを含めることができます。パーティションの情報は、ユーザーから抽象化します。(その中のすべてのテナントを含む) の指定されたパーティションは、複数のデータ センターに複製されます。テナントのパーティションは、テナント (国コードなど) のプロパティに基づいて選択されます。機密情報と各パーティション内の他の機密情報は、専用のキーで暗号化されます。キーは、新しいパーティションが作成されると自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="acf1b-p105">Azure Active Directory has North America, U.S. Government, European Union, Germany, and World Wide partitions. A tenant exists in a single partition, and partitions can contain multiple tenants. Partition information is abstracted away from users. A given partition (including all the tenants within it) is replicated to multiple datacenters. The partition for a tenant is chosen based on properties of the tenant (e.g., the country code). Secrets and other sensitive information in each partition is encrypted with a dedicated key. The keys are generated automatically when a new partition is created.</span></span>

<span data-ttu-id="acf1b-p106">Azure Active Directory システムの機能は、ユーザー セッションごとに一意のインスタンスです。さらに、Azure Active Directory は、承認されていないと想定外の情報の転送を防ぐためにネットワーク レベルでの共有システム リソースの分離を提供するのに暗号化テクノロジを使用します。</span><span class="sxs-lookup"><span data-stu-id="acf1b-p106">Azure Active Directory system functionalities are a unique instance to each user session. In addition, Azure Active Directory uses encryption technologies to provide isolation of shared system resources at the network level to prevent unauthorized and unintended transfer of information.</span></span>
