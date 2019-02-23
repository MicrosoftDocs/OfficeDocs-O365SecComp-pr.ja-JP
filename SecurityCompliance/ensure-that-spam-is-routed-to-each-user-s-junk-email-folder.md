---
title: スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 7/16/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: EOP のお客様のための既定のスパム対策アクションでは、スパム メッセージは受信者の [迷惑メール] フォルダーに移動されます。このアクションをオンプレミスのメールボックスで使用するには、EOP によって追加されたスパム ヘッダーを検出するように、オンプレミスのエッジ サーバーまたはハブ サーバーで Exchange トランスポート ルールを構成する必要があります。これらのトランスポート ルールにより、Set-OrganizationConfig コマンドレットの SclJunkThreshold プロパティで使用する Spam Confidence Level (SCL) が設定されます。
ms.openlocfilehash: f712e66934956bcf46215e4016501003ce9b1725
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30222886"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする

> [!IMPORTANT]
> このトピックは、ハイブリッド展開でオンプレミスのメールボックスをホストしている Exchange Online Protection (EOP) のお客様にのみ当てはまります。Office 365 でメールボックスが完全にホストされている Exchange Online のお客様は、ここに示すコマンドを実行する必要はありません。 
  
EOP のお客様のための既定のスパム対策アクションでは、スパム メッセージは受信者の [迷惑メール] フォルダーに移動されます。このアクションをオンプレミスのメールボックスで使用するには、EOP によって追加されたスパム ヘッダーを検出するように、オンプレミスのエッジ サーバーまたはハブ サーバーで Exchange トランスポート ルールを構成する必要があります。これらのトランスポート ルールにより、Set-OrganizationConfig コマンドレットの SclJunkThreshold プロパティで使用する Spam Confidence Level (SCL) が設定されます。 
  
### <a name="to-add-transport-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a>Windows PowerShell を使用して、スパムが [迷惑メール] フォルダーに移動されるようにするトランスポート ルールを追加するには

1. オンプレミス Exchange サーバーの Exchange 管理シェル にアクセスします。オンプレミスの Exchange 組織で Exchange 管理シェル を開く方法については、「 **Open the Shell**」を参照してください。
    
2. コンテンツでフィルターされたスパム メッセージを [迷惑メール] フォルダーにルーティングするには、次のコマンドを実行します。
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    _NameForRule_ は、新しいルールの名前です (例: JunkContentFilteredMail)。 
    
3. コンテンツ フィルターに到達する前にスパムとしてマークされたメッセージを [迷惑メール] フォルダーにルーティングするには、次のコマンドを実行します。
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    _NameForRule_ は新しいルールの名前です (例: JunkMailBeforeReachingContentFilter)。 
    
4. 次に示すコマンドを実行して、スパム フィルター ポリシーのブロック リスト ( **受信拒否送信者**一覧など) に登録されている送信者からのメッセージが [迷惑メール] フォルダーにルーティングされるようにします。 
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    _NameForRule_ は新しいルールの名前です (例: JunkMailInSenderBlockList)。 
    
**[迷惑メール フォルダーにメッセージを移動する]** アクションを使用しない場合は、Exchange 管理センター のコンテンツ フィルター ポリシーで別のアクションを選択してください。詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。メッセージ ヘッダー内で該当するフィールドの詳細については、「[スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)」を参照してください。
  
## <a name="see-also"></a>See also

[New-TransportRule コマンドレット](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

