---
title: 新しい Office 365 Message Encryption 機能を設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 新しい Office 365 メッセージの暗号化機能が Azure Information Protection の上に構築されており、組織は、組織の内外の人々との間で保護された電子メール通信を使用できます。 新しい OME 機能は、他の Office 365 組織、Outlook.com、Gmail、その他の電子メールサービスと連携して動作します。
ms.openlocfilehash: 415e598a28033271b115aff639fb1ddd7a6345af
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156509"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>新しい Office 365 Message Encryption 機能を設定する

新しい Office 365 メッセージ暗号化 (OME) 機能を使用すると、組織は、保護された電子メールを任意のデバイス上のすべてのユーザーと共有できます。 ユーザーは、保護されたメッセージを他の Office 365 組織や、Outlook.com、Gmail、その他の電子メールサービスを使用している非 Office 365 ユーザーと交換することができます。

||
|:-----|
|この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。 この記事は、管理者および IT 担当者を対象としています。 暗号化されたメッセージの送信または受信に関する情報をお探しの場合は、「 [Office 365 Message Encryption (OME)](ome.md) 」の記事の一覧を参照し、ニーズに最も適した記事を見つけてください。 |
||

Office 365 組織で新しい OME 機能が使用できることを確認するには、次の手順を実行します。

## <a name="verify-that-azure-rights-management-is-active"></a>Azure Rights Management がアクティブであることを確認する

新しい OME 機能により、azure [Rights Management Services (AZURE RMS)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection)の保護機能が活用されます。これは、 [azure Information protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)が暗号化とアクセス制御を介してメールやドキュメントを保護するために使用するテクノロジです。

新しい OME 機能を使用するための唯一の前提条件は、組織のテナントで[Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)をアクティブ化する必要があるということです。 その場合、Office 365 は新しい OME 機能を自動的に有効にし、何もする必要はありません。

Azure RMS は、ほとんどの対象となるプランに対して自動的にアクティブ化されるので、多くの場合、この点に関して何もする必要はありません。 詳細については、「 [Azure Rights Management をアクティブ化](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service)する」を参照してください。

>[!IMPORTANT]
>Exchange Online で Active Directory Rights Management サービス (AD RMS) を使用する場合は、新しい OME 機能を使用する前に、 [Azure Information Protection に移行](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms)する必要があります。 OME は AD RMS と互換性がありません。  

詳細については、以下を参照してください。

- [新しい OME 機能を使用するために必要なサブスクリプションは何ですか。](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)サブスクリプションプランに Azure Information Protection (Azure RMS 機能を含む) が含まれているかどうかを確認するには
- 適格なサブスクリプションの購入については、「 [Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) 」を参照してください。  

### <a name="manually-activating-azure-rights-management"></a>Azure Rights Management を手動でアクティブ化する

Azure RMS を無効にした場合、または何らかの理由で自動的にアクティブ化されなかった場合は、次の方法で手動でアクティブ化できます。

- **Office 365 管理センター**: 手順については[、「office 365 管理センターから Azure Rights Management をアクティブ化する方法](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365)」を参照してください。
- **Azure portal**: 手順については、「azure [Portal から azure Rights Management をアクティブ化する方法](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure)」を参照してください。

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Azure Information Protection のテナントキーの管理を構成する

これは、省略可能な手順です。 Microsoft が Azure Information Protection のルートキーを管理できるようにすることは、ほとんどの Office 365 テナントの既定の設定と推奨されるベストプラクティスです。 その場合は、何もする必要はありません。

多くの理由から、たとえばコンプライアンス要件によっては、独自のルートキーを生成して管理する必要が生じることがあります (つまり、独自のキーを持っている (BYOK))。 その場合は、新しい OME 機能を設定する前に必要な手順を完了することをお勧めします。 詳細については[、「Azure Information Protection のテナントキーを計画および実装](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)する」を参照してください。

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>Exchange Online PowerShell で新しい OME 構成を確認する

Office 365 テナントが、 [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)の新しい OME 機能を使用するように適切に構成されていることを確認できます。
  
1. Office 365 テナント内のグローバル管理者のアクセス許可を持つアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)します。

2. Get-IRMConfiguration コマンドレットを実行します。

     AzureRMSLicensingEnabled パラメーターに $True の値が表示されます。これは、テナントで OME が構成されていることを示します。 指定されていない場合は、AzureRMSLicensingEnabled $True を有効にするために OME を有効にするために、の値を設定するには、set-irmconfiguration を使用します。

3. 次の構文を使用して、テスト用の IRMConfiguration コマンドレットを実行します。

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **例**:

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - 送信者の電子メールを指定することはオプションですが、システムが追加のチェックを実行することを強制します。 Office 365 テナント内のユーザーの電子メールアドレスを使用します。

     結果は次のようになります。

     ```text
    Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
    ```

   - Office 365 組織名は*Contoso*と置き換えられます。

   - 既定のテンプレート名は、上に表示されているものとは異なる場合があります。 詳細については[、「Azure Information Protection のテンプレートを構成および管理](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates)する」を参照してください。

4. 削除コマンドレットを実行して、Rights Management サービスとの接続を解除します。

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a>次の手順: 新しい OME 機能を使用するためのメールフロールールを定義する

Office 365 組織の電子メールを暗号化するように事前に構成されたメールフロールールがある場合は、新しい OME 機能を使用するように既存のルールを更新する必要があります。 新規展開の場合は、新しいメールフロールールを作成する必要があります。

>[!IMPORTANT]
>既存のメールフロールールを更新しない場合、ユーザーは、新しいシームレスな OME の操作ではなく、以前の HTML 添付ファイル形式を使用する暗号化メールの受信を続行します。

メールフロールールは、電子メールメッセージを暗号化する条件、およびその暗号化を削除するための条件を決定します。 ルールのアクションを設定すると、ルールの条件に一致するメッセージはすべて、送信時に暗号化されます。
  
OME のメールフロールールを作成する手順については、「 [Office 365 で電子メールメッセージを暗号化するためのメールフロールールを定義する](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。

既存のルールを更新して、新しい OME 機能を使用するには、次のようにします。

1. Office 365 管理センターで、[**管理センター _GT_ Exchange**] に移動します。
2. Exchange 管理センターで、[**メールフロー _GT_ ルール**] に移動します。
3. ルールごとに、**次の操作を行い**ます。
    - [**メッセージのセキュリティを変更する**] を選択します。
    - [ **Office 365 メッセージの暗号化と権限保護を適用**する] を選択します。
    - 一覧から RMS テンプレートを選択します。
    - **[保存]** を選択します。
    - **[OK]** をクリックします。
