---
title: Project Server の GDPR
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: オンプレミスの Project Server で GDPR の要件に対応する方法について説明します。
ms.openlocfilehash: 8fb29c2d383c03c79d619d2c78df75cffb4eab27
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154499"
---
# <a name="gdpr-for-project-server"></a>Project Server の GDPR

Project Server では、Project Web App でユーザー データをエクスポートしたり編集したりするために、カスタム スクリプトが使用されます。基本的な処理は、次のとおりです。

1.  ファーム内で Project Web App のサイトを検索します。

2.  各サイトの中で、ユーザーが含まれているプロジェクトを検索します。

3.  確認対象となるタイプのデータをエクスポートし、確認します。

4.  必要に応じてデータを編集します。

これらの手順について、以下の記事で詳細に説明します。

- [Project Server からユーザー データをエクスポートする](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [Project Server からユーザー データを削除する](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


Project Server は SharePoint Server 上に構築されており、SharePoint ULS のログおよび利用状況データベースにイベントのログが出力されることに注意してください。詳細は「[SharePoint Server での GDPR への対応](gdpr-for-sharepoint-server.md)」をご覧ください。
