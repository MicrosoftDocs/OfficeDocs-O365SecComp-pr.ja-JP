---
title: Microsoft 365 セキュリティでのアプリの状態を監視および報告する
description: 組織でクラウドアプリを使用する方法について詳しく説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、モニター、レポート、アプリ
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 02cc511532f65172aba2c0f98cdf594776f586a5
ms.sourcegitcommit: ef27da3ea5340d6e7a2eaa1288e2e005ef8e4788
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2019
ms.locfileid: "30791796"
---
# <a name="monitor-and-report-app-status-in-microsoft-365-security"></a>Microsoft 365 セキュリティでのアプリの状態を監視および報告する

[!include[Prerelease�information](prerelease.md)]

これらのレポートでは、組織でクラウドアプリがどのように使用されているかについて、より多くの洞察を得ることができます。これには、アプリの種類、リスクレベル、アラートなどがあります。

## <a name="monitor-email-accounts-at-risk"></a>危険にさらされるメールアカウントを監視する

**電子メール保護**は、危険にさらされている電子メールアカウントを示します。 Windows Defender セキュリティセンターでは、アカウントをクリックしてさらに調査することができます。

![電子メール保護カード](./media/security-docs/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>ユーザーによって付与されるアプリのアクセス許可を監視する

**cloud app security-OAuth アプリ**は、ユーザーによってアクセス許可が付与されている cloud app security によって検出されたアプリを一覧表示します。 Cloud App Security のリスクカタログには、16000を超えるリスク要因を使用して評価されるのアプリが含まれています。

リスク要因は、アプリの発行元などの一般的な情報から、アプリケーションが rest での暗号化をサポートしているかどうか、またはユーザーアクティビティの監査ログを提供するかどうかなど、一般的な情報から始めて、セキュリティ対策や統制を開始します。

![Cloud App Security OAuth アプリカード](./media/security-docs/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>cloud app のユーザーアカウントを監視する

**確認のためのクラウドアプリアカウントに**は、注意が必要なアカウントが一覧表示されます。

![レビューカード用の Cloud App アカウント](./media/security-docs/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>使用されているクラウドアプリを理解する

検出された**クラウドアプリ (カテゴリ)** は、組織で使用されているアプリの種類と、cloud App Security でのクラウド検出ダッシュボードへのリンクを示しています。 詳細については、「[クイックスタート: 検出されたアプリの操作](https://docs.microsoft.com/cloud-app-security/discovered-apps)」を参照してください。  

![検出されたクラウドアプリのカテゴリカード](./media/security-docs/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>ユーザーがクラウドアプリにアクセスする監視を監視する

**クラウドアプリのアクティビティの場所**は、ユーザーがクラウドアプリにアクセスする場所を示しています。

![クラウドアプリのアクティビティの場所カード](./media/security-docs/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>インフラストラクチャの負荷の状態を監視する

**インフラストラクチャの状態**Azure セキュリティセンターのインフラストラクチャワークロードの正常性状態アラートを表示します。

Azure セキュリティセンターでは、オンプレミスとクラウドのワークロード全体にわたる統合セキュリティ管理と高度な脅威保護が提供されます。 ファイアウォールやその他のパートナーソリューションを含む、さまざまなソースからのセキュリティデータを収集、検索、および分析することができます。

詳細については、「 [Azure セキュリティセンターのドキュメント](https://docs.microsoft.com/azure/security-center/)」を参照してください。

![インフラストラクチャ正常性カード](./media/security-docs/infrastructure-health.png)
