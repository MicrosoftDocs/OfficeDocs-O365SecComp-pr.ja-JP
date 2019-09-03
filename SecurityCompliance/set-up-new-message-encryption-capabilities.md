---
title: 新しい Office 365 Message Encryption 機能を設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Azure Information Protection をベースに構築された、Office 365 Message Encryption (OME) の新機能を使用すると、自分の組織で組織内および組織外のユーザーと保護されたメール通信を使用することができます。 OME の新機能は、他の Office 365 組織、Outlook.com、Gmail、およびその他のメール サービスと連携します。
ms.openlocfilehash: 835b1d6f40868684536dbea8f75dab0665950210
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854801"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>新しい Office 365 Message Encryption 機能を設定する

新しい Office 365 Message Encryption (OME) 機能では、保護されたメールを任意のデバイス上の誰とでも共有できます。 ユーザーは、Outlook.com、Gmail、およびその他のメール サービスを使用して、他の Office 365 組織や Office 365 以外のユーザーと保護されたメッセージを交換できます。

||
|:-----|
|この記事は、Office 365 Message Encryption に関するより大きな一連の記事の一部です。 この記事は、管理者と IT 担当者を対象としています。 暗号化されたメッセージの送受信に関する情報だけを探している場合は、「[Office 365 のメッセージの暗号化](ome.md)」の記事の一覧を参照し、ニーズに最も適した記事を見つけてください。 |
||

Office 365 組織で新しい OME 機能が使用できるようにするには、次の手順に従います。

## <a name="verify-that-azure-rights-management-is-active"></a>Azure Rights Management が有効であることを確認する

新しい OME 機能は、[Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/ja-JP/azure/information-protection/what-is-information-protection) の保護機能を活用します。Azure RMS は、[Azure Information Protection](https://docs.microsoft.com/ja-JP/azure/information-protection/what-is-azure-rms) が暗号化とアクセス制御を介して電子メールとドキュメントを保護するために使用するテクノロジーです。

新しい OME 機能を使用するための唯一の前提条件は、組織のテナントで [Azure Rights Management](https://docs.microsoft.com/ja-JP/azure/information-protection/what-is-azure-rms) を有効化する必要があることです。 その場合、Office 365 は新しい OME 機能を自動的に有効化するため、何もする必要はありません。

また、Azure RMS はほとんどの対象となるプランで自動的に有効化されるため、おそらく何もする必要はありません。 詳細については、「[Azure Rights Management を有効化する](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service)」を参照してください。

>[!IMPORTANT]
>Exchange Online で Active Directory Rights Management サービス (AD RMS) を使用する場合、新しい OME 機能を使用する前に [Azure Information Protection に移行する](https://docs.microsoft.com/ja-JP/azure/information-protection/migrate-from-ad-rms-to-azure-rms)必要があります。 OME は、AD RMS と互換性がありません。  

詳しくは、次のトピックを参照してください。

- [新しい OME 機能を使用するには、どのサブスクリプションが必要か](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)については、サブスクリプションプランに Azure Information Protection (Azure RMS 機能を含む) が含まれているかどうかを確認します。
- 対象となるサブスクリプションの購入に関する情報については、「[Azure Information Protection](https://azure.microsoft.com/ja-JP/services/information-protection/)」を参照してください。  

### <a name="manually-activating-azure-rights-management"></a>Azure Rights Management を手動で有効化する

Azure RMS を無効にした場合、または何らかの理由で自動的に有効化されなかった場合は、次のように手動で有効化できます:

- **Microsoft 365 管理センター**: 手順については、「[管理センターから Azure Rights Management を有効化する方法](https://docs.microsoft.com/ja-JP/azure/information-protection/activate-office365)」を参照してください。
- **Azure Portal**: 手順については、「[Azure Portal から Azure Rights Management を有効化する方法](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure)」を参照してください。

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Azure Information Protection テナント キーの管理を構成する

この手順は省略可能です。 Microsoft が Azure Information Protection のルート キーを管理できるようにすることが既定であり、ほとんどの Office 365 テナントに推奨されるベスト プラクティスです。 このような場合は、何もする必要はありません。

コンプライアンス要件など、多くの理由により、独自のルート キー (Bring Your Own Key (BYOK) とも呼ばれる)の生成と管理が必要になる場合があります。 この場合、新しい OME 機能をセットアップする前に、必要な手順を完了することをお勧めします。 詳細については、「[Azure Information Protection テナント キーを計画して実装する](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)」を参照してください。

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>Exchange Online PowerShell で新しい OME 構成を確認する

[Exchange Online PowerShell](https://docs.microsoft.com/ja-JP/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) の新しい OME 機能を使用するように Office 365 テナントが適切に構成されていることを確認できます。
  
1. Office 365 テナントのグローバル管理者権限を持つアカウントを使用して、[Exchange Online PowerShell に接続](https://docs.microsoft.com/ja-JP/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)します。

2. Get-IRMConfiguration コマンドレットを実行します。

     AzureRMSLicensingEnabled パラメーターの $True 値が表示されます。これは、テナントで OME が構成されていることを示します。 そうでない場合は、Set-IRMConfiguration を使用して AzureRMSLicensingEnabled の値を $ True に設定し、OME を有効にします。

3. 次の構文を使用して Test-IRMConfiguration コマンドレットを実行します:

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **例**:

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - 送信者の電子メールの提供はオプションですが、システムに追加のチェックを強制的に実行させます。 Office 365 テナントの任意のユーザーのメール アドレスを使用します。

     結果は次のようになります:

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

   - *Contoso* は Office 365 の組織名に置き換えられます。

   - 既定のテンプレート名は、上に表示されているものとは異なる場合があります。 詳細については、「[Azure Information Protection のテンプレートを構成して管理する](https://docs.microsoft.com/ja-JP/azure/information-protection/configure-policy-templates)」を参照してください。

4. Rights Management サービスから切断するには、Remove-PSSession コマンドレットを実行します。

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a>次の手順: 新しい OME 機能を使用するためのメール フロー ルールを定義する

Office 365 組織のメールを暗号化するために以前に構成されたメール フロー ルールがある場合は、新しい OME 機能を使用するために既存のルールを更新する必要があります。 新しい展開の場合、新しいメール フロー ルールを作成する必要があります。

>[!IMPORTANT]
>既存のメール フロー ルールを更新しない場合、ユーザーは新しい、シームレスな OME の操作環境ではなく、以前の HTML 添付ファイルの形式を使用する暗号化されたメールを引き続き受信します。

メール フロー ルールは、メール メッセージを暗号化する条件、およびその暗号化を削除する条件を決定します。 ルールのアクションを設定すると、送信時に、ルールの条件に一致するすべてのメッセージが暗号化されます。
  
OME のメール フロー ルールの作成の手順については、「[Office 365 でメール メッセージを暗号化するためにメール フロー ルールを定義する](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。

新しい OME 機能を使用するために既存のルールを更新するには:

1. Microsoft 365 管理センターから [**管理センター]、[Exchange**] の順に移動します。
2. Exchange 管理センターで、[**メール フロー]、[ルール**] の順に移動します。
3. ルールごとに、**次の操作を行います**:
    - [**メッセージのセキュリティを変更する**] を選択します。
    - [**Office 365 Message Encryption および適切な保護を適用する**] を選択します。
    - 一覧から RMS テンプレートを選択します。
    - [**保存**] を選択します。
    - **[OK]** をクリックします。
