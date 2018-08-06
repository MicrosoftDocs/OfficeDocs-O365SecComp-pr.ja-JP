---
title: EOP を構成するためのベスト プラクティス
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Exchange Online Protection (EOP) のベスト プラクティス推奨に従って正しく設定し、一般的な構成エラーを防止してください。
ms.openlocfilehash: ef58e2cd5a3ffdbbeb02124442c355974d174073
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027274"
---
# <a name="best-practices-for-configuring-eop"></a>EOP を構成するためのベスト プラクティス
  
Exchange Online Protection (EOP) のベスト プラクティス推奨に従って正しく設定し、一般的な構成エラーを防止してください。原則として、既定の構成設定を使用することをお勧めします。このトピックでは、セットアップ プロセスが既に完了したことを前提としています。まだ EOP の設定が完了していない場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照してください。
  
## <a name="use-a-test-domain"></a>テスト ドメインの使用

大容量の運用ドメインにサービス機能を実装する前に、それらを試すためテスト ドメイン、サブドメイン、または容量の小さいドメインを使用することをお勧めします。
  
## <a name="synchronize-recipients"></a>受信者の同期

オンプレミスの Active Directory 環境に既存のユーザー アカウントがある場合、そのアカウント情報とクラウドの Azure Active Directory を同期させることができます。ディレクトリ同期の使用をお勧めします。ディレクトリ同期を使用することのメリットおよびそのセットアップの手順の詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」を参照してください。
  
## <a name="spf-record-customization-to-help-prevent-spoofing"></a>スプーフィングを防止するための SPF レコードのカスタマイズ

EOP をセットアップするときに DNS レコードの EOP の SPF (送信者ポリシー フレームワーク) レコードが追加されます。SPF レコードは、スプーフィングの防止に役立ちます。SPF レコードが悪用を防止する方法と、SPF レコードを設置型の IP アドレスを追加する方法の詳細については、[スプーフィングを防止するために Office 365 の SPF の設定](../set-up-spf-in-office-365-to-help-prevent-spoofing.md)を参照してください。 
  
## <a name="set-anti-spam-options"></a>スパム対策オプションを設定する

