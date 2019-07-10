---
title: リファレンスポリシー、プラクティス、ガイドライン
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft は、さまざまなポリシー、手順を開発し、業界のベストプラクティスをいくつか採用して、ユーザーを不適切な迷惑メールや悪意のあるメールから保護しています。
ms.openlocfilehash: 4a9c38822c4d0f3e06e209acf021618864540c83
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35601185"
---
# <a name="reference-policies-practices-and-guidelines"></a>リファレンス: ポリシー、プラクティス、ガイドライン
  
Microsoft は、Web 上におけるユーザー エクスペリエンスの信頼性を高めるための支援に取り組んでいます。そのため、さまざまなポリシー、手順を作成し、業界のいくつものベスト プラクティスを採用して、ユーザーが不適切で望ましくない、または悪意のあるメールから保護されるよう取り組んできました。Office 365 ユーザーに電子メールを送信しようとする送信者は、この取り組みに準じ、配信に関する潜在的な問題を回避するため、この記事のガイダンスを十分に理解して実行してください。
  
これらのポリシーとガイドラインに準拠していない場合、Microsoft サポート チームの支援を受けられないことがあります。この資料に記されているガイドライン、プラクティス、ポリシーを遵守しているものの、送信 IP アドレスに関して配信の問題が解決されない場合、以下の手順に従って除外要求を送信してください。詳しくは、「 [リストから除外のポータルを使って、Office 365 の受信拒否リストから自分自身を削除する](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)」をご覧ください。
  
## <a name="general-microsoft-policies"></a>一般的な Microsoft ポリシー
<a name="GenMsftPolicies"> </a>

Office 365 ユーザーに送信する電子メールは、電子メールの転送と Office 365 の使用に関する Microsoft ポリシーすべてに準拠していなければなりません。
  
- Office 365 に適用可能なサービス条件。特に、スパムやマルウェアの配布を禁止するサービス条件。
    
- [Microsoft サービス規約](https://www.microsoft.com/servicesagreement/)
    
## <a name="governmental-regulations"></a>政府の規制
<a name="GovtRegulations"> </a>

Office 365 ユーザーに送信する電子メールは、所定の裁判管轄権における電子メール通信に関する、すべての該当する法律と規制に従う必要があります。
  
- [CAN-SPAM 法:ビジネスのためのコンプライアンス ガイド](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)
    
- [「削除してください」。応答と責任: 電子メールのマーケティング担当者は「登録解除」要求を受け入れる必要がある](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)
    
## <a name="technical-guidelines"></a>テクニカル ガイドライン
<a name="TechGuidelines"> </a>

Office 365 に送信する電子メールは、次のドキュメントに記載されている該当する推奨事項に準拠している必要があります (一部のリンクは英語版のみです)。
  
- [RFC 2505:SMTP MTA のスパム対策の推奨事項](https://www.ietf.org/rfc/rfc2505.txt)
    
- [RFC 2920:コマンド パイプラインの SMTP サービス拡張機能](https://www.ietf.org/rfc/rfc2920.txt)
    
さらに、Office 365 に接続する電子メール サーバーは、次の要件に従う必要もあります。
  
- 送信者は、インターネット協会のインターネット技術標準化委員会 (IETF) が発行しているインターネット電子メールの送信に関する技術的な標準 (RFC 5321、RFC 5322 など) すべてに準拠していなければなりません。 
    
- 500 から 599 までの数字の SMTP エラー メッセージ コード (別名、永続的な配信不能レポート (NDR)) を受け取る場合、送信者はそのメッセージを対象の受信者に再送信してはなりません。
    
- 何度か配信不能応答が出されたなら、送信者は対象の受信者に対して電子メールの送信を中止する必要があります。
    
- 安全でない電子メール中継サーバーまたはプロキシ サーバー経由でメッセージを転送しないでください。
    
- 登録解除する方法は、個別のリストからであれ、送信者がホストするすべてのリストからであれ、受信者が簡単に見つけて実行できるように明記されている必要があります。
    
- 動的 IP 領域からの接続は受け付けられません。
    
- 電子メール サーバーでは逆引き DNS レコードを有効にしておく必要があります。
    
## <a name="reputation-management"></a>評判の管理
<a name="RepManagement"> </a>

送信者、ISP、およびその他のサービス プロバイダーは、積極的に、外部 IP アドレスの評価を管理する必要があります。
  
## <a name="office-365-limits"></a>Office 365 の制限
<a name="sectionSection4"> </a>

送信者は、「[Exchange Online Protection の制限](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx)」に記載されている Office 365 の制限に従わなければなりません。
  
## <a name="email-delivery-resources-and-organizations"></a>電子メール配信リソースと組織
<a name="sectionSection5"> </a>

Microsoft は、インターネットと電子メールのエコシステムを改善するために業界団体およびサービス プロバイダーと積極的に連携しています。これらの組織は、Microsoft がサポートし、送信者が準ずるよう推奨されているベスト プラクティスに関する資料を公開しています。これによって、世界の複数の電子メール サービス プロバイダー間で電子メールを配信することがより容易になります。
  
- [Messaging Malware Mobile Anti-Abuse Working Group](https://www.m3aawg.org/)
    
- [オンラインの信頼アライアンス](https://www.otalliance.org/resources)
    
- [Email Sender &amp; Provider Coalition](http://www.espcoalition.org/)
    
## <a name="abuse-and-spam-reporting"></a>迷惑行為とスパムの報告
<a name="AbuseSpamReports"> </a>

迷惑メールや不適切な迷惑メールを報告するには、 [Outlook on the web で迷惑メールとフィッシング詐欺を報告](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)してください。 これらの種類の通信を送信することは、Microsoft ポリシーに違反するものであり、確認レポートに基づいて適切な処置が取られます。
  
## <a name="law-enforcement"></a>法的処置
<a name="sectionSection7"> </a>

司法当局の一員で Office 365 に関する法的文書に関して Microsoft Corporation を支援してくださる方、または Microsoft に提出した法的文書に関して質問がある方は、(1) (425) 722-1299 までお電話ください。
  

