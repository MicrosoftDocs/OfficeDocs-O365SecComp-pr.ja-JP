---
title: Office 365 のお客様が管理の暗号化機能
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: は、Microsoft Office 365 のデータのリカバリ性を理解します。'
ms.openlocfilehash: e835587e07246154cd700555cc7263370bde8755
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531559"
---
# <a name="customer-managed-encryption-features-in-office-365"></a>Office 365 のお客様が管理の暗号化機能

Microsoft によって管理されている Office 365 の暗号化テクノロジ、Office 365 は、追加の暗号化テクノロジを管理でき、構成、次のようにも動作します。
- [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)
- [多目的インターネット メール拡張機能をセキュリティで保護します。](http://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)
- [Office 365 Message Encryption](http://products.office.com/en-us/exchange/office-365-message-encryption)
- [パートナー組織とセキュリティで保護されたメール フロー](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

これらのテクノロジの詳細については、 [Office 365 サービスの説明](https://technet.microsoft.com/en-us/library/office-365-service-descriptions.aspx)にもあります。

## <a name="azure-rights-management"></a>Azure Rights Management
[Azure の権限の管理](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)(Azure の RMS) は、[情報保護の Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)で使用される保護技術です。暗号化、id、および承認ポリシーを使用してヘルプのファイルを保護し、複数のプラットフォームとデバイスの間で電子メール、電話、タブレット、および pc の情報保護できます、組織の内外での保護が維持されるためデータです。Azure RMS ファイルのすべての種類の永続的な保護を提供するには、任意の場所にファイルを保護する、企業間のコラボレーション、および広い範囲の Windows と Windows 以外のデバイスをサポートしています。Azure の RMS による保護は、[データ損失防止 (DLP) のポリシー](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)を強化もできます。については、アプリケーションとサービス サービスを使用して Azure アクセス権管理 Azure の情報保護の詳細については、[アプリケーションが、Azure の権限の管理サービスをサポートする方法](https://docs.microsoft.com/information-protection/understand-explore/applications-support)を参照してください。

Azure の RMS は、Office 365 に統合し、すべての Office 365 のお客様に利用可能です。Azure の RMS を使用する Office 365 を構成するを参照してください。 [Azure アクセス権の管理と設定を使用する IRM を構成する SharePoint 管理センターの情報権利管理 (IRM) を](https://technet.microsoft.com/en-us/library/dn151475(v=exchg.150).aspx)。オンプレミスの Active Directory (AD) RMS サーバーを運用するかどうかは、することも[、設置型を使用する IRM を構成する AD RMS サーバー](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)、強くお勧めする[Azure RMS への移行](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms)を他のセキュリティで保護されたコラボレーションなどの新機能を使用するには組織。

Azure RMS に顧客データを保護すると、Azure RMS を使用して 2048 ビットの RSA 非対称キー sha-256 ハッシュ アルゴリズムでの整合性のデータを暗号化します。Office ドキュメントと電子メールのための対称キーは、AES 128 ビット (CBC モードと PKCS #7 パディング) です。各ドキュメントまたは Azure の RMS で保護された電子メールには、Azure RMS (、コンテンツ キーです)、1 つの AES キーを作成して、そのキーは、ドキュメントに埋め込まれているし、文書の版を通して持続します。コンテンツ キーは、ドキュメント内のポリシーの一部として組織の RSA キー (、Azure の情報保護のテナントはキーです) を使用して保護されているし、ポリシーは、ドキュメントの作成者が署名されてもします。このテナントのキーに共通するすべてのドキュメントおよび組織の Azure の RMS で保護されたメールは、Azure の情報保護管理者は、このキーを変更するだけ組織では、お客様が管理しているテナントのキーを使用している場合。Azure の RMS で使用される暗号化のコントロールの詳細についてを参照してください[Azure の RMS の動作ですか。内部で](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work)。

デフォルト Azure の RMS の実装では、Microsoft が生成し、各テナントに対して一意であるルート キーを管理します。お客様は、[前面の固有キー (BYOK)](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)と呼ばれるキーの管理方法を使用して、Azure キー ヴォールト ・ サービスを使用して RMS を Azure の場合は、そのルート キーのライフ サイクルを管理できます) を使用すると、設置型の Hsm にキーを生成し、このキーの制御を正しくキーをエクスポートまたはハードウェア セキュリティ モジュールを保護することから抽出することはできませんと、マイクロソフトの FIPS 140-2 レベル 2 検証 Hsm。 キーへのアクセス ルートへの転送は、担当者に表示されません。さらに、ルート キーに対するすべてのアクセスをいつでも表示、ほぼリアルタイムのログにアクセスすることができます。詳細については、[ログの記録と分析 Azure の権利管理の使用方法](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)を参照してください。

Azure のアクセス権管理支援は、wire-tapping、マニュアル、仲介者攻撃、データの盗用、組織の共有ポリシーの違反が意図的でないなどの脅威を軽減します。、同時にアクセスされ、不当な顧客データの転送中または休息を持っていないユーザー権限のないユーザーによって、適切なアクセス許可が間違った内データのリスクを軽減するため、データは手いずれかの方法に従うポリシーを使用してできませんでした意識的または無意識データ損失の防止機能を提供することとします。Azure の情報保護の一部として使用する場合は、Azure の RMS は、データのクラス分けし、機能、コンテンツのマーキング、ドキュメントのアクセスの追跡およびアクセス失効機能のラベル付けにも提供します。これらの機能に関する詳細については、 [Azure の情報の保護とは何です](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)、[情報保護の Azure 展開ロードマップ](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)、および[Azure の情報保護のためのクイック スタート チュートリアル](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)を参照してください。

## <a name="secure-multipurpose-internet-mail-extension"></a>多目的インターネット メール拡張機能をセキュリティで保護します。
/Multipurpose がセキュリティで保護されたインターネット メール拡張 (S/MIME) は、公開キー暗号方式と MIME データのデジタル署名の標準です。秒/MIME で定義されている Rfc 3369、3370、3850、3851、他のユーザーとします。これにより、ユーザーが電子メールを暗号化し、電子メールにデジタル署名できます。秒/MIME を使用して暗号化された電子メールは、その受信者には、秘密キーは、電子メールの受信者によってのみ解読できます。したがって、電子メールの受信者以外のユーザーによる電子メールを解読できません。

[マイクロソフトは、Office 365 では、S/MIME をサポートしています](http://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)。公開証明書はお客様のオンプレミスの Active Directory への分散し、Office 365 テナントにレプリケートする属性に格納されています。公開キーに対応する秘密キーは、設置型のままし、Office 365 に送信されることはありません。作成、暗号化、復号化、読み取り、および Outlook では、web、および Exchange ActiveSync クライアント上で Outlook を使用して組織内の 2 つのユーザー間の電子メールにデジタル署名をします。詳細については、 [Office 365 で S/MIME 暗号化](http://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)を参照してください。

## <a name="office-365-message-encryption"></a>Office 365 Message Encryption
[Office 365 のメッセージの暗号化](https://products.office.com/en-us/exchange/office-365-message-encryption)(ホーム) は、暗号化された送信してすべてのユーザーの権利で保護されたメール、 [Azure の情報の保護](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)(AIP) の上に構築されます。ホームでは、wire-tapping など、中間の攻撃の脅威および適切なアクセス許可を持っていないユーザー権限のないユーザーによるデータのされ、不当なアクセスなど、その他の脅威を軽減します。情報の保護を Azure 上に構築された、シンプルより直感的なセキュリティで保護された電子メール エクスペリエンスを提供するための投資を行った。組織の内外を問わずすべてのユーザーが Office 365 から送信されたメッセージを保護することができます。Azure Active Directory、Microsoft アカウントでは、Google の Id を含む、任意の id を使用してメール クライアントの多様なセットでは、これらのメッセージを表示できます。組織が暗号化されたメッセージを使用する方法の詳細については、 [Office 365 のメッセージの暗号化](https://support.office.com/article/F87CB016-7876-4317-AE3C-9169B311FF8A)を参照してください。

## <a name="transport-layer-security"></a>トランスポート ・ レイヤ ・ セキュリティ
パートナーとの通信をセキュリティで保護されたことを確認する場合は、セキュリティとメッセージの整合性を提供する受信および送信コネクタを使用できます。証明書を使用して、各コネクタに、強制の受信および送信 TLS を構成することができます。SMTP の暗号化されたチャネルを使用すると、データが中間の攻撃を使用して盗難防止できます。詳細については、[電子メール接続をセキュリティで保護する TLS を使用して Exchange オンライン](https://support.office.com/article/How-Exchange-Online-uses-TLS-to-secure-email-connections-in-Office-365-4CDE0CDA-3430-4DC0-B489-F2C0736C929F)を参照してください。

## <a name="domain-keys-identified-mail"></a>ドメインのキーは、メールを識別
Exchange オンライン保護 (EOP) および Exchange Online ドメイン キー確認メール (DKIM) メッセージの受信の検証をサポートします。DKIM は、メソッドの検証は、ユーザーから送信されたドメインからメッセージが送信されたことと、他のユーザーがスプーフィングされていないのです。電子メール メッセージを送信するには、責任を持つ組織に結合し、電子メールの暗号化の大きなパラダイムの一部であります。このパラダイムの 3 つの部分の詳細についてを参照してください。
- [スプーフィングを防止するために Office 365 で SPF を設定する](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)
- [DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)
- [DMARC を使用して Office 365 でメールを検証する](https://https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
