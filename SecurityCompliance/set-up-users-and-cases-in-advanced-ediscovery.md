---
title: Office 365 の高度な電子情報開示でユーザーとケースをセットアップする
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Office 365 Advanced eDiscovery でユーザーの役割を構成し、ケースを作成して、ケースにユーザーを割り当てる方法について説明します。  '
ms.openlocfilehash: 5a22e0683e49ebdaf8391e092aeb101386e0636b
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999270"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a>Office 365 の高度な電子情報開示でユーザーとケースをセットアップする

このトピックでは、Office 365 Advanced eDiscovery のユーザーおよびケースをセットアップする方法について説明します。
  
> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
## <a name="prerequisites"></a>前提条件

Advanced eDiscovery でケースとユーザーを設定する前に、次のものが必要です。
  
- Advanced eDiscovery を使用してユーザーのデータを分析するには、ユーザー (データの保管担当者) に Office365 E5 ライセンスが割り当てられている必要があります。または、Office365 E1 または E3 ライセンスを持つユーザーに Advanced eDiscovery 単体のライセンスを割り当てることもできます。ケースに割り当てられ、Advanced eDiscovery を使用してデータを分析する管理者および法令遵守責任者には E5 ライセンスは不要です。 
    
- 電子情報開示ケースを作成してメンバーを追加するには、Office 365 &amp;セキュリティコンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。 セキュリティ&amp; /コンプライアンスセンターの電子情報開示マネージャーの役割グループに自分を追加するには、Office 365 組織の全体管理者である必要があります。 全体管理者ではない場合は、電子情報開示マネージャーの役割グループに追加するように全体管理者に依頼する必要があります。 詳細については、次のトピックを参照してください。
    
  - [Microsoft 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)
    
  - [Microsoft 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a>手順 1: ユーザーに電子情報開示のアクセス許可を割り当てる

最初の手順は、ユーザーが電子情報開示ケースのメンバー &amp;として追加できるように、セキュリティコンプライアンスセンターで必要なアクセス許可をユーザーに割り当てることです。 セキュリティ&amp; /コンプライアンスセンターでユーザーをケースのメンバーとして追加すると、上級電子情報開示のケースにアクセスできるようになります。
  
電子情報開示ケースのメンバーとして追加できるように、必要なアクセス許可をユーザーに割り当てるには、 [Microsoft 365 セキュリティ&amp;コンプライアンスセンターの「電子情報開示のケース](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)」のステップ1を参照してください。
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a>手順 2: 電子情報開示ケースを作成し、メンバーを追加する

次の手順では、セキュリティ&amp;コンプライアンスセンターで新しい電子情報開示ケースを作成し、メンバーを追加します。 そのケースのメンバーは、高度な電子情報開示のケースにアクセスできるようになります。
  
1. 新しい電子情報開示ケースを作成するには、 [Microsoft 365 セキュリティ&amp;コンプライアンスセンターの「電子情報](ediscovery-cases.md#step-2-create-a-new-case)開示のケース」のステップ2を参照してください。
    
2. 電子情報開示ケースにメンバーを追加するには、 [Microsoft 365 セキュリティ&amp;コンプライアンスセンターの「電子情報開示ケース](ediscovery-cases.md#step-3-add-members-to-a-case)のステップ3」を参照してください。
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a>手順 3: 高度な電子情報開示でケースを進める

電子情報開示ケースを作成してメンバーを追加すると、そのユーザー (またはケースのメンバー) は、高度な電子情報開示で対応するケースにアクセスできるようになります。 高度な電子情報開示のケースにアクセスするには、 [Microsoft 365 セキュリティ&amp;コンプライアンスセンターの「電子情報](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery)開示のケース」の手順8を参照してください。
  
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[データの準備](prepare-data-for-advanced-ediscovery.md)
 