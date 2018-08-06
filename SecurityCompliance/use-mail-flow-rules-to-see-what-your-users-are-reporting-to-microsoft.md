---
title: メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/23/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
description: ユーザー分析のためのマイクロソフトに電子メール メッセージを送信するを防止し、独自のセキュリティ プロセスで使用する Exchange のトランスポート ルールを作成することができます。
ms.openlocfilehash: f2376668e2a1a16eba9913178a100fc31763b227
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026774"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a>メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する

正と負の値の false メッセージを Microsoft に送信するには分析のための複数の方法があります。管理者は、どのようなユーザーは、マイクロソフトに報告する迷惑メール、スパム以外の場合、フィッシング詐欺とを参照してくださいにメール フロー ルールを使用できます。詳細については、[迷惑メールの送信、スパム以外の場合、および分析のためのマイクロソフトのフィッシング詐欺メッセージ](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)を参照してください。逆に、ユーザー分析のためのマイクロソフトに電子メール メッセージを送信するを防止し、独自のセキュリティ プロセスで使用する Exchange トランスポート ルールを作成できます。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報
<a name="sectionSection0"> </a>

予想所要時間 : 5 分
  
[Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) トピックの この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「トランスポート ルール」のエントリと、 [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) トピックの「Outlook Web App メールボックス ポリシー」のエントリです。 
  
このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。
  
## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a>EAC を使用して、ユーザーの手動による迷惑メール レポート、フィッシング レポート、非迷惑メール レポートを表示するメール フロー ルールを作成する
<a name="sectionSection1"> </a>

1. EAC で、 **[メール フロー]** \> **[ルール]** に移動します。
    
2. ![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックしてから、 **[新しいルールを作成する]** を選択します。
    
3. ルールに名前を付けてから、 **[その他のオプション]** をクリックします。
    
4. **[このルールを適用する条件]** の下で **[受信者]** を選択してから、 **[アドレスに次のいずれかの単語が含まれる]** を選択します。
    
5. **[単語または語句の指定]** ボックスで、次の操作を行います。 
    - **abuse@messaging.microsoft.com** と入力してから ![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックし、次に **junk@office365.microsoft.com** と入力してから ![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックします。これらの電子メール アドレスは、偽陰性のメッセージをマイクロソフトに送信するために使用されます。
    - **phish@office365.microsoft.com** と入力し、次に ![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックします。この電子メール アドレスは、フィッシングとして処理されなかったフィッシング メッセージを Microsoft に送信するために使用されます。
    - **false_positive@messaging.microsoft.com** と入力してから ![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックし、次に **not_junk@office365.microsoft.com** と入力してから ![[追加] アイコン](media/ITPro-EAC-AddIcon.png) をクリックします。これらの電子メール アドレスは、偽陽性のメッセージをマイクロソフトに送信するために使用されます。
    - **[OK]** をクリックします。
    
6. **[次の操作を行います]** で、 **[メッセージを BCC で次へ送信する...]** を選択し、次にメッセージを受信するメールボックスを選択します。 
    
7. これ以外にも、ルールを監査する、ルールをテストする、一定期間だけルールをアクティブにするといった選択肢もあります。ルールを施行する前に一定期間ルールをテストすることをお勧めします。[Manage Transport Rules](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx) にこれらの選択肢に関する詳細が記載されています。 
    
8. **[保存]** ボタンをクリックしてルールを保存します。保存されたルールはルールの一覧に表示されます。 
    
ルールを作成して試行すると、指定したメール アドレス宛に組織内から送信されるすべてのメッセージが指定されたメールボックスにコピーされるようになります。
  

