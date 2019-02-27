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
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="53a14-104">新しい Office 365 Message Encryption 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="53a14-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="53a14-p102">新しい Office 365 メッセージ暗号化 (OME) 機能を使用すると、組織は、保護された電子メールを任意のデバイス上のすべてのユーザーと共有できます。ユーザーは、保護されたメッセージを他の office 365 組織や、Outlook.com、Gmail、その他の電子メールサービスを使用している非 office 365 ユーザーと交換することができます。</span><span class="sxs-lookup"><span data-stu-id="53a14-p102">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device. Users can exchange protected messages with other Office 365 organizations, as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>


>[!NOTE]
><span data-ttu-id="53a14-p103">この記事は、管理者および IT 担当者を対象としています。エンドユーザーの場合は、適切なソリューションについて、「 [Office 365 Message Encryption (OME)](ome.md) 」の記事の一覧を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53a14-p103">This article is intended for administrators and IT professionals. If you're an end-user, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) for appropriate solutions.</span></span>

<span data-ttu-id="53a14-109">Office 365 テナントで新しい OME 機能が使用できることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="53a14-109">Follow the steps below to ensure that the New OME capabilities are available in your Office 365 tenant.</span></span> 

## <a name="verify-azure-rights-management-arm-is-active"></a><span data-ttu-id="53a14-110">Azure Rights Management (ARM) がアクティブであることを確認する</span><span class="sxs-lookup"><span data-stu-id="53a14-110">Verify Azure Rights Management (ARM) is active</span></span>

>[!NOTE]
><span data-ttu-id="53a14-111">新しい OME 機能により、azure [Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)によって使用されるテクノロジである[azure Information protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection)の保護機能が活用されます。</span><span class="sxs-lookup"><span data-stu-id="53a14-111">The new OME capabilities leverage the protection features in [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), the technology used by [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms).</span></span>

<span data-ttu-id="53a14-p104">新しい OME 機能を使用するための唯一の前提条件は、Office 365 テナントで[Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)を有効にする必要があることです。その場合、Office 365 は新しい OME 機能を自動的に有効にし、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="53a14-p104">The only prerequisite for using the new OME capabilities is that [Azure Rights Management (ARM)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) must be activated in your Office 365 tenant. If it is, Office 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span> 

