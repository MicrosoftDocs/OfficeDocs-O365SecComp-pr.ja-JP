---
title: Office 365 でのデータの保持、削除、および破棄
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: データの保持、削除、および破壊に関する Microsoft の Office 365 のポリシーの概要。
ms.openlocfilehash: fcae11f10278f1357a68ea3f9a1178da97322775
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262839"
---
# <a name="data-retention-deletion-and-destruction-in-office-365"></a>Office 365 でのデータの保持、削除、および破棄

Microsoft は、顧客データの削除後に保持される期間を指定する Office 365 に対するデータ処理の標準ポリシーを備えています。 一般的に、顧客データが削除されるシナリオは2つあります。

- **アクティブな削除**-テナントにはアクティブなサブスクリプションがあり、ユーザーがデータを削除したか、ユーザーが提供したデータが管理者によって削除されています。
- **パッシブ削除**-テナントサブスクリプションが終了します。

## <a name="data-retention"></a>データ保持

これらの削除シナリオのそれぞれについて、次の表に、データの最大保持期間、データカテゴリ、および分類を示します。

| データカテゴリ | データ分類 | 説明 | 例 | 保持期間 |
|-----------------|-----------------|-----------------|----------------------------------|-------------------------------|
| 顧客データ | 顧客コンテンツ| 管理者とユーザーによって直接提供/作成されたコンテンツ <br><br> これには、Office 365 でサービスを使用しているときに、Microsoft データセンターに作成および保存されたすべてのテキスト、サウンド、ビデオ、イメージファイル、ソフトウェアが含まれます。 | Word、Excel、PowerPoint、Outlook、OneNote など、ユーザーがデータを作成できる、最も一般的に使用される Office 365 アプリケーションの例 <br><br> お客様のコンテンツには、お客様が所有/提供する機密情報 (パスワード、証明書、暗号化キー、ストレージキー) も含まれています。 | **アクティブな削除のシナリオ:** 最大で30日 <br><br> **パッシブ削除のシナリオ:** 最大180日 |
| 顧客データ | エンドユーザーを特定できる情報 (euii) | Microsoft サービスのユーザーを識別または特定するために使用されるデータ。 euii にお客様のコンテンツは含まれていません | ユーザー名または表示名 (DOMAIN\UserName) <br><br> ユーザープリンシパル名 (名前 @ ドメイン) <br><br>  ユーザー固有の IP アドレス | **アクティブな削除のシナリオ:** 最大180日 (テナント管理者のアクションのみ) <br><br> **パッシブ削除のシナリオ:** 最大180日 |
| 個人データ <br> (顧客データに含まれていないデータ) | エンドユーザー仮名識別子 (eupi) | microsoft サービスのユーザーに関連付けられた id。 eupi をマッピングテーブルなどの他の情報と組み合わせると、エンドユーザーを識別します。 <br><br> eupi お客様がアップロードまたは作成した情報は含まれません。 | ユーザー guid、PUIDs、または sid <br><br> セッション id | **アクティブな削除のシナリオ:** 最大で30日 <br><br> **パッシブ削除のシナリオ:** 最大180日 |

## <a name="subscription-retention"></a>サブスクリプションの保持期間

アクティブなサブスクリプションの期間中は常に、サブスクライバーは Office 365 に格納されている顧客データにアクセス、抽出、または削除することができます。 有料サブスクリプションが終了または終了した場合、Microsoft は Office 365 に格納されている顧客データを90日間の制限付き機能アカウントに保持して、サブスクライバーがデータを抽出できるようにします。 90日の保持期間が終了した後、Microsoft はアカウントを無効にして、顧客データを削除します。 Office 365 へのサブスクリプションの有効期限または終了後に、180日を超えていない場合、Microsoft はアカウントを無効にし、アカウントからすべての顧客データを削除します。 いずれかのデータの最大保持期間が経過すると、データは商業的に復旧できないように表示されます。

無料試用版の場合、お客様のアカウントは、ほとんどの国や地域で30日間、猶予状態に移行します。 この猶予期間中に、Office 365 を購入するオプションがあります。 Office 365 を購入しない場合は、試用期間をキャンセルするか、猶予期間を過ぎて、試用版のアカウント情報とデータが削除されることがあります。

## <a name="expedited-deletion"></a>優先削除
サブスクリプションの期間中は常に、サブスクライバーは Microsoft サポートに連絡して、サブスクリプションのプロビジョニング解除を要求することができます。 このプロセスでは、SharePoint online のデータを含むすべてのユーザーデータ、保留中または非アクティブなメールボックスに格納されている Exchange Online は、管理者が Microsoft によって提供されたロックアウトコードを入力してから3日後に削除されます。 優先プロビジョニングの詳細については、「 [Office 365 をキャンセル](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a)する」を参照してください。

## <a name="related-links"></a>関連リンク
- [データの破棄](office-365-data-destruction.md)
- [Office 365 での不変性](office-365-data-immutability.md)
- [Exchange Online でのデータ削除](office-365-exchange-online-data-deletion.md)
- [SharePoint Online でのデータ削除](office-365-sharepoint-online-data-deletion.md)
- [Skype for Business でのデータ削除](office-365-skype-data-deletion.md)