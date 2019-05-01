---
title: Office 365 で暗号化された電子メールの有効期限日を設定する高度なメッセージ暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
ms.audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: office 365 の高度なメッセージ暗号化機能が office 365 メッセージ暗号化 (OME) の上にあるため、電子メールのセキュリティを拡張するには、カスタムブランド化されたテンプレートを使用して、メールの有効期限を設定します。
ms.openlocfilehash: c1fb876724bed970095e950906500ff551d93cee
ms.sourcegitcommit: 8eb3cb4ec45ae0bb75fde249e35c4bc3d263b84f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2019
ms.locfileid: "33506726"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Office 365 で暗号化された電子メールの有効期限日を設定する高度なメッセージ暗号化

office 365 の高度なメッセージの暗号化は、特定のサブスクリプションの office 365 メッセージの暗号化の上で使用できます。 高度なメッセージ暗号化は、 [Microsoft 365 Enterprise e5](https://www.microsoft.com/microsoft-365/enterprise/home)、office 365 Enterprise e5、および Office 365 エデュケーション A5 に含まれています。 office 365 advanced message encryption を含まない office 365 サブスクリプションが組織にある場合は、advanced コンプライアンス SKU の E5 コンプライアンスを使用して、高度なメッセージ暗号化をアドオンとして購入できます。

OME ポータルを使用して暗号化された電子メールにアクセスする外部の受信者に送信するユーザーが電子メールでメッセージの有効期限を使用できます。 受信者が OME ポータルを使用して、組織によって送信される暗号化された電子メールを、Windows Powershell で有効期限を指定するカスタムブランド化テンプレートを使用して表示および返信できるようにします。

O365 グローバル管理者は、会社のブランドを適用して Office 365 組織の電子メールメッセージの外観をカスタマイズする場合、これらの電子メールメッセージの有効期限を指定することもできます。 Office 365 Advanced Message Encryption では、組織から送信される暗号化メール用に複数のテンプレートを作成できます。 テンプレートを使用すると、受信者がユーザーによって送信されたメールにアクセスできる期間を制御できます。

エンドユーザーが有効期限が設定されたメールを受信すると、ユーザーにはラッパーの電子メールの有効期限が表示されます。 ユーザーが期限切れメールを開こうとすると、OME ポータルにエラーが表示されます。

外部の受信者へのメールのみが expirable になります。

office 365 Advanced Message Encryption では、カスタムブランドを適用するたびに、office 365 は、テンプレートを適用するメールフロールールに適合するラッパーを電子メールに適用します。 また、有効期限は、カスタムブランド化が使用されている場合にのみ使用できます。

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>PowerShell を使用してメールの有効期限を強制するカスタムブランド化テンプレートを作成する

1. Office 365 テナント内のグローバル管理者のアクセス許可を持つアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)します。

2. omeconfiguration 新しいコマンドレットを実行します。

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" ExternalMailExpiryInDays 7
     ```

詳細は次のとおりです。

- Identity は、カスタムテンプレートの名前です。

- ExternalMailExpiryInDays は、受信者が期限切れになる前にメールを保持できる日数を指定します。 1から730日までの任意の値を使用できます。

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Office 365 の詳細なメッセージの暗号化に関する詳細情報

- [Office 365 の高度なメッセージの暗号化](ome-advanced-message-encryption.md)

- [Office 365 で暗号化されたメールの取り消し高度なメッセージ暗号化](revoke-ome-encrypted-mail.md)

- [メッセージポリシーとコンプライアンスサービスの説明](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)