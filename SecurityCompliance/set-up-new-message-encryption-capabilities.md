---
title: 新しい Office 365 Message Encryption 機能を設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: 新しい Office 365 メッセージの暗号化機能が Azure Information Protection の上に構築されており、組織は、組織の内外の人々との間で保護された電子メール通信を使用できます。新しい OME 機能は、他の Office 365 組織、Outlook.com、Gmail、その他の電子メールサービスと連携して動作します。
ms.openlocfilehash: 90247a7e3cd7e5978eb144a2b6f66a9de21a8f96
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296190"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>新しい Office 365 Message Encryption 機能を設定する

新しい Office 365 メッセージ暗号化 (OME) 機能を使用すると、組織は、保護された電子メールを任意のデバイス上のすべてのユーザーと共有できます。ユーザーは、保護されたメッセージを他の office 365 組織や、Outlook.com、Gmail、その他の電子メールサービスを使用している非 office 365 ユーザーと交換することができます。


>[!NOTE]
>この記事は、管理者および IT 担当者を対象としています。エンドユーザーの場合は、適切なソリューションについて、「 [Office 365 Message Encryption (OME)](ome.md) 」の記事の一覧を参照してください。

Office 365 テナントで新しい OME 機能が使用できることを確認するには、次の手順を実行します。 

## <a name="verify-azure-rights-management-arm-is-active"></a>Azure Rights Management (ARM) がアクティブであることを確認する

>[!NOTE]
>新しい OME 機能により、azure [Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)によって使用されるテクノロジである[azure Information protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection)の保護機能が活用されます。

新しい OME 機能を使用するための唯一の前提条件は、Office 365 テナントで[Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)を有効にする必要があることです。その場合、Office 365 は新しい OME 機能を自動的に有効にし、何もする必要はありません。 

ARM は、ほとんどの対象となるプランに対して自動的にアクティブ化されるので、この点を考慮する必要はありません。詳細については、「 [Azure Rights Management のアクティブ化](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service)」を参照してください。

>[!IMPORTANT]
>Exchange Online で Active Directory Rights Management サービス (AD RMS) を使用する場合は、新しい OME 機能を使用する前に、 [Azure Information Protection に移行](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms)する必要があります。AD RMS は ARM と互換性がありません。  

詳細については、以下を参照してください。

- [新しい OME 機能を使用するために必要なサブスクリプションは何ですか。](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)サブスクリプションプランに Azure Information Protection (ARM を含む) が含まれているかどうかを確認する。   
-  適格なサブスクリプションの購入については、「 [Azure information Protection](https://azure.microsoft.com/en-us/services/information-protection/) 」を参照してください。  

### <a name="manually-activating-arm"></a>ARM を手動でアクティブ化する

ARM を無効にした場合、または何らかの理由で自動的にアクティブ化されなかった場合は、次のように手動でアクティブ化できます。

- **office 365 管理センター**: 手順について[は、「office 365 管理センターから Azure Rights Management をアクティブ化する方法](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365)」を参照してください。
- **azure portal**: 手順については、「azure [portal から azure Rights Management をアクティブ化する方法](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure)」を参照してください。 


## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Azure Information Protection のテナントキーの管理を構成する

これは、省略可能な手順です。Microsoft が Azure Information Protection のルートキーを管理できるようにすることは、ほとんどの Office 365 テナントの既定の設定と推奨されるベストプラクティスです。その場合は、何もする必要はありません。 

多くの理由から、たとえばコンプライアンス要件によっては、独自のルートキーを生成して管理する必要が生じることがあります (つまり、独自のキーを持っている (byok))。その場合は、新しい OME 機能を設定する前に必要な手順を完了することをお勧めします。詳細については[、「Azure Information Protection のテナントキーを計画および実装](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)する」を参照してください。 


## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>Exchange Online PowerShell で新しい OME 構成を確認する

Office 365 テナントが、 [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)の新しい OME 機能を使用するように適切に構成されていることを確認できます。
  
1. Office 365 テナント内のグローバル管理者のアクセス許可を持つアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)します。

2. 次の構文を使用して、テスト用の irmconfiguration コマンドレットを実行します。

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **例**: 
   
     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```
     
     - 送信者の電子メールを指定することはオプションですが、システムが追加のチェックを実行することを強制します。Office 365 テナント内のユーザーの電子メールアドレスを使用します。 
     
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

   - 既定のテンプレート名は、上に表示されているものとは異なる場合があります。詳細については[、「Azure Information Protection のテンプレートを構成および管理](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates)する」を参照してください。

3. 削除コマンドレットを実行して、Rights Management サービスとの接続を解除します。
    
     ```powershell
     Remove-PSSession $session
     ```

## <a name="update-mail-flow-rules-to-use-new-ome-capabilities"></a>新しい OME 機能を使用するようにメールフロールールを更新する

Office 365 テナントの[電子メールを暗号化するように事前に](define-mail-flow-rules-to-encrypt-email.md)構成されたメールフロールールがある場合は、新しい OME 機能を使用するように既存のルールを更新する必要があります。新規展開の場合、この手順はこの段階では必要ありません。   

>[!Note]
>メールフロールールは、電子メールメッセージが暗号化されるとき、および暗号化が削除されるときの条件を定義します。詳細については、「 [Office 365 で電子メールメッセージを暗号化するためのメールフロールールの定義」を](define-mail-flow-rules-to-encrypt-email.md)参照してください。

既存のルールを更新して、新しい OME 機能を使用するには、次のようにします。

1. Office 365 管理センターで、[**管理センター > Exchange**] に移動します。

2. Exchange 管理センターで、[**メールフロー > ルール**] に移動します。 
3. ルールごとに、**次の操作を行い**ます。
    - [**メッセージのセキュリティを変更する**] を選択します。
    - [ **Office 365 メッセージの暗号化と権限保護を適用**する] を選択します。
    - 一覧から RMS テンプレートを選択する
    - **[保存]** を選択します。
    - [**OK**] を選びます。
  
>[!IMPORTANT]
>既存のメールフロールールを更新しない場合、ユーザーは、新しい OME 機能ではなく、以前の HTML 添付ファイル形式を使用する暗号化メールを引き続き受信できます。