<span data-ttu-id="53a14-p105">ARM は、ほとんどの対象となるプランに対して自動的にアクティブ化されるので、この点を考慮する必要はありません。詳細については、「 [Azure Rights Management のアクティブ化](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53a14-p105">ARM is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either. See [Activating Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) for more.</span></span>

>[!IMPORTANT]
><span data-ttu-id="53a14-p106">Exchange Online で Active Directory Rights Management サービス (AD RMS) を使用する場合は、新しい OME 機能を使用する前に、 [Azure Information Protection に移行](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms)する必要があります。AD RMS は ARM と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="53a14-p106">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities. AD RMS is not compatible with ARM.</span></span>  

<span data-ttu-id="53a14-118">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53a14-118">For more, see:</span></span>

- <span data-ttu-id="53a14-119">[新しい OME 機能を使用するために必要なサブスクリプションは何ですか。](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)サブスクリプションプランに Azure Information Protection (ARM を含む) が含まれているかどうかを確認する。</span><span class="sxs-lookup"><span data-stu-id="53a14-119">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes ARM).</span></span>   
-  <span data-ttu-id="53a14-120">適格なサブスクリプションの購入については、「 [Azure information Protection](https://azure.microsoft.com/en-us/services/information-protection/) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53a14-120">[Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-arm"></a><span data-ttu-id="53a14-121">ARM を手動でアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="53a14-121">Manually activating ARM</span></span>

<span data-ttu-id="53a14-122">ARM を無効にした場合、または何らかの理由で自動的にアクティブ化されなかった場合は、次のように手動でアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="53a14-122">If you disabled ARM, or if it was not automatically activated for any reason, you can activated it manually in the :</span></span>

- <span data-ttu-id="53a14-123">**office 365 管理センター**: 手順について[は、「office 365 管理センターから Azure Rights Management をアクティブ化する方法](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53a14-123">**Office 365 admin center**: See [How to activate Azure Rights Management from the Office 365 admin center](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) for instructions</span></span>
- <span data-ttu-id="53a14-124">**azure portal**: 手順については、「azure [portal から azure Rights Management をアクティブ化する方法](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53a14-124">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) for instructions.</span></span> 


## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="53a14-125">Azure Information Protection のテナントキーの管理を構成する</span><span class="sxs-lookup"><span data-stu-id="53a14-125">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="53a14-p107">これは、省略可能な手順です。Microsoft が Azure Information Protection のルートキーを管理できるようにすることは、ほとんどの Office 365 テナントの既定の設定と推奨されるベストプラクティスです。その場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="53a14-p107">This is an optional step. Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most Office 365 tenants. If this is the case, you don't need to do anything.</span></span> 

<span data-ttu-id="53a14-p108">多くの理由から、たとえばコンプライアンス要件によっては、独自のルートキーを生成して管理する必要が生じることがあります (つまり、独自のキーを持っている (byok))。その場合は、新しい OME 機能を設定する前に必要な手順を完了することをお勧めします。詳細については[、「Azure Information Protection のテナントキーを計画および実装](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53a14-p108">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)). If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities. See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span> 


## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="53a14-132">Exchange Online PowerShell で新しい OME 構成を確認する</span><span class="sxs-lookup"><span data-stu-id="53a14-132">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="53a14-133">Office 365 テナントが、 [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)の新しい OME 機能を使用するように適切に構成されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="53a14-133">You can verify that your Office 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="53a14-134">Office 365 テナント内のグローバル管理者のアクセス許可を持つアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="53a14-134">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="53a14-135">次の構文を使用して、テスト用の irmconfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="53a14-135">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="53a14-136">**例**:</span><span class="sxs-lookup"><span data-stu-id="53a14-136">**Example**:</span></span> 
   
     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```
     
     - <span data-ttu-id="53a14-p109">送信者の電子メールを指定することはオプションですが、システムが追加のチェックを実行することを強制します。Office 365 テナント内のユーザーの電子メールアドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="53a14-p109">Providing a sender email is optional, but forces the system to perform additional checks. Use the email address of any user in your Office 365 tenant.</span></span> 
     
    <span data-ttu-id="53a14-139">結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="53a14-139">Your results should be similar to:</span></span>

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

   - <span data-ttu-id="53a14-140">Office 365 組織名は*Contoso*と置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="53a14-140">Your Office 365 organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="53a14-p110">既定のテンプレート名は、上に表示されているものとは異なる場合があります。詳細については[、「Azure Information Protection のテンプレートを構成および管理](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53a14-p110">The default template names may be different from those displayed above. See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) for more.</span></span>

3. <span data-ttu-id="53a14-143">削除コマンドレットを実行して、Rights Management サービスとの接続を解除します。</span><span class="sxs-lookup"><span data-stu-id="53a14-143">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>
    
     ```powershell
     Remove-PSSession $session
     ```

## <a name="update-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="53a14-144">新しい OME 機能を使用するようにメールフロールールを更新する</span><span class="sxs-lookup"><span data-stu-id="53a14-144">Update mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="53a14-p111">Office 365 テナントの[電子メールを暗号化するように事前に](define-mail-flow-rules-to-encrypt-email.md)構成されたメールフロールールがある場合は、新しい OME 機能を使用するように既存のルールを更新する必要があります。新規展開の場合、この手順はこの段階では必要ありません。</span><span class="sxs-lookup"><span data-stu-id="53a14-p111">If there are previously configured [mail flow rules to encrypt email](define-mail-flow-rules-to-encrypt-email.md) in your Office 365 tenant, you need to update these existing rules to use the new OME capabilities. For new deployments, this step is unnecessary at this stage.</span></span>   

>[!Note]
><span data-ttu-id="53a14-p112">メールフロールールは、電子メールメッセージが暗号化されるとき、および暗号化が削除されるときの条件を定義します。詳細については、「 [Office 365 で電子メールメッセージを暗号化するためのメールフロールールの定義」を](define-mail-flow-rules-to-encrypt-email.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="53a14-p112">Mail flow rules define the conditions under which email messages are encrypted, and when encryption should be removed. See [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md) for more.</span></span>

<span data-ttu-id="53a14-149">既存のルールを更新して、新しい OME 機能を使用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="53a14-149">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="53a14-150">Office 365 管理センターで、[**管理センター > Exchange**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="53a14-150">In the Office 365 admin center, go to **Admin centers > Exchange**.</span></span>

2. <span data-ttu-id="53a14-151">Exchange 管理センターで、[**メールフロー > ルール**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="53a14-151">In the Exchange admin center, go to **Mail flow > Rules**.</span></span> 
3. <span data-ttu-id="53a14-152">ルールごとに、**次の操作を行い**ます。</span><span class="sxs-lookup"><span data-stu-id="53a14-152">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="53a14-153">[**メッセージのセキュリティを変更する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53a14-153">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="53a14-154">[ **Office 365 メッセージの暗号化と権限保護を適用**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="53a14-154">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="53a14-155">一覧から RMS テンプレートを選択する</span><span class="sxs-lookup"><span data-stu-id="53a14-155">Select an RMS template from the list</span></span>
    - <span data-ttu-id="53a14-156">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="53a14-156">Select **Save**.</span></span>
    - <span data-ttu-id="53a14-157">[**OK**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="53a14-157">Select **OK**.</span></span>
  
>[!IMPORTANT]
><span data-ttu-id="53a14-158">既存のメールフロールールを更新しない場合、ユーザーは、新しい OME 機能ではなく、以前の HTML 添付ファイル形式を使用する暗号化メールを引き続き受信できます。</span><span class="sxs-lookup"><span data-stu-id="53a14-158">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new OME capabilities.</span></span>
