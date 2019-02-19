---
title: Office 365 のお客様が管理する暗号化機能
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: Microsoft Office 365 のデータ復元性について理解します。'
ms.openlocfilehash: 26abb93e491a183c5c307dde8055f1050e16068c
ms.sourcegitcommit: 24659bdb09f49d0ffed180a4b80bbb7c45c2d301
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2019
ms.locfileid: "29664123"
---
# <a name="customer-managed-encryption-features-in-office-365"></a>Office 365 の顧客が管理する暗号化機能

Microsoft によって管理される office 365 の暗号化テクノロジとともに、office 365 は、次のような管理および構成が可能な追加の暗号化テクノロジにも対応しています。
- [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)
- [セキュリティで保護されたマルチパーパスインターネットメール内線番号](http://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)
- [Office 365 Message Encryption](http://products.office.com/en-us/exchange/office-365-message-encryption)
- [パートナー組織とのセキュリティで保護されたメールフロー](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

これらのテクノロジに関する追加情報については、「 [Office 365 のサービスの説明](https://technet.microsoft.com/en-us/library/office-365-service-descriptions.aspx)」も参照してください。

## <a name="azure-rights-management"></a>Azure Rights Management
[Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)(azure RMS) は、 [azure Information protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)で使用される保護テクノロジです。暗号化、id、および承認ポリシーを使用して、複数のプラットフォームとデバイス (電話、タブレット、pc) 間でファイルと電子メールをセキュリティで保護することができます。保護が維持されるため、組織の内部と外部の両方で情報を保護することができます。データ。Azure RMS は、すべてのファイルの種類の永続的な保護を提供し、どこからでもファイルを保護し、ビジネス間のコラボレーション、および幅広い windows デバイスと windows 以外のデバイスをサポートします。Azure RMS 保護は、[データ損失防止 (DLP) ポリシー](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)を強化することもできます。azure information Protection から azure rights management サービスを使用できるアプリケーションとサービスの詳細については、「[アプリケーションが azure rights management サービスをサポートする方法](https://docs.microsoft.com/information-protection/understand-explore/applications-support)」を参照してください。

Azure RMS は office 365 と統合されており、すべての office 365 のお客様が利用できます。azure RMS を使用するように Office 365 を構成するには、「 [azure Rights management を使用するように IRM を構成し、SharePoint 管理センターで Information Rights management (IRM) を設定](https://technet.microsoft.com/en-us/library/dn151475(v=exchg.150).aspx)する」を参照してください。オンプレミスの Active Directory (AD) rms サーバーを運用している場合は、[オンプレミスの ad rms サーバーを使用する](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)ように IRM を構成することもできますが、他のユーザーとのセキュリティで保護されたコラボレーションなどの新機能を使用するには、 [Azure RMS に移行](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms)することを強くお勧めします。団体.

azure rms を使用して顧客データを保護する場合、azure rms は整合性を確保するために、2048ビットの RSA 非対称キーと SHA-256 ハッシュアルゴリズムを使用してデータを暗号化します。Office ドキュメントおよび電子メールの対称キーは、AES 128 ビット (CBC モードの PKCS # 7 padding) です。azure rms によって保護されているドキュメントまたは電子メールごとに、1つの AES キー ("コンテンツキー") が作成され、そのキーはドキュメントに埋め込まれており、ドキュメントの各エディションで保持されます。コンテンツキーは、組織の RSA キー ("Azure Information Protection テナントキー") によってドキュメント内のポリシーの一部として保護され、そのポリシーはドキュメントの作成者によっても署名されます。このテナントキーは、組織で azure RMS によって保護されているすべてのドキュメントと電子メールに共通であり、このキーは、組織が顧客管理のテナントキーを使用している場合にのみ、azure Information Protection 管理者が変更できます。azure rms で使用される暗号化コントロールの詳細については、「azure rms のしくみ」を参照してください[。[内部] に](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work)あります。

既定の Azure RMS 実装では、Microsoft はテナントごとに一意のルートキーを生成して管理します。お客様は、オンプレミスの hsm でキーを生成できるキーの管理方法[(byok)](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)を使用して、azure key Vault サービスを使用して azure RMS のルートキーのライフサイクルを管理することができます。Microsoft の FIPS 140-2 レベル 2-検証された hsm に転送します。キーをエクスポートしたり、ハードウェアセキュリティモジュールから展開したりすることはできないため、ユーザーにはルートキーへのアクセス権は付与されません。さらに、ほぼリアルタイムログには、いつでもルートキーへのすべてのアクセス権が表示されます。詳細については、「 [Azure Rights Management の使用状況のログと分析](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)」を参照してください。

Azure Rights Management を使用すると、ワイヤタップ、man-in-the-middle 攻撃、データ窃盗、組織の共有ポリシーの意図しない違反などの脅威を軽減できます。同時に、適切なアクセス許可を持たない、承認されていないユーザーによる、送信中または保存中の顧客データの unwarranted アクセスは、そのデータに準拠するポリシーによって禁止されるため、そのデータが不適切なユーザーによって発生するリスクを軽減します。knowingly または気付かずに、データ損失防止機能を提供します。azure Information Protection の一部として使用されている場合、azure RMS はデータ分類とラベル付け機能、コンテンツマーキング、ドキュメントアクセス追跡、およびアクセス取り消し機能も提供します。これらの機能の詳細について[](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)は、「azure information protection」、「 [azure information protection 展開ロードマップ](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)」、および「 [Quick start チュートリアル for azure information protection](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)」を参照してください。

## <a name="secure-multipurpose-internet-mail-extension"></a>セキュリティで保護されたマルチパーパスインターネットメール内線番号
Secure/多目的インターネットメール内線 (S/mime) は、公開キー暗号化と MIME データのデジタル署名の標準です。S/MIME は、rfc 3369、3370、3850、3851、その他で定義されています。これにより、ユーザーは電子メールを暗号化し、電子メールにデジタル署名することができます。S/MIME を使用して暗号化された電子メールは、秘密キーを使用して電子メールの受信者によってのみ復号化できます。これは、その受信者のみが利用できます。そのため、電子メールの受信者以外は誰でも電子メールを復号化できません。

[Microsoft では、Office 365 で S/MIME をサポート](http://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)しています。パブリック証明書は、お客様のオンプレミスの Active Directory に配布され、Office 365 テナントにレプリケートできる属性に格納されます。公開キーに対応する秘密キーはオンプレミスのままであり、Office 365 に送信されることはありません。ユーザーは、outlook、web 上の outlook、および Exchange ActiveSync クライアントを使用して、組織内の2人のユーザー間で電子メールを作成、暗号化、暗号化解除、読み取り、およびデジタル署名することができます。詳細については、「 [Office 365 での S/MIME 暗号化の現在](http://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)の状態」を参照してください。

## <a name="office-365-message-encryption"></a>Office 365 Message Encryption
[Office 365 メッセージの暗号化](https://products.office.com/en-us/exchange/office-365-message-encryption)(OME) [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) (AIP) の上に構築され、暗号化され、権利で保護されたメールをだれにでも送信できます。OME は、ワイヤタップや man-in-the-middle 攻撃などの脅威、および適切なアクセス許可を持たない、承認されていないユーザーによるデータの unwarranted アクセスなどの脅威を軽減します。Azure Information Protection の上に構築された、よりシンプルで直感的な安全な電子メールの操作性を提供する投資が行われています。Office 365 から組織の内部または外部のすべてのユーザーに送信されるメッセージを保護することができます。これらのメッセージは、Azure Active Directory、Microsoft アカウント、Google id などの任意の id を使用して、さまざまなメールクライアントのセットで表示できます。組織が暗号化されたメッセージを使用する方法の詳細については、「 [Office 365 Message Encryption](https://support.office.com/article/F87CB016-7876-4317-AE3C-9169B311FF8A)」を参照してください。

## <a name="transport-layer-security"></a>トランスポート層セキュリティ
パートナーとの通信をセキュリティで保護する場合は、受信コネクタと送信コネクタを使用してセキュリティとメッセージの整合性を確保できます。証明書を使用して、各コネクタで強制受信および送信 TLS を構成できます。暗号化された SMTP チャネルを使用すると、man-in-the-middle 攻撃によってデータが盗まれるのを防ぐことができます。詳細については、「 [Exchange Online が TLS を使用して電子メール接続をセキュリティで保護する方法](https://support.office.com/article/How-Exchange-Online-uses-TLS-to-secure-email-connections-in-Office-365-4CDE0CDA-3430-4DC0-B489-F2C0736C929F)」を参照してください。

## <a name="domain-keys-identified-mail"></a>ドメインキーによって識別されたメール
exchange online Protection (EOP) および exchange online では、ドメインキー識別メール (dkim) メッセージの受信検証をサポートしています。dkim は、メッセージがドメインから送信されたことを検証する方法です。これは、そのメッセージが送信者からのものであり、他のユーザーによってスプーフィングされていないことを示します。電子メールメッセージを送信しようとしている組織に関連付け、電子メールの暗号化に関して大きなパラダイムの一部となります。このパラダイムの3つの部分の詳細については、以下を参照してください。
- [スプーフィングを防止するために Office 365 で SPF を設定する](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)
- [DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)
- [DMARC を使用して Office 365 でメールを検証する](https://https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
