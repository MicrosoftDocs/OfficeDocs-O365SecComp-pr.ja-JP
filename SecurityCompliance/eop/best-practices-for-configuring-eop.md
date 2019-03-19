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
ms.openlocfilehash: d58b03d4ac3e11c863cec32430236ca9f0cea13e
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670712"
---
# <a name="best-practices-for-configuring-eop"></a>EOP を構成するためのベスト プラクティス
  
Exchange Online Protection (EOP) のベスト プラクティス推奨に従って正しく設定し、一般的な構成エラーを防止してください。原則として、既定の構成設定を使用することをお勧めします。このトピックでは、セットアップ プロセスが既に完了したことを前提としています。まだ EOP の設定が完了していない場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照してください。
  
## <a name="use-a-test-domain"></a>テスト ドメインの使用

大容量の運用ドメインにサービス機能を実装する前に、それらを試すためテスト ドメイン、サブドメイン、または容量の小さいドメインを使用することをお勧めします。
  
## <a name="synchronize-recipients"></a>受信者の同期

オンプレミスの Active Directory 環境に既存のユーザー アカウントがある場合、そのアカウント情報とクラウドの Azure Active Directory を同期させることができます。ディレクトリ同期の使用をお勧めします。ディレクトリ同期を使用することのメリットおよびそのセットアップの手順の詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」を参照してください。
  
## <a name="spf-record-customization-to-help-prevent-spoofing"></a>スプーフィングを防止するための SPF レコードのカスタマイズ

EOP をセットアップすると、DNS レコードに EOP 用の SPF (Sender Policy Framework) レコードが追加されれます。 SPF レコードによって、スプーフィングを防止できます。 spf レコードがスプーフィングを防ぎ、オンプレミスの IP アドレスを spf レコードに追加する方法の詳細については、「 [Set up SPF in Office 365」を](../set-up-spf-in-office-365-to-help-prevent-spoofing.md)参照して、スプーフィングを防止してください。 
  
## <a name="set-anti-spam-options"></a>スパム対策オプションを設定する

