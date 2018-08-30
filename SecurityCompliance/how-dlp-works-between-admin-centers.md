---
title: セキュリティと DLP のしくみ&amp;コンプライアンス センターおよび Exchange 管理センター
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 学習方法セキュリティの DLP&amp;コンプライアンス センターは、Exchange 管理センターで DLP とトランスポートの規則で動作します。
ms.openlocfilehash: bc7494f504c2c0ffa668562d6e64b9f29992e24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532426"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a>セキュリティと DLP のしくみ&amp;コンプライアンス センターおよび Exchange 管理センター

、Office 365 では、2 つの異なる管理センターでのデータ損失防止 (DLP) ポリシーを作成できます。
  
- **セキュリティ&amp;コンプライアンス センター**、SharePoint、OneDrive、および Exchange のコンテンツを保護するために 1 つの DLP ポリシーを作成することができます。可能であれば、ここでは、DLP ポリシーを作成することをお勧めします。詳細についてを参照してください[セキュリティの DLP&amp;コンプライアンス センター](data-loss-prevention-policies.md)です。
    
- **Exchange 管理センター**では、Exchange でのみコンテンツを保護するための DLP ポリシーを作成できます。このポリシーは、電子メールを処理する特定その他のオプションがあるために、Exchange のトランスポート ルールを使用できます。詳細については、 [Exchange 管理センターで DLP](https://go.microsoft.com/fwlink/?linkid=852311)を参照してください。
    
DLP ポリシー センターの機能を並べてこのトピックで説明をこれらの管理ツールで作成する方法です。
  
![セキュリティおよびコンプライアンス センターや Exchange 管理センターで DLP のページ](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a>どのようにセキュリティの DLP&amp;コンプライアンス センターは、Exchange 管理センターでの DLP とトランスポート ルールと連携

セキュリティで DLP ポリシーを作成した後&amp;コンプライアンス センターでは、ポリシーのすべてのポリシーに含まれている場所に配置します。Exchange Online にポリシーが含まれている場合ポリシーのある同期し、Exchange 管理センターで作成した DLP ポリシーとまったく同じ方法で適用されます。 
  
DLP ポリシーを作成したら、Exchange 管理センターで、これらのポリシーが引き続きすべてのポリシー、セキュリティで作成した電子メールの密接に共同作業&amp;コンプライアンス センターです。Exchange 管理センターで作成されたルールの優先順位に注意してください。すべての Exchange トランスポート ルールが最初に処理し、セキュリティの規則を DLP&amp;コンプライアンス センターで処理されます。
  
これは、ことを意味します。
  
- Exchange トランスポート ルールによってブロックされているメッセージは DLP ルールの作成で、セキュリティでスキャンされることはありません&amp;コンプライアンス センターです。
    
- Exchange トランスポート ルールが、セキュリティでは、DLP ポリシーに一致するようにメッセージを変更するかどうかは&amp;コンプライアンス センター]-[外部のユーザーには、DLP の規則はこれを検出し、必要に応じてポリシーを適用するを追加するなど。
    
」の処理を停止する] アクションを使用するトランスポート ルールを Exchange が DLP の処理に影響しないが、セキュリティの規則も&amp;コンプライアンス センター - それらはまだ処理します。
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a>ポリシーのセキュリティのヒント&amp;Exchange 管理センターとコンプライアンス センター

ポリシー ヒントは DLP ポリシーのいずれかで作業し、メール フロー ルールが Exchange 管理センターで、またはセキュリティで作成した DLP ポリシーを作成した&amp;コンプライアンス ・ センターが、両方です。これは、これらのポリシーが別の場所に格納されているポリシーのヒントは、1 つの場所からのみ描画できるためです。
  
Exchange 管理センターでセキュリティを構成するすべてのポリシー ヒントのポリシー ヒントを構成したかどうかは&amp;コンプライアンス センターは、web 上の Outlook と Outlook 2013 および Exchange 管理センターでのヒントをオフにするまでは、後でユーザーに表示されません。こうと、現在の Exchange トランスポート ルールは、セキュリティに切り替えるときに選択するまでの作業を引き続き&amp;コンプライアンス センターです。
  
ポリシーのヒントは、1 つの場所からのみ描画できるときに電子メール通知を常に送信される、両方のセキュリティでは、DLP ポリシーを使用している場合でも&amp;コンプライアンス センターと、Exchange 管理センターです。
  

