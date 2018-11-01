---
title: Office 365 で電子メール メッセージを暗号化するためにメール フローの規則を定義します。
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
description: Office 365 グローバル管理者は、メールに Office 365 メッセージの暗号化 (ホーム) を有効にするのには、フロー ルールを作成できます。送信電子メール メッセージを暗号化し、内部のメッセージから、または組織から送信される、暗号化されたメッセージへの返信を暗号化を解除できます。
ms.openlocfilehash: bd94d36543653d5767fe27aee0f859fe9e374b2f
ms.sourcegitcommit: c0f5c92664b3fbed7b3c2f8232bb4046fc19d1b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "25890035"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a><span data-ttu-id="7b3ae-104">Office 365 で電子メール メッセージを暗号化するためにメール フローの規則を定義します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-104">Define mail flow rules to encrypt email messages in Office 365</span></span>

<span data-ttu-id="7b3ae-p102">Office 365 グローバル管理者は、メール フロー ルール、送受信する電子メールのメッセージを保護するために、トランスポート ルールとも呼ばれますを作成します。送信電子メール メッセージを暗号化および暗号化されたメッセージを組織内から、または組織から送信される、暗号化されたメッセージへの返信から暗号化を削除するルールを設定することができます。これらのルールを作成するのには、Exchange 管理センター (EAC) または Exchange のオンラインの Windows PowerShell コマンドレットを使用できます。 だけでなく全体の暗号化の規則を有効にするか、エンド ・ ユーザーの個々 のメッセージの暗号化オプションを無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p102">As an Office 365 global administrator, you can create mail flow rules, also known as transport rules, to help protect email messages you send and receive. You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization. You can use the Exchange admin center (EAC) or Windows PowerShell cmdlets for Exchange Online to create these rules.  In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end-users.</span></span>
  
<span data-ttu-id="7b3ae-p103">最近に移行する AD RMS から Azure 情報の保護、新しい環境で作業を続けられるようにするのには、既存のメール フロー ルールを確認する必要があります。さらに、新しい Office 365 メッセージの暗号化 (ホーム) 機能を使用するを通じて利用 Azure 情報保護する場合は、既存のメール フロー ルールを更新する必要があります。それ以外の場合、ユーザーは引き続き、シームレスな新しいホームの経験ではなく HTML 添付ファイルの以前の形式を使用する暗号化されたメールを受信します。ホームをまだ設定していない場合は、情報の[情報の保護を Azure 上に構築された、新しい Office 365 のメッセージの暗号化機能を設定](set-up-new-message-encryption-capabilities.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p103">If you recently migrated from AD RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment. Additionally, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules. Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience. If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md) for information.</span></span> 
  
<span data-ttu-id="7b3ae-p104">メール フロー ルール、およびメール フローによる作業時間の規則を構成するコンポーネントについては、 [Exchange Online でメールの流れのルール (トランスポート ルール)](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx)を参照してください。Azure の情報保護とメール フロー ルールの動作に関する詳細については、 [Azure の情報保護のラベルのメール フロー ルールを構成する Exchange のオンライン](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p104">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://technet.microsoft.com/library/jj919238%28v=exchg.150%29.aspx). For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>
  
## <a name="hybrid-exchange-environments-do-this-first"></a><span data-ttu-id="7b3ae-115">ハイブリッド Exchange 環境: この最初の操作を行います</span><span class="sxs-lookup"><span data-stu-id="7b3ae-115">Hybrid Exchange environments: Do this first</span></span>
<span data-ttu-id="7b3ae-p105">オンプレミス Exchange Online でメールをルーティングする場合は、ホームを使用して、暗号化されたメールを送信できます。これを行うには、メール、電子メール サーバーから Office 365 へのフローを構成する必要があります。1 回に設定されている、Office 365 を通過するメールし、この資料を使用してホームのメール フロー ルールを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p105">On-premises users can send encrypted mail using OME if you route email through Exchange Online. In order to do this, you need to configure mail to flow from your email server to Office 365. Once you've configured mail to flow through Office 365, then you can make mail flow rules for OME by using this article.</span></span>

<span data-ttu-id="7b3ae-p106">手順については、 [Office 365 と、独自のメール ・ サーバ間でメールをルーティングするコネクタのセットアップ](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)を参照してください。具体的には、手順に"第 2 部: メールをメール サーバーから Office 365 へのフローを構成する」です。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p106">For instructions, see [Set up connectors to route mail between Office 365 and your own email servers](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail). In particular, complete the steps in "Part 2: Configure mail to flow from your email server to Office 365".</span></span>

## <a name="create-a-mail-flow-rule-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="7b3ae-121">新しいホーム機能を持つ電子メール メッセージを暗号化するためにメール フロー ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-121">Create a mail flow rule to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="7b3ae-122">EAC を使用して新しいホーム機能でメッセージの暗号化をトリガーするためのメール フロー ルールを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-122">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>
  
### <a name="to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="7b3ae-123">EAC を使用して新しいホーム機能を持つ電子メール メッセージを暗号化するための規則を作成するには</span><span class="sxs-lookup"><span data-stu-id="7b3ae-123">To create a rule for encrypting email messages with the new OME capabilities by using the EAC</span></span>

1. <span data-ttu-id="7b3ae-124">Web ブラウザーで[Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)、グローバル管理者のアクセス許可が与えられている、職場、学校のアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-124">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="7b3ae-125">**管理者**のタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-125">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="7b3ae-126">Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-126">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="7b3ae-p107">EAC で**メールの流れ**に移動\>**ルール** \> ![新しいアイコン](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)(**新規**) \> **新しい規則を作成**します。詳細については、EAC を使用して、 [Exchange のオンラインでの Exchange 管理センター](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p107">In the EAC, go to **mail flow** \> **rules** \> ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) ( **New**) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx).</span></span>
    
