---
title: Office 365 Message Encryption によって暗号化された電子メールを取り消す
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/29/2019
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
description: Office 365 管理者は、Office 365 のメッセージの暗号化で暗号化された電子メールの一部を取り消すことができます。
ms.openlocfilehash: a3f5c08d2c8660e56c378fc5fa7a850ff2c12eb5
ms.sourcegitcommit: 03b9221d9885bcde1cdb5df2c2dc5d835802d299
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29614391"
---
# <a name="office-365-message-encryption-email-revocation"></a>Office 365 のメッセージの暗号化メールの取り消し

この資料は、 [Office 365 のメッセージの暗号化](ome.md)についての記事の大規模な一連の一部です。プレビューでは、現在、暗号化された電子メールの取り消しです。当社の製品を改善していく機能と、コンテンツに対する更新や変更を期待してください。

必要がありますが既に送信されている電子メールを無効にします。電子メールが Office 365 のメッセージの暗号化を使用して暗号化された Office 365 管理者は、する場合は、これを行う特定の条件下でメールをします。[どのような状況は考えられるとそれを行う方法について説明します。
  
## <a name="encrypted-emails-that-you-can-revoke"></a>暗号化された電子メールを無効にすること

受信者を受信した場合、リンク ・ ベース、暗号化された電子メールのブランドは、暗号化された電子メールを取り消すことができます。受信者は、サポートされている Outlook クライアントで、インラインのネイティブ機能を受信する場合は、これらの e メールを取り消すことはできません。

リンク ベースの操作性を受け取った受信者かどうか、またはインライン経験は、受信者の id の種類によって異なります: Office 365 と Microsoft アカウントの受信者 (たとえば、outlook.com ユーザー) がサポートされている Outlook クライアントでインライン経験を取得します。すべての他の受信者の種類など Gmail の受信者は、リンク ベースの操作性を取得します。

まもなく、組織は、受信者の id に関係なくリンク ベースのエクスペリエンスを強制する機能があります。この方法では、すべての受信者にブランドの電子メールと暗号化された電子メールを読み、返信できないこと、Office 365 のメッセージの暗号化のポータルへのリンクが表示されます。このようなすべての暗号化された電子メールは取り消しになります。
  
## <a name="recipient-experience-for-revoked-encrypted-emails"></a>失効した暗号化された電子メールの受信者の経験

電子メールが取り消された後、受信者エラーが表示されます Office 365 のメッセージの暗号化のポータルを通じて、暗号化された電子メールにアクセスしようとしています:「メッセージは、送信者によって失効されています」。

![失効した暗号化された電子メールを表示するスクリーン ショットです。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a>暗号化された電子メールを破棄する方法

### <a name="step-1-obtain-the-message-id-of-the-email"></a>手順 1 です。電子メールのメッセージ ID を取得します。

暗号化されたメールを取り消すことができる前に、メールのメッセージ ID を収集する必要があります。メッセージ Id は、通常の形式。

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

無効にする電子メールのメッセージ ID を検索する複数の方法があります。いくつかのオプションの説明ですが、ID を提供する任意のメソッドを使用することができます。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>セキュリティ メッセージのトレースを使用して無効に電子メールのメッセージ ID を識別する&amp;コンプライアンス センター

1. 送信者または受信者が[Office 365 のセキュリティ & コンプライアンス センターに新しいメッセージのトレース](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)を使用して電子メールを検索します。
2. 見つけた後、電子メールは**メッセージのトレースの詳細**ペインを表示を選択します。メッセージ ID を検索するのには**詳細情報**を展開します。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>セキュリティで Office のメッセージの暗号化のレポートを使用して解除しメールのメッセージ ID を識別する&amp;コンプライアンス センター

1. セキュリティ&amp;コンプライアンス センターでは、**メッセージの暗号化のレポート**に移動します。
2. **詳細を表示する**テーブルを選択し、無効にするメッセージを識別します。
3. メッセージ ID を含む詳細を表示するメッセージをダブルクリックしてください。

### <a name="step-2-revoke-the-mail"></a>手順 2 です。メールを取り消す  

無効に電子メールのメッセージ ID がわかったら、セット OMEMessageRevocation コマンドレットを使用して電子メールを取り消すことができます。

1. [オンライン リモート PowerShell を使用して Exchange に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。

2. とおりセット OMEMessageRevocation コマンドレットを実行します。

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```  

3. 電子メールが無効になっているかどうかを確認するには、次のように Get OMEMessageStatus コマンドレットを実行します。

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | fl Revoked
    ```  
    取り消しが成功した場合、コマンドレットは、次の結果を返します。  

    `Revoked: True`