管理、接続フィルターの設定で IP を許可して、IP 禁止一覧に IP アドレスを追加して誤検知 (スパムとして分類されている適切なメール) の数を減らす必要があります、**セーフ リストを有効にする**オプションを選択することによって表示されます。[接続フィルター ポリシーの構成](../configure-the-connection-filter-policy.md)の詳細を表示します。組織全体に適用するより多くの迷惑メール設定を見て[、メッセージがスパムとしてマークされたされていないことを確保する方法](https://go.microsoft.com/fwlink/p/?LinkId=534224)または[false の負の問題を防ぐために Office 365 のスパム フィルターを使用してスパム電子メールをブロック](https://go.microsoft.com/fwlink/p/?LinkId=534225)します。これらは、管理者レベルの制御があり、偽陽性や漏れを防止したい場合に便利です。
  
コンテンツ フィルターを管理するを確認し、必要に応じて既定の設定を変更します。などのアクションは、メッセージを迷惑メール検出の動作を変更できます。スパムのフィルタ リングの積極的なアプローチを追求する場合は、高度な迷惑メールのフィルタ リングのオプションを構成できます。最初にそれらを実装する、運用環境で (電源を入れること) でオプションをお勧めフィッシング詐欺を懸念している組織を有効にするこれらをテストすることをお勧め、 **SPF レコード: ハード失敗**オプションです。[スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)と[高度な迷惑メール フィルターのオプション](../advanced-spam-filtering-asf-options.md)の詳細を表示します。
  
> [!IMPORTANT]
> オンプレミスのメールボックスにこのアクションが動作することを確認するのには **[迷惑メール フォルダーにメッセージを移動**するには、デフォルトのコンテンツのフィルター処理を使用する場合、設置型のトランスポート ルールとも呼ばれます Exchange メール フロー ルールを構成する必要があります。EOP によって追加された迷惑メールのヘッダーを検出するサーバーです。詳細については、[各ユーザーの迷惑メール フォルダーに迷惑メールがルーティングされるようにする](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)を参照してください。 
  
[スパム対策の保護に関する FAQ](../anti-spam-protection-faq.md)など、送信宛名ベスト プラクティス セクションにより、送信メールが配信されることを確認することをお勧めします。
  
漏れ (スパム) と誤検知 (スパムではない) マイクロソフトにいくつかの方法で分析するために送信できます。詳細については、[迷惑メールの送信、スパム以外の場合、および分析のためのマイクロソフトのフィッシング詐欺メッセージ](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)を参照してください。
  
## <a name="set-anti-malware-options"></a>マルウェア対策オプションを設定する

確認し、Exchange 管理者の center(EAC) では、マルウェアのフィルター設定を調整します。[マルウェア対策ポリシーの構成](../configure-anti-malware-policies.md)の詳細を表示します。に関するその他のよく寄せられる質問と回答、[よく寄せられる質問のマルウェア対策保護](../anti-malware-protection-faq-eop.md)のマルウェア対策保護に関連する読み取りお勧めします。
  
マルウェアを含む実行可能ファイルを懸念している場合は、実行可能なコンテンツを含むすべての電子メール添付ファイルをブロックする Exchange メール フロー ルールを作成できます。「[Exchange Online Protection または Forefront Online Protection for Exchange の添付ファイルのブロック機能でマルウェアの脅威を低減する方法](https://support.microsoft.com/kb/2959596)」の手順に従って、「[Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)」の「トランスポート ルールによる検査でサポートされている実行可能ファイルの種類」にリストされたファイル タイプをブロックします。
  
EAC の一般的な添付ファイルの種類フィルターを使用できます。 **[保護]** \> **[マルウェア フィルター]** と選択します。実行可能なコンテンツが含まれるすべての電子メール添付ファイルをブロックする Exchange メール フロー ルール (別名: トランスポート ルール) を作成できます。 
  
保護を強化するために、メール フロー ルールを使用して、以下の拡張子のすべてまたは一部をブロックすることもお勧めします。ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、ht、hta、inf、ins、isp、job、js、jse、lnk、mda、mdb、mde、mdz、msc、msi、msp、mst、pcd、reg、scr、sct、shs、url、vb、vbe、vbs、wsc、wsf、wsh。これは、 **[任意の添付ファイルの拡張子に次の単語が含まれる場合]** の条件を使用して行うことができます。 
  
管理者およびエンド ユーザーは、分析のためにそのファイルを Microsoft に送信することによって、フィルターを通過したマルウェアやマルウェアとして誤判定されたと思われるファイルを報告できます。詳細については、「[Submitting malware and non-malware to Microsoft for analysis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md)」を参照してください。
  
## <a name="create-mail-flow-rules"></a>メール フロー ルールを作成する

ビジネス ニーズを満たすために、メール フロー ルール (カスタム フィルターともいう) を作成します。
  
新しいルールを運用環境に展開するときは、最初にテスト モードの 1 つを選択してルールの効果を確認します。ルールが意図したとおりに機能したら、ルールのモードを **[強制]** に変更します。
  
新しいルールを展開した場合は、適用中のルールを監視するために **[インシデント レポートの生成]** の追加を検討してください。 
  
ハイブリッド展開構成で、組織の構成がオンプレミスと Office 365 の場合は、組織全体に適用するルールを作成できます。これを行うには、オンプレミスと Office 365 の両方で使用できる条件を使用します。ほとんどの条件は両方の展開で使用可能ですが、特定の展開シナリオに固有の条件もいくつかあります。詳細については、「[Mail flow or Transport rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)」を参照してください。
  
組織内で送信中のメッセージのメール添付ファイルを検査する場合には、メール フロー ルールを設定します。その後、添付ファイルの内容や特性に基づいて検査されたメッセージに対してアクションを実行できます。詳細については、「[Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)」を参照してください。
  
### <a name="phishing-and-spoofing-prevention"></a>フィッシングとスプーフィングの防止

電子メールで個人情報が組織から外部に出ていくときに、それを検出することで、フィッシング詐欺対策保護を強化できます。たとえば、次の正規表現をメール フロー ルールで使用すると、個人の金融データやプライバシーを侵害する可能性のある情報の伝送を検出できます。
  
- \d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d (MasterCard Visa)
    
- \d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d (American Express)
    
- \d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d (任意の 16 桁の数字)
    
- \d\d\d\-\d\d\-\d\d\d\d (社会保障番号)
    
組織的なスパムやフィッシング詐欺行為による被害は、ユーザー自身のドメインから送信されたように見せかけた悪意のある電子メールの受信をブロックすることによっても減らせます。たとえば、ユーザーの会社のドメインから同じ会社のドメインに送信されたメッセージを拒否するメール フロー ルールを作成して、この種の送信者偽装をブロックできます。
  
> [!CAUTION]
> この拒否ルールは、ドメインからの正規の電子メールがインターネットからメール サーバーに送信されないことが確認されている場合にのみ作成することをお勧めします。この状況は、メッセージが組織内部のユーザーから外部の受信者に送信され、その後、組織内部の別の受信者に転送される場合が該当します。 
  
### <a name="extension-blocking"></a>拡張子ブロック

マルウェアが含まれている実行可能ファイルのファイルについて心配がある場合、電子メールの添付ファイルを持つ実行可能なコンテンツをブロックするマルウェア対策ポリシーを構成できます。[マルウェア対策ポリシーを構成する](../configure-anti-malware-policies.md)手順に従います。
  
保護を強化するために、次の拡張子の一部または全部をブロックすることもお勧めします。 ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、ht、hta、inf、ins、isp、job、js、jse、lnk、mda、mdb、mde、mdz、msc、msi、msp、mst、pcd、reg、scr、sct、shs、url、vb、vbe、vbs、wsc、wsf、wsh
  
## <a name="reporting-and-troubleshooting"></a>レポートとトラブルシューティング

Office 365 の管理センターのレポートを使って、一般的な課題と傾向のトラブルシューティングを行います。メッセージについて単一の固有なデータを探すには、メッセージ トレース ツールを使用します。レポートの詳細については、「[Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md)」を参照してください。メッセージ トレース ツールの詳細については、「[Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)」を参照してください。
  
## <a name="for-more-information"></a>詳細情報

[EOP の一般的な FAQ](eop-general-faq.md)
  
[EOP のヘルプとサポート](help-and-support-for-eop.md)
  
[EOP の使用を開始するためのビデオ](videos-for-getting-started-with-eop.md)
  
[メッセージがスパムとしてマークされないようにする方法](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

