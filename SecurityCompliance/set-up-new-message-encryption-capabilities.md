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
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="83950-104">新しい Office 365 Message Encryption 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="83950-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="83950-p102">Azure の情報保護の保護機能を活用するには、新しい Office 365 メッセージの暗号化 (ホーム) 機能を備えた組織は、任意のデバイス上の他のユーザーと保護された電子メールを簡単に共有できます。ユーザーは、他の Office 365 の組織と同様に Outlook.com、Gmail、その他の電子メール サービスを使用して Office 365 以外のお客様で保護されたメッセージを送受信することができます。</span><span class="sxs-lookup"><span data-stu-id="83950-p102">With the new Office 365 Message Encryption (OME) capabilities, which leverage the protection features in Azure Information Protection, your organization can easily share protected email with anyone on any device. Users can send and receive protected messages with other Office 365 organizations as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>
  
## <a name="get-started-with-ome-by-activating-azure-rights-management-part-of-azure-information-protection"></a><span data-ttu-id="83950-107">Azure の著作権管理、情報保護の Azure の一部をアクティブ化してホームを開始します。</span><span class="sxs-lookup"><span data-stu-id="83950-107">Get started with OME by activating Azure Rights Management, part of Azure Information Protection</span></span>

<span data-ttu-id="83950-p103">ホームの新機能を開始する簡単です。2018 年 2 月時点で Office 365 では、当社のデータ センター内で対象となる組織の新しいホーム機能が自動的に有効にします。組織は、新しい Office 365 テナント組織は、適切なサブスクリプションを持つ場合に対象となります。**Azure アクセス権管理 (Azure RMS)、Azure の情報の保護の一部を有効にした場合に自動的に Office 365 のメッセージの暗号化を有効にします**。ホームを有効にするのには何も行う必要はありません。Azure アクセス権の管理を有効にするのには、 [Azure アクセス権の管理をアクティブにする](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)を参照してください。サブスクリプションについては、どのようなサブスクリプションが必要新しいホームの capabilities? を使用する" [Office 365 のメッセージの暗号化の FAQ](ome-faq.md)を参照してください。Azure の情報保護へのサブスクリプションの購入方法の詳細については、 [Azure の情報の保護](https://azure.microsoft.com/services/information-protection/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83950-p103">It's now easy to get started with the new OME capabilities. As of February 2018, Office 365 automatically enables the new OME capabilities for eligible organizations within our datacenters. Your organization is eligible if it is a new Office 365 tenant and your organization has the appropriate subscriptions. **If you have enabled Azure Rights Management (Azure RMS), part of Azure Information Protection, then we automatically enable Office 365 Message Encryption for you.** You don't have to do anything else to enable OME. To activate Azure Rights Management, see [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service). For information on subscriptions, see "What subscriptions do I need to use the new OME capabilities?" in the [Office 365 Message Encryption FAQ](ome-faq.md). For information about purchasing a subscription to Azure Information Protection, see [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>
  
<span data-ttu-id="83950-p104">使用する場合 Exchange Online では、Active Directory の権限管理サービス (AD RMS)、これらの新機能を直ちに有効にできません。代わりに、Azure の情報保護をまず AD RMS から移行する必要があります。移行が終了したら、次の手順を正常に完了できます。</span><span class="sxs-lookup"><span data-stu-id="83950-p104">If you are using Exchange Online with Active Directory Rights Management service (AD RMS), you can't enable these new capabilities right away. Instead, you need to migrate from AD RMS to Azure Information Protection first. When you've finished the migration, you can successfully complete these steps.</span></span>
  
<span data-ttu-id="83950-120">引き続き使用する場合は、オンプレミス AD RMS Exchange 情報の保護を Azure に移行するのではなく、オンラインにすることはできませんこれらの新機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="83950-120">If you choose to continue to use on-premises AD RMS with Exchange Online instead of migrating to Azure Information Protection, you will not be able to use these new capabilities.</span></span>
  
## <a name="how-the-new-capabilities-for-ome-work"></a><span data-ttu-id="83950-121">ホームの新機能のしくみ</span><span class="sxs-lookup"><span data-stu-id="83950-121">How the new capabilities for OME work</span></span>

<span data-ttu-id="83950-p105">新しい Office 365 のメッセージの暗号化機能では、Azure の情報保護と Azure アクセス権管理 (Azure RMS) とも呼ばれます、保護機能を使用します。これには、電子メールをセキュリティで保護する暗号化、id、および承認のポリシーが含まれます。権利テンプレートの管理、[転送不可] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)では、[暗号化専用のオプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)を使用してメッセージを暗号化できます。ユーザーは、これらのオプションを使用して、電子メール メッセージ、およびさまざまな Office 365 の添付ファイルを暗号化できます。サポートされている添付ファイルの種類の完全なリストでは[「ファイルの種類に覆われてメッセージに接続されたときに IRM ポリシー」で電子メール メッセージの IRM の概要](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)」を参照してください。管理者は、この保護を適用するメールの流れの規則を定義することもできます。たとえば、ルール、特定の受信者にアドレス指定するか、件名に特定の文字が含まれているすべての保護されていないメッセージは、不正なアクセスから保護されていると、受信者は、コピーまたはメッセージの内容を印刷することはできませんを定義できます。</span><span class="sxs-lookup"><span data-stu-id="83950-p105">The new Office 365 Message Encryption capabilities use the protection capabilities, also called Azure Rights Management (Azure RMS), from Azure Information Protection. This includes encryption, identity, and authorization policies to help secure your email. You can encrypt messages by using rights management templates, the [Do Not Forward option](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails), and the [encrypt-only option](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails). Users can then encrypt email messages and a variety of Office 365 attachments by using these options. For a full list of supported attachment types, see ["File types covered by IRM policies when they are attached to messages" in Introduction to IRM for email messages](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM). As an administrator, you can also define mail flow rules to apply this protection. For example, you can define a rule where all unprotected messages that are addressed to a specific recipient or that contain specific words in the subject line are protected from unauthorized access, and the recipients can't copy or print the contents of the message.</span></span>
  
