---
title: Microsoft 365 セキュリティのデータを監視および報告する
description: 許可されていないデータの開示につながる可能性があるユーザーアクティビティを追跡する方法について説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティセンター、モニター、レポート、データ
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 741daff150ef52ef99c3da31159c02bc9431757f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263236"
---
# <a name="monitor-and-report-data-in-microsoft-365-security"></a><span data-ttu-id="fbdc0-104">Microsoft 365 セキュリティのデータを監視および報告する</span><span class="sxs-lookup"><span data-stu-id="fbdc0-104">Monitor and report data in Microsoft 365 security</span></span>

<span data-ttu-id="fbdc0-105">**データ**カテゴリは、承認されていないデータの開示につながる可能性があるユーザーアクティビティを追跡するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="fbdc0-105">The **Data** category helps track user activity that could lead to unauthorized data disclosure.</span></span> <span data-ttu-id="fbdc0-106">これらは、既存の Office 365 dlp ポリシーレポートに加えて、サードパーティの dlp ポリシー一致レポートを作成したものです。</span><span class="sxs-lookup"><span data-stu-id="fbdc0-106">These are the rework of existing Office 365 DLP policy reports plus a 3rd party DLP policy match report.</span></span>

<span data-ttu-id="fbdc0-107">次の点を確認できます。</span><span class="sxs-lookup"><span data-stu-id="fbdc0-107">You can see:</span></span>

* <span data-ttu-id="fbdc0-108">クラウドアプリから最も多くのファイルを共有するユーザー</span><span class="sxs-lookup"><span data-stu-id="fbdc0-108">Users who share the most files from cloud apps</span></span>
* <span data-ttu-id="fbdc0-109">一致した DLP ポリシーの数</span><span class="sxs-lookup"><span data-stu-id="fbdc0-109">How many DLP policy matches occurred</span></span>
* <span data-ttu-id="fbdc0-110">無視される DLP ポリシーまたは誤検知の数の報告</span><span class="sxs-lookup"><span data-stu-id="fbdc0-110">How many DLP policies overrides or false positives are reported</span></span>
* <span data-ttu-id="fbdc0-111">Microsoft cloud App Security を介してサードパーティのクラウドサービスで発生した DLP ポリシーの一致数</span><span class="sxs-lookup"><span data-stu-id="fbdc0-111">How many DLP policy matches happened in 3rd party cloud services via Microsoft Cloud App Security</span></span>

![「monitoring & reports」ページのデータカテゴリ](./media/security-docs/data.png)
