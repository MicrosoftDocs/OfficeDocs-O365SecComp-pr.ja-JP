---
title: Office 365 で送信スパムポリシー通知を構成する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/10/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 管理者は、Office 365 で送信スパム検出の通知設定を変更する方法について説明します。
ms.openlocfilehash: c48b6cd634417a00040fb5479313782b44f6aa8d
ms.sourcegitcommit: 81b3bff27bc60235a38004c5b0297ac454331b25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "36822517"
---
# <a name="configure-outbound-spam-policy-notifications-in-office-365"></a><span data-ttu-id="dab3c-103">Office 365 で送信スパムポリシー通知を構成する</span><span class="sxs-lookup"><span data-stu-id="dab3c-103">Configure outbound spam policy notifications in Office 365</span></span>

<span data-ttu-id="dab3c-104">送信電子メールの送信にサービスを使用すると、送信スパムフィルターは常に有効になり、それによって、そのサービスと目的の受信者を使用して組織が保護されます。</span><span class="sxs-lookup"><span data-stu-id="dab3c-104">Outbound spam filtering is always enabled if you use the service for sending outbound email, thereby protecting organizations using the service and their intended recipients.</span></span> <span data-ttu-id="dab3c-105">受信フィルターと同様に、送信スパムフィルターは、接続フィルターとコンテンツフィルターで構成されますが、送信フィルター設定は構成できません。</span><span class="sxs-lookup"><span data-stu-id="dab3c-105">Similar to inbound filtering, outbound spam filtering is comprised of connection filtering and content filtering, however the outbound filter settings are not configurable.</span></span> <span data-ttu-id="dab3c-106">送信メッセージがスパムであると判断された場合は、より危険度の高い配信プールを経由してルーティングされます。これにより、通常の送信 IP プールがブロックリストに追加される確率が低くなります。</span><span class="sxs-lookup"><span data-stu-id="dab3c-106">If an outbound message is determined to be spam, it is routed through the higher risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list.</span></span> <span data-ttu-id="dab3c-107">お客様がサービス経由で送信スパムを引き続き送信する場合、メッセージの送信はブロックされます。</span><span class="sxs-lookup"><span data-stu-id="dab3c-107">If a customer continues to send outbound spam through the service, they will be blocked from sending messages.</span></span>

<span data-ttu-id="dab3c-108">送信スパムフィルター処理を無効にしたり、変更したりすることはできませんが、次の送信スパム通知設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="dab3c-108">Although you can't disable or change outbound spam filtering, you can configure the following outbound spam notification settings:</span></span>

- <span data-ttu-id="dab3c-109">**疑わしいメッセージのコピーを送信**する: これらのメッセージは、SCL レベルに関係なく、スパムとしてマークされ、フィルターによって拒否されることはありませんが、より危険度の高い配信プールを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="dab3c-109">**Send copies of suspicious messages**: These messages are marked as spam (regardless of the SCL rating) and are not rejected by the filter, but are routed through the higher risk delivery pool.</span></span> <span data-ttu-id="dab3c-110">Exchange 管理センター (EAC) また\*\* \*は HostedOutboundSpamFilterPolicy\*\*コマンドレットを使用して、exchange online powershell または exchange online Protection powershell で、これらの検出されたメッセージの受信者を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="dab3c-110">You can use the Exchange admin center (EAC) or the **\*-HostedOutboundSpamFilterPolicy** cmdlets in Exchange Online PowerShell or Exchange Online Protection PowerShell to specify addition recipients for these detected messages.</span></span> <span data-ttu-id="dab3c-111">受信者は**Bcc**受信者として追加されることに注意してください **(差出人フィールド**と宛先フィールドは元の**送信者と受信**者です)。</span><span class="sxs-lookup"><span data-stu-id="dab3c-111">Note that the recipients are added as **Bcc** recipients (the **From** and **To** fields are the original sender and recipient).</span></span>

