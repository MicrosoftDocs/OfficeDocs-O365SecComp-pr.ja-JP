---
title: 電子メールが Office 365 と Exchange のオンライン保護で迷惑メールとして扱われることを防ぐ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 74aaade0-efc0-46ac-b949-f2d1d59256fa
description: 適切な電子メールを防ぐために、Office 365 管理者のためのヒントは、偽陽性として検疫に送信されてからの迷惑メールとしてマークされます。セーフリストと適切な電子メールがスパムとしてマークされているを防ぐために他のオプションをカスタマイズします。
ms.openlocfilehash: 42b27d237592e95e6d175ab335959bc82269c0f7
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531635"
---
# <a name="prevent-email-from-being-marked-as-spam-in-office-365-and-exchange-online-protection"></a>電子メールが Office 365 と Exchange のオンライン保護で迷惑メールとして扱われることを防ぐ

適切なアクセス資格情報を持つ Exchange Online または Exchange オンライン保護 (EOP) の管理者は、出張サービスから電子メール メッセージがスパムとしてマークされたされていないことを確実に次の手順を使用できます。
  
隔離または検疫用フォルダーでの着陸にスパムをブロックを正当なメールにイライラができます。スパム フィルターをバイパスして、適切な電子メール メッセージが迷惑メールとしてマークするを防ぐには、[差出人セーフ リスト] ボックスの一覧またはメール フロー ルールを使用できます。メッセージが正しくないスパムとしてマークされた迷惑メール フィルターによって、誤検知が呼び出されます。Office 365 の迷惑メール フィルターでは、エンド ・ ユーザーは、誤検出を防止するためにカスタマイズが可能ないくつかのオプションも提供します。
  
メールでは false 負の値、ヘルプを探している場合は、スパム メッセージを取得べきではない、[偽の負の問題を防ぐために Office 365 のスパム フィルターを使用してスパム電子メールのブロック](block-email-spam-to-prevent-false-negatives.md)内のヒントをチェックすることとします。
  
## <a name="eop-only-customers-use-directory-synchronization"></a>EOP 専用のお客様: ディレクトリ同期を使用します。

EOP は、スパムやマルウェアから組織を保護するのに役立つサービスをフィルタ リングするクラウド ベースの電子メールです。Office 365 のメールボックスがある場合に自動的にによって保護されている EOP サービスの一部であるためです。 
  
