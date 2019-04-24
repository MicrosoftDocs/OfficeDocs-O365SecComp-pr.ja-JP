---
title: 新しい Office 365 Message Encryption 機能を設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/12/2019
ms.audience: ITPro
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
ms.openlocfilehash: ea8756d08b1c172c433d6cd8ad1752c4c7ad64e9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260755"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="7b30d-104">新しい Office 365 Message Encryption 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="7b30d-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="7b30d-105">新しい Office 365 メッセージ暗号化 (OME) 機能を使用すると、組織は、保護された電子メールを任意のデバイス上のすべてのユーザーと共有できます。</span><span class="sxs-lookup"><span data-stu-id="7b30d-105">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="7b30d-106">ユーザーは、保護されたメッセージを他の office 365 組織や、Outlook.com、Gmail、その他の電子メールサービスを使用している非 office 365 ユーザーと交換することができます。</span><span class="sxs-lookup"><span data-stu-id="7b30d-106">Users can exchange protected messages with other Office 365 organizations, as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

||
|:-----|
|<span data-ttu-id="7b30d-107">この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。</span><span class="sxs-lookup"><span data-stu-id="7b30d-107">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="7b30d-108">この記事は、管理者および IT 担当者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="7b30d-108">This article is intended for administrators and IT Pros.</span></span> <span data-ttu-id="7b30d-109">暗号化されたメッセージの送信または受信に関する情報をお探しの場合は、「 [Office 365 message Encryption (OME)](ome.md) 」の記事の一覧を参照し、ニーズに最も適した記事を見つけてください。</span><span class="sxs-lookup"><span data-stu-id="7b30d-109">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

