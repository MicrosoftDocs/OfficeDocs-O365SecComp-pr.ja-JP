---
title: Office 365 Advanced Threat Protection
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 03/28/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection には、安全な添付ファイル、安全なリンク、高度なフィッシング詐欺対策ツール、レポート ツール、および脅威インテリジェンス機能が含まれています。
ms.openlocfilehash: d9dda9b19f601e26d01a18f7602f4fae3e0a0cb4
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761723"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

> [!IMPORTANT]
> この記事は、[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) をご利用の法人のお客様を対象としています。 Outlook.com、Office 365 Home、または Office 365 Personal を使用していて、Outlook の安全なリンクに関する情報を探している場合は、「[Outlook.com の高度なセキュリティ](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

## <a name="overview"></a>概要

Office 365 Advanced Threat Protection (ATP) は、電子メール メッセージ、リンク (URL) や共同作業ツールによって生じる悪意のある脅威から組織を保護します。 ATP には、次のものが含まれます:

- [脅威保護ポリシー](#configure-atp-policies): 脅威保護ポリシーを定義して、組織に適切なレベルの保護を設定します。 

- [レポート](#view-atp-reports): 組織の ATP パフォーマンスを監視するリアルタイム レポートを表示します。 

- [脅威の調査および反応機能](#use-threat-investigation-and-response-capabilities): 最先端のツールを使用して、脅威を調査、把握、シミュレーション、および回避を行います。 

- [自動調査および対応機能](#save-time-with-automated-investigation-and-response): 脅威の調査と軽減にかかる時間と労力を節約します。

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP プラン 1 およびプラン 2

ATP は Office 365 E5 に含まれています。ただし、ATP プラン 1 および ATP プラン 2 は、それぞれ特定のサブスクリプションのアドオンとして使用できます。 詳細については、「[ATP プランで利用できる機能](https://docs.microsoft.com/ja-JP/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)」を参照してください。

## <a name="configure-atp-policies"></a>ATP ポリシーを構成する

Office 365 ATP には、組織に適切なレベルの保護を設定する多くのツールが用意されています。 

組織のセキュリティ チームは、Office 365 セキュリティ/コンプライアンス センターで、各 ATP ツールのポリシーを定義する必要があります。 [**脅威の管理**] > [**ポリシー**] に移動して、ポリシー オプションにアクセスします。 (これに関するヘルプを表示するには「[クイック スタート ガイド: Office 365 Advanced Threat Protection のセットアップ](checklist-atp-setup.md)」を参照してください。)

組織で定義されているポリシーにより、定義済み脅威に対する動作と保護レベルが決まります。 ポリシー オプションは、非常に柔軟です。 たとえば、組織のセキュリティ チームは、ユーザー、組織、受信者、ドメイン レベルで詳細に脅威保護を設定できます。 新しい脅威や課題が毎日出現するため、ポリシーを定期的に確認することが重要です。  

- [ATP の安全な添付ファイル機能](atp-safe-attachments.md): 悪意のあるコンテンツのメールの添付ファイルを確認して、メッセージング システムを保護できるゼロデイ保護機能を提供します。 ウイルス/マルウェアの署名を持たないすべてのメッセージと添付ファイルを特別な環境にルートし、機械学習と分析技術を使用して悪意を検出します。 疑わしいアクティビティが見つからない場合、メッセージはメールボックスに転送されます。 詳細については、「[Office 365 ATP の安全な添付ファイル ポリシーを設定する](set-up-atp-safe-attachments-policies.md)」を参照してください。

- [ATP の安全なリンク](atp-safe-links.md): メール メッセージや Office ファイル内など、URL をクリック時に検証を行います。 保護は継続的に行われ、メッセージおよび Office 環境全体に適用されます。 クリックごとにリンクがスキャンされます。安全なリンクは常にアクセスでき、悪意のあるリンクは動的にブロックされます。 詳細については、「[Office 365 ATP の安全なリンク ポリシーを設定する](https://docs.microsoft.com/ja-JP/office365/securitycompliance/set-up-atp-safe-links-policies)」をご覧ください。 

- [SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md): チーム サイトやドキュメント ライブラリ内の悪意のあるファイルを特定してブロックすることで、ユーザーが共同作業し、ファイルを共有するときに組織を保護します。 詳細については、「[SharePoint、OneDrive、Microsoft の Office 365 ATP を有効にする](turn-on-atp-for-spo-odb-and-teams.md)」を参照してください。 

- [ATP のフィッシング詐欺対策保護](atp-anti-phishing.md): ユーザーおよびカスタム ドメインの偽装を検出します。 この機能は、コンピューターの学習モデルや高度な偽装検出アルゴリズムを適用してフィッシング攻撃に回避します。 詳細については、「[Office 365 の ATP フィッシング対策とフィッシング対策ポリシーをセットアップする](set-up-anti-phishing-policies.md)」を参照してください。

## <a name="view-atp-reports"></a>ATP レポートを表示する

Office 365 ATP には、ATP のパフォーマンスを監視する高度な[レポート ダッシュボード](view-reports-for-atp.md)が含まれています。 このにアクセスするには、セキュリティ/コンプライアンス センターの [**レポート]、[ダッシュ ボード**] の順に移動します。 

レポートはリアルタイムで更新され、最新の分析情報を提供します。 また、これらのレポートは推奨事項を提供し、間近に迫った脅威を警告します。 定義済みレポートには次のものが含まれます: 

- [脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)

- [脅威保護の状態レポート](view-reports-for-atp.md#threat-protection-status-report)

- [ATP ファイルの種類レポート](view-reports-for-atp.md#atp-file-types-report)

- [ATP メッセージの廃棄レポート](view-reports-for-atp.md#atp-message-disposition-report)

- 他にも多数あります。 

## <a name="use-threat-investigation-and-response-capabilities"></a>脅威の調査および対応機能を使用する

Office 365 ATP プラン 2 には、組織のセキュリティ チームが悪意のある攻撃を予測、把握、および回避するために、クラス最高の[脅威の調査および対応のツール](office-365-ti.md)が含まれます。 

- [脅威トラッカー](threat-trackers.md)は、一般的なサイバーセキュリティの問題に関する最新のインテリジェンスを提供します。 たとえば、最新のマルウェアに関する情報を表示し、組織に対する実際の脅威になる前に対策を講じることができます。 使用可能な脅威トラッカーには、[[注目のトラッカー](threat-trackers.md#noteworthy-trackers)]、[[急上昇中のトラッカー](threat-trackers.md#trending-trackers)]、[[追跡されたクエリ](threat-trackers.md#tracked-queries)]、[[保存されたクエリ](threat-trackers.md#saved-queries)] があります。

- [脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md) (またはエクスプローラーとも呼ばれる) は、最新の脅威を特定して分析できるリアルタイムのレポートです。 カスタム期間のデータを表示するようにエクスプローラーを構成することができます。

- [攻撃シミュレータ](attack-simulator.md)を使用すると、組織の現実的な攻撃シナリオを実行して、脆弱性を特定することができます。 [表示名のスピア フィッシング攻撃](attack-simulator.md#display-name-spear-phishing-attack)、[パスワード スプレー攻撃](attack-simulator.md#password-spray-attack)、[ブルート フォース パスワード攻撃](attack-simulator.md#brute-force-password-attack)など、現在の種類の攻撃のシミュレーションを利用できます。
    
## <a name="save-time-with-automated-investigation-and-response"></a>自動化された調査と対応で時間を節約する

(**新機能!**) 潜在的なサイバー攻撃を調査している場合は、期限厳守です。 より早く脅威を特定して軽減するほど、組織はより良くなります。 Office 365 ATP プラン 2 には、 [自動調査および対応 (AIR)](automated-investigation-response-office.md) 機能が含まれます。 (これらの機能をまだ持っていない場合は、ATP プラン 2 ですぐに使用できるようになります。)

AIR には、アラートがトリガーされたときなどには自動的に、またはエクスプローラーのビューから手動で起動できるセキュリティ プレイブックのセットが含まれています。 AIR は、セキュリティ運用チームの脅威を軽減するための時間と労力を効果的かつ効率的に節約できます。 詳細については、「[Office 365 による自動調査と応答 (AIR)](automated-investigation-response-office.md)」を参照してください。

## <a name="permissions-required-to-use-atp-features"></a>ATP 機能を使用するために必要なアクセス許可

セキュリティ/コンプライアンス センターで ATP 機能にアクセスするには、適切な役割が割り当てられている必要があります。 次の表にいくつかの例があります:

|役割または役割グループ  |追加情報  |
|---------|---------|
|Office 365 グローバル管理者 |[Office 365 の管理者の役割について](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|セキュリティ管理者 |[Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/ja-JP/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織の管理 |[Exchange Online のアクセス許可](https://docs.microsoft.com/ja-JP/exchange/permissions-exo/permissions-exo) <br>および<br> [Exchange Online の PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

詳しくは、次のトピックを参照してください。

- [セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md) 

- [ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)

## <a name="get-office-365-atp"></a>Office 365 ATP を入手する

Office 365 ATP プラン 2 は、Office 365 Enterprise E5、Office 365 Education A5、および Microsoft 365 Business に含まれています。 サブスクリプションに Office 365 ATP が含まれていない場合は、特定のサブスクリプションのアドオンとして ATP プラン 1 または ATP プラン 2 を購入することができます。 詳細については、次のリソースを参照してください。

- ATP プランを含むサブスクリプションの一覧については、「[Office 365 Advanced Threat Protection (ATP) の可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)」を参照してください。

- プラン 1 と 2 に含まれる機能のリストについては、「[Advanced Threat Protection (ATP) の各プランで利用できる機能](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)」を参照してください。

- プランの比較と Office 365 ATP の購入については、「[適切な Office 365 Advanced Threat Protection を入手する](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)」を参照してください。

## <a name="new-features-in-office-365-atp"></a>Office 365 ATP の新機能

新しい機能は、Office 365 ATP に継続的に追加されます。 詳細については、次のリソースを参照してください。

- [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)は、開発およびロール アウトの新機能の一覧を提供します。

- [Office 365 Advanced Threat Protection サービスの説明](https://docs.microsoft.com/ja-JP/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)では、ATP プラン全体の機能と可用性について説明します。
