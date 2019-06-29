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
ms.openlocfilehash: 5f8c615bed07b75cd3c06ec48f5ba73586f0f6d5
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394292"
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

悪意のある攻撃者は、ユーザーにメールを送信して、自分の資格情報をフィッシングし、会社の機密情報にアクセスできるようにすることができます。 これを回避するには、 [Exchange Online protection](eop/exchange-online-protection-overview.md)や[Advanced threat Protection](office-365-atp.md)などの Office 365 の脅威保護サービスを使用する必要があります。 ただし、攻撃者が URL を含むユーザーにメールを送信し、その URL を後で悪意のあるコンテンツ (マルウェアなど) に対して使用する場合があります。 または、組織内のユーザーが侵害されていて、そのユーザーが侵害されている間に、攻撃者がそのアカウントを使用して社内の他のユーザーに電子メールを送信していることにも気付きます。 これらのシナリオの両方をクリーンアップする際に、ユーザーの受信トレイから電子メールメッセージを削除することが必要な場合があります。 このような状況では、[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)を活用して、それらの電子メールメッセージを見つけて削除することができます。

## <a name="where-re-routed-emails-are-located-after-actions-are-taken"></a>再ルーティングされたメールは、アクションの実行後に配置されます。

脅威エクスプローラーのリアルタイム検出によって、配信状況の場所に [配信アクション] フィールドと [配信場所] フィールドが追加されました。 これにより、メールがどこにあるかをより完全に把握できます。 この変更の目的の一環として、セキュリティを確保したユーザーを探しやすくしていますが、最終的に問題のあるメールの場所がひとめでわかることになります。

配信状態は、次の2つの列に分けられました。

- **配信アクション**-この電子メールの状態は何ですか。
- **配信場所**-この電子メールは、結果としてルーティングされましたか?

配信アクションは、既存のポリシーまたは検出のために電子メールに対して実行されたアクションです。 電子メールで実行可能なアクションは次のとおりです。

1. **配信**済み–電子メールはユーザーの受信トレイまたはフォルダーに配信され、ユーザーは直接アクセスできます。
2. **Junked** –電子メールがユーザーの迷惑メールフォルダーまたは削除されたフォルダーに送信され、ユーザーは迷惑メールまたは削除されたフォルダー内のメールにアクセスできる。
3. [**ブロック**済み] –検疫済み、失敗、または削除されたすべての電子メール。 ユーザーが完全にアクセスすることはできません。
4. [**置換**] –悪意のある添付ファイルが、添付ファイルが悪意のあるファイルに置き換えられた場合の電子メール。
 
[配信場所] には、配信後に実行されるポリシーと検出の結果が表示されます。 配信アクションにリンクされています。 このフィールドは、問題のメールが検出されたときに実行される処理を把握するために追加されました。 配信場所の指定可能な値は次のとおりです。

1. **受信トレイまたはフォルダー** –電子メールは、受信トレイまたはフォルダー (メールルールに従って) にあります。
2. **オンプレミスまたは外部**–メールボックスがクラウド上に存在していますが、オンプレミスになっています。
3. **[迷惑**メール] フォルダー–ユーザーの [迷惑メール] フォルダーにあるメール。
4. **削除済みアイテムフォルダー** –ユーザーの [削除済みアイテム] フォルダー内の電子メール。
5. **検疫**–検疫内の電子メール。ユーザーのメールボックスには含まれません。
6. **Failed** –メールがメールボックスに到達できませんでした。
7. **削除**-電子メールはメールフローのどこかに失われます。
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>配信された疑わしいメールを見つけて削除する

> [!TIP]
> 脅威エクスプローラー (エクスプローラーとも呼ばれます) は、メッセージの検索と削除、悪意のある電子メールの送信者の IP アドレスの識別、さらなる調査のためのインシデントの開始など、複数の目的で利用できる強力なレポートです。 次の手順では、エクスプローラーを使用して受信者のメールボックスから悪意のある電子メールを検索し、削除する方法を説明します。

以前の配信状態フィールドへの変更を確認するには (現在、配信アクションと配信場所): 

1. に[https://protection.office.com](https://protection.office.com)移動して、Office 365 の職場または学校のアカウントを使用してサインインします。 これにより、セキュリティ&amp;コンプライアンスセンターに移動します。 
    
2. 左側のナビゲーションで、[**脅威管理** \> **エクスプローラー**] を選択します。

![脅威エクスプローラーのスクリーンショット。](media/Threat Explorer Delivery Action and Delivery Location.PNG)

<!--Comment>
    
3. In the View menu, choose **All email**.<br/>![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
4. Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.<br/>![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)<br/>(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)
    
5. In the report, choose **Delivered** to view only emails that ended up in users' inboxes.<br/>![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
6. Below the chart, review the **Email** list below the chart.<br/>![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
7. In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.<br/>![You can view additional information about an item, including details and any attachments](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. After viewing information about email messages, select one or more items in the list to activate **+ Actions**.
    
9. Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This will delete the selected messages from the recipients' mailboxes.<br/>![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)
  
-->
## <a name="related-topics"></a>関連項目

[Office 365 Advanced Threat Protection プラン2](office-365-ti.md)
  
[Office 365 で脅威から保護する](protect-against-threats.md)
  
[Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)
  

