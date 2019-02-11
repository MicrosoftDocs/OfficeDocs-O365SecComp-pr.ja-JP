---
title: Office 365 でメールを暗号化するためにメール フロー ルールを定義する
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
description: 管理者は、メールを暗号化し、Office 365 メッセージの暗号化 (ホーム) を使用してメッセージを復号化のフロー ルール (トランスポート ルールでとも呼ばれます) を作成するに学習できます。
ms.openlocfilehash: db421c808f1eed69ddbece2b333f9edd61712235
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696281"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a><span data-ttu-id="562e8-103">Office 365 でメールを暗号化するためにメール フロー ルールを定義する</span><span class="sxs-lookup"><span data-stu-id="562e8-103">Define mail flow rules to encrypt email messages in Office 365</span></span>

<span data-ttu-id="562e8-p101">Office 365 グローバル管理者は、ルールを作成できますメール フロー (トランスポートの規則とも呼ばれます) は、電子メール メッセージの送受信を保護するためです。送信電子メール メッセージを暗号化および暗号化されたメッセージを組織内から、または組織から送信される、暗号化されたメッセージへの返信から暗号化を削除するルールを設定することができます。これらのルールを作成するのには、Exchange 管理センター (EAC) または Exchange のオンライン PowerShell を使用できます。だけでなく全体の暗号化の規則を有効にするか、エンド ・ ユーザーの個々 のメッセージの暗号化オプションを無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="562e8-p101">As an Office 365 global administrator, you can create mail flow rules (also known as transport rules) to help protect email messages you send and receive. You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization. You can use the Exchange admin center (EAC) or Exchange Online PowerShell to create these rules. In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end-users.</span></span>

||
|:-----|
|<span data-ttu-id="562e8-p102">この資料は、Office 365 のメッセージの暗号化についての記事の大規模な一連の一部です。この資料は、管理者および ITPros。だけを行う場合、暗号化されたメッセージを送受信する情報は[Office 365 メッセージの暗号化 (ホーム)](ome.md)内のアーティクルの一覧を参照してくださいし、お客様のニーズに最も適した記事を検索します。</span><span class="sxs-lookup"><span data-stu-id="562e8-p102">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

