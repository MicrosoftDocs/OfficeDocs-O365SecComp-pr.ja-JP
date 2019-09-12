---
title: Skype for Business Server の GDPR
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: オンプレミスの Skype for Business Server および Lync Server での GDPR の要件に対応する方法について説明します。
ms.openlocfilehash: 835876af133dfbce056ee765336c9e981732226d
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154389"
---
# <a name="gdpr-for-skype-for-business-server-and-lync-server"></a>Skype for Business Server および Lync Server の GDPR

Skype for Business Server および Lync Server のデータのほとんどは、Exchange Server に保存されます。それには、次のものが含まれます。

-   会話の履歴

-   ボイスメールの通知とトランスクリプション

-   会議の招待

[GDPR for Exchange Server](gdpr-for-exchange-server.md) について概要が示されている手順を使用して、GDPR 要求のこれらのデータ タイプを検索、エクスポート、削除します。

連絡先リストは、SQL Server のデータベースに保存されます。それらは、次の方法でエクスポートできます。

-   エンド ユーザー自身がグループ ヘッダーを右クリックして [コピー] を選択することにより、連絡先をエクスポートできます。この場合、そのグループのすべての連絡先がクリップボードにコピーされ、任意のアプリに貼り付けることができるようになります。

-   [Export-CsUserData](https://docs.microsoft.com/ja-JP/powershell/module/skype/export-csuserdata) コマンドレットを使用することにより、このデータをエクスポートできます。

会議にアップロードされるコンテンツ (PowerPoint のファイルや配布資料など) または会議で生成されるコンテンツ (ホワイトボード、投票、Q/A など) は、ファイラーに保存されます。また、これらは、エンド ユーザーがまだ期限切れでない会議に再びログインして、アップロードされたコンテンツをダウンロードしたり、生成されたコンテンツの場合にはスクリーンショットを撮ってエクスポートすることもできます。

Exchange の予定表および連絡先リストにない MeetNow 会議および連絡先権限 (家族や同僚など) は、ユーザー データベース内にあります。Lync Server 2013 以降の場合は、[Export-CsUserData](https://docs.microsoft.com/ja-JP/powershell/module/skype/export-csuserdata) コマンドレットを使用することにより、このデータをエクスポートできます。
