---
title: メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: ユーザー分析のためのマイクロソフトに電子メール メッセージを送信するを防止し、独自のセキュリティ プロセスで使用する Exchange のトランスポート ルールを作成することができます。
ms.openlocfilehash: 92acabe133ef154d880104c20aeed7572ea87d41
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002625"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する

正と負の値の false メッセージを Microsoft に送信するには分析のための複数の方法があります。管理者は、どのようなユーザーは、マイクロソフトに報告する迷惑メール、スパム以外の場合、フィッシング詐欺とを参照してくださいにメール フロー ルールを使用できます。詳細については、[迷惑メールの送信、スパム以外の場合、および分析のためのマイクロソフトのフィッシング詐欺メッセージ](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)を参照してください。逆に、ユーザー分析のためのマイクロソフトに電子メール メッセージを送信するを防止し、独自のセキュリティ プロセスで使用する Exchange トランスポート ルールを作成できます。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

予想所要時間 : 5 分
  
[Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) トピックの この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「トランスポート ルール」のエントリと、 [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) トピックの「Outlook Web App メールボックス ポリシー」のエントリです。 
  
このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>EAC を使用して、ユーザーの手動による迷惑メール レポート、フィッシング レポート、非迷惑メール レポートを表示するメール フロー ルールを作成する

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。
    
2. ![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) をクリックしてから、 **[新しいルールを作成する]** を選択します。
    
3. ルールに名前を付けてから、 **[その他のオプション]** をクリックします。
    
4. **[このルールを適用する条件]** の下で **[受信者]** を選択してから、 **[アドレスに次のいずれかの単語が含まれる]** を選択します。
    
5. **[単語または語句の指定]** ボックスで、次の操作を行います。 
    - 型`abuse@messaging.microsoft.com`] をクリックし、![アイコンの追加](media/ITPro-EAC-AddIcon.gif)と入力し、 `junk@office365.microsoft.com` ] をクリックし、![アイコンの追加](media/ITPro-EAC-AddIcon.gif)。これらの電子メール アドレスを使用して、マイクロソフトに負の値は false のメッセージを送信します。
    - 型`phish@office365.microsoft.com`] をクリックし、![アイコンの追加](media/ITPro-EAC-AddIcon.gif)。この電子メール アドレスを使用して、マイクロソフトのフィッシング詐欺の不在メッセージを送信します。
    - 型`false_positive@messaging.microsoft.com`] をクリックし、![アイコンの追加](media/ITPro-EAC-AddIcon.gif)と入力し、 `not_junk@office365.microsoft.com` ] をクリックし、![アイコンの追加](media/ITPro-EAC-AddIcon.gif)。これらの電子メール アドレスを使用して、マイクロソフトに正偽のメッセージを送信します。
    - **[OK]** をクリックします。
    
6. **[次の操作を行います]** で、 **[メッセージを BCC で次へ送信する...]** を選択し、次にメッセージを受信するメールボックスを選択します。 
    
7. 希望する場合は、監査規則、ルールをテスト、特定の期間中にルールをアクティブにするための選択および他の選択を行うことができます。それを実施する前に一定のルールをテストすることをお勧めします。[メール フロー ルールの手順](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures)を参照してください。 
    
8. **[保存]** ボタンをクリックしてルールを保存します。保存されたルールはルールの一覧に表示されます。 
    
ルールを作成して試行すると、指定したメール アドレス宛に組織内から送信されるすべてのメッセージが指定されたメールボックスにコピーされるようになります。
  