EOP 専用の顧客の場合、つまり、オンプレミスの Exchange Server で使用の EOP サービスに登録する、ディレクトリ同期を使用するサービスとユーザー設定を同期する必要があります。これにより、差出人セーフ リストが EOP を尊重します。詳細については、 [EOP のメール ユーザーの管理](https://go.microsoft.com/fwlink/?LinkId=534098)で「メール ユーザーを管理するためにディレクトリ同期を使用」を参照してください。
  
## <a name="prevent-false-positive-email-by-using-the-connection-filters-ip-allow-list"></a>正偽の電子メールを防ぐフィルターの IP 接続を使用してリストを許可します。

送信者の電子メールは常に、組織内の迷惑メール フォルダーに移動、メールの送信者の IP アドレスを追加するには、接続フィルターの ip を検索する場合は、リストを使用できます。通常、この送信者を組織内のすべての受信者に偽の肯定応答をできないようにします。ユーザー オプションを有効にする場合は例外です"セーフ リスト] のみ: ユーザーまたはドメインを [差出人セーフ リストまたは宛先セーフ リストからのメールのみを受信トレイに配信されます「Outlook でし、その送信者を差出人セーフ リストに追加されません。このオプションを上書きする方法についてを参照してください[トラブルシューティング: EOP 非スパムとしてメッセージをマークする場合でも [迷惑メール] フォルダー メッセージ終了](prevent-email-from-being-marked-as-spam-0.md#TroubleshootingJunkEOPNonSpam)。
  
 **フィルターの IP 許可一覧を接続する IP アドレスを追加するのには**
  
1. 許可する送信者によって送信されたメッセージからヘッダーを取得します。[メッセージ ヘッダーの分析](https://go.microsoft.com/fwlink/p/?LinkId=306583)で説明するよう、Outlook など、Web 上の Outlook のユーザーのメール クライアントからこれを実行できます。
    
2. CIP タグ X Forefront スパム対策レポートのヘッダーまたは[リモート接続アナライザー](https://testconnectivity.microsoft.com/?tabid=mha)の [**メッセージの分析**] タブを使用して、次の IP アドレスを手動で検索します。
    
3. 追加の ip アドレスに IP アドレス「既定の接続フィルター ポリシーを編集するのには EAC を使用する」の手順に従って、[接続フィルター ポリシー構成](https://go.microsoft.com/fwlink/?LinkId=534132)リストを許可します。
    
## <a name="prevent-false-positive-email-by-configuring-spam-filter-policies"></a>正偽の電子メールを防ぐため、スパム フィルター ポリシーを構成することによって

[スパム フィルター ポリシーの構成](https://go.microsoft.com/fwlink/?LinkID=534136)の手順を実行して、許可リストにドメインまたは個々 の電子メール アドレスを追加できます。
  
## <a name="review-your-advanced-spam-filter-policies"></a>高度な迷惑メール フィルターのポリシーを確認します。

ドメイン全体をブロックした場合、スパム フィルター ポリシーで、たとえば、特別な制限があるかどうか、それらが原因で誤検知を確認することを確認します。[スパム フィルター ポリシーを構成](https://go.microsoft.com/fwlink/?LinkId=534136)するにはを参照してくださいし、その他[高度な迷惑メール フィルターのオプション](https://go.microsoft.com/fwlink/?LinkId=534137)が迷惑メールとしてマークするメッセージが発生する可能性がありますを無効にします。 
  
## <a name="help-your-end-users-create-a-safe-sender-list-to-prevent-good-email-from-being-marked-as-spam"></a>な電子メールがスパムとしてマークされていることを防ぐための安全な送信者リストを作成する、エンド ・ ユーザーを支援します。
<a name="BKMK_email-user-help-safelist"> </a>

[Outlook](https://go.microsoft.com/fwlink/p/?LinkId=270065)または[Outlook Web 上](https://go.microsoft.com/fwlink/p/?LinkId=294862)で安全な送信者リストに信頼できる差出人アドレスを追加するのには、ユーザーに指示します。開始するには、Web 上の Outlook で**の設定**を選択します![ConfigureAPowerBIAnalysisServicesConnector_settingsIcon](media/24bd5467-c8d2-4936-9c37-a179bd0e21ec.png) \> **オプション** \> **ブロックまたは許可する**です。次の図は、何か、[差出人セーフ リスト] ボックスの一覧に追加する例を示します。
  
![Outlook Web App の [差出人セーフ リストを追加します。](media/8de6b24e-429e-4e8f-8ce8-53ba659cbfcb.png)
  
EOP は、ユーザーの [差出人セーフ リストと受信者がいない安全なドメインを優先します。これは、ドメインを Web 上で Outlook を使用して追加または Outlook に追加するかどうかは関係ありませんし、ディレクトリ同期を使用して同期します。
  
## <a name="troubleshooting-a-message-ends-up-in-the-junk-folder-even-though-eop-marked-the-message-as-non-spam"></a>トラブルシューティング: メッセージ最終的に迷惑メール フォルダーに EOP 非スパムとしてメッセージをマークする場合でも
<a name="TroubleshootingJunkEOPNonSpam"> </a>

ユーザーに対して有効にする Outlook のオプションがあるかどうかは"セーフ リスト] のみ: ユーザーまたはドメインを [差出人セーフ リストまたは宛先セーフ リストからのメールのみを受信トレイに配信されます」をクリックしすべての電子メールが迷惑メール フォルダーに送信者の送信者、reci に含まれていない限り、pient の差出人セーフ リスト] ボックスの一覧です。これは、EOP 非スパムとしてメッセージをマークするかどうか、またはメッセージを非スパムとしてマークする EOP でルールを設定した場合に関係なく行われます。
  
指示に従って、Outlook ユーザーのセーフ リスト] のみのオプションを無効にすることができます[Outlook: 迷惑メールの UI を無効にするポリシー設定とフィルター機能](https://support.microsoft.com/en-us/kb/2180568)です。
  
Web 上の Outlook でメッセージを表示する場合、メッセージが迷惑メール フォルダーに、送信者が受信者の [差出人セーフ リストにはないためであることを示す黄色の安全性のヒントがあります。
  
メッセージのヘッダーを見ると、スタンプの SFV:SKN (IP を許可するか、ETR を許可する) または SFV:NSPM (スパム以外) が含まれますが、メッセージがユーザーの迷惑メール フォルダーに配置されます。ありませんメッセージ ヘッダーには、ユーザーが [セーフ リスト] のみ] が有効になっていることを示します。これは、[セーフ リストのみ] オプションを Outlook でユーザーが設定した EOP 設定をオーバーライドするために発生します。 
  
 **確認するのにはなぜ安全な送信者からのメッセージがスパムとしてマークされた以外のメッセージのヘッダーがまだ終了ユーザーの迷惑メール フォルダーに**
  
1. オンライン PowerShell を Exchange に接続する方法については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)を参照してください。 
    
2. ユーザーの迷惑メール構成の設定を表示するのには次のコマンドを実行します。
    
  ```
  Get-MailboxJunkEmailConfiguration example@contoso.com | fl TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
  ```

    TrustedListsOnly が True に設定されている場合は、この設定が有効になっていることを意味します。ContactsTrusted を True に設定すると、[差出人セーフ リストと連絡先の両方をユーザーが信頼されるためです。TrustedSendersAndDomains は、ユーザーの [差出人セーフ リストの内容を一覧表示します。
    
## <a name="still-need-help"></a>ヘルプが必要ですか。
<a name="TroubleshootingJunkEOPNonSpam"> </a>

[![Office 365 コミュニティ フォーラムからヘルプを取得する](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![管理者:サインインしてサービス リクエストを作成する](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![管理者:サポートの依頼](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  
## <a name="see-also"></a>関連項目
<a name="TroubleshootingJunkEOPNonSpam"> </a>

[迷惑メール フィルターの概要](https://support.office.com/article/5AE3EA8E-CF41-4FA0-B02A-3B96E21DE089)
  
[ブロックまたは許可 (迷惑メールの設定)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46)
  
[検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする](block-email-spam-to-prevent-false-negatives.md)

