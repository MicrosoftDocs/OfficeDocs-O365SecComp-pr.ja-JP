---
title: セキュリティ&amp;コンプライアンスセンターと Exchange 管理センターの間で DLP がどのように機能するか
ms.author: stephow
author: stephow-msft
manager: laurawi
ms.date: 8/4/2017
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: セキュリティ&amp; /コンプライアンスセンターの dlp が、Exchange 管理センターの dlp およびトランスポートルールとどのように連動するかについて説明します。
ms.openlocfilehash: 531a45308594d03dc219f50d989a08236b8b5e20
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215647"
---
# <a name="how-dlp-works-between-the-security-amp-compliance-center-and-exchange-admin-center"></a>セキュリティ&amp;コンプライアンスセンターと Exchange 管理センターの間で DLP がどのように機能するか

Office 365 では、2つの異なる管理センターでデータ損失防止 (DLP) ポリシーを作成できます。
  
- ** &amp;セキュリティ/コンプライアンスセンター**では、SharePoint、OneDrive、および Exchange のコンテンツを保護するための単一の DLP ポリシーを作成できます。可能な場合は、ここで DLP ポリシーを作成することをお勧めします。詳細については、 [ &amp;セキュリティ/コンプライアンスセンター](data-loss-prevention-policies.md)の「DLP」を参照してください。
    
- **exchange 管理センター**では、exchange でのみコンテンツを保護できる DLP ポリシーを作成できます。このポリシーでは、Exchange トランスポートルールを使用できます。そのため、電子メールの処理に固有のオプションがあります。詳細については、「 [Exchange 管理センターでの DLP](https://go.microsoft.com/fwlink/?linkid=852311)」を参照してください。
    
これらの管理センターで作成された DLP ポリシーは、並行して機能します。このトピックでは、その方法について説明します。
  
![セキュリティ/コンプライアンスセンターと Exchange 管理センターの DLP ページ](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security-amp-compliance-center-works-with-dlp-and-transport-rules-in-the-exchange-admin-center"></a>セキュリティ&amp; /コンプライアンスセンターの dlp が Exchange 管理センターの dlp およびトランスポートルールとどのように連動するか

セキュリティ&amp; /コンプライアンスセンターで DLP ポリシーを作成すると、ポリシーに含まれるすべての場所にポリシーが展開されます。ポリシーに exchange Online が含まれている場合は、exchange 管理センターで作成された DLP ポリシーとまったく同じ方法でポリシーが同期され、適用されます。 
  
Exchange 管理センターで DLP ポリシーを作成した場合、これらのポリシーは、セキュリティ&amp;コンプライアンスセンターで作成した電子メールのポリシーと共に引き続き機能します。ただし、Exchange 管理センターで作成したルールは優先されることに注意してください。最初にすべての Exchange トランスポートルールが処理され、次にセキュリティ&amp;コンプライアンスセンターの DLP ルールが処理されます。
  
これは、次のことを意味します。
  
- Exchange トランスポートルールによってブロックされているメッセージは、セキュリティ&amp;コンプライアンスセンターで作成された DLP ルールによってスキャンされません。
    
- Exchange トランスポートルールによって、外部ユーザーの追加など、セキュリティ&amp;コンプライアンスセンターの dlp ポリシーに一致するようにメッセージが変更された場合、dlp ルールによって検出され、必要に応じてポリシーが適用されます。
    
また、"stop 処理" アクションを使用する Exchange トランスポートルールは、セキュリティ&amp;コンプライアンスセンターの DLP ルールの処理には影響しません。ただし、処理は続行されます。
  
## <a name="policy-tips-in-the-security-amp-compliance-center-vs-the-exchange-admin-center"></a>セキュリティ&amp; /コンプライアンスセンターおよび Exchange 管理センターのポリシーヒント

ポリシーヒントは、Exchange 管理センターで作成された dlp ポリシーとメールフロールール、またはセキュリティ&amp; /コンプライアンスセンターで作成された dlp ポリシーによって機能しますが、両方を使用することはできません。これは、これらのポリシーが異なる場所に格納されているため、ポリシーヒントは1つの場所からのみ描画できるからです。
  
exchange 管理センターでポリシーヒントを構成した場合は、セキュリティ&amp; /コンプライアンスセンターで設定したポリシーヒントは、outlook on the web および outlook 2013 以降のユーザーには表示されません。そのためには、exchange 管理センターのヒントをオフにします。これにより、セキュリティ&amp;コンプライアンスセンターへの切り替えを選択するまでは、現在の Exchange トランスポートルールが引き続き機能します。
  
ポリシーヒントは1つの場所からしか描画できませんが、セキュリティ&amp;コンプライアンスセンターと Exchange 管理センターの両方で DLP ポリシーを使用している場合でも、電子メール通知は常に送信されることに注意してください。
  

