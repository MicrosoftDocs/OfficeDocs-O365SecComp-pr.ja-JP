---
title: Exchange Online メールボックスに適用されている保留の種類を特定する方法
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: Office 365 メールボックスに配置できるさまざまな種類の保留リストを識別する方法について説明します。これらの種類には、訴訟ホールド、電子情報開示の保持、および Office 365 アイテム保持ポリシーが含まれます。ユーザーが組織全体のアイテム保持ポリシーから除外されているかどうかを確認することもできます。
ms.openlocfilehash: 5b9e8437b688a5c1b35726834c3d80d07cc4ba50
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296810"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a><span data-ttu-id="2c095-105">Exchange Online メールボックスに適用されている保留の種類を特定する方法</span><span class="sxs-lookup"><span data-stu-id="2c095-105">How to identify the type of hold placed on an Exchange Online mailbox</span></span>

<span data-ttu-id="2c095-106">この記事では、Office 365 の Exchange Online メールボックスに配置された保留リストを特定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c095-106">This article explains how to identify holds placed on Exchange Online mailboxes in Office 365.</span></span>

<span data-ttu-id="2c095-p102">Office 365 には、組織がメールボックスの内容が完全に削除されないようにする方法がいくつか用意されています。これにより、組織は、コンプライアンス regulars または法的またはその他の種類の調査の期間中に、コンテンツを保持することができます。Office 365 の保持機能 (*保留*とも呼ばれます) の一覧を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="2c095-p102">Office 365 offers a number of ways that your organization can prevent mailbox content from being permanently deleted. This allows your organization to retain content to meet compliance regulars or for the duration of legal or other types of investigations. Here's a list of the retention features (also called *holds*) in Office 365:</span></span>

- <span data-ttu-id="2c095-110">**訴訟ホールド**-Exchange Online のユーザーメールボックスに適用されるホールド。</span><span class="sxs-lookup"><span data-stu-id="2c095-110">**Litigation Hold** - Holds that are applied to user mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="2c095-p103">**電子**情報開示の保持-セキュリティ & コンプライアンスセンターの電子情報開示ケースに関連付けられている保留。電子情報開示の保持は、ユーザーのメールボックス、および対応する Office 365 グループおよび Microsoft Teams のメールボックスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="2c095-p103">**eDiscovery hold** - Holds that are associated with an eDiscovery case in the Security & Compliance Center. eDiscovery holds can be applied to user mailboxes, and on the corresponding mailbox for Office 365 Groups and Microsoft Teams.</span></span>

- <span data-ttu-id="2c095-113">インプレース**保持**-exchange Online の exchange 管理センターでインプレース電子情報開示 & ホールドツールを使用して、ユーザーのメールボックスに適用されるホールド。</span><span class="sxs-lookup"><span data-stu-id="2c095-113">**In-Place Hold** - Holds that are applied to user mailboxes by using the In-Place eDiscovery & Hold tool in the Exchange admin center in Exchange Online.</span></span>

- <span data-ttu-id="2c095-p104">**office 365 アイテム保持ポリシー** -Exchange Online のユーザーメールボックスおよび office 365 グループと Microsoft Teams の対応するメールボックスにコンテンツを保持します。アイテム保持ポリシーを作成すると、ユーザーのメールボックスに格納されている Skype for business 会話が保持されます。</span><span class="sxs-lookup"><span data-stu-id="2c095-p104">**Office 365 retention policy** - Retains content in user mailboxes in Exchange Online and in the corresponding mailbox for Office 365 Groups and Microsoft Teams. You can create a retention policy retains Skype for Business Conversations, which are stored in user mailboxes.</span></span>

  <span data-ttu-id="2c095-116">メールボックスに割り当てることができる Office 365 のアイテム保持ポリシーには、2種類あります。</span><span class="sxs-lookup"><span data-stu-id="2c095-116">There are two types of Office 365 retention policies that can be assigned to mailboxes.</span></span>

    - <span data-ttu-id="2c095-p105">**特定の場所の保持ポリシー** -特定のユーザーのコンテンツの場所に割り当てられているポリシーです。Exchange Online の PowerShell で、**メールボックスの取得**コマンドレットを使用して、特定のメールボックスに割り当てられているアイテム保持ポリシーに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="2c095-p105">**Specific location retention policies** - These are policies that are assigned to the content locations of specific users. You use the **Get-Mailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific mailboxes.</span></span>

    - <span data-ttu-id="2c095-p106">**組織全体のアイテム保持ポリシー** -組織内のすべてのコンテンツの場所に割り当てられているポリシーです。組織全体のアイテム保持ポリシーについての情報を取得するには、Exchange Online の PowerShell で、" **get-help/** 組織全体の構成" コマンドレットを使用します。詳細については、「 [Office 365 アイテム保持ポリシーの概要](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)」の「組織全体または特定の場所にアイテム保持ポリシーを適用する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c095-p106">**Organization-wide retention policies** - These are policies that are assigned to all content locations in your organization. You use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies. For more information, see the "Applying a retention policy to an entire organization or specific locations" section in [Overview of Office 365 retention policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).</span></span>

