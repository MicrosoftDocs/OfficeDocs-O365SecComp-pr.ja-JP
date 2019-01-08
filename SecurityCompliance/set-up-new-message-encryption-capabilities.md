---
title: 新しい Office 365 Message Encryption 機能を設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
description: Azure の情報保護、組織の上に組み込まれている機能が使用できる新しい Office 365 メッセージ暗号化では、電子メール、組織内外のユーザーとの通信が保護されています。ホームの新機能は、他の Office 365 の組織、Outlook.com、Gmail、その他の電子メール サービスと動作します。
ms.openlocfilehash: 0f601b425da294fbb2ddbfe1d7497c0d582e3238
ms.sourcegitcommit: bd1762ccf63c7d2ad8b49a936115171c72fb2c0f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2019
ms.locfileid: "27750036"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>新しい Office 365 Message Encryption 機能を設定する

Azure の情報保護の保護機能を活用するには、新しい Office 365 メッセージの暗号化 (ホーム) 機能を備えた組織は、任意のデバイス上の他のユーザーと保護された電子メールを簡単に共有できます。ユーザーは、他の Office 365 の組織と同様に Outlook.com、Gmail、その他の電子メール サービスを使用して Office 365 以外のお客様で保護されたメッセージを送受信することができます。
  
## <a name="get-started-with-ome-by-activating-azure-rights-management-part-of-azure-information-protection"></a>Azure の著作権管理、情報保護の Azure の一部をアクティブ化してホームを開始します。

ホームの新機能を開始する簡単です。2018 年 2 月時点で Office 365 では、当社のデータ センター内で対象となる組織の新しいホーム機能が自動的に有効にします。組織は、新しい Office 365 テナント組織は、適切なサブスクリプションを持つ場合に対象となります。**Azure アクセス権管理 (Azure RMS)、Azure の情報の保護の一部を有効にした場合に自動的に Office 365 のメッセージの暗号化を有効にします**。ホームを有効にするのには何も行う必要はありません。Azure アクセス権の管理を有効にするのには、 [Azure アクセス権の管理をアクティブにする](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)を参照してください。サブスクリプションについては、どのようなサブスクリプションが必要新しいホームの capabilities? を使用する" [Office 365 のメッセージの暗号化の FAQ](ome-faq.md)を参照してください。Azure の情報保護へのサブスクリプションの購入方法の詳細については、 [Azure の情報の保護](https://azure.microsoft.com/services/information-protection/)を参照してください。
  
使用する場合 Exchange Online では、Active Directory の権限管理サービス (AD RMS)、これらの新機能を直ちに有効にできません。代わりに、Azure の情報保護をまず AD RMS から移行する必要があります。移行が終了したら、次の手順を正常に完了できます。
  
引き続き使用する場合は、オンプレミス AD RMS Exchange 情報の保護を Azure に移行するのではなく、オンラインにすることはできませんこれらの新機能を使用します。
  
## <a name="how-the-new-capabilities-for-ome-work"></a>ホームの新機能のしくみ

新しい Office 365 のメッセージの暗号化機能では、Azure の情報保護と Azure アクセス権管理 (Azure RMS) とも呼ばれます、保護機能を使用します。これには、電子メールをセキュリティで保護する暗号化、id、および承認のポリシーが含まれます。権利テンプレートの管理、[転送不可] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)では、[暗号化専用のオプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)を使用してメッセージを暗号化できます。ユーザーは、これらのオプションを使用して、電子メール メッセージ、およびさまざまな Office 365 の添付ファイルを暗号化できます。サポートされている添付ファイルの種類の完全なリストでは[「ファイルの種類に覆われてメッセージに接続されたときに IRM ポリシー」で電子メール メッセージの IRM の概要](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)」を参照してください。管理者は、この保護を適用するメールの流れの規則を定義することもできます。たとえば、ルール、特定の受信者にアドレス指定するか、件名に特定の文字が含まれているすべての保護されていないメッセージは、不正なアクセスから保護されていると、受信者は、コピーまたはメッセージの内容を印刷することはできませんを定義できます。
  
ホームの以前のバージョンとは異なり、組織内、または Office 365 の外部の受信者にメールを送信するかどうか、これらの新機能は送信者の統合されたエクスペリエンスを提供します。さらに、2016 の Outlook または Outlook web 上の Office 365 アカウントに送信される保護された電子メール メッセージを受信する受信者のメッセージを表示する追加アクションを実行する必要はありません。シームレスに動作します。その他の電子メール クライアントと電子メール サービス プロバイダーを使用して受信者には、改善された経験があります。については、 [Office 365 で保護されたメッセージを表示](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)し、[保護されたメッセージを開く方法](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)を参照してください。
  
## <a name="steps-to-manually-set-up-the-new-capabilities-for-ome"></a>ホームに、新しい機能を手動で設定する手順を実行します。

組織に自動的に有効にすると、ホームがあるない場合、またはホームの電源をオンにした場合は、手順はホーム用の新しい機能を手動で設定します。
  