<span data-ttu-id="562e8-p103">最近に移行する AD RMS から Azure 情報の保護、新しい環境で作業を続けられるようにするのには、既存のメール フロー ルールを確認する必要があります。さらに、新しい Office 365 メッセージの暗号化 (ホーム) 機能を使用するを通じて利用 Azure 情報保護する場合は、既存のメール フロー ルールを更新する必要があります。それ以外の場合、ユーザーは引き続き、シームレスな新しいホームの経験ではなく HTML 添付ファイルの以前の形式を使用する暗号化されたメールを受信します。ホームをまだ設定していない場合は、情報の[新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562e8-p103">If you recently migrated from AD RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment. Additionally, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules. Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience. If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md) for information.</span></span>

<span data-ttu-id="562e8-p104">メール フロー ルール、およびメール フローによる作業時間の規則を構成するコンポーネントについては、 [Exchange Online でメールの流れのルール (トランスポート ルール)](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)を参照してください。Azure の情報保護とメール フロー ルールの動作に関する詳細については、 [Azure の情報保護のラベルのメール フロー ルールを構成する Exchange のオンライン](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562e8-p104">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules). For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="562e8-p105">ハイブリッド Exchange 環境では、オンプレミス ユーザーは、Exchange Online でメールをルーティングする場合にのみホームを使用して、暗号化されたメールを送信できます。ハイブリッドな Exchange 環境では、ホームを構成するには、最初の[ハイブリッド構成ウィザードを使用してハイブリッドを構成](https://docs.microsoft.com/Exchange/exchange-hybrid)し、 [Office 365 に電子メール サーバーからメールを設定](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)する必要があります。1 回このガイダンスを使用してホームのメール フロー ルールを構成することができますし、Office 365 を通過するメールを構成しました。</span><span class="sxs-lookup"><span data-stu-id="562e8-p105">For hybrid Exchange environments, on-premises users can send encrypted mail using OME only if email is routed through Exchange Online. To configure OME in a hybrid Exchange environment, you need to first [configure hybrid using the Hybrid Configuration wizard](https://docs.microsoft.com/Exchange/exchange-hybrid) and then [configure mail to flow from your email server to Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365). Once you've configured mail to flow through Office 365, then you can configure mail flow rules for OME by using this guidance.</span></span>

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="562e8-120">メール ホームの新機能を持つ電子メール メッセージを暗号化するためにフロー ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="562e8-120">Create mail flow rules to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="562e8-121">EAC を使用して新しいホーム機能でメッセージの暗号化をトリガーするためのメール フロー ルールを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="562e8-121">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="562e8-122">EAC を使用して、新しいホーム機能を持つ電子メール メッセージを暗号化するための規則を作成するには</span><span class="sxs-lookup"><span data-stu-id="562e8-122">Use the EAC to create a rule for encrypting email messages with the new OME capabilities</span></span>

1. <span data-ttu-id="562e8-123">Web ブラウザーで[Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)、グローバル管理者のアクセス許可が与えられている、職場、学校のアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="562e8-123">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="562e8-124">**管理者**のタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="562e8-124">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="562e8-125">Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="562e8-125">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="562e8-p106">**メール フロー**には、EAC で\>**の規則**と**新規**作成]![新しいアイコン](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しい規則を作成します**。詳細については、EAC を使用して、 [Exchange のオンラインでの Exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562e8-p106">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**. For more information about using the EAC, see [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="562e8-128">[**名前**] には、DrToniRamos@hotmail.com の暗号化メールのルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="562e8-128">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="562e8-p107">**[次の場合、このルールを適用する]** で条件を選択し、必要に応じて値を入力します。たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="562e8-p107">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="562e8-131">**[次の場合、このルールを適用する]** で、**[受信者]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="562e8-131">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="562e8-132">連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="562e8-132">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="562e8-133">既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="562e8-133">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="562e8-134">新しい名前を入力、[**名前**] ボックスで電子メール アドレスを入力し、 **[名前の確認**を\> **OK**です。</span><span class="sxs-lookup"><span data-stu-id="562e8-134">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="562e8-135">さらに条件を追加するのには**他のオプション**を選択**条件の追加**] を選択し、一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="562e8-135">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span>

   <span data-ttu-id="562e8-136">たとえば、組織外の受信者がいる場合にのみルールを適用するに**条件を追加**] を選択し、[**受信者が外部および内部** \> **組織外** \> **OK**です。</span><span class="sxs-lookup"><span data-stu-id="562e8-136">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="562e8-p108">ホームの新機能で、**次の操作**をからを使用して暗号化を有効にするには、**メッセージ セキュリティの変更**] を選択し、 **Office 365 メッセージ暗号化を適用し権利保護**します。RMS テンプレートを一覧から選択、**保存**を選択し、[ **ok]** します。</span><span class="sxs-lookup"><span data-stu-id="562e8-p108">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
  <span data-ttu-id="562e8-p109">テンプレートの一覧には、すべての既定のテンプレートが含まれていて、オプションと同様に作成したカスタム テンプレートを Office 365 で使用します。リストが空の場合は、設定することが Office 365 のメッセージの暗号化を新しい機能を備えた[新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)の説明に従ってを確認します。既定のテンプレートの詳細については、[構成して Azure の情報保護のためのテンプレートを管理する](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)を参照してください。[**転送不可**] オプションの詳細については、[電子メールの転送不可] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を参照してください。**のみ暗号化**オプションの詳細については、[電子メールの暗号化のみ] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562e8-p109">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

  <span data-ttu-id="562e8-144">別のアクションを指定する場合は、**アクションを追加する**選択できます。</span><span class="sxs-lookup"><span data-stu-id="562e8-144">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a><span data-ttu-id="562e8-145">EAC を使用して、新しいホーム機能を使用する既存のメール フロー ルールを更新するには</span><span class="sxs-lookup"><span data-stu-id="562e8-145">Use the EAC to update an existing mail flow rule to use the new OME capabilities</span></span>

1. <span data-ttu-id="562e8-146">Web ブラウザーで[Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)、グローバル管理者のアクセス許可が与えられている、職場、学校のアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="562e8-146">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="562e8-147">**管理者**のタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="562e8-147">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="562e8-148">Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="562e8-148">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="562e8-149">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="562e8-149">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

5. <span data-ttu-id="562e8-150">メール フロー ルールの一覧で、ホームの新機能を使用して、**編集**を選択し、変更するルールを選択します![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="562e8-150">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>

6. <span data-ttu-id="562e8-p110">ホームの新機能で、**次の操作**をからを使用して暗号化を有効にするには、**メッセージのセキュリティの変更**を選択し、**適用 Office 365 のメッセージの暗号化および権利の保護**します。RMS テンプレートを一覧から選択、**保存**を選択し、[ **ok]** します。</span><span class="sxs-lookup"><span data-stu-id="562e8-p110">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>

   <span data-ttu-id="562e8-p111">テンプレートの一覧には、すべての既定のテンプレートが含まれていて、オプションと同様に作成したカスタム テンプレートを Office 365 で使用します。リストが空の場合は、設定することが Office 365 のメッセージの暗号化を新しい機能を備えた[Azure の情報保護の上位に構築され、新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)の説明に従ってを確認します。既定のテンプレートの詳細については、[構成して Azure の情報保護のためのテンプレートを管理する](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)を参照してください。[**転送不可**] オプションの詳細については、[電子メールの転送不可] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を参照してください。**のみ暗号化**オプションの詳細については、[電子メールの暗号化のみ] オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562e8-p111">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="562e8-158">別のアクションを指定する場合は、**アクションを追加する**選択できます。</span><span class="sxs-lookup"><span data-stu-id="562e8-158">You can choose **add action** if you want to specify another action.</span></span>

7. <span data-ttu-id="562e8-159">**次の操作**] ボックスの一覧から、**メッセージ セキュリティの変更**] に割り当てられているすべてのアクションを削除します\>**ホームの以前のバージョンを適用**します。</span><span class="sxs-lookup"><span data-stu-id="562e8-159">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>

8. <span data-ttu-id="562e8-160">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="562e8-160">Choose **Save**.</span></span>

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="562e8-161">新しい機能がない Office 365 のメッセージの暗号化メール フロー ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="562e8-161">Create mail flow rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="562e8-p112">新しいホーム機能を提供する、Office 365 の組織にまだ移動していない場合、は、組織のメッセージを暗号化するためにメール フローの規則を定義するのにはこれらのタスクを使用します。ホームの新機能、組織の適切なことがすぐに移動するための計画を作成することをお勧めします。手順については、[情報の保護を Azure 上に構築された、新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562e8-p112">If you haven't yet moved your Office 365 organization to the new OME capabilities, use these tasks to define mail flow rules to encrypt messages for your organization. Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span>

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="562e8-165">EAC を使用して、新しいホーム機能のない電子メール メッセージを暗号化するためのメール フロー ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="562e8-165">Use the EAC to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="562e8-166">Web ブラウザーで[Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)、グローバル管理者のアクセス許可が与えられている、職場、学校のアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="562e8-166">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="562e8-167">**管理者**のタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="562e8-167">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="562e8-168">Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="562e8-168">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="562e8-p113">**メール フロー**には、EAC で\>**の規則**と**新規**作成]![新しいアイコン](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しい規則を作成します**。詳細については、EAC を使用して、 [Exchange 管理センター オンラインの Exchange](https://docs.microsoft.com/exchange/exchange-admin-center)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562e8-p113">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**. For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="562e8-171">[**名前**] には、DrToniRamos@hotmail.com の暗号化メールのルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="562e8-171">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="562e8-p114">**[次の場合、このルールを適用する]** で条件を選択し、必要に応じて値を入力します。たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="562e8-p114">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="562e8-174">**[次の場合、このルールを適用する]** で、**[受信者]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="562e8-174">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="562e8-175">連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="562e8-175">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="562e8-176">既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="562e8-176">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="562e8-177">新しい名前を入力、[**名前**] ボックスで電子メール アドレスを入力し、 **[名前の確認**を\> **OK**です。</span><span class="sxs-lookup"><span data-stu-id="562e8-177">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="562e8-178">さらに条件を追加するに**他のオプション**を選択し、[**条件の追加**] を選択し、リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="562e8-178">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span>

   <span data-ttu-id="562e8-179">たとえば、組織外の受信者がいる場合にのみルールを適用するに**条件を追加**] を選択し、[**受信者が外部および内部** \> **組織外** \> **OK**です。</span><span class="sxs-lookup"><span data-stu-id="562e8-179">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="562e8-180">なし機能を使用して、新しいホーム、**次の操作**で暗号化を有効にするのには **、メッセージ セキュリティの変更**] を選択\>**ホームの以前のバージョンを適用**し、**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="562e8-180">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>

  <span data-ttu-id="562e8-p115">エラーが発生する場合は、使用許諾契約が IRM 機能が有効になってし、まだ組織のホームを設定していません。ホームをここで設定したい場合は、新しいホーム機能を使用するを設定する必要があります。については、[情報の保護を Azure 上に構築された、新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)を参照してください。Microsoft は、新しい機能がないホームの新規の展開の設定をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="562e8-p115">If you receive an error that IRM licensing isn't enabled, then you haven't set up OME for your organization yet. If you'd like to set up OME now, you must set it up to use the new OME capabilities. For information, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). Microsoft no longer supports setting up new deployments of OME without the new capabilities.</span></span>

  <span data-ttu-id="562e8-185">別のアクションを指定する場合は、**アクションを追加する**選択できます。</span><span class="sxs-lookup"><span data-stu-id="562e8-185">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="562e8-186">Exchange オンライン PowerShell を使用して、新しいホーム機能のない電子メール メッセージを暗号化するためのメール フロー ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="562e8-186">Use Exchange Online PowerShell to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="562e8-p116">オンライン PowerShell を交換するために接続します。詳細については、 [Exchange オンライン PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562e8-p116">Connect to Exchange Online PowerShell. For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="562e8-189">**新規 TransportRule**コマンドレットを使用してルールを作成し、 _ApplyOME_パラメーターを設定`$true`。</span><span class="sxs-lookup"><span data-stu-id="562e8-189">Create a rule by using the **New-TransportRule** cmdlet and set the _ApplyOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="562e8-190">この例では、DrToniRamos@hotmail.com に送信されるすべての電子メール メッセージを暗号化する必要がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="562e8-190">This example requires that all email messages sent to DrToniRamos@hotmail.com must be encrypted.</span></span>

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   <span data-ttu-id="562e8-191">**注**:</span><span class="sxs-lookup"><span data-stu-id="562e8-191">**Notes**:</span></span>

   - <span data-ttu-id="562e8-192">新しいルールの一意の名前は、「Dr Toni タモの暗号化ルール」です。</span><span class="sxs-lookup"><span data-stu-id="562e8-192">The unique name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>

   - <span data-ttu-id="562e8-p117">_SentTo_パラメーターは、(名前、電子メール アドレス、識別名などで識別される) メッセージの受信者を指定します。この例では、受信者が電子メール アドレス"DrToniRamos@hotmail.com"によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="562e8-p117">The _SentTo_ parameter specifies the message recipients (identified by name, email address, distinguished name, etc.). In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span>

   - <span data-ttu-id="562e8-p118">_SentToScope_パラメーターは、メッセージの受信者の場所を指定します。この例では、受信者のメールボックス hotmail では、Office 365 の組織の一部、値`NotInOrganization`を使用します。</span><span class="sxs-lookup"><span data-stu-id="562e8-p118">The _SentToScope_ parameter specifies the location of the message recipients. In this example, the recipient's mailbox is in hotmail and is not part of the Office 365 organization, so the value `NotInOrganization` is used.</span></span>

   <span data-ttu-id="562e8-197">詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562e8-197">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="562e8-198">新しいホーム機能なしで暗号化電子メールの返信の暗号化を解除します。</span><span class="sxs-lookup"><span data-stu-id="562e8-198">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="562e8-p119">電子メール ユーザーは、暗号化されたメッセージを送信、ときにそれらのメッセージの受信者が暗号化された応答で応答できます。メールの返信を組織のメール ユーザーを表示するための暗号化のポータルにサインインする必要はありませんので暗号化を自動的に削除するフロー ルールを作成できます。EAC または Windows PowerShell コマンドレットを使用すると、これらの規則を定義します。ホームの新機能を使用されていない場合は、あなたの組織または組織内から送信されたメッセージへの返信のメッセージから送信されたいずれかのメッセージのみ解読できます。組織の外部から発信されたメッセージを暗号化の暗号化を解除することはできません。</span><span class="sxs-lookup"><span data-stu-id="562e8-p119">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies. You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them. You can use the EAC or Windows PowerShell cmdlets to define these rules. If you are not yet using the new OME capabilities, you can only decrypt messages that are either sent from within your organization or messages that are replies to messages sent from within your organization. You cannot decrypt encrypted messages originating from outside of your organization.</span></span>

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="562e8-204">EAC を使用して、新しいホーム機能なしで暗号化電子メールの返信を暗号化を削除するルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="562e8-204">Use the EAC to create a rule for removing encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="562e8-205">Web ブラウザーで[Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)の管理者権限が与えられている、職場、学校のアカウントを使用してください。</span><span class="sxs-lookup"><span data-stu-id="562e8-205">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="562e8-206">**管理者**のタイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="562e8-206">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="562e8-207">Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="562e8-207">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="562e8-p120">**メール フロー**には、EAC で\>**の規則**と**新規**作成]![新しいアイコン](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しい規則を作成します**。詳細については、EAC を使用して、 [Exchange 管理センター オンラインの Exchange](https://docs.microsoft.com/exchange/exchange-admin-center)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562e8-p120">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**. For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="562e8-210">[**名前**] には、受信メールから削除暗号化など、ルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="562e8-210">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>

6. <span data-ttu-id="562e8-211">**場合は、このルールを適用する**には、**受信者は**、メッセージから暗号化を削除する必要がある条件を選択して\> **、組織の内部**。</span><span class="sxs-lookup"><span data-stu-id="562e8-211">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>

7. <span data-ttu-id="562e8-212">**次の操作**をには、**メッセージ セキュリティの変更**] を選択\>**ホームの以前のバージョンを削除**します。</span><span class="sxs-lookup"><span data-stu-id="562e8-212">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>

8. <span data-ttu-id="562e8-213">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="562e8-213">Select **Save**.</span></span>

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="562e8-214">Exchange オンライン PowerShell を使用して、新しいホーム機能なしで暗号化電子メールの返信を暗号化を解除する規則を作成するには</span><span class="sxs-lookup"><span data-stu-id="562e8-214">Use Exchange Online PowerShell to create a rule to remove encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="562e8-p121">オンライン PowerShell を交換するために接続します。詳細については、 [Exchange オンライン PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562e8-p121">Connect to Exchange Online PowerShell. For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="562e8-217">**新規 TransportRule**コマンドレットを使用してルールを作成し、 _RemoveOME_パラメーターを設定`$true`。</span><span class="sxs-lookup"><span data-stu-id="562e8-217">Create a rule by using the **New-TransportRule** cmdlet and set the _RemoveOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="562e8-218">この例では、Office 365 の組織内の受信者に送信されるすべてのメールから暗号化を削除します。</span><span class="sxs-lookup"><span data-stu-id="562e8-218">This example removes the encryption from all mail sent to recipients in the Office 365 organization.</span></span>

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   <span data-ttu-id="562e8-219">**注**:</span><span class="sxs-lookup"><span data-stu-id="562e8-219">**Notes**:</span></span>

   - <span data-ttu-id="562e8-220">新しいルールの一意の名前は、「受信メールから暗号化を削除する」です。</span><span class="sxs-lookup"><span data-stu-id="562e8-220">The unique name of the new rule is "Remove encryption from incoming mail".</span></span>

   - <span data-ttu-id="562e8-p122">_SentToScope_パラメーターは、メッセージの受信者の場所を指定します。この例では、値`InOrganization`値が使用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="562e8-p122">The _SentToScope_ parameter specifies the location of the message recipients. In this example, the value `InOrganization` value is used, which indicates:</span></span>

     - <span data-ttu-id="562e8-223">受信者は、メールボックス、メール ユーザー、グループ、または組織内のパブリック フォルダーのメールが有効です。</span><span class="sxs-lookup"><span data-stu-id="562e8-223">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization.</span></span>

       <span data-ttu-id="562e8-224">または</span><span class="sxs-lookup"><span data-stu-id="562e8-224">or</span></span>

     - <span data-ttu-id="562e8-225">受信者の電子メール アドレスが、権限のあるドメインまたは組織_および_メッセージが送信または、認証された接続経由で受信した、内部の中継ドメインとして構成されている承認済みドメインです。</span><span class="sxs-lookup"><span data-stu-id="562e8-225">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain in your organization, _and_ the message was sent or received over an authenticated connection.</span></span>

<span data-ttu-id="562e8-226">詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="562e8-226">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

## <a name="related-topics"></a><span data-ttu-id="562e8-227">関連項目</span><span class="sxs-lookup"><span data-stu-id="562e8-227">Related Topics</span></span>

[<span data-ttu-id="562e8-228">Office 365 での暗号化</span><span class="sxs-lookup"><span data-stu-id="562e8-228">Encryption in Office 365</span></span>](encryption.md)

[<span data-ttu-id="562e8-229">新しい Office 365 Message Encryption 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="562e8-229">Set up new Office 365 Message Encryption capabilities</span></span>](set-up-new-message-encryption-capabilities.md)

[<span data-ttu-id="562e8-230">暗号化メッセージへのブランドの追加</span><span class="sxs-lookup"><span data-stu-id="562e8-230">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)

[<span data-ttu-id="562e8-231">Exchange Online のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="562e8-231">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[<span data-ttu-id="562e8-232">Exchange Online Protection のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="562e8-232">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)