<span data-ttu-id="83950-p106">ホームの以前のバージョンとは異なり、組織内、または Office 365 の外部の受信者にメールを送信するかどうか、これらの新機能は送信者の統合されたエクスペリエンスを提供します。さらに、2016 の Outlook または Outlook web 上の Office 365 アカウントに送信される保護された電子メール メッセージを受信する受信者のメッセージを表示する追加アクションを実行する必要はありません。シームレスに動作します。その他の電子メール クライアントと電子メール サービス プロバイダーを使用して受信者には、改善された経験があります。については、 [Office 365 で保護されたメッセージを表示](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)し、[保護されたメッセージを開く方法](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83950-p106">Unlike the previous version of OME, these new capabilities provide a unified sender experience whether you're sending mail inside your organization or to recipients outside of Office 365. In addition, recipients who receive a protected email message sent to an Office 365 account in Outlook 2016 or Outlook on the web, don't have to take any additional action to view the message. It works seamlessly. Recipients using other email clients and email service providers also have an improved experience. For information, see [Learn about protected messages in Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) and [How do I open a protected message](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).</span></span>
  
## <a name="steps-to-manually-set-up-the-new-capabilities-for-ome"></a><span data-ttu-id="83950-134">ホームに、新しい機能を手動で設定する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="83950-134">Steps to manually set up the new capabilities for OME</span></span>

<span data-ttu-id="83950-135">組織に自動的に有効にすると、ホームがあるない場合、またはホームの電源をオンにした場合は、手順はホーム用の新しい機能を手動で設定します。</span><span class="sxs-lookup"><span data-stu-id="83950-135">If your organization does not automatically have OME enabled, or if you turned OME off, follow these steps to manually set up the new capabilities for OME.</span></span>
  
### <a name="to-manually-set-up-the-new-capabilities-for-ome"></a><span data-ttu-id="83950-136">ホームに、新しい機能を手動で設定するには</span><span class="sxs-lookup"><span data-stu-id="83950-136">To manually set up the new capabilities for OME</span></span>

1. <span data-ttu-id="83950-p107">組織のサブスクリプションがあることを確認します。サブスクリプションについてを参照してください「どのようなサブスクリプションが必要、新しいホーム capabilities? を使用する」で、 [Office 365 のメッセージの暗号化に関する FAQ です。](ome-faq.md)です。Azure の情報保護へのサブスクリプションの購入方法の詳細については、 [Azure の情報の保護](https://azure.microsoft.com/services/information-protection/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83950-p107">Ensure you have the right subscription for your organization. For information on subscriptions, see "What subscriptions do I need to use the new OME capabilities?" in the [Office 365 Message Encryption FAQ.](ome-faq.md). For information about purchasing a subscription to Azure Information Protection, see [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span></span>

2. <span data-ttu-id="83950-p108">Microsoft Azure 情報の保護 (既定値) のルート キーを管理するかを生成し (独自のキー、または BYOK と呼ばれる) 手動でこのキーを管理するかどうかを決定します。生成し、このキーを手動で管理する場合は、ホームの新機能を設定する前にいくつかの手順を完了する必要があります。詳細については、[計画と Azure の情報保護のテナントのキーを実装する](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)を参照してください。ホームを設定する前に次の手順を完了することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="83950-p108">Decide whether you want Microsoft to manage the root key for Azure Information Protection (the default), or generate and manage this key yourself (known as bring your own key, or BYOK). If you want to generate and manage this key yourself, you need to complete some steps before you set up the new capabilities for OME. For more information, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key). Microsoft recommends that you complete these steps before you set up OME.</span></span>

3. <span data-ttu-id="83950-p109">Azure アクセス権の管理を実行することによって、ホームの新しい機能を有効にします。手順については、 [Azure アクセス権の管理をアクティブにする](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service)を参照してください。これを行うと、Office 365 は自動的にするためホームの新機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="83950-p109">Enable the new capabilities for OME by activating Azure Rights Management. For instructions, see [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service). When you do this, Office 365 automatically enables the new OME capabilities for you.</span></span>

    > [!TIP]
    > <span data-ttu-id="83950-p110">Web 上で outlook は、ホームのこのクライアントを使用して電子メール メッセージに新しい機能を適用する前に 1 日を待機することをお勧めするための UI をキャッシュします。UI は、新しい構成を反映するように更新をする前に、ホームの新しい機能は使用できません。UI を更新した後、ユーザーは、ホームの新しい機能を使用して電子メール メッセージを保護できます。</span><span class="sxs-lookup"><span data-stu-id="83950-p110">Outlook on the Web caches its UI, so it's a good idea to wait a day before you try applying the new capabilities for OME to email messages using this client. Before the UI updates to reflect the new configuration, the new capabilities for OME won't be available. After the UI updates, users can protect email messages by using the new capabilities for OME.</span></span>
  
4. <span data-ttu-id="83950-151">(省略可能)新しいメール フロー ルールを設定または組織から送信されたメッセージを暗号化するために Office 365 をする時期と方法を定義する既存のメール フロー ルールを更新します。</span><span class="sxs-lookup"><span data-stu-id="83950-151">(Optional) Set up new mail flow rules or update existing mail flow rules that define how and when you want Office 365 to encrypt messages sent from your organization.</span></span>

## <a name="verify-that-the-new-capabilities-for-ome-are-configured-properly-by-using-windows-powershell"></a><span data-ttu-id="83950-152">Windows PowerShell を使用してホームの新機能が正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="83950-152">Verify that the new capabilities for OME are configured properly by using Windows PowerShell</span></span>

<span data-ttu-id="83950-153">この手順では、Exchange オンライン PowerShell からホームの新機能を使用するのには、テナントが正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="83950-153">Follow these steps to verify that your tenant is properly configured to use the new capabilities for OME through Exchange Online PowerShell.</span></span>
  
1. <span data-ttu-id="83950-p111">大域管理者アクセス許可を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、Windows PowerShell セッションを開始し、Exchange Online に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://aka.ms/exopowershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83950-p111">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="83950-156">次の構文を使用してテスト IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="83950-156">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

    ```Test-IRMConfiguration [-Sender <email address >]```  

   <span data-ttu-id="83950-157">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="83950-157">For example:</span></span>

    ```Test-IRMConfiguration -Sender securityadmin@contoso.com```

    <span data-ttu-id="83950-p112">電子メール アドレスの Office 365 の組織内のユーザーの電子メール アドレスです。オプションであり、提供するときに、送信者の電子メール アドレスは追加チェックを実行するシステムを強制します。結果は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="83950-p112">Where email address is the email address of a user in your Office 365 organization. While optional, providing a sender email address forces the system to perform additional checks. Your results should look like these:</span></span>

    
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

    <span data-ttu-id="83950-161">*Contoso 社*では、Office 365 の組織の名前に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="83950-161">Where *Contoso* is replaced with the name of your Office 365 organization.</span></span> 

    <span data-ttu-id="83950-162">結果で返される既定のテンプレートの名前は、上記の結果に表示されるものとは異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83950-162">The names of the default templates returned in the results may be different from those displayed in the results above.</span></span>

    <span data-ttu-id="83950-p113">テンプレートと既定のテンプレートについての情報の概要については、[構成して Azure の情報保護のためのテンプレートを管理する](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)を参照してください。転送の実行方法について] して、[暗号化専用のオプションを作成する既存のテンプレートに追加のテンプレート、またはどのような権限を確認は含まれている、方法は、 [Azure の権利管理の使用権限を設定する](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83950-p113">For an introduction to templates and information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the Do Not Forward option, encrypt-only option, and how to create additional templates, or find out what rights are included in an existing template, see [Configuring usage rights for Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights).</span></span>

3. <span data-ttu-id="83950-165">権限管理サービスから切断するのには削除 PSSession コマンドレットを実行するには。</span><span class="sxs-lookup"><span data-stu-id="83950-165">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>
    
    ```Remove-PSSession $session```

## <a name="next-steps-define-new-mail-flow-rules-that-use-the-new-ome-capabilities"></a><span data-ttu-id="83950-166">次の手順: ホームの新機能を使用して、新規のメール フロー ルールを定義します。</span><span class="sxs-lookup"><span data-stu-id="83950-166">Next steps: Define new mail flow rules that use the new OME capabilities</span></span>
<span data-ttu-id="83950-167"><a name="Rules_1"> </a></span><span class="sxs-lookup"><span data-stu-id="83950-167"></span></span>

<span data-ttu-id="83950-p114">この手順では、ホームの新規導入では省略可能、ただし、この手順は、既にメール フロー ルール設定の送信メールを暗号化されている既存のホームの展開に必要です。ホームの新機能を利用する場合、既存のメール フロー ルールを更新する必要があります。それ以外の場合、ユーザーは引き続き、シームレスな新しいホームの経験ではなく HTML 添付ファイルの以前の形式を使用する暗号化されたメールを受信します。</span><span class="sxs-lookup"><span data-stu-id="83950-p114">This step is optional for new OME deployments, however, this step is required for existing OME deployments that already have mail flow rules set up to encrypt outgoing mail. If you want to take advantage of the new OME capabilities, you must update your existing mail flow rules. Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience.</span></span>
  
<span data-ttu-id="83950-p115">メール フロー ルールは、どのような条件の e メールでメッセージを暗号化するか、その暗号化を削除するための条件とを確認します。ルールのアクションを設定すると、送信することと、ルールの条件に一致するすべてのメッセージは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="83950-p115">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption. When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="83950-173">メール フロー ルールの詳細については、 [Office 365 で電子メール メッセージを暗号化するためにメール フロー ルールの定義](define-mail-flow-rules-to-encrypt-email.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83950-173">For more information about mail flow rules, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="83950-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="83950-174">Related Topics</span></span>

[<span data-ttu-id="83950-175">送信、表示、および Outlook で暗号化されたメッセージに返信します。</span><span class="sxs-lookup"><span data-stu-id="83950-175">Send, view, and reply to encrypted messages in Outlook</span></span>](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)
  
[<span data-ttu-id="83950-176">有効にする Aadrm</span><span class="sxs-lookup"><span data-stu-id="83950-176">Enable-Aadrm</span></span>](https://docs.microsoft.com/powershell/module/aadrm/enable-aadrm?view=azureipps)
  
[<span data-ttu-id="83950-177">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="83950-177">Connect to Exchange Online PowerShell</span></span>](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="83950-178">Office 365 でメールを暗号化するためにメール フロー ルールを定義する</span><span class="sxs-lookup"><span data-stu-id="83950-178">Define mail flow rules to encrypt email messages in Office 365</span></span>](define-mail-flow-rules-to-encrypt-email.md)
