---
title: Office 365 で脅威に自動的に調査して応答する
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/04/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection プラン2の自動調査および応答機能の使用を開始します。
ms.openlocfilehash: 2c64ea936170524811839db7c593d67bfe11a928
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2019
ms.locfileid: "36762027"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a>Office 365 で脅威に自動的に調査して応答する

## <a name="overview"></a>概要

[Office 365 Advanced Threat Protection](office-365-atp.md)プラン2には自動調査と応答 (AIR) 機能が含まれており、セキュリティ運用チームの時間と、アラートと脅威を処理するための労力を節約できます。 Office 365 の機能の使用を開始するには、この記事をお読みください。 空気のしくみの詳細については、「 [Office 365 での自動調査と応答 (AIR)](automated-investigation-response-office.md)」を参照してください。

AIR を使用すると、特定のアラートがトリガーされ、1つ以上のセキュリティプレイブックが開始され、自動調査が開始します。 自動化された調査プロセスの最中および実行後に、管理者およびセキュリティ運用チームは次のことを行うことができます。

- [調査の詳細を表示する](#view-details-of-an-investigation)

- [調査の結果としてアクションを確認して承認する](#review-and-approve-actions) 

- [調査に関連する通知の詳細を表示する](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> この記事で説明されているタスクを実行するには、全体管理者、セキュリティ管理者、セキュリティオペレーター、またはセキュリティリーダーである必要があります。 詳細については、「 [Microsoft 365 セキュリティセンター: 役割とアクセス許可](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)」を参照してください。

## <a name="view-details-of-an-investigation"></a>調査の詳細を表示する

1. Office 365 の全体管理者、セキュリティ管理者、またはセキュリティ閲覧者[https://protection.office.com](https://protection.office.com)として、に移動して、サインインします。 これにより、セキュリティ & コンプライアンスセンターに移動できます。

2. 次のいずれかを実行します。

    - [**脅威管理** > ]**ダッシュボード**に移動します。 これにより、[セキュリティダッシュボード](security-dashboard.md)が表示されます。 エアウィジェットは、[セキュリティダッシュボード](security-dashboard.md)の上部に表示されます。 **調査の概要**などのウィジェットを選択します。

    - [**脅威管理** > の**調査**] に移動します。 

    どちらの方法でも、調査の一覧を取得できます。

    ![エアのメイン調査ページ](media/air-maininvestigationpage.png) 

3. 調査の一覧で、[ **ID** ] 列のアイテムを選択します。 これにより、調査の詳細ページが表示され、調査のグラフが開始されます。

    ![AIR 調査グラフページ](media/air-investigationgraphpage.png)

4. 調査の詳細については、さまざまなタブを使用してください。

## <a name="review-and-approve-actions"></a>アクションの確認と承認

Office 365 では、通常、自動調査は1つまたは複数の推奨されるアクションになります。 ただし、セキュリティ運用チームによって承認されるまで、アクションは実行されません。 アクションを確認して承認するには、以下の手順を使用します。

1. Office 365 の全体管理者、セキュリティ管理者、またはセキュリティ閲覧者[https://protection.office.com](https://protection.office.com)として、に移動して、サインインします。 

2. [**脅威管理** > の**調査**] に移動します。

3. 調査の一覧で、[ **ID** ] 列のアイテムを選択します。 

3. 調査の詳細ビューで、[**操作**] タブを選択します。承認待ちのすべてのアクションがここに表示されます。

4. リストからアイテムを選択します。

5. 推奨されるアクションを実行する場合は [**承認**] を選択します (アクションを行わずに調査を終了する場合は**拒否**)。

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>調査に関連する通知の詳細を表示する

特定の種類の通知では、Office 365 で自動調査がトリガーされます。 詳細については、「 [Alerts](automated-investigation-response-office.md#alerts)」を参照してください。 次の手順を使用して、自動調査に関連付けられている通知の詳細を表示します。

1. Office 365 の全体管理者、セキュリティ管理者、またはセキュリティ閲覧者[https://protection.office.com](https://protection.office.com)として、に移動して、サインインします。 これにより、セキュリティ & コンプライアンスセンターに移動できます。

2. [**脅威管理** > の**調査**] に移動します。

3. 調査の一覧で、[ **ID** ] 列のアイテムを選択します。 

4. 調査の詳細を開いた状態で、[**通知**] タブを選択します。調査をトリガーしたアラートが一覧表示されています。

5. リストからアイテムを選択します。 ポップアップが開き、通知に関する詳細と追加情報およびアクションへのリンクが表示されます。

6. ポップアップの情報を確認し、特定の通知に応じて、ユーザーの**解決**、**抑制**、または**通知**などのアクションを実行します。 

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>カスタムまたはサードパーティのレポートソリューションに Office 365 Management Activity API を使用する

組織でカスタムレポートソリューションを使用している場合、またはサードパーティのレポートソリューションを使用している場合は、Office 365 Management Activity API を使用して、そのソリューションの自動化された調査に関する情報を表示することができます。

これを設定するには、次のリソースを使用します。

|リソース  |説明  |
|---------|---------|
|[Office 365 管理 API の概要](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |Office 365 管理アクティビティ API は、Office 365 と Azure Active Directory のアクティビティ ログからの、ユーザー、管理者、システム、およびポリシー アクションとポリシー イベントについての情報を提供します。         |
|[Office 365 管理 API の使用を開始する](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |Office 365 管理 API は、Azure AD を使用して、アプリケーションが Office 365 データにアクセスするための認証サービスを提供します。 これを設定するには、この記事の手順に従います。          |
|[Office 365 管理アクティビティ API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |Office 365 Management Activity API を使用して、Office 365 および Azure AD のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得することができます。 この機能の詳細については、この記事を参照してください。        |
|[Office 365 管理アクティビティ API のスキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |Office 365 Management Activity API を通じて使用できる特定の種類のデータについて理解するために、[共通スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)と[OFFICE 365 の ATP および脅威の調査および応答スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)の概要を説明します。         |

## <a name="next-steps"></a>次のステップ

[通知の詳細情報](alert-policies.md)

[Office 365 で配信された悪意のある電子メールを手動で検索して調査する](investigate-malicious-email-that-was-delivered.md)

[Microsoft Defender ATP のエアダスターの詳細](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[Microsoft 365 ロードマップを参照して、近日中およびロールアウトされているものを確認します。](https://www.microsoft.com/microsoft-365/roadmap?filters=)