---
title: Office 365 で誤検知が発生しないようにする方法
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: Strat_O365_IP
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Office 365 で誤検知が発生しないようにして、正しいメールが迷惑メールにならないようにする方法について説明します。
ms.openlocfilehash: d225f7ae3a97d497787c91ed6d4baab1b979f0c3
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410782"
---
# <a name="how-to-prevent-real-email-from-being-marked-as-spam-in-office-365"></a>Office 365 でメールが迷惑メールとしてマークされるのを防ぐ方法

 **Office 365 でメールが迷惑メールとしてマークされていますか? 以下のようにしてください。**
  
誤検知が発生する場合は、「[迷惑メール報告アドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)」ことにより Microsoft にそのメールを報告してください。または、メッセージを*添付ファイルとして* not_junk@office365.microsoft.com に転送することもできます。

**重要**: メッセージを添付ファイルとして転送しなければ、ヘッダーがないために Office 365 の迷惑メール フィルターの改善ができなくなります。
    
## <a name="determine-the-reason-why-the-message-was-marked-as-spam"></a>メッセージが迷惑メールとしてマークされた理由を判断する

Office 365 での迷惑メールに関する多くの問題は、[電子メール メッセージ ヘッダーの表示](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c)によって解決し、何が原因か特定することができます。X-Forefront-Antispam-Report という名前のヘッダーを検索する必要があります。詳細については、「[スパム対策メッセージ ヘッダー](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)」を参照してください。
  
ヘッダーで、次の見出しと値を探します。
  
### <a name="x-forefront-antispam-report"></a>X-Forefront-Antispam-Report

- **SFV:SPM** EOP のスパム対策フィルターにより、メッセージが迷惑メールとしてマークされたことを示します。 

- **SFV:BLK** 送信元アドレスが受信者の受信拒否リストにあるためにメッセージが迷惑メールとしてマークされたことを示します。 
    
- **SFV:SKS** コンテンツ フィルターの前にメッセージが迷惑メールとしてマークされたことを示します。この場合は、メッセージを迷惑メールとしてマークするメール フロー ルール (別名: トランスポート ルール) が関係している可能性があります。メッセージ トレースを実行して、Spam Confidence Level (SCL) が高く設定されていそうなメール フロー ルールがトリガーされたかどうかを調べてください。 
    
- **SFV:SKB** メッセージは迷惑メール フィルター ポリシーの拒否リストと一致したために迷惑メールとしてマークされたことを示します。 
    
