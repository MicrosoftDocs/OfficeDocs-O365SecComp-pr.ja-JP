---
title: Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/28/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection には、安全な添付ファイル、安全なリンク、高度なフィッシング対策ツール、レポートツール、および脅威インテリジェンス機能が含まれています。
ms.openlocfilehash: 903e089af172d8eac414aea69af75fcd696d5f20
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408382"
---
# <a name="office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection

> [!IMPORTANT]
> この記事は、Office 365 Enterprise および Microsoft 365 Enterprise のお客様を対象としています。 Outlook.com、Office 365 Home、または Office 365 Personal を使用していて、Outlook での安全なリンクに関する情報をお探しの場合は、「 [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

## <a name="overview"></a>概要

Office 365 Advanced Threat Protection (ATP) は、電子メールメッセージ、リンク (Url)、およびコラボレーションツールがもたらす悪意のある脅威から組織を保護します。 ATP の内容は次のとおりです。

- [脅威保護ポリシー](#configure-atp-policies): 脅威保護ポリシーを定義して、組織に適したレベルの保護を設定します。 

- [レポート](#view-atp-reports): 組織内の ATP のパフォーマンスを監視するためのリアルタイムレポートを表示します。 

- [脅威の調査と応答の機能](#use-threat-investigation-and-response-capabilities): トップエッジツールを使用して、脅威の調査、理解、シミュレーション、および防止を行います。 

- 自動化された[調査と応答の機能](#save-time-with-automated-investigation-and-response): 脅威を調査および軽減する時間と労力を節約します。

## <a name="office-365-atp-plan-1-and-plan-2"></a>Office 365 ATP プラン1およびプラン2

ATP は Office 365 E5 に含まれています。ただし、ATP プランと ATP プラン2は、それぞれ特定のサブスクリプションのアドオンとして使用できます。 詳細については、「 [ATP プランで利用できる機能](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)」を参照してください。

## <a name="configure-atp-policies"></a>ATP ポリシーを構成する

Office 365 ATP には、組織に適したレベルの保護を設定するための多数のツールが用意されています。 

組織のセキュリティチームは、Office 365 Security & コンプライアンスセンターの各 ATP ツールに対してポリシーを定義する必要があります。 [**脅威管理** > **ポリシー** ] に移動して、[ポリシーオプションにアクセスします。 (詳細については、「[クイックスタートガイド: Office 365 Advanced Threat Protection をセットアップ](checklist-atp-setup.md)する」を参照してください)。

組織に対して定義されているポリシーによって、定義済みの脅威の動作と保護レベルが決まります。 ポリシーオプションは、非常に柔軟です。 たとえば、組織のセキュリティチームは、ユーザー、組織、受信者、およびドメインレベルできめ細かな脅威保護を設定できます。 新しい脅威や課題が日々浮上するため、ポリシーを定期的に確認することが重要です。  

- [ATP の安全な添付ファイル](atp-safe-attachments.md): 悪意のあるコンテンツの電子メールの添付ファイルを確認することによって、メッセージングシステムを保護するゼロ日の保護を提供します。 ウイルス/マルウェアの署名を持たないすべてのメッセージと添付ファイルを特別な環境にルーティングし、機械学習と分析の手法を使用して悪意のある目的を検出します。 疑わしい動作が見つからない場合、メッセージはメールボックスに転送されます。 詳細については、「 [Office 365 ATP の安全な添付ファイルのポリシーを](set-up-atp-safe-attachments-policies.md)セットアップする」を参照してください。

- [ATP の安全なリンク](atp-safe-links.md): 電子メールメッセージおよび Office ファイル内での url の確認時間の確認を提供します。 保護は進行中で、メッセージングおよび Office 環境全体に適用されます。 各クリックでリンクがスキャンされます。安全なリンクは常にアクセス可能で、悪意のあるリンクは動的にブロックされます。 詳細については、「 [Office 365 ATP 安全リンクポリシー](https://docs.microsoft.com/en-us/office365/securitycompliance/set-up-atp-safe-links-policies)のセットアップ」を参照してください。 

- [SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md): チームサイトおよびドキュメントライブラリ内の悪意のあるファイルを特定してブロックすることにより、ユーザーがファイルを共同作業したり、共有したりするときに組織を保護します。 詳細については、「 [Turn On Office 365 ATP For SharePoint, OneDrive, And Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)」を参照してください。 

- [ATP のフィッシング対策保護](atp-anti-phishing.md): ユーザーおよびカスタムドメインの偽装の試行を検出します。 これは、機械学習モデルと高度な偽造検知アルゴリズムを avert フィッシング攻撃に適用します。 詳細については、「 [Office 365 の ATP のフィッシング対策およびフィッシング対策ポリシー](set-up-anti-phishing-policies.md)をセットアップする」を参照してください。

## <a name="view-atp-reports"></a>ATP レポートを表示する

Office 365 ATP には、ATP のパフォーマンスを監視するための高度な[レポートダッシュボード](view-reports-for-atp.md)が含まれています。 これは、Security & コンプライアンスセンターの**Reports _GT_ Dashboard**でアクセスできます。 

最新の洞察を提供して、リアルタイムで更新を報告します。 これらのレポートでは、推奨事項も提供されており、脅威を差し迫っていることを警告します。 定義済みのレポートには、以下のものがあります。 

- [脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)

- [脅威保護の状態レポート](view-reports-for-atp.md#threat-protection-status-report)

- [ATP ファイルタイプレポート](view-reports-for-atp.md#atp-file-types-report)

- [ATP メッセージディスポジションレポート](view-reports-for-atp.md#atp-message-disposition-report)

- ...その他。 

## <a name="use-threat-investigation-and-response-capabilities"></a>脅威の調査と応答の機能を使用する

Office 365 ATP プラン2には、クラスの適切な[脅威調査および応答ツール](office-365-ti.md)が含まれており、組織のセキュリティチームが悪意のある攻撃を予測、理解、および阻止することができます。 

- [脅威のトラッカー](threat-trackers.md)は、優先 cybersecurity の問題に関する最新のインテリジェンスを提供します。 たとえば、最新のマルウェアに関する情報を表示して、組織の実際の脅威になる前に対策を実行できます。 利用可能なトラッカーには、[注目すべきトラッカー](threat-trackers.md#noteworthy-trackers)、[傾向分析](threat-trackers.md#trending-trackers)、[追跡クエリ](threat-trackers.md#tracked-queries)、および[保存されたクエリ](threat-trackers.md#saved-queries)が含まれます。

- [脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)(エクスプローラーとも呼ばれます) は、最新の脅威を特定して分析できるリアルタイムレポートです。 カスタムの期間のデータを表示するようにエクスプローラーを構成できます。

- [アタックシミュレータ](attack-simulator.md)を使用すると、組織内で現実的な攻撃シナリオを実行して vulnerabilites を識別できます。 [表示名のスピアーフィッシング攻撃](attack-simulator.md#display-name-spear-phishing-attack)、[パスワードスプレー攻撃](attack-simulator.md#password-spray-attack)、[ブルートフォースパスワード攻撃](attack-simulator.md#brute-force-password-attack)など、現在の種類の攻撃のシミュレーションを利用できます。
    
## <a name="save-time-with-automated-investigation-and-response"></a>自動調査と応答による時間の節約

(**新**)潜在的なサイバー攻撃を調査している場合、時間は基本的なものです。 すぐに脅威を特定して軽減することができますが、組織の方が適しています。 Office 365 ATP プラン2には[、自動調査と応答 (AIR)](automated-investigation-response-office.md)機能が含まれるようになりました。 (これらの機能がまだインストールされていない場合は、ATP プラン2に近い時期になります)。

AIR には、アラートがトリガーされたときや、エクスプローラーのビューなどから手動で開始できるセキュリティプレイブックのセットが含まれています。 AIR を使用すると、セキュリティ運用チームの時間と、脅威を軽減するための労力を効果的かつ効率的に保存することができます。 詳細については、「 [Office 365 での自動調査と応答 (AIR)](automated-investigation-response-office.md)」を参照してください。

## <a name="permissions-required-to-use-atp-features"></a>ATP 機能を使用するために必要なアクセス許可

セキュリティ & コンプライアンスセンターの ATP 機能にアクセスするには、適切な役割が割り当てられている必要があります。 次の表は、いくつかの例を示しています。

|役割または役割グループ  |詳細については、リソースを参照してください  |
|---------|---------|
|Office 365 グローバル管理者 |[Office 365 の管理者の役割について](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|セキュリティ管理者 |[Azure Active Directory での管理者の役割のアクセス許可](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 組織の管理 |[Exchange Online でのアクセス許可](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>and<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

詳細については、以下を参照してください。

- [セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md) 

- [ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)

## <a name="get-office-365-atp"></a>Office 365 ATP を取得する

Office 365 ATP プラン2は、Office 365 Enterprise E5、Office 365 エデュケーション A5、および Microsoft 365 Business に含まれています。 サブスクリプションに Office 365 ATP が含まれていない場合は、特定のサブスクリプションへのアドオンとして ATP プラン1または ATP Plan 2 を購入することができます。 詳細については、以下のリソースを参照してください。

- ATP プランを含むサブスクリプションの一覧については、「 [Office 365 Advanced Threat Protection (ATP) availability](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) 」を参照してください。

- プラン1および2に含まれる機能の一覧については、「 [Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) Plan」の「機能の可用性」を参照してください。

- プランを比較し、Office 365 ATP を購入するに[は、「適切な office 365 Advanced Threat Protection を入手](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)する」を参照してください。

## <a name="new-features-in-office-365-atp"></a>Office 365 の新機能 ATP

新機能が Office 365 ATP に継続的に追加されます。 詳細については、以下のリソースを参照してください。

- [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)は、開発時に新機能の一覧を提供し、ロールアウトします。

- [Office 365 Advanced Threat Protection サービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)では、ATP プラン全体での機能と可用性について説明します。