<span data-ttu-id="7b30d-110">Office 365 組織で新しい OME 機能が使用できることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-110">Follow the steps below to ensure that the New OME capabilities are available in your Office 365 organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="7b30d-111">Azure Rights Management がアクティブであることを確認する</span><span class="sxs-lookup"><span data-stu-id="7b30d-111">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="7b30d-112">新しい OME 機能により、azure [Rights Management Services (azure RMS)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection)の保護機能が活用されます。これは、 [azure Information protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)が暗号化とアクセス制御を介してメールやドキュメントを保護するために使用するテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="7b30d-112">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/en-us/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="7b30d-113">新しい OME 機能を使用するための唯一の前提条件は、組織のテナントで[Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms)をアクティブ化する必要があるということです。</span><span class="sxs-lookup"><span data-stu-id="7b30d-113">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](https://docs.microsoft.com/en-us/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="7b30d-114">その場合、Office 365 は新しい OME 機能を自動的に有効にし、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7b30d-114">If it is, Office 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="7b30d-115">Azure RMS は、ほとんどの対象となるプランに対して自動的にアクティブ化されるので、多くの場合、この点に関して何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7b30d-115">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="7b30d-116">詳細については、「 [Azure Rights Management をアクティブ化](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b30d-116">See [Activating Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="7b30d-117">Exchange Online で Active Directory Rights Management サービス (AD RMS) を使用する場合は、新しい OME 機能を使用する前に、 [Azure Information Protection に移行](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b30d-117">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="7b30d-118">OME は AD RMS と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="7b30d-118">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="7b30d-119">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b30d-119">For more information, see:</span></span>

- <span data-ttu-id="7b30d-120">[新しい OME 機能を使用するために必要なサブスクリプションは何ですか。](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)サブスクリプションプランに azure Information Protection (azure RMS 機能を含む) が含まれているかどうかを確認するには</span><span class="sxs-lookup"><span data-stu-id="7b30d-120">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="7b30d-121">適格なサブスクリプションの購入については、「 [Azure information Protection](https://azure.microsoft.com/en-us/services/information-protection/) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b30d-121">[Azure Information Protection](https://azure.microsoft.com/en-us/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="7b30d-122">Azure Rights Management を手動でアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="7b30d-122">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="7b30d-123">Azure RMS を無効にした場合、または何らかの理由で自動的にアクティブ化されなかった場合は、次の方法で手動でアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="7b30d-123">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="7b30d-124">**office 365 管理センター**: 手順については[、「office 365 管理センターから Azure Rights Management をアクティブ化する方法](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b30d-124">**Office 365 admin center**: See [How to activate Azure Rights Management from the Office 365 admin center](https://docs.microsoft.com/en-us/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="7b30d-125">**azure portal**: 手順については、「azure [portal から azure Rights Management をアクティブ化する方法](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b30d-125">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="7b30d-126">Azure Information Protection のテナントキーの管理を構成する</span><span class="sxs-lookup"><span data-stu-id="7b30d-126">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="7b30d-127">これは、省略可能な手順です。</span><span class="sxs-lookup"><span data-stu-id="7b30d-127">This is an optional step.</span></span> <span data-ttu-id="7b30d-128">Microsoft が Azure Information Protection のルートキーを管理できるようにすることは、ほとんどの Office 365 テナントの既定の設定と推奨されるベストプラクティスです。</span><span class="sxs-lookup"><span data-stu-id="7b30d-128">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most Office 365 tenants.</span></span> <span data-ttu-id="7b30d-129">その場合は、何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7b30d-129">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="7b30d-130">多くの理由から、たとえばコンプライアンス要件によっては、独自のルートキーを生成して管理する必要が生じることがあります (つまり、独自のキーを持っている (byok))。</span><span class="sxs-lookup"><span data-stu-id="7b30d-130">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="7b30d-131">その場合は、新しい OME 機能を設定する前に必要な手順を完了することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7b30d-131">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="7b30d-132">詳細については[、「Azure Information Protection のテナントキーを計画および実装](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b30d-132">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="7b30d-133">Exchange Online PowerShell で新しい OME 構成を確認する</span><span class="sxs-lookup"><span data-stu-id="7b30d-133">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="7b30d-134">Office 365 テナントが、 [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)の新しい OME 機能を使用するように適切に構成されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7b30d-134">You can verify that your Office 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="7b30d-135">Office 365 テナント内のグローバル管理者のアクセス許可を持つアカウントを使用して、 [Exchange Online PowerShell に接続](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-135">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="7b30d-136">Get-irmconfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-136">Run the Get-IRMConfiguration cmdlet.</span></span>

     <span data-ttu-id="7b30d-137">AzureRMSEnabled パラメーターに $True の値が表示されます。これは、テナントで OME が構成されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-137">You should see a value of $True for the AzureRMSEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="7b30d-138">指定されていない場合は、AzureRMSEnabled を有効にするために OME を有効にするために、の値を設定するには、set-irmconfiguration を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-138">If it is not, use Set-IRMConfiguration to set the value of AzureRMSEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="7b30d-139">次の構文を使用して、テスト用の irmconfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-139">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="7b30d-140">**例**:</span><span class="sxs-lookup"><span data-stu-id="7b30d-140">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="7b30d-141">送信者の電子メールを指定することはオプションですが、システムが追加のチェックを実行することを強制します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-141">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="7b30d-142">Office 365 テナント内のユーザーの電子メールアドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-142">Use the email address of any user in your Office 365 tenant.</span></span>

     <span data-ttu-id="7b30d-143">結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="7b30d-143">Your results should be similar to:</span></span>

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

   - <span data-ttu-id="7b30d-144">Office 365 組織名は*Contoso*と置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="7b30d-144">Your Office 365 organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="7b30d-145">既定のテンプレート名は、上に表示されているものとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b30d-145">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="7b30d-146">詳細については[、「Azure Information Protection のテンプレートを構成および管理](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b30d-146">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="7b30d-147">削除コマンドレットを実行して、Rights Management サービスとの接続を解除します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-147">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="7b30d-148">次の手順: 新しい OME 機能を使用するためのメールフロールールを定義する</span><span class="sxs-lookup"><span data-stu-id="7b30d-148">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="7b30d-149">Office 365 組織の電子メールを暗号化するように事前に構成されたメールフロールールがある場合は、新しい OME 機能を使用するように既存のルールを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b30d-149">If there are previously configured mail flow rules to encrypt email in your Office 365 organization, you need to update the existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="7b30d-150">新規展開の場合は、新しいメールフロールールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b30d-150">For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="7b30d-151">既存のメールフロールールを更新しない場合、ユーザーは、新しいシームレスな OME の操作ではなく、以前の HTML 添付ファイル形式を使用する暗号化メールの受信を続行します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-151">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="7b30d-152">メールフロールールは、電子メールメッセージを暗号化する条件、およびその暗号化を削除するための条件を決定します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-152">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="7b30d-153">ルールのアクションを設定すると、ルールの条件に一致するメッセージはすべて、送信時に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="7b30d-153">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="7b30d-154">OME のメールフロールールを作成する手順については、「 [Office 365 で電子メールメッセージを暗号化するためのメールフロールールを定義する](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b30d-154">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="7b30d-155">既存のルールを更新して、新しい OME 機能を使用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7b30d-155">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="7b30d-156">Office 365 管理センターで、[**管理センター > Exchange**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-156">In the Office 365 admin center, go to **Admin centers > Exchange**.</span></span>
2. <span data-ttu-id="7b30d-157">Exchange 管理センターで、[**メールフロー > ルール**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-157">In the Exchange admin center, go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="7b30d-158">ルールごとに、**次の操作を行い**ます。</span><span class="sxs-lookup"><span data-stu-id="7b30d-158">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="7b30d-159">[**メッセージのセキュリティを変更する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-159">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="7b30d-160">[ **Office 365 メッセージの暗号化と権限保護を適用**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-160">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="7b30d-161">一覧から RMS テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-161">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="7b30d-162">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b30d-162">Select **Save**.</span></span>
    - <span data-ttu-id="7b30d-163">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b30d-163">Select **OK**.</span></span>
