---
title: 'Outlook on the web で迷惑メールとフィッシング詐欺を報告する '
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Microsoft Outlook on the web ユーザーは、組み込みの電子メール報告オプションを使用して、迷惑メール (スパム) とフィッシング詐欺を報告することができます。 また、電子メールが誤って迷惑メール (スパム) として識別されたかどうかを Microsoft に知らせることもできます。
ms.openlocfilehash: c8ee481271d77d0b131af44944b9e94a934d45ba
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156889"
---
# <a name="report-junk-email-and-phishing-scams-in-outlook-on-the-web"></a>Outlook on the web で迷惑メールとフィッシング詐欺を報告する 

組織のユーザーが迷惑メールを受信したり、重要なメールがスパムと誤認されたため受信できなかったりすると、苛立つ原因になることがあります。Exchange Online Protection (EOP) スパム フィルターは精度を上げるための微調整が継続的に行われているため、お客様とエンド ユーザーはこのプロセスから恩恵を受けることができます。Microsoft Outlook on the web のユーザーは、組み込みの電子メール レポート オプションを使用して、迷惑メール (スパム) とフィッシング詐欺を報告できます。電子メールが迷惑メール (スパム) として誤って識別されたかどうかを Microsoft に通知することもできます。
  
## <a name="submit-junk-messages-in-outlook-on-the-web"></a>Outlook on the web で迷惑メール メッセージを送信する

迷惑メール メッセージを Microsoft に送信するには:
  
1. 迷惑メール メッセージをクリックしてから、ツールバーの **[迷惑メール]** をクリックします。 これにより、メッセージが迷惑メール フォルダーに移動され、その送信者が受信拒否リストに追加されます。 
    ![電子メールが Web 上の Outlook からの迷惑メールであることを示しています](media/a10ae792-aab6-4374-a041-6c3f732eb2e3.png)
  
    > [!NOTE]
    > または、メッセージを右クリックしてメニューを表示し、 **[迷惑メールにする]** をクリックします。 
  
迷惑メール メッセージは、 **受信トレイ**、 **低優先メール**、または **削除済みアイテム** フォルダーから報告できます。 
  
2. 迷惑メール メッセージのコピーを分析のために Microsoft に送信するかどうかを確認するダイアログ ボックスが開きます。 Microsoft スパム分析チームにメッセージを送信する場合は、 **[報告]** をクリックします。 今後の迷惑メール メッセージをプロンプトなしで Microsoft に自動的に送信する場合には、オプションで、 **[今後、このメッセージを表示しない]** チェック ボックスを選択します。 
    ![Web 上の Outlook から Microsoft に迷惑メールについて報告します](media/e8d3a9f9-6eb6-4309-ba6d-643dffdb6a33.png)
  
    > [!TIP]
    > **[今後、このメッセージを表示しない]** チェック ボックスを選択した場合でも、後で Outlook on the web の表示設定にアクセスすることによって、迷惑メールを報告するようにこの設定を変更することができます (これらの設定には、サインイン名の横にあるギア メニューからアクセスできます)。 
  
## <a name="submit-phishing-scam-messages-in-outlook-on-the-web"></a>Outlook on the web でフィッシング詐欺メッセージを送信する

フィッシング詐欺メッセージを Microsoft に送信するには:
  
1. フィッシング詐欺メッセージをクリックして、 **[迷惑メール]** の横にある下向き矢印をクリックしてから、ツールバーの **[フィッシング]** をクリックします。 フィッシング詐欺メッセージの送信者は正当な送信者を偽装していることが多いため、Office 365 は送信者をブロックしません。 必要に応じて、「 [ブロックまたは許可 (迷惑メール設定)](https://go.microsoft.com/fwlink/?LinkId=627572)」のトピックの手順に従って、送信者を受信拒否リストに追加してください。 
    ![電子メールが Web 上の Outlook 内のフィッシング詐欺メールであることを示しています](media/959bb577-341c-41ee-a159-e46600b2cf8a.png)<br/>または、メッセージを右クリックしてメニューを表示し、 **[Mark as Phishing] (フィッシングとして報告する)** をクリックします。<br/>フィッシング詐欺メッセージは、 **受信トレイ**、 **低優先メール**、または **削除済みアイテム** フォルダーから報告できます。 
  
2. 組織によっては、フィッシング詐欺メールのコピーを分析のために Microsoft に送信するかどうかを尋ねるダイアログ ボックスが表示されます。メッセージを Microsoft スパム分析チームに送信するには、 **[報告]** をクリックします。この報告オプションは、現在、一部の組織でしか利用できません。そのため、フィッシング詐欺を Microsoft に報告するかどうかが尋ねられない場合があります。 
    
## <a name="submit-not-junk-messages-in-outlook-on-the-web"></a>Outlook on the web で「迷惑メールではないメール」メッセージを送信する

Office 365 によってメッセージが迷惑メールとして誤って識別された場合は、メッセージを「迷惑メールではないメール」として Microsoft に送信します。
  
1. 迷惑メール フォルダーで、そのメッセージをクリックしてから、ツールバーの **[迷惑メールではないメール]** をクリックします。これにより、メッセージが **受信トレイ**に移動され、その送信者が差出人セーフ リストに追加されます。<br/>[迷惑メール] フォルダー内のメッセージを右クリックしてメニューを表示し、[迷惑メールで**はないメールとしてマーク**] をクリックすることもできます。 
  
2. 迷惑メールではないメール メッセージのコピーを分析のために Microsoft に送信するかどうかを尋ねるダイアログ ボックスが表示されます。Microsoft スパム分析チームにメッセージを送信するには、**[報告]** をクリックします。 
    
## <a name="for-more-information"></a>詳細情報

[迷惑メールやフィッシング詐欺について](https://go.microsoft.com/fwlink/p/?LinkId=270068)

[Microsoft Outlook 用迷惑メール報告アドイン](https://docs.microsoft.com/en-us/office365/securitycompliance/junk-email-reporting-add-in-for-microsoft-outlook)
  
  