5. <span data-ttu-id="7b3ae-129">[**名前**] には、DrToniRamos@hotmail.com の暗号化メールのルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-129">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>
    
6. <span data-ttu-id="7b3ae-p108">**[次の場合、このルールを適用する]** で条件を選択し、必要に応じて値を入力します。たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p108">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span> 
    
    1. <span data-ttu-id="7b3ae-132">**[次の場合、このルールを適用する]** で、**[受信者]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-132">In **Apply this rule if**, select **the recipient is**.</span></span>
    
    2. <span data-ttu-id="7b3ae-133">連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-133">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span> 
    
        <span data-ttu-id="7b3ae-134">既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-134">To select an existing name, select it from the list and then click **OK**.</span></span>
    
        <span data-ttu-id="7b3ae-135">新しい名前を入力、[**名前**] ボックスで電子メール アドレスを入力し、 **[名前の確認**を\> **OK**です。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-135">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>
    
7. <span data-ttu-id="7b3ae-136">さらに条件を追加するのには**他のオプション**を選択**条件の追加**] を選択し、一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-136">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span> 
    
    <span data-ttu-id="7b3ae-137">たとえば、組織外の受信者がいる場合にのみルールを適用するに**条件を追加**] を選択し、[**受信者が外部および内部** \> **組織外** \> **OK**です。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-137">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>
    
8. <span data-ttu-id="7b3ae-p109">ホームの新機能で、**次の操作**をからを使用して暗号化を有効にするには、**メッセージ セキュリティの変更**] を選択し、 **Office 365 メッセージ暗号化を適用し権利保護**します。RMS テンプレートを一覧から選択、**保存**を選択し、[ **ok]** します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p109">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
    
    <span data-ttu-id="7b3ae-p110">テンプレートの一覧には、すべての既定のテンプレートが含まれていて、オプションと同様に作成したカスタム テンプレートを Office 365 で使用します。リストが空の場合は、設定することが Office 365 のメッセージの暗号化を新しい機能を備えた[Azure の情報保護の上位に構築され、新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)の説明に従ってを確認します。既定のテンプレートの詳細については、[構成して Azure の情報保護のためのテンプレートを管理する](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)を参照してください。[**転送不可**] オプションの詳細については、[電子メールの転送不可] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を参照してください。**のみ暗号化**オプションの詳細については、[電子メールの暗号化のみ] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p110">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>
    
    <span data-ttu-id="7b3ae-145">別のアクションを指定する場合は、**アクションを追加する**選択できます。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-145">You can choose **add action** if you want to specify another action.</span></span> 
    
