---
title: Office 365 でメールを暗号化するためにメール フロー ルールを定義する
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: 管理者は、Office 365 メッセージの暗号化を使用してメッセージを暗号化および復号化するメールフロールール (トランスポートルール) を作成する方法について説明します。
ms.openlocfilehash: 1f5b0ff9be5994f036d2367d0b15744c24f2bbe0
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357558"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a><span data-ttu-id="e67e0-103">Office 365 でメールを暗号化するためにメール フロー ルールを定義する</span><span class="sxs-lookup"><span data-stu-id="e67e0-103">Define mail flow rules to encrypt email messages in Office 365</span></span>

<span data-ttu-id="e67e0-p101">Office 365 全体管理者は、メールフロールール (トランスポートルールとも呼ばれます) を作成して、送受信する電子メールメッセージを保護することができます。送信電子メールメッセージを暗号化したり、組織内から送信される暗号化されたメッセージから暗号化を削除したり、組織から送信された暗号化メッセージへの返信を削除したりするためのルールを設定できます。これらのルールを作成するには、exchange 管理センター (EAC) または exchange Online PowerShell を使用できます。暗号化ルール全体に加えて、エンドユーザーの個々のメッセージ暗号化オプションを有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p101">As an Office 365 global administrator, you can create mail flow rules (also known as transport rules) to help protect email messages you send and receive. You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization. You can use the Exchange admin center (EAC) or Exchange Online PowerShell to create these rules. In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end-users.</span></span>

||
|:-----|
|<span data-ttu-id="e67e0-p102">この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。この記事は、管理者および it 担当者を対象としています。暗号化されたメッセージの送信または受信に関する情報をお探しの場合は、「 [Office 365 message Encryption (OME)](ome.md) 」の記事の一覧を参照し、ニーズに最も適した記事を見つけてください。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p102">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