- <span data-ttu-id="2c095-p107">**office 365 の保持ラベル**-ユーザーが自分のメールボックス内の*任意*のフォルダーまたはアイテムに office 365 の保持ラベル (コンテンツを保持するように構成されている、またはコンテンツを保持してから削除するように構成されている) を適用すると、メールボックスがメールボックスの場合と同じように保持されます。訴訟ホールドの対象にするか、Office 365 アイテム保持ポリシーに割り当てられます。詳細については、この記事の「[フォルダーまたはアイテムに保持ラベルが適用されているため、保留中のメールボックスを識別](#identifying-mailboxes-on-hold-because-a-label-has-been-applied-to-a-folder-or-item)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c095-p107">**Office 365 retention labels** - If a user applies an Office 365 retention label (one that's configured to retain content or retain and then delete content) to *any* folder or item in their mailbox, a hold is placed on the mailbox just as if the mailbox was placed on Litigation Hold or assigned to an Office 365 retention policy. For more information, see the [Identifying mailboxes on hold because a retention label has been applied to a folder or item](#identifying-mailboxes-on-hold-because-a-label-has-been-applied-to-a-folder-or-item) section in this article.</span></span>

<span data-ttu-id="2c095-p108">保留中のメールボックスを管理するには、保持期間の変更、一時的または完全に保持を削除する、または Office 365 アイテム保持ポリシーからメールボックスを除外するなどのタスクを実行できるように、メールボックスに設定されているホールドの種類を特定する必要がある場合があります。このような場合は、最初の手順として、メールボックスに設定されている保留の種類を特定します。また、複数のホールド (および異なる種類の保留リスト) を単一のメールボックスに配置することができるため、そのような保留リストを削除または変更する場合は、メールボックスに設定されているすべての保留リストを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c095-p108">To manage mailboxes on hold, you may have to identify the type of hold that's placed on a mailbox so that you can perform tasks such as changing the hold duration, temporarily or permanently removing the hold, or excluding a mailbox from a Office 365 retention policy. In these cases, the first step is to identify the type of hold placed on the mailbox. And because multiple holds (and different types of holds) can be placed on a single mailbox, you'll have to identify all holds placed on a mailbox if you want to remove or change those holds.</span></span>

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a><span data-ttu-id="2c095-127">手順 1: メールボックスに配置された保留リストの GUID を取得する</span><span class="sxs-lookup"><span data-stu-id="2c095-127">Step 1: Obtaining the GUID for holds placed on a mailbox</span></span>

<span data-ttu-id="2c095-p109">Exchange Online PowerShell で次の2つのコマンドレットを実行して、メールボックスに配置されている保留リストの GUID を取得できます。GUID を取得した後、それを使用して、手順2で特定のホールドを識別します。訴訟ホールドは GUID で識別されないことに注意してください。訴訟ホールドは、メールボックスに対して有効または無効のどちらかになります。</span><span class="sxs-lookup"><span data-stu-id="2c095-p109">You can run the following two cmdlets in Exchange Online PowerShell to get the GUID of the holds that are placed on a mailbox. After you obtain a GUID, you use it to identify the specific hold in Step 2. Note that Litigation Holds are not identified by a GUID. Litigation Holds are either enabled or disabled for a mailbox.</span></span>

- <span data-ttu-id="2c095-p110">**Get メールボックス**-メールボックスに対して訴訟ホールドが有効になっているかどうかを確認し、メールボックスに割り当てられている電子情報開示の保持ポリシー、インプレースホールド、および Office 365 アイテム保持ポリシーの guid を取得するには、このコマンドレットを使用します。このコマンドレットの出力は、メールボックスが組織全体のアイテム保持ポリシーから明示的に除外されているかどうかも示します。</span><span class="sxs-lookup"><span data-stu-id="2c095-p110">**Get-Mailbox** - Use this cmdlet to determine whether Litigation Hold is enabled for a mailbox and to get the GUIDs for eDiscovery holds, In-Place Holds, and Office 365 retention policies that are specifically assigned to a mailbox. The output of this cmdlet will also indicate if a mailbox has been explicitly excluded from an organization-wide retention policy.</span></span>

- <span data-ttu-id="2c095-134">**get-help config** -組織全体のアイテム保持ポリシーの guid を取得するには、このコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2c095-134">**Get-OrganizationConfig** - Use this cmdlet to get the GUIDs for organization-wide retention policies.</span></span>

<span data-ttu-id="2c095-135">exchange online powershell に接続するには、「 [exchange online powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c095-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

### <a name="get-mailbox"></a><span data-ttu-id="2c095-136">Get-Mailbox</span><span class="sxs-lookup"><span data-stu-id="2c095-136">Get-Mailbox</span></span>

<span data-ttu-id="2c095-137">次のコマンドを実行して、メールボックスに適用されている保留リストと Office 365 アイテム保持ポリシーに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="2c095-137">Run the following command to get information about the holds and Office 365 retention policies applied to a mailbox.</span></span>

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="2c095-138">InPlaceHolds プロパティに含まれる値が多すぎて、一部が表示されていない場合は、 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`コマンドを実行して各 GUID を別々の行に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="2c095-138">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="2c095-139">次の表は、InPlaceHolds コマンドレットを実行するときに、 \*\* プロパティの値に基づいてさまざまな\*\*\*\* 種類の保留リストを識別する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2c095-139">The following table describes how to identify different types of holds based on the values in the *InPlaceHolds* property when you run the **Get-Mailbox** cmdlet.</span></span>


|<span data-ttu-id="2c095-140">ホールドの種類</span><span class="sxs-lookup"><span data-stu-id="2c095-140">Hold type</span></span>  |<span data-ttu-id="2c095-141">値の例</span><span class="sxs-lookup"><span data-stu-id="2c095-141">Example value</span></span>  |<span data-ttu-id="2c095-142">保留リストを識別する方法</span><span class="sxs-lookup"><span data-stu-id="2c095-142">How to identify the hold</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="2c095-143">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="2c095-143">Litigation Hold</span></span>     |    `True`     |     <span data-ttu-id="2c095-144">*LitigationHoldEnabled*プロパティがに`True`設定されている場合、メールボックスに対して訴訟ホールドが有効になります。</span><span class="sxs-lookup"><span data-stu-id="2c095-144">Litigation Hold is enabled for a mailbox if the *LitigationHoldEnabled* property is set to `True`.</span></span>    |
|<span data-ttu-id="2c095-145">電子情報開示の保留</span><span class="sxs-lookup"><span data-stu-id="2c095-145">eDiscovery hold</span></span>     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   <span data-ttu-id="2c095-p111">*InPlaceHolds プロパティ*には、セキュリティ & コンプライアンスセンターの電子情報開示ケースに関連付けられている保留の GUID が含まれています。GUID は`UniH`プレフィックス (統合された保持を示す) で始まっているため、これが電子情報開示の保留であることを伝えることができます。</span><span class="sxs-lookup"><span data-stu-id="2c095-p111">The *InPlaceHolds property* contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center. You can tell this is an eDiscovery hold because the GUID starts with the `UniH` prefix (which denotes a Unified Hold).</span></span>      |
|<span data-ttu-id="2c095-148">インプレース ホールド</span><span class="sxs-lookup"><span data-stu-id="2c095-148">In-Place Hold</span></span>     |     `c0ba3ce811b6432a8751430937152491` <br/> <span data-ttu-id="2c095-149">または</span><span class="sxs-lookup"><span data-stu-id="2c095-149">or</span></span> <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     <span data-ttu-id="2c095-p112">*InPlaceHolds*プロパティには、メールボックスに配置されたインプレースホールドの GUID が含まれています。GUID がプレフィックスで始まっていないか、 `cld`プレフィックスで始まっていないため、これはインプレースホールドであると判断できます。</span><span class="sxs-lookup"><span data-stu-id="2c095-p112">The *InPlaceHolds* property contains the GUID of the In-Place Hold that's placed on the mailbox. You can tell this is an In-Place Hold because the GUID either doesn't start with a prefix or it starts with the `cld` prefix.</span></span>     |
|<span data-ttu-id="2c095-152">特にメールボックスに適用される Office 365 アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="2c095-152">Office 365 retention policy specifically applied to the mailbox</span></span>     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> <span data-ttu-id="2c095-153">または</span><span class="sxs-lookup"><span data-stu-id="2c095-153">or</span></span> <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     <span data-ttu-id="2c095-p113">InPlaceHolds プロパティには、メールボックスに適用される特定の場所保持ポリシーの guid が含まれています。GUID は`mbx`または`skp`プレフィックスで始まっているため、アイテム保持ポリシーを識別できます。プレフィックス`skp`は、アイテム保持ポリシーがユーザーのメールボックス内の Skype for business の会話に適用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="2c095-p113">The InPlaceHolds property contains GUIDs of any specific location retention policy that's applied to the mailbox. You can identify retention policies because the GUID starts with the `mbx` or the `skp` prefix. The `skp` prefix indicates that the retention policy is applied to Skype for Business conversations in the user's mailbox.</span></span>    |
|<span data-ttu-id="2c095-157">組織全体の Office 365 アイテム保持ポリシーから除外されます。</span><span class="sxs-lookup"><span data-stu-id="2c095-157">Excluded from an organization-wide Office 365 retention policy</span></span>     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     <span data-ttu-id="2c095-158">メールボックスが組織全体の Office 365 アイテム保持ポリシーから除外されている場合、メールボックスが除外されるアイテム保持ポリシーの GUID は InPlaceHolds プロパティに表示され`-mbx` 、プレフィックスで識別されます。</span><span class="sxs-lookup"><span data-stu-id="2c095-158">If a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy the mailbox is excluded from is displayed in the InPlaceHolds property and is identified by the `-mbx` prefix.</span></span>    |

### <a name="get-organizationconfig"></a><span data-ttu-id="2c095-159">取得-組織の構成</span><span class="sxs-lookup"><span data-stu-id="2c095-159">Get-OrganizationConfig</span></span>
<span data-ttu-id="2c095-p114">**メールボックスの取得**コマンドレットを実行したときに*InPlaceHolds*プロパティが空の場合、依然として、1つ以上の組織全体の Office 365 アイテム保持ポリシーがメールボックスに適用されている可能性があります。Exchange Online PowerShell で次のコマンドを実行して、組織全体の Office 365 保持ポリシーの guid の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="2c095-p114">If the *InPlaceHolds* property is empty when you run the **Get-Mailbox** cmdlet, there still may be one or more organization-wide Office 365 retention policies applied to the mailbox. Run the following command in Exchange Online PowerShell to get a list of GUIDs for organization-wide Office 365 retention policies.</span></span>

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="2c095-162">InPlaceHolds プロパティに含まれる値が多すぎて、一部が表示されていない場合は、 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`コマンドを実行して各 GUID を別々の行に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="2c095-162">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="2c095-163">次の表では、組織全体のさまざまな種類と、InPlaceHolds コマンドレットを実行するときに、 \*\* プロパティに含まれている\*\*\*\* guid に基づいて各種類を識別する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c095-163">The following table describes the different types of organization-wide holds and how to identify each type based on the GUIDs contained in *InPlaceHolds* property when you run the **Get-OrganizationConfig** cmdlet.</span></span>


|<span data-ttu-id="2c095-164">ホールドの種類</span><span class="sxs-lookup"><span data-stu-id="2c095-164">Hold type</span></span>  |<span data-ttu-id="2c095-165">値の例</span><span class="sxs-lookup"><span data-stu-id="2c095-165">Example value</span></span>  |<span data-ttu-id="2c095-166">説明</span><span class="sxs-lookup"><span data-stu-id="2c095-166">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="2c095-167">exchange メールボックス、exchange パブリックフォルダー、およびチームチャットに適用される Office 365 アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="2c095-167">Office 365 retention policies applied to Exchange mailboxes, Exchange public folders, and Teams chats</span></span>    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   <span data-ttu-id="2c095-p115">exchange メールボックス、exchange パブリックフォルダー、および Microsoft Teams の1xn チャットに適用される組織全体のアイテム保持ポリシーは、 `mbx`プレフィックスで始まる guid によって識別されます。1xn チャットは、個々のチャット参加者のメールボックスに格納されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2c095-p115">Organization-wide retention policies applied to Exchange mailboxes, Exchange public folders, and 1xN chats in Microsoft Teams are identified by GUIDs that start with the `mbx` prefix. Note that 1xN chats are stored in the mailbox of the individual chat participants.</span></span>      |
|<span data-ttu-id="2c095-170">office 365 グループおよび Teams チャネルメッセージに適用される office 365 アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="2c095-170">Office 365 retention policy applied to Office 365 Groups and Teams channel messages</span></span>     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    <span data-ttu-id="2c095-p116">Office 365 グループに適用される組織全体のアイテム保持ポリシーと、Microsoft Teams のチャネルメッセージは、 `grp`プレフィックスで始まる guid によって識別されます。チャネルメッセージは、Microsoft teams に関連付けられているグループメールボックスに格納されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2c095-p116">Organization-wide retention policies applied to Office 365 groups and channel messages in Microsoft Teams are identified by GUIDs that start with the `grp` prefix. Note that channel messages are stored in the group mailbox that is associated with a Microsoft Team.</span></span>     |

<span data-ttu-id="2c095-173">Microsoft teams に適用される詳細なアイテム保持ポリシーについては、「[アイテム保持ポリシーの概要](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)」の「teams の場所」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c095-173">For more information retention policies applied to Microsoft Teams, see the "Teams location" section [Overview of retention policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).</span></span>

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a><span data-ttu-id="2c095-174">保持ポリシーの InPlaceHolds 値の形式について</span><span class="sxs-lookup"><span data-stu-id="2c095-174">Understanding the format of the InPlaceHolds value for retention policies</span></span>

<span data-ttu-id="2c095-p117">Office 365 アイテム保持ポリシーとして InPlaceHolds プロパティのアイテムを識別するプレフィックス (、skp、または grp) に加えて、この値には、ポリシーに対して構成されている保持アクションの種類を識別するサフィックスも含まれています。たとえば、次の例では、アクションのサフィックスが太字で強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="2c095-p117">In addition to the prefix (mbx, skp, or grp) that identifies an item in the InPlaceHolds property as an Office 365 retention policy, the value also contains a suffix that identifies the type of retention action that's configured for the policy. For example, the action suffix is highlighted in bold type in the following examples:</span></span>

   <span data-ttu-id="2c095-177">`skp127d7cf1076947929bf136b7a2a8c36f`**: 1**</span><span class="sxs-lookup"><span data-stu-id="2c095-177">`skp127d7cf1076947929bf136b7a2a8c36f`**:1**</span></span>

   <span data-ttu-id="2c095-178">`mbx7cfb30345d454ac0a989ab3041051209`**: 2**</span><span class="sxs-lookup"><span data-stu-id="2c095-178">`mbx7cfb30345d454ac0a989ab3041051209`**:2**</span></span>

   <span data-ttu-id="2c095-179">`grp1a0a132ee8944501a4bb6a452ec31171`**: 3**</span><span class="sxs-lookup"><span data-stu-id="2c095-179">`grp1a0a132ee8944501a4bb6a452ec31171`**:3**</span></span>

<span data-ttu-id="2c095-180">次の表では、3つの保持アクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="2c095-180">The following table defines the three possible retention actions:</span></span>

|<span data-ttu-id="2c095-181">値</span><span class="sxs-lookup"><span data-stu-id="2c095-181">Value</span></span>  |<span data-ttu-id="2c095-182">説明</span><span class="sxs-lookup"><span data-stu-id="2c095-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="2c095-183">**1**</span><span class="sxs-lookup"><span data-stu-id="2c095-183">**1**</span></span>     | <span data-ttu-id="2c095-184">アイテムを削除するようにアイテム保持ポリシーが構成されていることを示します。ポリシーはアイテムを保持しません。</span><span class="sxs-lookup"><span data-stu-id="2c095-184">Indicates the retention policy is configured to delete items; the policy doesn't retain items.</span></span>        |
|<span data-ttu-id="2c095-185">**2**</span><span class="sxs-lookup"><span data-stu-id="2c095-185">**2**</span></span>    |    <span data-ttu-id="2c095-186">アイテム保持ポリシーがアイテムを保持するように構成されていることを示します。保持期間が経過すると、ポリシーによってアイテムが削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="2c095-186">Indicates the retention policy is configured to hold items; the policy doesn't delete items after the retention period expires.</span></span>     |
|<span data-ttu-id="2c095-187">**3**</span><span class="sxs-lookup"><span data-stu-id="2c095-187">**3**</span></span>     |   <span data-ttu-id="2c095-188">アイテム保持ポリシーがアイテムを保持するように構成されていて、保存期間が経過した後にアイテムを削除することを示します。</span><span class="sxs-lookup"><span data-stu-id="2c095-188">Indicates the retention policy is configured to hold items and then delete them after the retention period expires.</span></span>      |

<span data-ttu-id="2c095-189">保持アクションの詳細については、「[アイテム保持ポリシーの概要](retention-policies.md#retaining-content-for-a-specific-period-of-time)」の「特定の期間だけコンテンツを保持する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c095-189">For more information about retention actions, see the "Retaining content for a specific period of time" section in [Overview of retention policies](retention-policies.md#retaining-content-for-a-specific-period-of-time).</span></span>
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a><span data-ttu-id="2c095-190">手順 2: GUID を使用して保留リストを識別する</span><span class="sxs-lookup"><span data-stu-id="2c095-190">Step 2: Using the GUID to identify the hold</span></span>

<span data-ttu-id="2c095-p118">メールボックスに適用されている保留リストの guid を取得した後、次の手順として、その guid を使用して保留リストを識別します。次のセクションでは、ホールド GUID を使用して、保留 (およびその他の情報) の名前を識別する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2c095-p118">After you obtain the GUID for a hold that is applied to a mailbox, the next step is to use that GUID to identify the hold. The following sections show how to identify the name of the hold (and other information) by using the hold GUID.</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="2c095-193">電子情報開示の保持</span><span class="sxs-lookup"><span data-stu-id="2c095-193">eDiscovery holds</span></span>

<span data-ttu-id="2c095-p119">Security & コンプライアンスセンターの PowerShell で次のコマンドを実行して、メールボックスに適用されている電子情報開示ホールドを識別します。手順1で特定した電子情報開示の保留リストの GUID (unih プレフィックスを含まない) を使用します。最初のコマンドは、ホールドに関する情報を含む変数を作成します。この変数は、他のコマンドで使用されます。2番目のコマンドは、保留が関連付けられている電子情報開示ケースの名前を表示します。3番目のコマンドは、保留リストの名前と、保留が適用されるメールボックスのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="2c095-p119">Run the following commands in Security & Compliance Center PowerShell to identify an eDiscovery hold that's applied to the mailbox. Use the GUID (not including the UniH prefix) for the eDiscovery hold that you identified in Step 1. The first command creates a variable that contains information about the hold; this variable is used in the other commands. The second command displays the name of the eDiscovery case the hold is associated with. The third command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

<span data-ttu-id="2c095-199">security & コンプライアンスセンター powershell に接続するには、「 [connect to Office 365 Security & コンプライアンスセンター powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c095-199">To connect to Security & Compliance Center PowerShell, see  [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

### <a name="in-place-holds"></a><span data-ttu-id="2c095-200">インプレース ホールド</span><span class="sxs-lookup"><span data-stu-id="2c095-200">In-Place Holds</span></span>

<span data-ttu-id="2c095-p120">Exchange Online PowerShell で次のコマンドを実行して、メールボックスに適用されているインプレースホールドを識別します。手順1で特定したインプレースホールドの GUID を使用します。このコマンドは、保留リストの名前と、保留が適用されるメールボックスのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="2c095-p120">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's applied to the mailbox. Use the GUID for the In-Place Hold that you identified in Step 1. The command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
<span data-ttu-id="2c095-204">インプレース保持の GUID が`cld`プレフィックスで始まる場合は、前のコマンドを実行するときに必ずプレフィックスを含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="2c095-204">Note that if the GUID for the In-Place Hold starts with the `cld` prefix, be sure to include the prefix when running the previous command.</span></span>

### <a name="office-365-retention-policies"></a><span data-ttu-id="2c095-205">Office 365 のアイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="2c095-205">Office 365 retention policies</span></span>

<span data-ttu-id="2c095-p121">Security & コンプライアンスセンターの PowerShell で次のコマンドを実行して、メールボックスに適用されている Office 365 アイテム保持ポリシー (組織全体または特定の場所) を識別します。手順1で特定した GUID を使用します (この場合は、[説明]、[skp]、[grp prefix] または [action サフィックス] は含まれません)。</span><span class="sxs-lookup"><span data-stu-id="2c095-p121">Run the following command in Security & Compliance Center PowerShell to identity the Office 365 retention policy (organization-wide or specific location) that's applied to the mailbox. Use the GUID (not including the mbx, skp, or grp prefix or the action suffix) that you identified in Step 1.</span></span>

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a><span data-ttu-id="2c095-208">フォルダーまたはアイテムに保持ラベルが適用されているため、保留中のメールボックスを識別する</span><span class="sxs-lookup"><span data-stu-id="2c095-208">Identifying mailboxes on hold because a retention label has been applied to a folder or item</span></span>

<span data-ttu-id="2c095-p122">コンテンツを保持するように構成されている、またはメールボックス内の任意のフォルダーまたはアイテムにコンテンツを削除するように、ユーザーが保持ラベルを適用するときには、 *ComplianceTagHoldApplied* mailbox プロパティが**True**に設定されます。このような場合、メールボックスは、訴訟ホールドの対象として、または Office 365 アイテム保持ポリシーに割り当てられているかのように、保留中であると見なされます。*ComplianceTagHoldApplied*プロパティが**True**に設定されている場合は、次のような状況が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="2c095-p122">Whenever a user applies a retention label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**. When this happens, the mailbox is considered to be on hold, just as if it was placed on Litigation Hold or assigned to an Office 365 retention policy. When the *ComplianceTagHoldApplied* property is set to **True**, the following things may occur:</span></span>

- <span data-ttu-id="2c095-212">メールボックスまたはユーザーの Office 365 ユーザーアカウントが削除されると、メールボックスは[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)になります。</span><span class="sxs-lookup"><span data-stu-id="2c095-212">If the mailbox or the user's Office 365 user account is deleted, the mailbox becomes an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span>
- <span data-ttu-id="2c095-213">メールボックス (プライマリメールボックスまたはアーカイブメールボックスが有効になっている場合) を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2c095-213">You won't be able to disable the mailbox (either the primary mailbox or the archive mailbox, if it's enabled).</span></span>
- <span data-ttu-id="2c095-p123">メールボックス内のアイテムが予想よりも長く保持されている可能性があります。これは、メールボックスが保持されているため、完全に削除 (パージ) されるアイテムがないためです。</span><span class="sxs-lookup"><span data-stu-id="2c095-p123">Items in the mailbox may be retained longer than expected. This is because the mailbox is on hold and therefore no items will be permanently deleted (purged).</span></span>

<span data-ttu-id="2c095-216">*ComplianceTagHoldApplied*プロパティの値を表示するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c095-216">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="2c095-217">保持ラベルの詳細については、「 [Office 365 の保持ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c095-217">For more information about retention labels, see [Overview of Office 365 retention labels](labels.md).</span></span>

## <a name="managing-mailboxes-on-delay-hold"></a><span data-ttu-id="2c095-218">遅延保持時のメールボックスの管理</span><span class="sxs-lookup"><span data-stu-id="2c095-218">Managing mailboxes on delay hold</span></span>

<span data-ttu-id="2c095-p124">メールボックスから何らかの種類の保留が解除されると、 *DelayHoldApplied* mailbox プロパティの値は**True**に設定されます。これは、管理フォルダーアシスタントが次回メールボックスを処理し、ホールドが削除されたことを検出したときに発生します。これは*遅延ホールド*と呼ばれ、保留を実際に削除すると、メールボックスからデータが完全に削除 (パージ) されないようにするために30日間は遅延することになります。これにより、管理者は、保留が実際に削除された後に削除されるメールボックスアイテムを検索したり、回復したりする機会を得ることができます。メールボックスに遅延保持が設定されている場合でも、メールボックスが訴訟ホールドの対象であったかのように、無期限に保持されていると見なされます。30日後、遅延保持が有効期限切れになり、Office 365 は遅延保持を自動的に削除します ( *DelayHoldApplied*プロパティを**False**に設定する)。これにより、ホールドが実際に削除されます。*DelayHoldApplied*プロパティの値を**False**に設定すると、削除がマークされているアイテムは、次回メールボックスが管理フォルダーアシスタントによって処理されたときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="2c095-p124">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**. This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed. This is called a *delay hold* and means that the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted (purged) from the mailbox. This gives admins an opportunity to search for or recover mailbox items that will be purged after the hold is actually removed. When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold. After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold will be actually removed. After the *DelayHoldApplied* property to **False**, items that are marked for removal will be purged the next time the mailbox is processed by the Managed Folder Assistant.</span></span>

<span data-ttu-id="2c095-226">メールボックスの*DelayHoldApplied*プロパティの値を表示するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c095-226">To view the value for the *DelayHoldApplied* property for a mailbox, run the following command in Exchange Online PowerShell.</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="2c095-227">遅延が期限切れになるまでの遅延を削除するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c095-227">To remove the delay hold before it expires, you can run the following command in Exchange Online PowerShell:</span></span> 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="2c095-228">*RemoveDelayHoldApplied*パラメーターを使用するには、Exchange Online で法的情報保留の役割が割り当てられている必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2c095-228">Note that you must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter</span></span> 

<span data-ttu-id="2c095-229">非アクティブなメールボックスの遅延ホールドを削除するには、Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c095-229">To remove the delay hold on an inactive mailbox, run the following command in Exchange Online PowerShell:</span></span>

```
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

> [!TIP]
> <span data-ttu-id="2c095-p125">以前のコマンドで非アクティブなメールボックスを指定するには、その識別名または Exchange GUID 値を使用するのが最善の方法です。これらの値のいずれかを使用すると、間違ったメールボックスを誤って指定することがなくなります。</span><span class="sxs-lookup"><span data-stu-id="2c095-p125">The best way to specify an inactive mailbox in the previous command is to use its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="2c095-232">次の手順</span><span class="sxs-lookup"><span data-stu-id="2c095-232">Next steps</span></span>

<span data-ttu-id="2c095-p126">メールボックスに適用されている保留リストを識別した後、保留の期間の変更、一時的または完全に保持の削除、または Office 365 のアイテム保持ポリシーの場合は、ポリシーからの非アクティブなメールボックスを除外するなどのタスクを実行できます。保留に関連するタスクの実行の詳細については、以下のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c095-p126">After you identify the holds that are applied to a mailbox, you can perform tasks such as changing the duration of the hold, temporarily or permanently removing the hold, or in the case of Office 365 retention policies, excluding an inactive mailbox from the policy. For more information about performing tasks related to holds, see the one of the following topics:</span></span>

- <span data-ttu-id="2c095-p127">セキュリティ & コンプライアンスセンターの PowerShell で[ \<new-retentioncompliancepolicy-addexchangelocationexception user mailbox>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)コマンドを実行して、組織全体の Office 365 アイテム保持ポリシーからメールボックスを除外します。このコマンドは、 *exchangelocation*プロパティの値がと等しい`All`アイテム保持ポリシーにのみ使用できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2c095-p127">Run the [Set-RetentionCompliancePolicy -AddExchangeLocationException \<user mailbox>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps) command in Security & Compliance Center PowerShell to exclude a mailbox from an organization-wide Office 365 retention policy. Note that this command can only be used for retention policies where the value for the *ExchangeLocation* property equals `All`.</span></span>

- <span data-ttu-id="2c095-237">Exchange Online PowerShell で[プレフィックスまたは\<suffix> コマンドを指定せずに ExcludeFromOrgHolds hold GUID](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)を実行して、組織全体の Office 365 アイテム保持ポリシーから非アクティブなメールボックスを除外します。</span><span class="sxs-lookup"><span data-stu-id="2c095-237">Run the [Set-Mailbox -ExcludeFromOrgHolds \<hold GUID without prefix or suffix>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide Office 365 retention policy.</span></span>

- [<span data-ttu-id="2c095-238">Office 365 の非アクティブなメールボックスの保持期間を変更する</span><span class="sxs-lookup"><span data-stu-id="2c095-238">Change the hold duration for an inactive mailbox in Office 365</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="2c095-239">Office 365 で非アクティブなメールボックスを削除する</span><span class="sxs-lookup"><span data-stu-id="2c095-239">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

- <span data-ttu-id="2c095-240">[保留中のクラウド ベースのメールボックスの [回復可能なアイテム] フォルダーのアイテムを削除する](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)</span><span class="sxs-lookup"><span data-stu-id="2c095-240">[Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)</span></span>