### <a name="to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="7b3ae-146">EAC を使用してホームの新機能を使用する既存のメール フロー ルールを更新するには</span><span class="sxs-lookup"><span data-stu-id="7b3ae-146">To update an existing mail flow rule to use the new OME capabilities by using the EAC</span></span>

1. <span data-ttu-id="7b3ae-147">Web ブラウザーで[Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)、グローバル管理者のアクセス許可が与えられている、職場、学校のアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-147">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="7b3ae-148">**管理者**のタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-148">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="7b3ae-149">Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-149">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="7b3ae-150">**メール フロー**には、EAC で\>**の規則**。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-150">In the EAC, go to **mail flow** \> **rules**.</span></span>
    
5. <span data-ttu-id="7b3ae-151">メール フロー ルールの一覧で、新しいホーム機能を使用し、選択を変更するルールを選択します![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)(**編集**) します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-151">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ( **Edit**).</span></span>
    
6. <span data-ttu-id="7b3ae-p111">ホームの新機能で、**次の操作**をからを使用して暗号化を有効にするには、**メッセージのセキュリティの変更**を選択し、**適用 Office 365 のメッセージの暗号化および権利の保護**します。RMS テンプレートを一覧から選択、**保存**を選択し、[ **ok]** します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p111">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>
    
    <span data-ttu-id="7b3ae-p112">テンプレートの一覧には、すべての既定のテンプレートが含まれていて、オプションと同様に作成したカスタム テンプレートを Office 365 で使用します。リストが空の場合は、設定することが Office 365 のメッセージの暗号化を新しい機能を備えた[Azure の情報保護の上位に構築され、新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)の説明に従ってを確認します。既定のテンプレートの詳細については、[構成して Azure の情報保護のためのテンプレートを管理する](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)を参照してください。[**転送不可**] オプションの詳細については、[電子メールの転送不可] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を参照してください。**のみ暗号化**オプションの詳細については、[電子メールの暗号化のみ] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p112">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>
    
    <span data-ttu-id="7b3ae-159">別のアクションを指定する場合は、**アクションを追加する**選択できます。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-159">You can choose **add action** if you want to specify another action.</span></span> 
    
7. <span data-ttu-id="7b3ae-160">**次の操作**] ボックスの一覧から、**メッセージ セキュリティの変更**] に割り当てられているすべてのアクションを削除します\>**ホームの以前のバージョンを適用**します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-160">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>
    
8. <span data-ttu-id="7b3ae-161">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-161">Choose **Save**.</span></span>
    
## <a name="creating-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="7b3ae-162">Office 365 のメッセージの暗号化のルールを作成する新しい機能がないです。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-162">Creating rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="7b3ae-p113">新しいホーム機能を提供する、Office 365 の組織にまだ移動していない場合、は、組織のメッセージを暗号化するためにメール フローの規則を定義するのにはこれらのタスクを使用します。ホームの新機能、組織の適切なことがすぐに移動するための計画を作成することをお勧めします。手順については、[情報の保護を Azure 上に構築された、新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p113">If you haven't yet moved your Office 365 organization to the new OME capabilities, use these tasks to define mail flow rules to encrypt messages for your organization. Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span>
  
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="7b3ae-166">EAC を使用して新しいホーム機能のない電子メール メッセージを暗号化するための規則を作成するには</span><span class="sxs-lookup"><span data-stu-id="7b3ae-166">To create a rule for encrypting email messages without the new OME capabilities by using the EAC</span></span>

1. <span data-ttu-id="7b3ae-167">Web ブラウザーで[Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)、グローバル管理者のアクセス許可が与えられている、職場、学校のアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-167">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="7b3ae-168">**管理者**のタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-168">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="7b3ae-169">Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-169">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="7b3ae-p114">EAC で**メールの流れ**に移動\>**ルール** \> **+** (**新規**) \> **新しい規則を作成**します。詳細については、EAC を使用して、 [Exchange のオンラインでの Exchange 管理センター](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p114">In the EAC, go to **mail flow** \> **rules** \> **+** ( **New**) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/library/jj200743%28v=exchg.150%29.aspx).</span></span>
    
5. <span data-ttu-id="7b3ae-172">[**名前**] には、DrToniRamos@hotmail.com の暗号化メールのルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-172">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>
    
