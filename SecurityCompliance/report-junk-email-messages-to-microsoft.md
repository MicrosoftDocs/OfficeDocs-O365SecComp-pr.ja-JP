---
title: 迷惑メール メッセージを Microsoft に報告する
ms.author: krowley
author: kccross
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
description: Microsoft Office Outlook 用迷惑メール報告アドインでは、次のような複数の方法で迷惑メール メッセージを報告できます。
ms.openlocfilehash: c32f66aee48eea6f7536680ba4e165776685f7ae
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002308"
---
# <a name="report-junk-email-messages-to-microsoft"></a>迷惑メール メッセージを Microsoft に報告する

Microsoft Office Outlook 用迷惑メール報告アドインでは、次のような複数の方法で迷惑メール メッセージを報告できます。
  
- Outlook リボンから報告する
    
- 受信トレイから報告する
    
- 開いた電子メール メッセージから報告する
    
迷惑メール報告アドインは、Microsoft Exchange Online Protection (EOP) サービスにレポートを送信するために役立ちます。メールボックスがサービスによって保護されていない場合、迷惑メールのレポートを送信しても、スパム フィルターは影響を受けません。管理者は、組織全体に適用されるスパム設定についての詳細を、「[メッセージがスパムとしてマークされないようにする方法](https://go.microsoft.com/fwlink/p/?LinkId=534224)」や「[検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする (Block email spam with the Office 365 spam filter to prevent false negative issues)](https://go.microsoft.com/fwlink/p/?LinkId=534225)」で知ることができます。これらは、管理者レベルの制御権を持っている場合に、誤検知や検出漏れを防止する上で役立ちます。
  
> [!TIP]
> [Not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com)の電子メール アドレスを使用して[junk@office365.microsoft.com](mailto:junk@office365.microsoft.com)の電子メール アドレスを使用してマイクロソフトに直接メッセージを迷惑メールと間違って正 (迷惑メール) メッセージを送信することもできます。詳細については、[迷惑メールの送信、スパム以外の場合、および分析のためのマイクロソフトのフィッシング詐欺メッセージ](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)を参照してください。 
  
### <a name="to-report-junk-email-messages-from-outlook"></a>Outlook からメッセージを迷惑メールを報告するには

[レポート メッセージのアドインの使用します。](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) 
  
### <a name="to-report-junk-email-messages-from-your-inbox"></a>受信トレイから迷惑メール メッセージを報告するには

1. 迷惑メールとして報告するメッセージを右クリックします。
    
2. **迷惑メール**を選択し、[**迷惑メールの報告**] をクリックします。 ![、受信トレイから迷惑メールを報告します。](media/EOP-Outlook-Junk-Reporting-Tool-3.jpg)
  
3. **Microsoft 迷惑電子メールのレポート作成アドイン**] ダイアログ ボックスが開きます。迷惑メールとして選択したメッセージを送信することを確認したら、[**はい**] をクリックします。 ![迷惑メールとしてレポートを確認します。](media/EOP-Outlook-Junk-Reporting-Tool-2.jpg)
  
    > [!NOTE]
    > 迷惑メール メッセージの送信時にこの確認メッセージを表示しない場合は、 **[今後、このメッセージを表示しない]** チェック ボックスをオンにします。 
  
選択したメッセージが、分析用に Microsoft に送信され、迷惑メール フォルダーに移動されます。メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。 
  
### <a name="to-report-a-junk-email-message-from-within-an-opened-message"></a>開いたメッセージから迷惑メール メッセージを報告するには

1. 開いているメッセージ内で、メッセージ リボンの [**迷惑メールの報告**] ボタンをクリックします。たとえば、[**迷惑メール**] をクリックして\>**レポート迷惑**![メッセージ内からの迷惑メールを報告します。](media/EOP-Outlook-Junk-Reporting-Tool-4.jpg)
  
2. **Microsoft 迷惑電子メールのレポート作成アドイン**] ダイアログ ボックスが開きます。迷惑メールとして選択したメッセージを送信することを確認したら、[**はい**] をクリックします。 ![迷惑メールとしてレポートを確認します。](media/EOP-Outlook-Junk-Reporting-Tool-2.jpg)
  
    > [!NOTE]
    > 迷惑メール メッセージの送信時にこの確認メッセージを表示しない場合は、 **[今後、このメッセージを表示しない]** チェック ボックスをオンにします。 
  
選択したメッセージが、分析用に Microsoft に送信され、迷惑メール フォルダーに移動されます。メッセージが送信されたことを確認するには、 **[送信済みアイテム]** フォルダーを開いて、送信済みのメッセージを表示します。 
  
## <a name="for-more-information"></a>詳細情報

[レポート メッセージ アドインを有効にする](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)
  
[トラブルシューティングとサポート情報](troubleshooting-and-support-information.md)
  
[メッセージがスパムとしてマークされないようにする方法](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

