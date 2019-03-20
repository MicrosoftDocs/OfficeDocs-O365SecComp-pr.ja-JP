---
title: スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 7/16/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection でスパムをユーザーの迷惑メールフォルダーにルーティングする方法について説明します。
ms.openlocfilehash: 30b115b5d7f8f02767e3e380b672341765052a9c
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692816"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする

> [!IMPORTANT]
> このトピックは、ハイブリッド展開でオンプレミスのメールボックスをホストしている Exchange Online Protection (EOP) のお客様にのみ当てはまります。Office 365 でメールボックスが完全にホストされている Exchange Online のお客様は、ここに示すコマンドを実行する必要はありません。 
  
EOP のお客様のための既定のスパム対策アクションでは、スパム メッセージは受信者の [迷惑メール] フォルダーに移動されます。 このアクションをオンプレミスのメールボックスで使用するには、オンプレミスのエッジサーバーまたはハブサーバーで Exchange メールフロールール (トランスポートルールとも呼ばれます) を構成して、EOP によって追加されたスパムヘッダーを検出する必要があります。 これらのメールフロールールは、SclJunkThreshold コマンドレットのプロパティで使用されるスパム信頼レベル (SCL) を設定し、スパムを各メールボックスの迷惑メールフォルダーに移動します。 
  
### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a>Windows PowerShell を使用してスパムが迷惑メールフォルダーに移動されるようにメールフロールールを追加するには

1. オンプレミス Exchange サーバーの Exchange 管理シェル にアクセスします。オンプレミスの Exchange 組織で Exchange 管理シェル を開く方法については、「 **Open the Shell**」を参照してください。
    
2. コンテンツでフィルターされたスパム メッセージを [迷惑メール] フォルダーにルーティングするには、次のコマンドを実行します。
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    _NameForRule_ は、新しいルールの名前です (例: JunkContentFilteredMail)。 
    
3. コンテンツ フィルターに到達する前にスパムとしてマークされたメッセージを [迷惑メール] フォルダーにルーティングするには、次のコマンドを実行します。
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    _NameForRule_ は新しいルールの名前です (例: JunkMailBeforeReachingContentFilter)。 
    
4. 次に示すコマンドを実行して、スパム フィルター ポリシーのブロック リスト ( **受信拒否送信者**一覧など) に登録されている送信者からのメッセージが [迷惑メール] フォルダーにルーティングされるようにします。 
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    _NameForRule_ は新しいルールの名前です (例: JunkMailInSenderBlockList)。 
    
**[迷惑メール フォルダーにメッセージを移動する]** アクションを使用しない場合は、Exchange 管理センター のコンテンツ フィルター ポリシーで別のアクションを選択してください。詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。メッセージ ヘッダー内で該当するフィールドの詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。
  

> [!TIP]
> [**迷惑メールフォルダーにメッセージを移動**する] アクションを使用しない場合は、Exchange 管理センターのコンテンツフィルターポリシーで別のアクションを選択できます。 詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。 メッセージ ヘッダー内で該当するフィールドの詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。
> 
## <a name="see-also"></a>関連項目

[New-TransportRule コマンドレット](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

