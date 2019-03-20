---
title: メール フロー ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection でメッセージの SCL を設定する方法について説明します。
ms.openlocfilehash: e07b90ab1ab004c39ef36b2aa744ca87120c11fe
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692746"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>メール フロー ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する

電子メールメッセージのスパム信頼レベル (SCL) を設定するメールフロールール (トランスポートルールとも呼ばれます) を作成できます。 SCL は、メッセージがスパムである可能性がどの程度かを測定します。 スパムとは、迷惑な (通常は不要な) 電子メール メッセージです。 メッセージに対するアクションは、メッセージの SCL 評価によって異なります。 たとえば、同僚からのメッセージはスパムでないと信頼できるため、社内ユーザーからのメッセージの場合はスパム コンテンツ フィルターをバイパスできます。 メールフロールールを使用してメッセージの SCL 値を設定すると、スパムの処理の制御が強化されます。 
  
 **始める前に把握しておくべき情報**
  
- この手順の予想所要時間:10 分。
    
- この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 必要なアクセス許可については、「 [Exchange Online の機能のアクセス](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)許可」の「メールフロールール」、または「 [EOP の機能のアクセス許可](eop/feature-permissions-in-eop.md)」を参照してください。 
    
- このトピックの手順で使用可能なキーボード ショートカットについては、「**Exchange 管理センターのキーボード ショートカット**」を参照してください。
    
### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>メッセージの SCL を設定するメールフロールールを作成するには

1. Exchange 管理センター (EAC) で、 **[メール フロー]** \> **[ルール]** を選択します。
    
2. **[新規作成]**![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) を選択し、 **[新しいルールの作成]** を選択します。
    
3. ルールの名前を指定します。
    
4. **[その他のオプション]** を選択し、 **[このルールを適用する条件]** で、このルールに設定するアクション (つまり、SCL 値の設定) をトリガーする条件を指定します。
    
    たとえば、 **[送信者]** \> **[外部/内部である]** を設定し、 **[送信者の場所の選択]** ダイアログ ボックスで **[組織内]**、 **[OK]** の順に選択します。<br/>
    ![送信者の場所の選択](media/EOP-ETR-SetSCL-1.jpg)
  
5. **[実行する処理]** で、 **[メッセージのプロパティを変更する]** \> **[SCL (Spam Confidence Level) の設定]** の順に選択します。
  
6. **[SCL の指定]** ダイアログ ボックスで、次の値のいずれかを選択し、 **[OK]** を選択します。
    
  - **[スパム対策フィルターのバイパス]**: SCL が -1 に設定され、コンテンツ フィルターは実行されません。 
    
  - **0 ～ 4**: SCL をこれらの値のいずれかに設定すると、追加の処理のためにメッセージはコンテンツ フィルターに渡されます。 
    
  - **5、6**: SCL をこれらの値のいずれかに設定すると、適用可能なコンテンツ フィルター ポリシーに指定された **[スパム]** のアクションが適用されます。既定では、メッセージは受信者の迷惑メール フォルダーに送られます。 
    
  - **7 ～ 9**: SCL をこれらの値のいずれかに設定すると、適用可能なコンテンツ フィルター ポリシーに指定された **[精度の高いスパム]** のアクションが適用されます。既定では、メッセージは受信者の迷惑メール フォルダーに送られます。 
    
    コンテンツ フィルター ポリシーの構成の詳細については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。サービスの SCL 値の詳細については、「[Spam Confidence Level](spam-confidence-levels.md)」を参照してください。
    
7. ルールのその他のプロパティを指定し、 **[保存]** を選択します。
    
    > [!TIP]
    > このルールで選択または指定できるその他のプロパティの詳細については、「 [EAC を使用してメールフロールールを作成する](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules)」を参照してください。 
  
## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

この処理が正常に動作することを確認するには、組織内のユーザーに電子メール メッセージを送信し、必要なアクションがメッセージに対して実行されたかどうかを確認します。たとえば、 **[SCL (Spam Confidence Level) の設定]** を **[スパム対策フィルターのバイパス]** に設定した場合、メッセージは指定された受信者の受信トレイに送信される必要があります。また、 **[SCL (Spam Confidence Level) の設定]** を **9** に設定し、適用可能なコンテンツ フィルター ポリシーの **[精度の高いスパム]** に対するアクションが迷惑メール フォルダーへのメッセージの送信である場合、メッセージは指定された受信者の迷惑メール フォルダーに送られる必要があります。 
  