- **SFV:BULK** x-microsoft-antispam ヘッダーにある Bulk Complaint Level (BCL) 値が、コンテンツ フィルターに設定されているバルクしきい値を超えていることを示します。バルク メールとは、ユーザーはサインアップした可能性があるとしても望ましくないと思われるメールのことです。メッセージ ヘッダーで、X-Microsoft-Antispam ヘッダーの中の BCL (Bulk Confidence Level) プロパティを見つけます。迷惑メール フィルターに設定されたしきい値よりも BCL 値の方が小さければ、これらのタイプのバルク メッセージを迷惑メールとしてマークするようにしきい値を調整することが必要になる場合があります。[バルク メールの処理](https://docs.microsoft.com/ja-JP/office365/SecurityCompliance/bulk-complaint-level-values)に関する許容度とユーザー設定はユーザーによって異なります。ユーザー設定ごとに異なるポリシーやルールを作成できます。
    
- **CAT:SPOOF** または **CAT:PHISH** メッセージはなりすましと思われることを示します。つまり、メッセージ ソースは検証できないため、疑わしい可能性があるということです。有効であるなら、送信元は SPF と DKIM が適切に構成されていることを確認する必要があります。詳細については、Authentication-Results ヘッダーを確認してください。すべての送信元に適切なメール認証方法を使用させるのは難しいかもしれませんが、こうした確認を省略することは極めて危険であり、侵害の一番の原因です。 
    
### <a name="x-customspam"></a>x-customspam

- このヘッダーがあるということは、迷惑メール フィルターでいずれかの[高度な迷惑メール オプションが有効になっている](https://technet.microsoft.com/library/jj200750%28v=exchg.150%29.aspx)ためにメッセージが迷惑メールとしてマークされたことを示しています。これらの機能を必要としない限り、既定の設定を使用することをお勧めします。 
    
## <a name="solutions-to-additional-causes-of-too-much-spam"></a>大量の迷惑メールの他の原因の解決方法

Exchange Online Protection (EOP) が効率的に機能するためには、いくつかのタスクを管理者が実行する必要があります。Office 365 テナントの管理者でなく、大量の迷惑メールを受け取っているユーザーは、これらのタスクを管理者と一緒に行うこともできます。そうしない場合は、ユーザーのセクションにスキップしてください。
  
### <a name="for-admins"></a>管理者向け

- **DNS レコードが Office 365 を指すようにする** EOP が保護を提供するためには、すべてのドメインのメール エクスチェンジャー (MX) DNS レコードが Office 365 だけを指すようにする必要があります。お使いの MX が Office 365 を指していない場合、EOP はユーザーに迷惑メール フィルター機能を提供しません。別のサービスまたはアプライアンスを使用してドメインのための迷惑メールをフィルタリングする場合、EOP の迷惑メール保護を無効にすることを検討する必要があります。これを行うには、SCL 値を -1 に設定するメール フロー ルールを作成します。EOP を使用することを後で決定する場合は、このメール フロー ルールを必ず削除してください。 
    
- **ユーザーのメッセージ報告アドインをオンにする** [ユーザーのメッセージ報告アドインを有効にする](enable-the-report-message-add-in.md)ことを強くお勧めします。管理者は、ユーザーが送信しているフィードバックを調べ、あらゆるパターンを使用して、問題の原因と思われる設定を調整することもできます。
    
### <a name="for-users"></a>ユーザー向け
    
- **信頼できる差出人リストを作成する** 信頼できる差出人のアドレスを [Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065) または [Outlook on the web](https://go.microsoft.com/fwlink/p/?LinkId=294862) で信頼できる差出人リストに追加します。Outlook on the web でこの操作を行うには、**[設定]**![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **[オプション] ** \> **[ブロックまたは許可]** の順に選びます。次の図は、信頼できる差出人リストにアドレスを追加する例です。
  
![Outlook on the web で信頼できる差出人を追加する](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
EOP では、ユーザーの信頼できる差出人と宛先のリストは適用されますが、信頼できるドメインは適用されません。ドメインが Outlook on the web と Outlook のどちらで追加されたか、Outlook で追加してからディレクトリ同期によって同期されたかにかかわらず、適用されません。

- **Outlook の SmartScreen フィルターを無効にする** ユーザーが古い Outlook デスクトップ クライアントを使用している場合、廃止されている SmartScreen フィルター機能を無効にする必要があります。有効にしておくと、誤検知の原因になることがあります。これは、更新されたデスクトップ Outlook クライアントを実行している場合は必要ありません。

## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a>トラブルシューティング: EOP がメッセージを迷惑メールではないとマークしてもメッセージが迷惑メール フォルダーに送られる
<a name="TroubleshootingJunkEOPNonSpam"> </a>

ユーザーが Outlook のオプションで、[セーフ リストのみ: 差出人セーフ リストまたは宛先セーフ リストに登録されたユーザーやドメインからのメールのみを受信トレイに配信する] を有効にしている場合、受信者が信頼できる差出人のリストに登録していない差出人からのすべてのメールは、迷惑メールに送られます。EOP がメッセージを迷惑メールではないと判断したかどうか、または管理者がメッセージを迷惑メールではないと判断するルールを EOP に設定したかどうかにかかわらず、この処理は実行されます。
  
Outlook ユーザーの [セーフ リストのみ] オプションを無効にするには、「[Outlook: 迷惑メール UI とフィルター処理機構を無効にするポリシー設定](https://support.microsoft.com/ja-JP/kb/2180568)」の指示に従って操作してください。
  
Outlook on the web でメッセージを表示している場合、受信者の信頼できる差出人のリストに差出人が登録されていないため、メッセージが迷惑メール フォルダーに送られた、という黄色の安全性のヒントが表示されます。
  
メッセージのヘッダーに "SFV:SKN (IP Allow or ETR Allow)" または "SFV:NSPM (non-spam)" というスタンプが含まれていても、メッセージがユーザーの迷惑メール フォルダーに送られることがあります。メッセージ ヘッダーには、ユーザーが [セーフ リストのみ] を有効にしたことを示すものがありません。これは、Outlook でユーザーが設定した [セーフ リストのみ] オプションの方が、EOP 設定よりも優先されるために起こります。 
  
 **信頼できる差出人からのメッセージがメッセージ ヘッダーでは迷惑メールではないとマークされているのに、最終的にはユーザーの迷惑メール フォルダーに送られる理由を検証するには**
  
1. Exchange Online PowerShell への接続方法については、「[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?LinkId=396554)」を参照してください。 
    
2. 次のコマンドを実行して、ユーザーの迷惑メール構成設定を確認します。
    
  ```
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

- TrustedListsOnly が True に設定されている場合、[セーフ リストのみ] が有効であることを示します。
- ContactsTrusted が True の場合、ユーザーが連絡先と信頼できる差出人の両方を信頼していることを示します。
- TrustedSendersAndDomains では、ユーザーの信頼できる差出人のリストの内容が表示されます。


## <a name="eop-only-customers-use-directory-synchronization"></a>EOP のみのユーザー: ディレクトリ同期の使用

EOP のみのユーザーの場合、つまり、オンプレミス Exchange メール サーバーで使用するために EOP サービスにサブスクライブしている場合、ディレクトリ同期を使用して、ユーザー設定をサービスと同期することをお勧めします。こうすることで、信頼できる差出人のリストが EOP に適用されます。詳細については、「[EOP でメール ユーザーを管理する](https://go.microsoft.com/fwlink/?LinkId=534098)」の記事の「ディレクトリ同期を使用してメール ユーザーを管理する」を参照してください。