ip 許可一覧と ip 禁止一覧に ip アドレスを追加し、[**セーフリストを有効に**する] オプションを選択することによって、接続フィルター設定を整理します。受信する誤検知 (良好なメールとして分類されるメール) の数を減らす必要があります。 詳細につい[ては、「Configure the connection filter policy」を](../configure-the-connection-filter-policy.md)参照してください。 組織全体に適用されるスパム設定の詳細については、「 [EOP と Office 365 でメールが迷惑メールとして検出されないようにする](https://go.microsoft.com/fwlink/p/?LinkId=534224)」または「[Office 365 のスパム フィルターでスパムや迷惑メールをブロックして、検出漏れ問題を防止する](https://go.microsoft.com/fwlink/p/?LinkId=534225)」を参照してください。 これらは、管理者レベルの制御権限を持っている場合にスパムの誤検知や検出漏れを防ぐ上で役立ちます。
  
コンテンツフィルターを管理するには、既定の設定を確認し、必要に応じて変更します。 たとえば、スパム検出メッセージに対して行われる処理を変更することができます。 スパムフィルター処理に積極的なアプローチを使用する場合は、高度なスパムフィルターオプションを構成できます。 これらのオプションは、運用環境に実装する前にまずテストすることをお勧めします (オンにすることにより)。フィッシングを懸念している組織では、 **SPF レコード: hard fail**オプションをオンにすることをお勧めします。 詳細につい[ては、「スパムフィルターポリシーの構成](../configure-your-spam-filter-policies.md)」および[「Advanced spam filtering options](../advanced-spam-filtering-asf-options.md)」を参照してください。
  
> [!IMPORTANT]
> 既定のコンテンツフィルター操作を使用している場合は、[**迷惑メール] フォルダーにメッセージを移動**して、このアクションがオンプレミスのメールボックスで機能するようにするには、オンプレミスの Exchange メールフロールール (トランスポートルールとも呼ばれます) を構成する必要があります。EOP によって追加されたスパムヘッダーを検出するサーバー。 詳細については、「[スパムが各ユーザーの [迷惑メール] フォルダーにルーティングされるようにする](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。 
  
送信メールが配信されるようにするために、「送信のベストプラクティス」セクションを含む[スパム対策保護](../anti-spam-protection-faq.md)に関する FAQ を確認することをお勧めします。
  
検出漏れ (スパム) と誤検知 (非スパム) を Microsoft に送信して分析を依頼する方法がいくつかあります。 詳細については、「[スパム、非スパム、フィッシング詐欺メッセージを分析のために Microsoft に送信する](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)」を参照してください。
  
## <a name="set-anti-malware-options"></a>マルウェア対策オプションを設定する

Exchange 管理センター(EAC) でマルウェアのフィルター設定を確認し、微調整を行います。 詳細については[、「マルウェア対策ポリシーを構成する](../configure-anti-malware-policies.md)」を参照してください。 また、[マル](../anti-malware-protection-faq-eop.md)ウェア対策保護に関するよく寄せられる質問や、マルウェア対策の保護に関する回答についてもお読みください。
  
マルウェアを含む実行可能ファイルを懸念している場合は、実行可能なコンテンツを含むすべての電子メール添付ファイルをブロックする Exchange メール フロー ルールを作成できます。 「[メールフロールールを使用して exchange online のメッセージの添付ファイルを検査する](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)」に記載されているファイルの種類をブロックするには、「 [exchange online Protection でのファイル添付ブロックを介してマルウェアの脅威を軽減する](https://support.microsoft.com/kb/2959596)」の手順に従います。
  
EAC の一般的な添付ファイルの種類フィルターを使用できます。 **[保護]** \> **[マルウェア フィルター]** と選択します。 実行可能なコンテンツを含むすべての電子メール添付ファイルをブロックするメールフロールールを作成できます。 
  
保護を強化するために、メール フロー ルールを使用して、以下の拡張子のすべてまたは一部をブロックすることもお勧めします。ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、ht、hta、inf、ins、isp、job、js、jse、lnk、mda、mdb、mde、mdz、msc、msi、msp、mst、pcd、reg、scr、sct、shs、url、vb、vbe、vbs、wsc、wsf、wsh。これは、 **[任意の添付ファイルの拡張子に次の単語が含まれる場合]** の条件を使用して行うことができます。 
  
管理者およびエンド ユーザーは、分析のためにそのファイルを Microsoft に送信することによって、フィルターを通過したマルウェアやマルウェアとして誤判定されたと思われるファイルを報告できます。詳細については、「[Submitting malware and non-malware to Microsoft for analysis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md)」を参照してください。
  
## <a name="create-mail-flow-rules"></a>メール フロー ルールを作成する

ビジネスニーズを満たすように、メールフロールール (トランスポートルールとも呼ばれる) またはカスタムフィルターを作成します。
  
新しいルールを運用環境に展開するときは、最初にテスト モードの 1 つを選択してルールの効果を確認します。ルールが意図したとおりに機能したら、ルールのモードを **[強制]** に変更します。
  
新しいルールを展開した場合は、適用中のルールを監視するために **[インシデント レポートの生成]** の追加を検討してください。 
  
ハイブリッド展開構成で、組織の構成がオンプレミスと Office 365 の場合は、組織全体に適用するルールを作成できます。 これを行うには、オンプレミスと Office 365 の両方で使用できる条件を使用します。 ほとんどの条件は両方の展開で使用可能ですが、特定の展開シナリオに固有の条件もいくつかあります。 詳細について[は、「メールフロールール (トランスポートルール) (Exchange Online)」を](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)参照してください。
  
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

マルウェアを含む実行可能ファイルについて懸念している場合は、マルウェア対策ポリシーを構成して、実行可能なコンテンツを含む電子メール添付ファイルをブロックすることができます。 「[マルウェア対策ポリシーを構成する](../configure-anti-malware-policies.md)」の手順に従います。
  
保護を強化するために、次の拡張子の一部または全部をブロックすることもお勧めします。 ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、ht、hta、inf、ins、isp、job、js、jse、lnk、mda、mdb、mde、mdz、msc、msi、msp、mst、pcd、reg、scr、sct、shs、url、vb、vbe、vbs、wsc、wsf、wsh 
  
## <a name="reporting-and-troubleshooting"></a>レポートとトラブルシューティング

管理センターのレポートを使用して、一般的な問題と傾向をトラブルシューティングします。 メッセージについて単一の固有なデータを探すには、メッセージ トレース ツールを使用します。 レポートの詳細については、「[Exchange Online Protection でのレポート作成とメッセージ追跡](reporting-and-message-trace-in-exchange-online-protection.md)」を参照してください。 メッセージ トレース ツールの詳細については、「[Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)」を参照してください。
  
## <a name="for-more-information"></a>関連情報

[EOP の一般的な FAQ](eop-general-faq.md)
  
[EOP のヘルプとサポート](help-and-support-for-eop.md)
  
[EOP の使用を開始するためのビデオ](videos-for-getting-started-with-eop.md)
  
[メッセージがスパムとしてマークされないようにする方法](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