6. <span data-ttu-id="7b3ae-p115">**[次の場合、このルールを適用する]** で条件を選択し、必要に応じて値を入力します。たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p115">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span> 
    
1. <span data-ttu-id="7b3ae-175">**[次の場合、このルールを適用する]** で、**[受信者]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-175">In **Apply this rule if**, select **the recipient is**.</span></span>
    
2. <span data-ttu-id="7b3ae-176">連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-176">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span> 
    
    <span data-ttu-id="7b3ae-177">既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-177">To select an existing name, select it from the list and then click **OK**.</span></span>
    
    <span data-ttu-id="7b3ae-178">新しい名前を入力、[**名前**] ボックスで電子メール アドレスを入力し、 **[名前の確認**を\> **OK**です。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-178">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>
    
7. <span data-ttu-id="7b3ae-179">さらに条件を追加するに**他のオプション**を選択し、[**条件の追加**] を選択し、リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-179">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span> 
    
    <span data-ttu-id="7b3ae-180">たとえば、組織外の受信者がいる場合にのみルールを適用するに**条件を追加**] を選択し、[**受信者が外部および内部** \> **組織外** \> **OK**です。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-180">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>
    
8. <span data-ttu-id="7b3ae-181">なし機能を使用して、新しいホーム、**次の操作**で暗号化を有効にするのには **、メッセージ セキュリティの変更**] を選択\>**ホームの以前のバージョンを適用**し、**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-181">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>
    
    <span data-ttu-id="7b3ae-p116">エラーが発生する場合は、使用許諾契約が IRM 機能が有効になってし、まだ組織のホームを設定していません。ホームをここで設定したい場合は、新しいホーム機能を使用するを設定する必要があります。については、[情報の保護を Azure 上に構築された、新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)を参照してください。Microsoft は、新しい機能がないホームの新規の展開の設定をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p116">If you receive an error that IRM licensing isn't enabled, then you haven't set up OME for your organization yet. If you'd like to set up OME now, you must set it up to use the new OME capabilities. For information, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). Microsoft no longer supports setting up new deployments of OME without the new capabilities.</span></span>
    
    <span data-ttu-id="7b3ae-186">別のアクションを指定する場合は、**アクションを追加する**選択できます。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-186">You can choose **add action** if you want to specify another action.</span></span> 
    
### <a name="to-create-a-rule-for-encrypting-email-messages-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a><span data-ttu-id="7b3ae-187">Exchange オンラインの Windows PowerShell を使用して新しいホーム機能のない電子メール メッセージを暗号化するための規則を作成するには</span><span class="sxs-lookup"><span data-stu-id="7b3ae-187">To create a rule for encrypting email messages without the new OME capabilities by using Windows PowerShell for Exchange Online</span></span>