- <span data-ttu-id="dab3c-112">**送信者がブロックされたときに通知を送信**する: 特定のユーザーが大量のスパムを受信した場合、そのユーザーは電子メールメッセージの送信を無効にします。</span><span class="sxs-lookup"><span data-stu-id="dab3c-112">**Send notifications when a sender is blocked**: When a significant amount of spam is coming from a particular user, the user is disabled from sending email messages.</span></span> <span data-ttu-id="dab3c-113">管理者には既定で通知されますが、Office 365 セキュリティ & コンプライアンスセンターで [**ユーザーによるメール通知の送信を制限** [](alert-policies.md)する] を使用して、追加の通知受信者を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="dab3c-113">Admins are notified by default, but you can use the **User restricted from sending email** [alert policy](alert-policies.md) in the Office 365 Security & Compliance Center to configure additional notification recipients.</span></span>

  <span data-ttu-id="dab3c-114">この通知がどのように表示されるかを確認するには、「[送信者が送信スパムの送信をブロックされる場合の通知例](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dab3c-114">To see what this notification looks like, see [Sample notification when a sender is blocked sending outbound spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).</span></span> <span data-ttu-id="dab3c-115">作業を再度有効にする方法については、「[Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dab3c-115">For information about getting re-enabled, see [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dab3c-116">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="dab3c-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="dab3c-117">予想所要時間 : 5 分</span><span class="sxs-lookup"><span data-stu-id="dab3c-117">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="dab3c-118">セキュリティ/コンプライアンス センターを開くには、「[Office 365 のセキュリティ センターとコンプライアンス センターに移動する](go-to-the-securitycompliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dab3c-118">To open the Security & Compliance Center, see [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md).</span></span>

- <span data-ttu-id="dab3c-119">EAC を開くには、「exchange [online の exchange 管理センター](https://docs.microsoft.com/Exchange/exchange-admin-center) 」または「exchange [Admin Center In exchange online Protection](exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dab3c-119">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="dab3c-120">Exchange Online PowerShell を開くには、「 [Exchange Online powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dab3c-120">To open Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="dab3c-121">Exchange Online Protection PowerShell を開くには、「 [Exchange Online protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dab3c-121">To open Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="dab3c-122">この手順を実行する前に、アカウントにアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dab3c-122">Your account needs to be assigned permissions before you can perform this procedure.</span></span> <span data-ttu-id="dab3c-123">必要なアクセス許可については、「 [Office 365 セキュリティ & コンプライアンスセンター](permissions-in-the-security-and-compliance-center.md)」の「アクセス許可」の「通知を管理する」の役割エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dab3c-123">To see what permissions you need, see the "Manage Alerts" role entry in [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-eac-to-configure-additional-recipients-for-outbound-spam-messages"></a><span data-ttu-id="dab3c-124">EAC を使用して、送信スパムメッセージの追加の受信者を構成する</span><span class="sxs-lookup"><span data-stu-id="dab3c-124">Use the EAC to configure additional recipients for outbound spam messages</span></span>

1. <span data-ttu-id="dab3c-125">EAC で、[**保護** \> **送信スパム**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-125">In the EAC, go to **Protection** \> **Outbound spam**.</span></span>

2. <span data-ttu-id="dab3c-126">**Default**という名前のポリシーを選択し、[編集](media/ITPro-EAC-EditIcon.png)] ![編集アイコン**をクリックし**ます。</span><span class="sxs-lookup"><span data-stu-id="dab3c-126">Select the policy named **Default**, and then click **Edit** ![Edit icon](media/ITPro-EAC-EditIcon.png).</span></span>

3. <span data-ttu-id="dab3c-127">開いたプロパティページで、[**送信スパムの設定**] タブが選択されていることを確認し、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-127">In the properties page that opens, verify that the **Outbound spam preferences** tab is selected, and then configure the following setting:</span></span>

   <span data-ttu-id="dab3c-128">**疑わしい送信電子メールメッセージすべてのコピーを次の電子メールアドレスまたはアドレスに送信**する: チェックボックスをオンにして、検出されたメッセージの**Bcc**フィールドに追加する1人以上の管理者の電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-128">**Send a copy of all suspicious outbound email messages to the following email address or addresses**: Select the check box and enter the email addresses of one or more administrators who should be added to the **Bcc** field of detected messages.</span></span> <span data-ttu-id="dab3c-129">複数の電子メールアドレスは、セミコロン (;) で区切ります。</span><span class="sxs-lookup"><span data-stu-id="dab3c-129">Separate multiple email addresses with a semicolon ( ; ).</span></span>

   <span data-ttu-id="dab3c-130">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dab3c-130">When you're finished, click **Save**.</span></span>

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-additional-recipients-for-outbound-spam-messages"></a><span data-ttu-id="dab3c-131">Exchange Online PowerShell または Exchange Online Protection PowerShell を使用して、送信スパムメッセージの追加の受信者を構成する</span><span class="sxs-lookup"><span data-stu-id="dab3c-131">Use Exchange Online PowerShell or Exchange Online Protection PowerShell to configure additional recipients for outbound spam messages</span></span>

<span data-ttu-id="dab3c-132">送信スパムメッセージの追加の受信者を有効にして構成するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-132">To enable and configure additional recipients for outbound spam messages, use the following syntax:</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients <recipients>
```

- <span data-ttu-id="dab3c-133">既存のすべての値を上書きする受信者を指定する`emailaddress1,emailaddress2,...emailaddressN`には、構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-133">To specify recipients that overwrite all existing values, use the syntax `emailaddress1,emailaddress2,...emailaddressN`.</span></span>

- <span data-ttu-id="dab3c-134">他のエントリに影響を与えずに、受信者を追加また`@{Add="\<emailaddress1\>","\<emailaddress2\>"...; Remove="\<emailaddress1\>","\<emailaddress2\>"...}`は削除するには、構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-134">To selectively add or remove recipients without affecting the other entries, use the syntax `@{Add="\<emailaddress1\>","\<emailaddress2\>"...; Remove="\<emailaddress1\>","\<emailaddress2\>"...}`.</span></span>

<span data-ttu-id="dab3c-135">この例では、chris@contoso.com、laura@contoso.com、および julia@contoso.com を送信スパムメッセージの Bcc 受信者として構成します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-135">This example enables and configures chris@contoso.com, laura@contoso.com and julia@contoso.com as Bcc recipients for outbound spam messages.</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundMail $true -BccSuspiciousOutboundAdditionalRecipients chris@contoso.com,laura@contoso.com,julia@contoso.com
```

<span data-ttu-id="dab3c-136">この例では、追加の Bcc 受信者として michelle@contoso.com を追加します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-136">This example adds michelle@contoso.com as an additional Bcc recipient.</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Add=michelle@contoso.com}
```

<span data-ttu-id="dab3c-137">この例では、Bcc 受信者のリストから chris@contoso.com および julia@contoso.com を削除します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-137">This example removes chris@contoso.com and julia@contoso.com from the list of Bcc recipients.</span></span>

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity Default -BccSuspiciousOutboundAdditionalRecipients @{Remove='chris@contoso.com','julia@contoso.com'}
```

<span data-ttu-id="dab3c-138">構文およびパラメーターの詳細については、「 [HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dab3c-138">For detailed syntax and parameter information, see [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).</span></span>

<span data-ttu-id="dab3c-139">**注**: コマンド`Get-HostedOutboundSpamFilterPolicy | Format-List`を実行して、 *BccSuspiciousOutboundMail*プロパティと*BccSuspiciousOutboundAdditionalRecipients*プロパティの現在の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-139">**Note**: Run the command `Get-HostedOutboundSpamFilterPolicy | Format-List` to see the current values of the *BccSuspiciousOutboundMail* and *BccSuspiciousOutboundAdditionalRecipients* properties.</span></span>

## <a name="use-the-security--compliance-center-to-configure-notifications-when-a-sender-is-blocked"></a><span data-ttu-id="dab3c-140">セキュリティ & コンプライアンスセンターを使用して、送信者がブロックされたときの通知を構成する</span><span class="sxs-lookup"><span data-stu-id="dab3c-140">Use the Security & Compliance Center to configure notifications when a sender is blocked</span></span>

1. <span data-ttu-id="dab3c-141">[セキュリティ & コンプライアンスセンター] で、[**アラート** \> **ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-141">In the Security & Compliance Center, go to **Alerts** \> **Alert Policies**.</span></span>

2. <span data-ttu-id="dab3c-142">[**ユーザーによるメール送信からの制限**] という名前のポリシーを検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-142">Find and select the policy named **User restricted from sending email**.</span></span>

3. <span data-ttu-id="dab3c-143">スライドが開いたら、[ポリシーの**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dab3c-143">In the fly out that opens, click **Edit policy**.</span></span>

4. <span data-ttu-id="dab3c-144">表示される [**受信者の編集**] ページで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-144">In the **Edit recipients** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="dab3c-145">**電子メール通知\*\*\*\*の**送信: が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-145">**Send email notifications**: Verify that **On** is selected.</span></span>

   - <span data-ttu-id="dab3c-146">**電子メール受信者**: 既定では、 **tenantadmins**のみがこの値になります。</span><span class="sxs-lookup"><span data-stu-id="dab3c-146">**Email recipients**: By default **TenantAdmins** is the only value here.</span></span> <span data-ttu-id="dab3c-147">その他の受信者を追加するには、このボックスの空の場所をクリックし、受信者の入力を開始して、名前が解決される受信者を選択します。</span><span class="sxs-lookup"><span data-stu-id="dab3c-147">To add additional recipients, click in an empty spot in this box, start typing the recipient, and select the recipient when their name resolves.</span></span> <span data-ttu-id="dab3c-148">受信者を削除するには、名前の横にある [ **X** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dab3c-148">To remove recipients, click on the **X** next to their names.</span></span>

   - <span data-ttu-id="dab3c-149">[**毎日の通知制限**]: 既定値は**制限なし**ですが、1 ~ 200 のさまざまな制限を構成できます。</span><span class="sxs-lookup"><span data-stu-id="dab3c-149">**Daily notification limit**: The default value is **No limit**, but you can configure various limits from 1 to 200.</span></span>

   <span data-ttu-id="dab3c-150">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dab3c-150">When you're finished, click **Save**.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="dab3c-151">関連情報</span><span class="sxs-lookup"><span data-stu-id="dab3c-151">For more information</span></span>

[<span data-ttu-id="dab3c-152">送信メッセージにおける危険度の高い配信プール</span><span class="sxs-lookup"><span data-stu-id="dab3c-152">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="dab3c-153">スパム対策保護に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="dab3c-153">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
