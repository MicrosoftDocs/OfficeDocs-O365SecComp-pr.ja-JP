---
title: 配信された悪意のある電子メールを検索して調査する (Office 365 の脅威の調査と応答
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 脅威の調査と応答機能を使用して、悪意のある電子メールを検索して調査する方法について説明します。
ms.openlocfilehash: 7e2cef742339e54c094cfb0c3b32fbf596896a3d
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408302"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-advanced-threat-protection-plan-2"></a>配信された悪意のある電子メールを検索して調査する (Office 365 Advanced Threat Protection プラン 2)

[Office 365 Advanced Threat Protection](office-365-atp.md)を使用すると、ユーザーが危険にさらされ、組織を保護するアクションを実行するアクティビティを調査できます。 たとえば、組織のセキュリティチームに属している場合は、ユーザーに配信された不審な電子メールメッセージを見つけて調査することができます。 これを行うには、[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)を使用します。
  
## <a name="before-you-begin"></a>開始する前に

次の要件が満たされていることを確認してください。
  
- 組織に[Office 365 Advanced Threat Protection](office-365-atp.md) (プラン1またはプラン 2) があり、[ライセンスがユーザーに割り当てら](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)れている。
    
- [Office 365 監査ログ](turn-audit-log-search-on-or-off.md)は、組織に対して有効になっています。 
    
- 組織には、スパム対策、マルウェア対策、フィッシング対策などに対して定義されたポリシーがあります。 「 [Office 365 の脅威から保護](protect-against-threats.md)する」を参照してください。
    
- Office 365 の全体管理者であるか、セキュリティ管理者、またはセキュリティ&amp;コンプライアンスセンターで割り当てられている検索および削除の役割を持っているかどうか。 「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可」を](permissions-in-the-security-and-compliance-center.md)参照してください。
    
## <a name="dealing-with-suspicious-emails"></a>疑わしいメールの処理

悪意のある攻撃者は、ユーザーにメールを送信して、自分の資格情報をフィッシングし、会社の機密情報にアクセスできるようにすることができます。 これを防止するには、Office 365 で提供されている脅威保護サービス ( [Exchange Online protection](eop/exchange-online-protection-overview.md)や[Advanced threat protection](office-365-atp.md)など) を使用する必要があります。 ただし、攻撃者が URL を含むユーザーにメールを送信し、その URL を後で悪意のあるコンテンツ (マルウェアなど) に対して使用する場合があります。 または、組織内のユーザーが侵害され、そのユーザーが侵害されたときに、そのアカウントを使用して社内の他のユーザーに電子メールを送信したことがあります。 これらのシナリオの両方をクリーンアップする際に、ユーザーの受信トレイから電子メールメッセージを削除することが必要な場合があります。 このような状況では、[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)を活用して、それらの電子メールメッセージを見つけて削除することができます。
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>配信された疑わしいメールを見つけて削除する

> [!TIP]
> 脅威エクスプローラー (エクスプローラーとも呼ばれます) は、メッセージの検索と削除、悪意のある電子メールの送信者の IP アドレスの識別、さらなる調査のためのインシデントの開始など、複数の目的で利用できる強力なレポートです。 次の手順では、エクスプローラーを使用して受信者のメールボックスから悪意のある電子メールを検索し、削除する方法を説明します。 
  
1. に[https://protection.office.com](https://protection.office.com)移動して、Office 365 の職場または学校のアカウントを使用してサインインします。 これにより、セキュリティ&amp;コンプライアンスセンターに移動します。 
    
2. 左側のナビゲーションで、[**脅威管理** \> **エクスプローラー**] を選択します。
    
3. [表示] メニューの [**すべての電子メール**] をクリックします。<br/>![[表示] メニューを使用して電子メールとコンテンツレポートを選択する](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. レポートに表示されるラベル (**配信**済み、**不明**、**迷惑メール**など) に注目してください。<br/>![すべての電子メールのデータが表示されている脅威エクスプローラー](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>(組織の電子メールメッセージに対して実行されたアクションによっては、**ブロック**されたり**置き換えら**れたりするなど、他のラベルが表示される場合があります)。
    
5. レポートで、[**配信**済み] を選択して、ユーザーの受信トレイに終了した電子メールのみを表示します。<br/>![[迷惑メールに配信済み] をクリックすると、そのデータがビューから削除されます。](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. グラフの下にある、グラフの下にある**電子メール**リストを確認します。<br/>![グラフの下に、検出された電子メールメッセージの一覧を表示します。](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. リストで、その電子メールメッセージの詳細を表示するアイテムを選択します。 たとえば、件名行をクリックして、送信者、受信者、添付ファイル、その他の同様の電子メールメッセージに関する情報を表示することができます。<br/>![詳細および添付ファイルを含む、アイテムに関する追加情報を表示できます。](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. 電子メールメッセージに関する情報を表示した後、リスト内の1つ以上のアイテムを選択して、 **+ アクション**をアクティブ化します。
    
9. [ **+ アクション**] リストを使用して、[**削除済みアイテムに移動する**] などのアクションを適用します。 これにより、選択したメッセージが受信者のメールボックスから削除されます。<br/>![1つまたは複数の電子メールメッセージを選択する場合は、いくつかの使用可能なアクションから選択できます。](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
## <a name="related-topics"></a>関連項目

[Office 365 Advanced Threat Protection プラン2](office-365-ti.md)
  
[Office 365 で脅威から保護する](protect-against-threats.md)
  
[Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)
  