1. <span data-ttu-id="7b3ae-p117">オンラインの Exchange へのリモート PowerShell セッションを作成するのには、ローカル コンピューター上の Windows PowerShell を使用します。詳細については、 [Exchange オンライン PowerShell への接続](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p117">Use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online. For more information, see [Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).</span></span>
    
2. <span data-ttu-id="7b3ae-190">**新規 TransportRule**コマンドレットを使用してルールを定義し、 **ApplyOME**属性を**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-190">Define a rule by using the **New-TransportRule** cmdlet and set the **ApplyOME** attribute to **true**.</span></span>
    
    <span data-ttu-id="7b3ae-191">たとえば、DrToniRamos@hotmail.com にアドレス指定されたすべての電子メール メッセージを暗号化する必要があることを必要とする次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-191">For example, to require that all email messages that are addressed to DrToniRamos@hotmail.com must be encrypted, type:</span></span>
    
     ```
     New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
     ```

    <span data-ttu-id="7b3ae-192">この例では次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-192">In this example:</span></span>
    
  - <span data-ttu-id="7b3ae-193">新しいルールの名前は、「Dr Toni タモの暗号化ルール」です。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-193">The name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>
    
  - <span data-ttu-id="7b3ae-p118">**-送信**パラメーターでは、電子メール メッセージ内の受信者を検索する条件を指定します。など、電子メール アドレス、名、識別名 (DN)、受信者を一意に識別する任意の値を使用することができます。この例では、受信者が電子メール アドレス"DrToniRamos@hotmail.com"によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p118">The **-SentTo** parameter, specifies a condition that looks for recipients in email messages. You can use any value that uniquely identifies the recipient, such as an email address, name, distinguished name (DN), etc. In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span> 
    
  - <span data-ttu-id="7b3ae-p119">**-SentToScope**パラメーターは、受信者の場所を検索する条件を指定します。この例では、受信者のメールボックスは hotmail し、"NotInOrganization"の値が使用されるので、Office 365 の組織の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p119">The **-SentToScope** parameter specifies a condition that looks for the location of recipients. In this example, the recipient's mailbox is in hotmail and is not part of the Office 365 organization, so the "NotInOrganization" value is used.</span></span> 
    
    <span data-ttu-id="7b3ae-198">このコマンドレットを使用してメール フローの規則を設定することができます、条件の詳細については、[新規 TransportRule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-198">For more information about the conditions you can set on mail flow rules using this cmdlet, see [New-TransportRule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx).</span></span>
    
### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="7b3ae-199">新しいホーム機能なしで暗号化電子メールの返信の暗号化を解除します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-199">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="7b3ae-p120">電子メール ユーザーは、暗号化されたメッセージを送信、ときにそれらのメッセージの受信者が暗号化された応答で応答できます。メールの返信を組織のメール ユーザーを表示するための暗号化のポータルにサインインする必要はありませんので暗号化を自動的に削除するフロー ルールを作成できます。EAC または Windows PowerShell コマンドレットを使用すると、これらの規則を定義します。ホームの新機能を使用されていない場合は、あなたの組織または組織内から送信されたメッセージへの返信のメッセージから送信されたいずれかのメッセージのみ解読できます。組織の外部から発信されたメッセージを暗号化の暗号化を解除することはできません。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p120">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies. You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them. You can use the EAC or Windows PowerShell cmdlets to define these rules. If you are not yet using the new OME capabilities, you can only decrypt messages that are either sent from within your organization or messages that are replies to messages sent from within your organization. You cannot decrypt encrypted messages originating from outside of your organization.</span></span>
  
#### <a name="to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-the-eac"></a><span data-ttu-id="7b3ae-205">EAC を使用して新しいホーム機能なしで暗号化電子メールの返信を暗号化を削除するルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="7b3ae-205">To create a rule for removing encryption from email replies encrypted without the new OME capabilities by using the EAC</span></span>
<span data-ttu-id="7b3ae-206"><a name="DecryptruleEACNoNewOME"> </a></span><span class="sxs-lookup"><span data-stu-id="7b3ae-206"></span></span>

1. <span data-ttu-id="7b3ae-207">Web ブラウザーで[Office 365 にサインイン](https://support.office.com/article/Sign-in-to-Office-or-Office-365-b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)の管理者権限が与えられている、職場、学校のアカウントを使用してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-207">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/Sign-in-to-Office-or-Office-365-b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>
    
2. <span data-ttu-id="7b3ae-208">**管理者**のタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-208">Choose the **Admin** tile.</span></span> 
    
3. <span data-ttu-id="7b3ae-209">Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-209">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>
    
4. <span data-ttu-id="7b3ae-p121">EAC で**メールの流れ**に移動\>**ルール** \> **+** (**新規**) \> **新しい規則を作成**します。詳細については、EAC を使用して、 [Exchange のオンラインでの Exchange 管理センター](https://technet.microsoft.com/en-us/library/jj200743%28v=exchg.150%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p121">In the EAC, go to **mail flow** \> **rules** \> **+** ( **New**) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://technet.microsoft.com/en-us/library/jj200743%28v=exchg.150%29.aspx).</span></span>
    
5. <span data-ttu-id="7b3ae-212">[**名前**] には、受信メールから削除暗号化など、ルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-212">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>
    
6. <span data-ttu-id="7b3ae-213">**場合は、このルールを適用する**には、**受信者は**、メッセージから暗号化を削除する必要がある条件を選択して\> **、組織の内部**。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-213">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>
    
7. <span data-ttu-id="7b3ae-214">**次の操作**をには、**メッセージ セキュリティの変更**] を選択\>**ホームの以前のバージョンを削除**します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-214">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>
    
8. <span data-ttu-id="7b3ae-215">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-215">Select **Save**.</span></span>
    
#### <a name="to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities-by-using-windows-powershell-for-exchange-online"></a><span data-ttu-id="7b3ae-216">Exchange オンラインの Windows PowerShell を使用して新しいホーム機能なしで暗号化電子メールの返信を暗号化を解除する規則を作成するには</span><span class="sxs-lookup"><span data-stu-id="7b3ae-216">To create a rule to remove encryption from email replies encrypted without the new OME capabilities by using Windows PowerShell for Exchange Online</span></span>
<span data-ttu-id="7b3ae-217"><a name="DecryptrulePShellNoNewOME"> </a></span><span class="sxs-lookup"><span data-stu-id="7b3ae-217"></span></span>

1. <span data-ttu-id="7b3ae-p122">オンラインの Exchange へのリモート PowerShell セッションを作成するのには、ローカル コンピューター上の Windows PowerShell を使用します。詳細については、 [Exchange オンライン PowerShell への接続](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p122">Use Windows PowerShell on your local computer to create a remote PowerShell session to Exchange Online. For more information, see [Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx).</span></span>
    
2. <span data-ttu-id="7b3ae-220">**新規 TransportRule**コマンドレットを使用してルールを定義し、 **RemoveOME**属性を**true**に設定します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-220">Define a rule by using the **New-TransportRule** cmdlet and set the **RemoveOME** attribute to **true**.</span></span>
    
    <span data-ttu-id="7b3ae-221">たとえば、Office 365 の組織内の受信者に送信されるすべてのメールから暗号化を削除するのには次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-221">For example, to remove the encryption from all mail sent to recipients in your Office 365 organization, type:</span></span>
    
     ```
     New-TransportRule - Name "Remove encryption from incoming mail"     -SentToScope "InOrganization" -RemoveOME $true
     ```

    <span data-ttu-id="7b3ae-222">この例では次のようになっています。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-222">In this example:</span></span>
    
  - <span data-ttu-id="7b3ae-223">新しいルールの名前は、「受信メールから暗号化を削除する」です。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-223">The name of the new rule is "Remove encryption from incoming mail".</span></span>
    
  - <span data-ttu-id="7b3ae-p123">**-SentToScope**パラメーターは、受信者の場所を検索する条件を指定します。この例では、あることを示す"InOrganization"の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-p123">The **-SentToScope** parameter specifies a condition that looks for the location of recipients. In this example, the "InOrganization" value is used which indicates that:</span></span> 
    
  - <span data-ttu-id="7b3ae-226">受信者のメールボックス、メール ユーザー、グループ、または組織内のパブリック フォルダーのメールが有効なのですか</span><span class="sxs-lookup"><span data-stu-id="7b3ae-226">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization, or</span></span>
    
  - <span data-ttu-id="7b3ae-227">受信者のメール アドレスが、権限のあるドメインまたは内部の中継ドメインとして構成されている承認済みドメインに属していて、かつ メッセージが認証済み接続経由で送信または受信された。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-227">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain, and the message was sent or received over an authenticated connection.</span></span>
    
    <span data-ttu-id="7b3ae-228">このコマンドレットを使用してメール フローの規則を設定することができます、条件の詳細については、[新規 TransportRule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3ae-228">For more information about the conditions you can set on mail flow rules using this cmdlet, see [New-TransportRule](https://technet.microsoft.com/en-us/library/bb125138%28v=exchg.160%29.aspx).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="7b3ae-229">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b3ae-229">Related Topics</span></span>

[<span data-ttu-id="7b3ae-230">Office 365 での暗号化</span><span class="sxs-lookup"><span data-stu-id="7b3ae-230">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="7b3ae-231">情報の保護を Azure 上に構築された、新しい Office 365 のメッセージの暗号化機能を設定します</span><span class="sxs-lookup"><span data-stu-id="7b3ae-231">Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection</span></span>](set-up-new-message-encryption-capabilities.md)
  
[<span data-ttu-id="7b3ae-232">暗号化メッセージへのブランドの追加</span><span class="sxs-lookup"><span data-stu-id="7b3ae-232">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)
  
[<span data-ttu-id="7b3ae-233">Exchange Online のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="7b3ae-233">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)
  
[<span data-ttu-id="7b3ae-234">Exchange Online Protection のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="7b3ae-234">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)
  

