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
# <a name="isolation-and-access-control-in-azure-active-directory"></a>Azure Active Directory での分離とアクセス制御

Azure Active Directory は、論理的なデータ分離による安全性の高い方法で複数のテナントをホストするために設計されました。Azure Active Directory へのアクセスは、承認、レイヤーで区切られています。Azure Active Directory では、コンテンツのアクセスできないかまたは、共同テナントによって侵害されるようにお客様のコンテンツを保護するセキュリティの境界としてテナントのコンテナーを使用しているユーザーを分離します。Azure Active Directory の認証のレイヤーでは、次の 3 つのチェックが実行されます。
- Azure Active Directory のテナントにアクセスするため、プリンシパルが有効ですか。
- このテナントのデータにアクセスするため、プリンシパルが有効ですか。
- 主体の役割は、要求されたデータ アクセスの種類を許可するこのテナントのですか。

アプリケーション、ユーザー、サーバー、またはサービスにアクセスできません Azure Active Directory に適切な認証とトークンや証明書。適切な資格情報が伴わないしない場合、要求は拒否されます。

実際には、Azure Active Directory は、ポリシーとだけ所有し、テナントによって管理されているコンテナー内でアクセス許可と、自身の保護されたコンテナー内の各テナントをホストします。
 
![Azure のコンテナー](media/office-365-isolation-azure-container.png)

テナント コンテナーという概念が深く根深いに永続的なストレージ ・ ポータルからのすべてのレイヤーにあるディレクトリ サービスで。Azure Active Directory のテナントの複数のメタデータは、同じ物理ディスクに保存されている場合にも関係がまったく存在にテナントの管理者によって指定されるディレクトリ サービスで定義されている以外のコンテナー間で。必要があります直接接続 Azure Active Directory の記憶域からの要求元のアプリケーションや承認レイヤーを経由しないでサービスです。

次の例では、contoso 社と fabrikam 社、独立した専用のコンテナーがありが独立して、互いから分離しで区切られても、それらのコンテナーなど、サーバとストレージの同じ基になるインフラストラクチャの一部を共有する場合があります。承認とアクセス制御のレイヤーです。
 
![Azure の専用コンテナー](media/office-365-isolation-azure-dedicated-containers.png)

さらに、Azure Active Directory 内から実行可能なアプリケーションのコンポーネントがないと、1 つのテナントを強制的に他のテナントの整合性に違反、他のテナントの暗号化キーへのアクセスやサーバーからの生データを読み取ることはできません。

既定では、Azure Active Directory は、他のテナントのユーザーによって発行されたすべての操作を禁止します。各テナントは、クレーム ベースのアクセス コントロールを Azure Active Directory 内で論理的に分離されます。読み取りと書き込みディレクトリ データがテナントのコンテナーのスコープし、セキュリティの境界としてテナントを一緒に強制する内部の抽象レイヤーと、役割ベースのアクセス制御 (RBAC) レイヤーで区切られています。これらのレイヤーをすべてのディレクトリ データのアクセス要求が処理され、Office 365 内のすべてのアクセス要求で上記のロジックによって制限します。

Azure Active Directory には、北アメリカ、米国政府、欧州連合 (ドイツ)、および World Wide のパーティションがあります。テナントは、1 つのパーティションに存在して、パーティションは、複数のテナントを含めることができます。パーティションの情報は、ユーザーから抽象化します。(その中のすべてのテナントを含む) の指定されたパーティションは、複数のデータ センターに複製されます。テナントのパーティションは、テナント (国コードなど) のプロパティに基づいて選択されます。機密情報と各パーティション内の他の機密情報は、専用のキーで暗号化されます。キーは、新しいパーティションが作成されると自動的に生成されます。

Azure Active Directory システムの機能は、ユーザー セッションごとに一意のインスタンスです。さらに、Azure Active Directory は、承認されていないと想定外の情報の転送を防ぐためにネットワーク レベルでの共有システム リソースの分離を提供するのに暗号化テクノロジを使用します。
