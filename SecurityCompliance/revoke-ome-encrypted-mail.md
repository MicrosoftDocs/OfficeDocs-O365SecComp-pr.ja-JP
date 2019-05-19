---
title: Office 365 Advanced Message Encryption 機能を使って暗号化されたメールを無効にする
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Office 365 管理者は、Office 365 Advanced Message Encryption で暗号化された特定の電子メールを取り消すことができます。
ms.openlocfilehash: 098ce50791152c8bbb4e4692d6fb85e4c2c7cb58
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156789"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a>Office 365 Advanced Message Encryption 機能を使って暗号化されたメールを無効にする

電子メールの取り消しは、Office 365 Advanced Message Encryption の一部として提供されます。 Office 365 の高度なメッセージの暗号化は、特定のサブスクリプションの Office 365 メッセージの暗号化の上で使用できます。 高度なメッセージ暗号化は、 [Microsoft 365 Enterprise e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 Enterprise e5、および Office 365 エデュケーション A5 に含まれています。 Office 365 Advanced Message Encryption を含まない Office 365 サブスクリプションが組織にある場合は、Advanced コンプライアンス SKU の E5 コンプライアンスを使用して、高度なメッセージ暗号化をアドオンとして購入できます。

この記事は、 [Office 365 メッセージの暗号化](ome.md)についてのより大きな一連の記事の一部です。

既に送信されている電子メールを取り消す必要がある場合があります。 Office 365 Advanced Message Encryption を使用して電子メールを暗号化していて、Office 365 管理者である場合は、特定の条件下で電子メールに対してこれを行うことができます。 この記事では、これが可能な状況とその方法について説明します。
  
## <a name="encrypted-emails-that-you-can-revoke"></a>取り消すことができる暗号化された電子メール

受信者がリンクベースの、ブランド化された電子メールを受信した場合は、暗号化された電子メールを取り消すことができます。 受信者が、サポートされている Outlook クライアントでネイティブインライン環境を受信した場合は、それらの電子メールを取り消すことはできません。

受信者がリンクベースの機能を受信するか、またはインラインでの使用を許可するかは、受信者の id の種類によって異なります。 Office 365 と Microsoft アカウントの受信者 (たとえば、outlook.com users) は、サポートされている Outlook クライアントでインラインの動作を取得します。 Gmail 受信者など、他のすべての受信者の種類は、リンクベースの処理を行います。

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>取り消された暗号化された電子メールの受信者向けの手順

電子メールが失効されると、受信者は Office 365 メッセージ暗号化ポータルを経由して暗号化された電子メールにアクセスしようとすると、エラーが発生します。 "メッセージは送信者によって取り消されました" というメッセージが表示されます。

![取り消された暗号化された電子メールを示すスクリーンショット。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a>暗号化された電子メールを取り消す方法

### <a name="step-1-obtain-the-message-id-of-the-email"></a>手順 1. 電子メールのメッセージ ID を取得する

暗号化されたメールを取り消すには、メールのメッセージ ID を収集する必要があります。 MessageId は通常、次の形式になります。

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

取り消したい電子メールのメッセージ ID を複数の方法で見つけることができます。 このセクションでは、いくつかのオプションについて説明しますが、ID を提供する任意の方法を使用できます。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>セキュリティ&amp; /コンプライアンスセンターのメッセージ追跡を使用して取り消す電子メールのメッセージ ID を特定するには

1. [Office 365 セキュリティ _AMP_ コンプライアンスセンターで、新しいメッセージの追跡](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)を使用して、送信者または受信者別に電子メールを検索します。

2. 電子メールを見つけたら、それを選択して**メッセージ追跡の詳細**ウィンドウを開きます。 **詳細情報**を展開して、メッセージ ID を見つけます。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>セキュリティ&amp; /コンプライアンスセンターで Office メッセージの暗号化レポートを使用して取り消す電子メールのメッセージ ID を特定するには

1. セキュリティ&amp; /コンプライアンスセンターで、[メッセージの**暗号化] レポート**に移動します。

2. [**詳細の表示**] テーブルを選択し、取り消すメッセージを識別します。

3. メッセージをダブルクリックして、メッセージ ID を含む詳細を表示します。

### <a name="step-2-verify-that-the-mail-is-revocable"></a>手順 2. メールが revocable かどうかを確認する

特定の電子メールメッセージを取り消すことができるかどうかを確認するには、セキュリティ&amp;コンプライアンスセンターの**詳細**テーブルに [失効状態] フィールドが表示されているかどうかを確認します。

Windows Powershell を使用して特定の電子メールメッセージを取り消すことができるかどうかを確認するには、次の手順を実行します。

1. Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。 手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。

2. 次のように、Set-OMEMessageStatus コマンドレットを実行します。

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   これにより、メッセージの件名と、メッセージが revocable かどうかが返されます。 For example,

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a>手順 3. メールを取り消す  

取り消したい電子メールのメッセージ ID がわかっており、メッセージが revocable であることを確認したら、電子メールを取り消すことができます。

セキュリティ&amp; /コンプライアンスセンターで電子メールを取り消すには、**詳細**表で [**取り消し**] を選択します。

OMEMessageRevocation コマンドレットを使用して、Windows Powershell を使用して電子メールを失効させることができます。

1. [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)。

2. OMEMessageRevocation コマンドレットを次のように実行します。

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. 電子メールが失効したかどうかを確認するには、次のようにして、次のコマンドレットを実行します。

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    失効が成功した場合、コマンドレットは次の結果を返します。  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Office 365 の詳細なメッセージの暗号化に関する詳細情報

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Office 365 の高度なメッセージの暗号化-電子メールの有効期限](ome-advanced-expiration.md)

- [メッセージポリシーとコンプライアンスサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)