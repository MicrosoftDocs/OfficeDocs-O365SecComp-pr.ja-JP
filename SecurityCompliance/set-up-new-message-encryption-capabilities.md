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
ms.openlocfilehash: eddafca15fa4efdd3f929145e7933a3b7dfb5f27
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220647"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a>新しい Office 365 Message Encryption 機能を設定する

新しい Office 365 Message Encryption (OME) 機能を使用すると、Azure Information protection の保護機能を活用できるため、組織は、保護された電子メールを任意のデバイス上のすべてのユーザーと簡単に共有できます。ユーザーは、Outlook.com、Gmail、その他の電子メールサービスを使用して、他の office 365 組織および非 office 365 ユーザーとの保護されたメッセージを送受信できます。

||
|:-----|
|この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。この記事は、管理者および it 担当者を対象としています。暗号化されたメッセージの送信または受信に関する情報をお探しの場合は、「 [Office 365 message Encryption (OME)](ome.md) 」の記事の一覧を参照し、ニーズに最も適した記事を見つけてください。 |
||

## <a name="get-started-with-ome-by-activating-azure-rights-management-part-of-azure-information-protection"></a>azure Rights Management をアクティブ化して OME の使用を開始する (azure Information Protection の一部)

これで、新しい OME 機能を使い始めることができます。2018年2月時点で、Office 365 はデータセンター内の対象組織に対して新しい OME 機能を自動的に有効にします。組織が新しい Office 365 テナントであり、組織が適切なサブスクリプションを持っている場合は、組織は対象となります。azure **Rights Management (azure RMS) を有効にしている場合は、azure Information Protection の一部として、Office 365 メッセージの暗号化が自動的に有効になります。** OME を有効にするために他の作業を行う必要はありません。azure rights management をアクティブ化するには、「 [azure rights management をアクティブ](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)化する」を参照してください。サブスクリプションの詳細については、「 [Office 365 メッセージ暗号化](ome-faq.md)に関する FAQ」の「新しい OME capabilities? を使用するために必要なサブスクリプションについて」を参照してください。azure information protection のサブスクリプションを購入する方法については、「 [azure information protection](https://azure.microsoft.com/services/information-protection/)」を参照してください。
  
Active Directory Rights Management サービス (AD RMS) を使用して Exchange Online を使用している場合、これらの新機能をすぐに有効にすることはできません。代わりに、まず AD RMS から Azure Information Protection に移行する必要があります。移行が完了したら、次の手順を正常に完了できます。
  
Azure Information Protection に移行するのではなく、Exchange Online でオンプレミスの AD RMS を引き続き使用することを選択した場合、これらの新機能を使用することはできません。
  
## <a name="how-the-new-capabilities-for-ome-work"></a>OME の新機能のしくみ

新しい Office 365 メッセージの暗号化機能では、azure Information protection から azure Rights Management (azure RMS) とも呼ばれる保護機能を使用します。これには、電子メールのセキュリティ保護に役立つ暗号化、id、および承認のポリシーが含まれます。[rights management テンプレート]、[[転送不可] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)、および [[暗号化のみ] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)を使用してメッセージを暗号化できます。ユーザーは、これらのオプションを使用して、電子メールメッセージとさまざまな Office 365 添付ファイルを暗号化できます。サポートされている添付ファイルの種類の完全な一覧については、「[電子メールメッセージの irm の概要」の「メッセージに添付されているファイルの種類」](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)を参照してください。管理者は、この保護を適用するメールフロールールを定義することもできます。たとえば、特定の受信者に宛てられた、または件名に特定の単語が含まれているすべての保護されていないメッセージが、権限のないアクセスから保護されるルールを定義できます。また、受信者はメッセージの内容をコピーまたは印刷できません。
  
以前のバージョンの OME とは異なり、これらの新機能により、組織内または Office 365 の外部の受信者にメールを送信しているかどうかにかかわらず、統合された送信者の環境が提供されます。また、outlook 2016 または web 上の outlook で Office 365 アカウントに送信される保護された電子メールメッセージを受信する受信者は、メッセージを表示するために追加のアクションを実行する必要はありません。シームレスに動作します。他の電子メールクライアントや電子メールサービスプロバイダーを使用する受信者にも、改善された操作性があります。詳細については、「 [Office 365 で保護されたメッセージについ](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)て」および「[保護されたメッセージを開く方法](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)」を参照してください。

以前のバージョンの OME と新しい OME 機能との違いの詳細な一覧については、「 [OME のバージョンを比較](ome-version-comparison.md)する」を参照してください。
  
## <a name="steps-to-manually-set-up-the-new-capabilities-for-ome"></a>OME の新機能を手動でセットアップする手順

OME の新機能は、ほとんどの Office 365 組織で自動的に有効になります。組織の OME が自動的に有効になっていない場合、または新しい OME 機能をオフにした場合は、次の手順に従って、OME の新しい機能を手動でセットアップします。
  
### <a name="to-manually-set-up-the-new-capabilities-for-ome"></a>OME の新機能を手動でセットアップするには

1. 組織に適切なサブスクリプションがあることを確認します。サブスクリプションの詳細については、「 [Office 365 のメッセージ暗号化](ome-faq.md)に関する FAQ」の「新しい OME capabilities? を使用するために必要なサブスクリプションについて」を参照してください。azure information protection のサブスクリプションを購入する方法については、「 [azure information protection](https://azure.microsoft.com/services/information-protection/)」を参照してください。

2. Microsoft が Azure Information Protection (既定) のルートキーを管理するかどうかを決定するか、このキーを自分で生成して管理するか (自分のキーを持参する、または byok) を決定します。このキーを自分で生成して管理する場合は、OME の新機能をセットアップする前に、いくつかの手順を完了する必要があります。詳細については、「 [Azure information Protection のテナントキーを計画および実装する](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)」を参照してください。Microsoft では、OME をセットアップする前に、これらの手順を完了することをお勧めします。

3. Azure Rights Management をアクティブ化することにより、OME の新機能を有効にします。手順については、「 [Azure Rights Management をアクティブ化](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)する」を参照してください。この操作を行うと、Office 365 は自動的に新しい OME 機能を有効にします。

    > [!TIP]
    > Web 上の Outlook では UI がキャッシュされるので、このクライアントを使用して電子メールメッセージを送信するための新しい機能を OME に適用する前に、1日以内に待機することをお勧めします。UI を更新して新しい構成を反映する前に、OME の新機能は使用できません。UI を更新した後、ユーザーは OME の新機能を使用して電子メールメッセージを保護できます。
  
4. オプション新しいメールフロールールを設定したり、組織から送信されたメッセージを Office 365 で暗号化する方法とタイミングを定義する既存のメールフロールールを更新します。

## <a name="verify-that-the-new-capabilities-for-ome-are-configured-properly-by-using-windows-powershell"></a>Windows PowerShell を使用して、OME の新機能が適切に構成されていることを確認する

次の手順に従って、Exchange Online PowerShell を使用して OME の新しい機能を使用するようにテナントが適切に構成されていることを確認します。
  
1. Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、「 [Exchange Online PowerShell への接続](https://aka.ms/exopowershell)」を参照してください。

2. 次の構文を使用して、テスト用の irmconfiguration コマンドレットを実行します。

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   次に例を示します。

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

    ここで、電子メールアドレスは、Office 365 組織のユーザーの電子メールアドレスです。オプションで、送信者の電子メールアドレスを指定すると、システムが追加のチェックを実行することを強制します。結果は次のようになります。

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

    *Contoso*は、Office 365 組織の名前に置き換えられます。

    結果で返される既定のテンプレートの名前は、上記の結果に表示されるものと異なる場合があります。

    既定のテンプレートに関するテンプレートと情報の概要については、「 [Azure information Protection 用のテンプレートを構成および管理](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)する」を参照してください。[転送不可] オプション、[暗号化のみ] オプション、追加テンプレートを作成する方法、または既存のテンプレートに含まれている権限を確認する方法については、「 [Azure rights Management の使用権限の構成](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights)」を参照してください。

3. 削除コマンドレットを実行して、Rights Management サービスとの接続を解除します。
    
     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-new-mail-flow-rules-that-use-the-new-ome-capabilities"></a>次の手順: 新しい OME 機能を使用する新しいメールフロールールを定義する

この手順は、新しい OME 展開ではオプションですが、この手順は、メールフロールールが既に設定されている既存の OME 展開で、送信メールを暗号化するために必要です。新しい OME 機能を利用する場合は、既存のメールフロールールを更新する必要があります。そうしないと、ユーザーは、新しいシームレスな OME の操作ではなく、前の HTML 添付ファイル形式を使用する暗号化メールを引き続き受信できます。
  
メールフロールールは、電子メールメッセージを暗号化する条件、およびその暗号化を削除するための条件を決定します。ルールのアクションを設定すると、ルールの条件に一致するメッセージはすべて、送信時に暗号化されます。
  
メールフロールールの詳細については、「 [Office のメールメッセージを暗号化するためのメールフロールールを定義する 365](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。
  
## <a name="related-topics"></a>関連トピック

[Outlook で暗号化されたメッセージの送信、表示、および返信を行う](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)
  
[し](https://docs.microsoft.com/powershell/module/aadrm/enable-aadrm?view=azureipps)
  
[Exchange Online PowerShell への接続](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)
  
[Office 365 でメールを暗号化するためにメール フロー ルールを定義する](define-mail-flow-rules-to-encrypt-email.md)