### <a name="to-manually-set-up-the-new-capabilities-for-ome"></a>ホームに、新しい機能を手動で設定するには

1. 組織のサブスクリプションがあることを確認します。サブスクリプションについてを参照してください「どのようなサブスクリプションが必要、新しいホーム capabilities? を使用する」で、 [Office 365 のメッセージの暗号化に関する FAQ です。](ome-faq.md)です。Azure の情報保護へのサブスクリプションの購入方法の詳細については、 [Azure の情報の保護](https://azure.microsoft.com/services/information-protection/)を参照してください。

2. Microsoft Azure 情報の保護 (既定値) のルート キーを管理するかを生成し (独自のキー、または BYOK と呼ばれる) 手動でこのキーを管理するかどうかを決定します。生成し、このキーを手動で管理する場合は、ホームの新機能を設定する前にいくつかの手順を完了する必要があります。詳細については、[計画と Azure の情報保護のテナントのキーを実装する](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)を参照してください。ホームを設定する前に次の手順を完了することをお勧めします。

3. Azure アクセス権の管理を実行することによって、ホームの新しい機能を有効にします。手順については、 [Azure アクセス権の管理をアクティブにする](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)を参照してください。これを行うと、Office 365 は自動的にするためホームの新機能を使用できます。

    > [!TIP]
    > Web 上で outlook は、ホームのこのクライアントを使用して電子メール メッセージに新しい機能を適用する前に 1 日を待機することをお勧めするための UI をキャッシュします。UI は、新しい構成を反映するように更新をする前に、ホームの新しい機能は使用できません。UI を更新した後、ユーザーは、ホームの新しい機能を使用して電子メール メッセージを保護できます。
  
4. (省略可能)新しいメール フロー ルールを設定または組織から送信されたメッセージを暗号化するために Office 365 をする時期と方法を定義する既存のメール フロー ルールを更新します。

## <a name="verify-that-the-new-capabilities-for-ome-are-configured-properly-by-using-windows-powershell"></a>Windows PowerShell を使用してホームの新機能が正しく構成されていることを確認します。

この手順では、Exchange オンライン PowerShell からホームの新機能を使用するのには、テナントが正しく構成されていることを確認します。
  
1. 大域管理者アクセス許可を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://aka.ms/exopowershell)を参照してください。

2. 次の構文を使用してテスト IRMConfiguration コマンドレットを実行します。

    ```Test-IRMConfiguration [-Sender <email address >]```  

   次に例を示します。

    ```Test-IRMConfiguration -Sender securityadmin@contoso.com```

    電子メール アドレスの Office 365 の組織内のユーザーの電子メール アドレスです。オプションであり、提供するときに、送信者の電子メール アドレスは追加チェックを実行するシステムを強制します。結果は、次のようになります。

    
    ```
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

    *Contoso 社*では、Office 365 の組織の名前に置き換えられます。 

    結果で返される既定のテンプレートの名前は、上記の結果に表示されるものとは異なる可能性があります。

    テンプレートと既定のテンプレートについての情報の概要については、[構成して Azure の情報保護のためのテンプレートを管理する](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)を参照してください。転送の実行方法について] して、[暗号化専用のオプションを作成する既存のテンプレートに追加のテンプレート、またはどのような権限を確認は含まれている、方法は、 [Azure の権利管理の使用権限を設定する](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights)を参照してください。

3. 権限管理サービスから切断するのには削除 PSSession コマンドレットを実行するには。
    
    ```Remove-PSSession $session```

## <a name="next-steps-define-new-mail-flow-rules-that-use-the-new-ome-capabilities"></a>次の手順: ホームの新機能を使用して、新規のメール フロー ルールを定義します。
<a name="Rules_1"> </a>

この手順では、ホームの新規導入では省略可能、ただし、この手順は、既にメール フロー ルール設定の送信メールを暗号化されている既存のホームの展開に必要です。ホームの新機能を利用する場合、既存のメール フロー ルールを更新する必要があります。それ以外の場合、ユーザーは引き続き、シームレスな新しいホームの経験ではなく HTML 添付ファイルの以前の形式を使用する暗号化されたメールを受信します。
  
メール フロー ルールは、どのような条件の e メールでメッセージを暗号化するか、その暗号化を削除するための条件とを確認します。ルールのアクションを設定すると、送信することと、ルールの条件に一致するすべてのメッセージは暗号化されます。
  
メール フロー ルールの詳細については、 [Office 365 で電子メール メッセージを暗号化するためにメール フロー ルールの定義](define-mail-flow-rules-to-encrypt-email.md)を参照してください。
  
## <a name="related-topics"></a>関連項目

[送信、表示、および Outlook で暗号化されたメッセージに返信します。](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)
  
[有効にする Aadrm](https://docs.microsoft.com/powershell/module/aadrm/enable-aadrm?view=azureipps)
  
[Exchange Online PowerShell への接続](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)
  
[Office 365 でメールを暗号化するためにメール フロー ルールを定義する](define-mail-flow-rules-to-encrypt-email.md)