<span data-ttu-id="e67e0-p103">AD RMS から Azure Information Protection に最近移行した場合は、既存のメールフロールールを確認して、新しい環境で引き続き動作するようにする必要があります。さらに、Azure Information Protection を使用して利用できる新しい Office 365 Message Encryption (OME) 機能を利用する場合は、既存のメールフロールールを更新する必要があります。そうしないと、ユーザーは、新しいシームレスな OME の操作ではなく、前の HTML 添付ファイル形式を使用する暗号化メールを引き続き受信できます。まだ OME をセットアップしていない場合は、「 [Office の新しい365メッセージ暗号化機能を設定](set-up-new-message-encryption-capabilities.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p103">If you recently migrated from AD RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment. Additionally, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules. Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience. If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md) for information.</span></span>

<span data-ttu-id="e67e0-p104">メールフロールールを構成するコンポーネントと、メールフロールールのしくみについては、「 [Exchange Online のメールフロールール (トランスポートルール)](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)」を参照してください。メールフロールールが azure information protection でどのように機能するかの詳細については、「 [azure information protection のラベルの Exchange Online メールフロールールの構成](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p104">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules). For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e67e0-p105">ハイブリッド exchange 環境では、オンプレミスのユーザーは、電子メールが Exchange Online を経由してルーティングされる場合にのみ、OME を使用して暗号化されたメールを送信できます。ハイブリッド Exchange 環境で OME を構成するには、まず[ハイブリッド構成ウィザードを使用してハイブリッドを構成](https://docs.microsoft.com/Exchange/exchange-hybrid)し、次に、[電子メールサーバーから Office 365 にメールが流れるように構成](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)する必要があります。Office 365 を通過するようにメールを構成したら、このガイダンスを使用して OME のメールフロールールを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p105">For hybrid Exchange environments, on-premises users can send encrypted mail using OME only if email is routed through Exchange Online. To configure OME in a hybrid Exchange environment, you need to first [configure hybrid using the Hybrid Configuration wizard](https://docs.microsoft.com/Exchange/exchange-hybrid) and then [configure mail to flow from your email server to Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365). Once you've configured mail to flow through Office 365, then you can configure mail flow rules for OME by using this guidance.</span></span>

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="e67e0-120">メールフロールールを作成して、新しい OME 機能で電子メールメッセージを暗号化する</span><span class="sxs-lookup"><span data-stu-id="e67e0-120">Create mail flow rules to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="e67e0-121">EAC を使用して、新しい OME 機能でメッセージの暗号化をトリガーするためのメールフロールールを定義できます。</span><span class="sxs-lookup"><span data-stu-id="e67e0-121">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="e67e0-122">EAC を使用して、新しい OME 機能で電子メールメッセージを暗号化するためのルールを作成する</span><span class="sxs-lookup"><span data-stu-id="e67e0-122">Use the EAC to create a rule for encrypting email messages with the new OME capabilities</span></span>

1. <span data-ttu-id="e67e0-123">web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-123">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="e67e0-124">[**管理**] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-124">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="e67e0-125">Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="e67e0-125">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="e67e0-p106">EAC で、[**メールフロー** \> ] [**ルール**] に\*\*\*\* ![移動し、](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> [新しい新規作成] アイコンを選択して**新しいルールを作成**します。EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p106">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**. For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="e67e0-128">[**名前**] にルールの名前 (DrToniRamos@hotmail.com のメールの暗号化など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-128">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="e67e0-p107">**[次の場合、このルールを適用する]** で条件を選択し、必要に応じて値を入力します。たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p107">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="e67e0-131">**[次の場合、このルールを適用する]** で、**[受信者]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-131">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="e67e0-132">連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-132">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="e67e0-133">既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e67e0-133">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="e67e0-134">新しい名前を入力するには、[**名前の確認**] ボックスに電子メールアドレスを入力し、[**名前** \>の確認 **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-134">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="e67e0-135">他の条件を追加するには、[**その他のオプション**] を選択し、[**条件の追加**] を選択して、一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-135">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span>

   <span data-ttu-id="e67e0-136">たとえば、受信者が組織の外部にいる場合にのみルールを適用するには、[**条件の追加**] を選択し、[**受信者が外部/内部** \>の**組織** \>外にある **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-136">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="e67e0-p108">新しい OME 機能を使用して暗号化を有効にするには、**次の操作を行い**ます。次に、[**メッセージのセキュリティを変更**する] を選択し、[ **Office 365 メッセージの暗号化と権限保護を適用**する] を選択します。一覧から RMS テンプレートを選択し、[**保存**] を選択して、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p108">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
  <span data-ttu-id="e67e0-p109">テンプレートの一覧には、既定のテンプレートとオプションのすべてに加えて、Office 365 で使用するために作成したカスタムテンプレートがすべて含まれています。リストが空の場合は、「office の[新しいメッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」の説明に従って、office 365 メッセージの暗号化を新しい機能で設定していることを確認してください。既定のテンプレートの詳細については、「 [Azure information Protection 用のテンプレートを構成および管理](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)する」を参照してください。[**転送**しない] オプションの詳細については、「[メールの転送オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を送信しない」を参照してください。[**暗号化のみ**] オプションの詳細については、「[電子メールの暗号化のみオプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p109">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

  <span data-ttu-id="e67e0-144">別のアクションを指定する場合は、[**アクションの追加**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e67e0-144">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a><span data-ttu-id="e67e0-145">EAC を使用して既存のメールフロールールを更新し、新しい OME 機能を使用する</span><span class="sxs-lookup"><span data-stu-id="e67e0-145">Use the EAC to update an existing mail flow rule to use the new OME capabilities</span></span>

1. <span data-ttu-id="e67e0-146">web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-146">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="e67e0-147">[**管理**] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-147">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="e67e0-148">Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="e67e0-148">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="e67e0-149">EAC で、 **[メール フロー]** \> **[ルール]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-149">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

5. <span data-ttu-id="e67e0-150">メールフロールールの一覧で、新しい OME 機能を使用するように変更するルールを選択し、[編集\*\*\*\* ![] [編集](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-150">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>

6. <span data-ttu-id="e67e0-p110">新しい OME 機能を使用して暗号化を有効にするには、**次の操作を行い**ます。次に、[**メッセージのセキュリティを変更**する] を選択し、[ **Office 365 メッセージの暗号化と権限保護を適用**する] を選択します。一覧から RMS テンプレートを選択し、[**保存**] を選択して、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p110">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**. Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>

   <span data-ttu-id="e67e0-p111">テンプレートの一覧には、既定のテンプレートとオプションのすべてに加えて、Office 365 で使用するために作成したカスタムテンプレートがすべて含まれています。リストが空の場合は、「 [Azure Information Protection の上に構築された新しい office 365 メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」に記載されているように、新しい機能を使用して office 365 メッセージの暗号化を設定していることを確認してください。既定のテンプレートの詳細については、「 [Azure information Protection 用のテンプレートを構成および管理](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)する」を参照してください。[**転送**しない] オプションの詳細については、「[メールの転送オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)を送信しない」を参照してください。[**暗号化のみ**] オプションの詳細については、「[電子メールの暗号化のみオプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p111">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365. If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="e67e0-158">別のアクションを指定する場合は、[**アクションの追加**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e67e0-158">You can choose **add action** if you want to specify another action.</span></span>

7. <span data-ttu-id="e67e0-159">[**実行**する処理] で、**メッセージセキュリティ** \>を変更するために割り当てられているアクションを削除します。**以前のバージョンの OME を適用**します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-159">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>

8. <span data-ttu-id="e67e0-160">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-160">Choose **Save**.</span></span>

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="e67e0-161">新しい機能を使用せずに Office 365 メッセージ暗号化のメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="e67e0-161">Create mail flow rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="e67e0-p112">Office 365 組織を新しい OME 機能にまだ移行していない場合は、これらのタスクを使用して、組織のメッセージを暗号化するためのメールフロールールを定義します。Microsoft は、組織にとって適切であることをすぐに、新しい OME 機能に移行するための計画を立てることを推奨します。手順については、「 [Azure Information Protection の上に構築された新しい Office 365 メッセージ暗号化機能のセットアップ](set-up-new-message-encryption-capabilities.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p112">If you haven't yet moved your Office 365 organization to the new OME capabilities, use these tasks to define mail flow rules to encrypt messages for your organization. Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span>

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="e67e0-165">EAC を使用して、新しい OME 機能を使用せずに電子メールメッセージを暗号化するためのメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="e67e0-165">Use the EAC to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="e67e0-166">web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-166">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="e67e0-167">[**管理**] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-167">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="e67e0-168">Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="e67e0-168">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="e67e0-p113">EAC で、[**メールフロー** \> ] [**ルール**] に\*\*\*\* ![移動し、](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> [新しい新規作成] アイコンを選択して**新しいルールを作成**します。EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p113">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**. For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="e67e0-171">[**名前**] にルールの名前 (DrToniRamos@hotmail.com のメールの暗号化など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-171">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="e67e0-p114">**[次の場合、このルールを適用する]** で条件を選択し、必要に応じて値を入力します。たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p114">In **Apply this rule if** select a condition, and enter a value if necessary. For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="e67e0-174">**[次の場合、このルールを適用する]** で、**[受信者]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-174">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="e67e0-175">連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-175">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="e67e0-176">既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e67e0-176">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="e67e0-177">新しい名前を入力するには、[**名前の確認**] ボックスに電子メールアドレスを入力し、[**名前** \>の確認 **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-177">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="e67e0-178">さらに条件を追加するには、[**その他のオプション**] を選択し、[**条件の追加**] を選択してリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-178">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span>

   <span data-ttu-id="e67e0-179">たとえば、受信者が組織の外部にいる場合にのみルールを適用するには、[**条件の追加**] を選択し、[**受信者が外部/内部** \>の**組織** \>外にある **]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-179">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="e67e0-180">新しい OME 機能を使用せずに暗号化を有効にするには、**次の操作を行い**ます。 [**メッセージセキュリティ** \>を変更する] [**前のバージョンの OME を適用**する]、[**保存**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-180">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>

  <span data-ttu-id="e67e0-p115">IRM ライセンスが有効になっていないというエラーが表示された場合は、まだ組織の OME をセットアップしていません。今すぐ OME を設定したい場合は、新しい OME 機能を使用するように設定する必要があります。詳細については、「 [Azure information Protection の上に構築された新しい Office 365 メッセージ暗号化機能のセットアップ](set-up-new-message-encryption-capabilities.md)」を参照してください。Microsoft では、新しい機能なしで OME の新しい展開をセットアップすることはサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p115">If you receive an error that IRM licensing isn't enabled, then you haven't set up OME for your organization yet. If you'd like to set up OME now, you must set it up to use the new OME capabilities. For information, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). Microsoft no longer supports setting up new deployments of OME without the new capabilities.</span></span>

  <span data-ttu-id="e67e0-185">別のアクションを指定する場合は、[**アクションの追加**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="e67e0-185">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="e67e0-186">Exchange Online の PowerShell を使用して、新しい OME 機能なしで電子メールメッセージを暗号化するためのメールフロールールを作成する</span><span class="sxs-lookup"><span data-stu-id="e67e0-186">Use Exchange Online PowerShell to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="e67e0-p116">Exchange Online PowerShell に接続します。詳細については、「 [Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p116">Connect to Exchange Online PowerShell. For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e67e0-189">**new-transportrule**コマンドレットを使用してルールを作成し、 _ApplyOME_パラメーターをに`$true`設定します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-189">Create a rule by using the **New-TransportRule** cmdlet and set the _ApplyOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="e67e0-190">この例では、DrToniRamos@hotmail.com に送信されるすべての電子メールメッセージが暗号化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e67e0-190">This example requires that all email messages sent to DrToniRamos@hotmail.com must be encrypted.</span></span>

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   <span data-ttu-id="e67e0-191">**注**:</span><span class="sxs-lookup"><span data-stu-id="e67e0-191">**Notes**:</span></span>

   - <span data-ttu-id="e67e0-192">新しいルールの一意の名前は、"Dr toni ramos の暗号化ルール" です。</span><span class="sxs-lookup"><span data-stu-id="e67e0-192">The unique name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>

   - <span data-ttu-id="e67e0-p117">パラメーター_に_は、メッセージの受信者を指定します (名前、電子メールアドレス、識別名などで識別されます)。この例では、受信者は電子メールアドレス "DrToniRamos@hotmail.com" によって識別されます。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p117">The _SentTo_ parameter specifies the message recipients (identified by name, email address, distinguished name, etc.). In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span>

   - <span data-ttu-id="e67e0-p118">/ __ は、メッセージの受信者の場所を指定します。この例では、受信者のメールボックスは hotmail にあり、Office 365 組織の一部ではないため`NotInOrganization` 、値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p118">The _SentToScope_ parameter specifies the location of the message recipients. In this example, the recipient's mailbox is in hotmail and is not part of the Office 365 organization, so the value `NotInOrganization` is used.</span></span>

   <span data-ttu-id="e67e0-197">詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e67e0-197">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="e67e0-198">新しい OME 機能を使用せずに暗号化された電子メールの返信から暗号化を削除する</span><span class="sxs-lookup"><span data-stu-id="e67e0-198">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="e67e0-p119">電子メールユーザーが暗号化されたメッセージを送信すると、それらのメッセージの受信者は暗号化された応答で応答できます。メールフロールールを作成して、返信からの暗号化を自動的に削除することで、組織内の電子メールユーザーが暗号化ポータルにサインインして表示されないようにすることができます。これらのルールは、EAC または Windows PowerShell コマンドレットを使用して定義できます。新しい OME 機能をまだ使用していない場合は、組織内から送信されたメッセージまたは組織内から送信されたメッセージに返信されるメッセージの暗号化を解除することしかできません。組織外からの暗号化されたメッセージを解読することはできません。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p119">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies. You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them. You can use the EAC or Windows PowerShell cmdlets to define these rules. If you are not yet using the new OME capabilities, you can only decrypt messages that are either sent from within your organization or messages that are replies to messages sent from within your organization. You cannot decrypt encrypted messages originating from outside of your organization.</span></span>

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="e67e0-204">EAC を使用して、新しい OME 機能を使用せずに暗号化された電子メールの返信からの暗号化を削除するためのルールを作成する</span><span class="sxs-lookup"><span data-stu-id="e67e0-204">Use the EAC to create a rule for removing encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="e67e0-205">web ブラウザーで、管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-205">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="e67e0-206">[**管理**] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-206">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="e67e0-207">Office 365 管理センター で、 **[管理センター]** \> **[Exchange]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="e67e0-207">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="e67e0-p120">EAC で、[**メールフロー** \> ] [**ルール**] に\*\*\*\* ![移動し、](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> [新しい新規作成] アイコンを選択して**新しいルールを作成**します。EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p120">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**. For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="e67e0-210">[**名前**] にルールの名前を入力します。たとえば、[受信メールからの暗号化の削除] などです。</span><span class="sxs-lookup"><span data-stu-id="e67e0-210">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>

6. <span data-ttu-id="e67e0-211">[**次の場合、このルールを適用**する] [**受信者が** \> **組織内**にある] など、メッセージから暗号化を削除する条件を選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-211">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>

7. <span data-ttu-id="e67e0-212">[**実行する処理**] で、[**メッセージのセキュリティ** \>を変更する] を選択します。**以前のバージョンの OME を削除**します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-212">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>

8. <span data-ttu-id="e67e0-213">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-213">Select **Save**.</span></span>

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="e67e0-214">Exchange Online PowerShell を使用して、新しい OME 機能なしで暗号化された電子メールの返信から暗号化を削除するルールを作成する</span><span class="sxs-lookup"><span data-stu-id="e67e0-214">Use Exchange Online PowerShell to create a rule to remove encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="e67e0-p121">Exchange Online PowerShell に接続します。詳細については、「 [Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p121">Connect to Exchange Online PowerShell. For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="e67e0-217">**new-transportrule**コマンドレットを使用してルールを作成し、 _RemoveOME_パラメーターをに`$true`設定します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-217">Create a rule by using the **New-TransportRule** cmdlet and set the _RemoveOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="e67e0-218">この例では、Office 365 組織内の受信者に送信されるすべてのメールから暗号化を削除します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-218">This example removes the encryption from all mail sent to recipients in the Office 365 organization.</span></span>

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   <span data-ttu-id="e67e0-219">**注**:</span><span class="sxs-lookup"><span data-stu-id="e67e0-219">**Notes**:</span></span>

   - <span data-ttu-id="e67e0-220">新しいルールの一意の名前は、"受信メールから暗号化を削除する" です。</span><span class="sxs-lookup"><span data-stu-id="e67e0-220">The unique name of the new rule is "Remove encryption from incoming mail".</span></span>

   - <span data-ttu-id="e67e0-p122">/ __ は、メッセージの受信者の場所を指定します。この例では、値`InOrganization`の値を使用して、次のことを示します。</span><span class="sxs-lookup"><span data-stu-id="e67e0-p122">The _SentToScope_ parameter specifies the location of the message recipients. In this example, the value `InOrganization` value is used, which indicates:</span></span>

     - <span data-ttu-id="e67e0-223">受信者が組織内のメールボックス、メールユーザー、グループ、またはメールが有効なパブリックフォルダーである。</span><span class="sxs-lookup"><span data-stu-id="e67e0-223">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization.</span></span>

       <span data-ttu-id="e67e0-224">または</span><span class="sxs-lookup"><span data-stu-id="e67e0-224">or</span></span>

     - <span data-ttu-id="e67e0-225">受信者の電子メールアドレスが、組織内の権限のあるドメインまたは内部の中継ドメインとして構成さ__ れている承認済みドメイン内にあり、認証された接続を介してメッセージが送信または受信された。</span><span class="sxs-lookup"><span data-stu-id="e67e0-225">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain in your organization, _and_ the message was sent or received over an authenticated connection.</span></span>

<span data-ttu-id="e67e0-226">詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e67e0-226">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e67e0-227">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e67e0-227">Related Topics</span></span>

[<span data-ttu-id="e67e0-228">Office 365 での暗号化</span><span class="sxs-lookup"><span data-stu-id="e67e0-228">Encryption in Office 365</span></span>](encryption.md)

[<span data-ttu-id="e67e0-229">新しい Office 365 Message Encryption 機能を設定する</span><span class="sxs-lookup"><span data-stu-id="e67e0-229">Set up new Office 365 Message Encryption capabilities</span></span>](set-up-new-message-encryption-capabilities.md)

[<span data-ttu-id="e67e0-230">暗号化メッセージへのブランドの追加</span><span class="sxs-lookup"><span data-stu-id="e67e0-230">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)

[<span data-ttu-id="e67e0-231">Exchange Online のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="e67e0-231">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[<span data-ttu-id="e67e0-232">Exchange Online Protection のメール フロー ルール (トランスポート ルール)</span><span class="sxs-lookup"><span data-stu-id="e67e0-232">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)
