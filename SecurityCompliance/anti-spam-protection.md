---
title: Office 365 電子メールのスパム対策の保護
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
description: Exchange Online と Office 365 のスパムを防ぐために役立つフィルター、スパム対策の設定について説明します。Office 365 で大量の迷惑メールを取得しますか。スパム フィルターや迷惑メール対策ポリシーの設定をカスタマイズすることができます。
ms.openlocfilehash: 5547904633a0be9ad57fa7431aeddf1267871662
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532182"
---
# <a name="office-365-email-anti-spam-protection"></a>Office 365 の電子メールのスパム対策保護

Office 365 で大量の迷惑メールについて懸念していますか。私たちしたに組み込まれている複数の迷惑メール フィルター、Office 365 サービスまたは Exchange オンライン保護 (EOP) サービス、電子メールが最初のメッセージを受信した時点から保護されているためです。Office 365 でスパムを防止するために、組織内の特定の問題に対処するための保護設定を変更するのにはすることがあります-発生する大量の迷惑メール、特定の送信者からなどと答えると、だけで正常になるようの設定を調整または最適に満たすため、組織のニーズを調整します。これを行うには、Office 365 のセキュリティでスパム対策設定を変更することができます&amp;コンプライアンス センターです。
  
この資料は、Office 365 の管理者向けです。管理者は、していないが、Office 365 ユーザー、受信するスパムに対処する方法を詳しく知りたい場合は、探している資料がありません。代わりに、PC の Outlook または Outlook for Mac を使用する場合は、[迷惑メール フィルターの概要について説明](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)を開始します。Web 上で Outlook を使用する場合は、[迷惑メールとフィッシング詐欺について理解](https://support.office.com/article/86c1d76f-4d5a-4967-9647-35665dc17c31)を開始します。
  
## <a name="these-options-help-you-prevent-spam-in-office-365"></a>これらのオプションでは、Office 365 でスパムを防止できます。

 **接続をフィルタ リングします**。接続フィルターを使用して、Office 365 を通過するメッセージを許可する前に、送信者の評判をチェックします。許可する] ボックスの一覧または特定の IP アドレスまたは IP アドレスの範囲から送信するすべてのメッセージを受信するかどうかを確認するのには、差出人セーフ リストの一覧を作成することができます。ブロック リストと呼ばれる、メッセージをブロックする IP アドレスの一覧を作成することもできます。詳細については、[接続フィルター ポリシーを構成する](https://technet.microsoft.com/library/jj200718%28v=exchg.150%29.aspx)を参照してください。Office 365 のスパムについて心配がある場合、迷惑メールを防止するために接続フィルターを使用します。
  
Office 365 エンタープライズ E5 または高度な脅威保護 (ATP) のライセンスを購入したお客様の場合は、接続フィルターを使用スプーフィングのインテリジェンスを作成するを許可して、ドメインのスプーフィングは、送信者のリストをブロックします。詳細については、[なりすましのインテリジェンスについての詳細](https://go.microsoft.com/fwlink/?LinkID=735009)を参照してください。
  
 **スパムのフィルタ リングします**。Office 365 は、スパムのフィルタ リングを使用して、スパムと一貫性のあるメッセージの特性をチェックします。スパムとして識別されたメッセージに対しては、特定の言語で記述された、または特定の国や地域から送信されるメッセージにフィルターを適用するかどうかを選択するには、どのようなアクションを変更できます。高度な迷惑メールがスパムのフィルタ リングの積極的なアプローチを追求する場合、フィルター オプションにすることもできます。さらに、通知するためにユーザーに宛てられたメッセージは、検疫に送信されたときに代わりにエンド ・ ユーザーの迷惑メール通知を設定できます。(検疫にメッセージを送信する、設定可能なアクションのいずれか)。これらの通知では、エンド ・ ユーザーは、偽陽性をリリースし、分析をマイクロソフトに報告します。詳細については、[スパム フィルター ポリシーの構成](https://go.microsoft.com/fwlink/p/?LinkId=617147)を参照してください。ために Office 365 のスパムを防ぐため、スパムのフィルタ リングを使用して、Office 365 で大量のスパムを心配している場合、迷惑メールを防止するために接続フィルターを使用します。
  
> [!NOTE]
> EOP スタンドアロン向け: 既定では、EOP のスパム フィルターは各受信者の迷惑メール フォルダーにスパム検出のメッセージを送信します。ただし、オンプレミスのメールボックスの**迷惑メール フォルダーにメッセージを移動**アクションが動作することを確認するには、するために EOP によって追加された迷惑メールのヘッダーを検出するために、オンプレミスのサーバーに 2 つの Exchange トランスポート ルールを構成する必要があります。詳細については、[各ユーザーの迷惑メール フォルダーに迷惑メールがルーティングされるようにする](https://technet.microsoft.com/library/jj837173%28v=exchg.150%29.aspx)を参照してください。 
  
## <a name="extra-information-if-you-receive-too-much-spam-in-office-365"></a>Office 365 で大量の迷惑メールを受信した場合、追加情報

次のビデオでは、EOP でフィルタ リングする迷惑メールの構成の概要を示します。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/608be94c-d763-4c47-af94-99e7cb277713?autoplay=false]
  
詳細については、[スパム フィルター ポリシーの構成](https://go.microsoft.com/fwlink/p/?LinkId=617147)のトピックを参照してください。 
  
## <a name="check-your-outgoing-messages-to-prevent-spam-in-office-365"></a>Office 365 のスパムを防ぐために送信するメッセージを確認します。

 **送信フィルタ リングします**。Office 365 は、ユーザーがスパムを送信しないことを確認するのにもチェックします。ユーザーのコンピューターは、*送信フィルター*と呼ばれることに対する保護を構築するために、スパム メッセージを送信するマルウェアに感染を得る可能性があります。送信フィルターは、オフにすることはできませんが、[送信スパム ポリシーを構成する](https://technet.microsoft.com/library/jj200737%28v=exchg.150%29.aspx)」に記載の設定を構成することができます。Office 365 で大量の迷惑メールの心配がある場合、Exchange のオンラインでの迷惑メールを防止するために送信フィルターを使用します。
  
## <a name="beyond-the-basics-more-ways-to-prevent-spam-in-office-365"></a>基本の実践: Office 365 のスパムを防ぐためにより多くの方法
<a name="BeyondBasics"> </a>

 **フロー ルールを送信します**。組み込みのスパムのフィルタ リングを越えるし、は、ビジネス ポリシーに基づいて、*[メール フロー ルール](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)*、*トランスポート ルール*とも呼ばれますが、カスタム ルールを作成する場合は、ヘルプを別のフィルターは、Office 365 のスパム メールを防ぐ。たとえば、[メッセージでスパム信頼レベル (SCL) を設定するのには、メール フロー ルールを使用して](https://technet.microsoft.com/library/dn798345%28v=exchg.150%29.aspx)で説明したように、スパム信頼レベル (SCL) の値の特定の条件に一致するメッセージを設定するのには、メール フロー ルールを使用できます。 
  
 **電子メール認証します**。検証可能な情報を電子メール メッセージの送信者の電子メール メッセージに追加するのにはドメイン ネーム システム (DNS) を使用する手法は、電子メールの認証と呼ばれます。これら e メールの認証方法の詳細設定の Office 365 管理者が行うことができますを使用します。 
  
- **送信者ポリシー フレームワーク (SPF) です**。SPF は、送信側ドメインの申し立ての所有者に対して送信者の IP アドレスを確認することによって電子メール メッセージの送信元を検証します。SPF を迅速に構成するための簡単な説明、[スプーフィングを防止するために Office 365 の SPF を設定](https://technet.microsoft.com/library/dn789058%28v=exchg.150%29.aspx)を参照してください。Office 365 の SPF、使用方法について詳細に説明またはハイブリッド展開などのトラブルシューティング、または標準の導入では、[どの Office 365 を使用して送信者ポリシー フレームワーク (SPF) のスプーフィングを防ぐために](https://technet.microsoft.com/library/mt712724%28v=exchg.150%29.aspx)始まります。
    
- **DomainKeys は、メール (DKIM) を識別します**。DKIM では、送信する電子メールのメッセージ ヘッダー内の電子メール メッセージにデジタル署名を添付することができます。ドメインから電子メールを受信する電子メール システムは、受信した電子メールの受信が正当かどうか判断するのにはこのデジタル署名を使用します。DKIM および Office 365 の詳細については、 [Office 365 でドメインから送信された送信の電子メールを検証するために使用 DKIM](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx)を参照してください。
    
- **メッセージのドメイン ベースの認証、レポート、および準拠 (DMARC) です**。DMARC 支援のメール システムを受信では、SPF や DKIM のチェックが失敗して、e メール パートナーの別のレベルの信頼を提供するメッセージの処理方法を確認します。DMARC をセットアップする方法については、 [Office 365 で電子メールを検証するために使用して DMARC](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)を参照してください。
    
スパム、フィッシング、および Office 365 のなりすましの心配がある場合、併用 SPF、DKIM、DMARC 迷惑メールや不要ななりすましが行われるようにします。
  
 **エンド ・ ユーザーの設定を管理します**。エンド ・ ユーザーが独自の迷惑メール設定を管理する方法についての情報を探している場合またはチェック アウト (Microsoft Outlook ユーザー用) [、迷惑メール フィルターの概要](https://go.microsoft.com/fwlink/?LinkId=270065)(web ユーザーの Outlook) の[[迷惑メールとフィッシング詐欺について学習](https://go.microsoft.com/fwlink/?LinkId=270068)します。EOP をオンプレミスのメールボックスを保護するために使用する場合は、サービスにこれらの設定が同期されていることを確認するのにはディレクトリ同期を使用することを確認します。ディレクトリ同期の設定に関する詳細については、 [EOP のメール ユーザーの管理](https://technet.microsoft.com/library/dn636911%28v=exchg.150%29.aspx)で「メール ユーザーを管理するためにディレクトリ同期を使用」を参照してください。
  
## <a name="for-more-information"></a>詳細情報
<a name="BeyondBasics"> </a>

[ブログ: 理由はスパムやフィッシング取得 Office 365 を使用しますか。](https://go.microsoft.com/fwlink/?LinkId=528179 )
  
[スパム対策保護に関してよく寄せられる質問](https://technet.microsoft.com/library/jj937231%28v=exchg.150%29.aspx)
  
[セーフリストまたはその他の手法で誤検知の電子メールがスパムとしてマークされないようにする](prevent-email-from-being-marked-as-spam-0.md)
  
[Office 365 の迷惑メールが迷惑メール メッセージをブロックするためのフィルタ リングを設定する方法](block-email-spam-to-prevent-false-negatives.md)
  
[迷惑メール、一括メールの違いは何ですか。](https://technet.microsoft.com/library/dn720441%28v=exchg.150%29.aspx)
  
[スパム対策メッセージ ヘッダー](https://technet.microsoft.com/library/dn205071%28v=exchg.150%29.aspx)
  
[Backscatter メッセージおよび EOP](https://technet.microsoft.com/library/dn499795%28v=exchg.150%29.aspx)
  
## <a name="still-need-help"></a>ヘルプが必要ですか。
<a name="BeyondBasics"> </a>

[![Office 365 コミュニティ フォーラムからヘルプを取得する](media/12a746cc-184b-4288-908c-f718ce9c4ba5.png)](https://go.microsoft.com/fwlink/p/?LinkId=518605)
  
[![管理者:サインインしてサービス リクエストを作成する](media/10862798-181d-47a5-ae4f-3f8d5a2874d4.png)]( https://go.microsoft.com/fwlink/p/?LinkId=519124)
  
[![管理者:サポートの依頼](media/9f262e67-e8c9-4fc0-85c2-b3f4cfbc064e.png)](https://go.microsoft.com/fwlink/p/?LinkID=518322)
  

