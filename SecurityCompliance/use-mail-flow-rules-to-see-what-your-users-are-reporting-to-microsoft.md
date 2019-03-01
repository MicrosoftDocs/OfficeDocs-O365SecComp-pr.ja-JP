---
title: メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Exchange メールフロールールを作成して、ユーザーが電子メールメッセージを分析のために Microsoft に送信したり、独自のセキュリティプロセスで使用したりできないようにすることができます。
ms.openlocfilehash: e93c90074ad2d143a964b928d8e868bee24acba2
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341168"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する

誤検知および false 否定的メッセージを分析のために Microsoft に送信する方法は複数あります。管理者は、メールフロールールを使用して、ユーザーがスパム、非スパム、フィッシング詐欺として Microsoft に報告する内容を確認できます。詳細については、「[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。反対に、Exchange メールフロールール (トランスポートルールとも呼ばれます) を作成して、ユーザーが電子メールメッセージを分析のために Microsoft に送信したり、独自のセキュリティプロセスで使用したりするのを防ぐことができます。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

予想所要時間 : 5 分
  
この手順を実行する前に、アクセス許可を割り当てる必要があります。必要なアクセス許可を確認するには、「[メッセージングポリシーとコンプライアンスのアクセス許可](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)」トピックの「メールフロールール」、および「[クライアントとモバイルデバイスのアクセス許可](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx)」の「web メールボックスポリシー」エントリを参照してください。 
  
このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>EAC を使用して、ユーザーの手動による迷惑メール レポート、フィッシング レポート、非迷惑メール レポートを表示するメール フロー ルールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。
    
2. ![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールを作成する]** を選択します。
    
3. ルールに名前を付けてから、 **[その他のオプション]** をクリックします。
    
4. **[このルールを適用する条件]** の下で **[受信者]** を選択してから、 **[アドレスに次のいずれかの単語が含まれる]** を選択します。
    
5. **[単語または語句の指定]** ボックスで、次の操作を行います。 
    - 入力`abuse@messaging.microsoft.com`してから![[追加](media/ITPro-EAC-AddIcon.gif)] アイコンをクリック`junk@office365.microsoft.com`し、[ ![追加]](media/ITPro-EAC-AddIcon.gif)アイコンをクリックします。これらの電子メールアドレスは、偽の否定的なメッセージを Microsoft に送信するために使用されます。
    - 入力`phish@office365.microsoft.com`して、 ![[追加](media/ITPro-EAC-AddIcon.gif)] アイコンをクリックします。この電子メールアドレスは、不在時のフィッシングメッセージを Microsoft に送信するために使用されます。
    - 入力`false_positive@messaging.microsoft.com`してから![[追加](media/ITPro-EAC-AddIcon.gif)] アイコンをクリック`not_junk@office365.microsoft.com`し、[ ![追加]](media/ITPro-EAC-AddIcon.gif)アイコンをクリックします。これらの電子メールアドレスは、偽陽性のメッセージをマイクロソフトに送信するために使用されます。
    - **[OK]** をクリックします。
    
6. **[次の操作を行います]** で、 **[メッセージを BCC で次へ送信する...]** を選択し、次にメッセージを受信するメールボックスを選択します。 
    
7. 必要に応じて、ルールを監査したり、ルールをテストしたり、特定の期間中にルールをアクティブ化したり、その他の選択を行ったりすることができます。ルールを適用する前に、期間に対してルールをテストすることをお勧めします。「[メールフロールールの手順」を](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)参照してください。 
    
8. **[保存]** ボタンをクリックしてルールを保存します。保存されたルールはルールの一覧に表示されます。 
    
ルールを作成して試行すると、指定したメール アドレス宛に組織内から送信されるすべてのメッセージが指定されたメールボックスにコピーされるようになります。
  

