---
title: 迷惑メール メッセージを Microsoft に報告する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Microsoft Office Outlook 用迷惑メール報告アドインでは、次のような複数の方法で迷惑メール メッセージを報告できます。
ms.openlocfilehash: 90687c90c7594163d48dfb9bd329e7c94c25935f
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275597"
---
# <a name="report-junk-email-messages-to-microsoft"></a>迷惑メール メッセージを Microsoft に報告する

Microsoft Office Outlook 用迷惑メール報告アドインでは、次のような複数の方法で迷惑メール メッセージを報告できます。
  
- Outlook リボンから報告する
    
- 受信トレイから報告する
    
- 開いた電子メール メッセージから報告する
    
迷惑メール報告アドインは、Microsoft Exchange Online Protection (EOP) サービスにレポートを送信するために役立ちます。メールボックスがサービスによって保護されていない場合、迷惑メールのレポートを送信しても、スパム フィルターは影響を受けません。管理者は、組織全体に適用されるスパム設定についての詳細を、「[メッセージがスパムとしてマークされないようにする方法](https://go.microsoft.com/fwlink/p/?LinkId=534224)」や「[検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする (Block email spam with the Office 365 spam filter to prevent false negative issues)](https://go.microsoft.com/fwlink/p/?LinkId=534225)」で知ることができます。これらは、管理者レベルの制御権を持っている場合に、誤検知や検出漏れを防止する上で役立ちます。
  
> [!TIP]
> また、 [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com)電子メールアドレスを使用して、 [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com)の電子メールアドレスと誤検知 (非スパム) メッセージを使用して、スパムメッセージを Microsoft に直接送信することもできます。詳細については、「[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。 
  
### <a name="to-report-junk-email-messages-from-outlook"></a>Outlook から迷惑メールメッセージを報告するには

[迷惑メール報告アドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) 
  
### <a name="to-report-junk-email-messages-from-your-inbox"></a>受信トレイから迷惑メール メッセージを報告するには

1. 迷惑メールとして報告するメッセージを右クリックします。
    
2. [**迷惑メール**] を選択し、[**迷惑メールの報告**] をクリックします。 ![受信トレイから迷惑メールメッセージを報告する](media/EOP-Outlook-Junk-Reporting-Tool-3.jpg)
  
3. [ **Microsoft 迷惑メール報告アドイン**] ダイアログボックスが表示されます。選択したメッセージを迷惑メールとして送信する場合は、[**はい**] をクリックします。 ![迷惑メールとしてレポートを確認する](media/EOP-Outlook-Junk-Reporting-Tool-2.jpg)
  
    > [!NOTE]
    > 迷惑メール メッセージの送信時にこの確認メッセージを表示しない場合は、 **[今後、このメッセージを表示しない]** チェック ボックスをオンにします。 
  
選択したメッセージが、分析用に Microsoft に送信され、迷惑メール フォルダーに移動されます。メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。 
  
### <a name="to-report-a-junk-email-message-from-within-an-opened-message"></a>開いたメッセージから迷惑メール メッセージを報告するには

1. 開いたメッセージ内から、メッセージリボンの [**迷惑メールの報告**] ボタンをクリックします。たとえば、[迷惑**** \>メール**レポート迷惑** ![メール] をクリックすると、メッセージ内から迷惑メールを受信します。](media/EOP-Outlook-Junk-Reporting-Tool-4.jpg)
  
2. [ **Microsoft 迷惑メール報告アドイン**] ダイアログボックスが表示されます。選択したメッセージを迷惑メールとして送信する場合は、[**はい**] をクリックします。 ![迷惑メールとしてレポートを確認する](media/EOP-Outlook-Junk-Reporting-Tool-2.jpg)
  
    > [!NOTE]
    > 迷惑メール メッセージの送信時にこの確認メッセージを表示しない場合は、 **[今後、このメッセージを表示しない]** チェック ボックスをオンにします。 
  
選択したメッセージが、分析用に Microsoft に送信され、迷惑メール フォルダーに移動されます。メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。 
  
## <a name="for-more-information"></a>詳細情報

[レポート メッセージ アドインを有効にする](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)
  
[トラブルシューティングとサポート情報](troubleshooting-and-support-information.md)
  
[メッセージがスパムとしてマークされないようにする方法](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

