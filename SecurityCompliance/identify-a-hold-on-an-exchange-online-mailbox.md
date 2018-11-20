---
title: Exchange Online メールボックスに適用されている保留の種類を特定する方法
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: Office 365 のメールボックスに配置できる保留中のさまざまな種類を識別する方法を説明します。保留のこれらの種類には、証拠保全、電子的証拠開示の保留、および Office 365 のリテンション ・ ポリシーが含まれます。ユーザーが組織全体の保持ポリシーから除外されているかどうかを確認することも
ms.openlocfilehash: 1572b34d3f9abef2fb922fc9b01d1f5a27fcdf7b
ms.sourcegitcommit: e4ebef6aaf756eefb86c9f3a602cf75f5d344271
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026514"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a><span data-ttu-id="925a3-105">Exchange Online メールボックスに適用されている保留の種類を特定する方法</span><span class="sxs-lookup"><span data-stu-id="925a3-105">How to identify the type of hold placed on an Exchange Online mailbox</span></span>

<span data-ttu-id="925a3-106">この資料では、Office 365 のオンラインの Exchange メールボックスに配置する保留リストを識別する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="925a3-106">This article explains how to identify holds placed on Exchange Online mailboxes in Office 365.</span></span>

<span data-ttu-id="925a3-p102">Office 365 には、いくつかの組織が完全に削除されるからメールボックスの内容を妨げる可能性が方法が用意されています。これにより、コンプライアンスの常連を満たすためにコンテンツを保持する組織、法的または他の種類の調査の間。Office 365 の保存機能 (も呼び出されたを*保持している*) の一覧を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="925a3-p102">Office 365 offers a number of ways that your organization can prevent mailbox content from being permanently deleted. This allows your organization to retain content to meet compliance regulars or for the duration of legal or other types of investigations. Here's a list of the retention features (also called *holds*) in Office 365:</span></span>

- <span data-ttu-id="925a3-110">**証拠保全**の Exchange Online のユーザーのメールボックスに適用されているを保持します。</span><span class="sxs-lookup"><span data-stu-id="925a3-110">**Litigation Hold** - Holds that are applied to user mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="925a3-p103">**電子的証拠開示を保持**・ セキュリティとコンプライアンスの中心で、電子的証拠開示のケースに関連付けられているを保持します。電子的証拠開示の保留リストは、Office 365 のグループとマイクロソフトのチームのユーザーのメールボックスと対応するメールボックスに適用できます。</span><span class="sxs-lookup"><span data-stu-id="925a3-p103">**eDiscovery hold** - Holds that are associated with an eDiscovery case in the Security & Compliance Center. eDiscovery holds can be applied to user mailboxes, and on the corresponding mailbox for Office 365 Groups and Microsoft Teams.</span></span>

- <span data-ttu-id="925a3-113">**埋め込み保持**- 埋め込み電子的証拠開示と保持のツールを使用して Exchange 管理ツールで、ユーザーのメールボックスに適用される保留リストを中央揃え Exchange オンライン。</span><span class="sxs-lookup"><span data-stu-id="925a3-113">**In-Place Hold** - Holds that are applied to user mailboxes by using the In-Place eDiscovery & Hold tool in the Exchange admin center in Exchange Online.</span></span>

- <span data-ttu-id="925a3-p104">**保持ポリシーを office 365**の Office 365 のグループとマイクロソフトのチームの Exchange Online と対応するメールボックスのユーザーのメールボックス内のコンテンツを保持します。保持を作成するポリシーは、ユーザーのメールボックスに格納されている、ビジネス会話の Skype を保持します。</span><span class="sxs-lookup"><span data-stu-id="925a3-p104">**Office 365 retention policy** - Retains content in user mailboxes in Exchange Online and in the corresponding mailbox for Office 365 Groups and Microsoft Teams. You can create a retention policy retains Skype for Business Conversations, which are stored in user mailboxes.</span></span>

  <span data-ttu-id="925a3-116">メールボックスに割り当てることができる Office 365 の保持ポリシーの 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="925a3-116">There are two types of Office 365 retention policies that can be assigned to mailboxes.</span></span>

    - <span data-ttu-id="925a3-p105">**保存ポリシーの特定の場所**- これらは、特定のユーザーのコンテンツの場所に割り当てられているポリシーです。Exchange オンライン PowerShell で特定のメールボックスに割り当てられているリテンション ・ ポリシーに関する情報を取得するのに**Get メールボックス**コマンドレットを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="925a3-p105">**Specific location retention policies** - These are policies that are assigned to the content locations of specific users. You use the **Get-Mailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific mailboxes.</span></span>

    - <span data-ttu-id="925a3-p106">**組織全体の保存ポリシー** - これらは、組織内のすべてのコンテンツの場所に割り当てられているポリシーです。Exchange オンライン PowerShell で組織全体の保存ポリシーに関する情報を取得するのに**Get OrganizationConfig**コマンドレットを使用するとします。詳細については、 [Office 365 の概要の保存ポリシー](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)で「組織全体または特定の場所に保持ポリシーを適用する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="925a3-p106">**Organization-wide retention policies** - These are policies that are assigned to all content locations in your organization. You use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies. For more information, see the "Applying a retention policy to an entire organization or specific locations" section in [Overview of Office 365 retention policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).</span></span>

- <span data-ttu-id="925a3-p107">**保存期間のラベルを office 365**のユーザーは、フォルダー *、* または自分のメールボックスでは、保留リストにアイテムを (1 つのコンテンツを保持または保持し、コンテンツを削除し、構成されている)、Office 365 の保存のラベルを適用する場合は、場合と同様、メールボックスがメールボックスに配置されます。証拠保全に配置または Office 365 のリテンション ・ ポリシーに割り当てられています。詳細については、この資料の[特定のメールボックス フォルダーまたはアイテムに保存期間のラベルが適用されているためにの保持](#identifying-mailboxes-on-hold-because-a-label-has-been-applied-to-a-folder-or-item)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="925a3-p107">**Office 365 retention labels** - If a user applies an Office 365 retention label (one that's configured to retain content or retain and then delete content) to *any* folder or item in their mailbox, a hold is placed on the mailbox just as if the mailbox was placed on Litigation Hold or assigned to an Office 365 retention policy. For more information, see the [Identifying mailboxes on hold because a retention label has been applied to a folder or item](#identifying-mailboxes-on-hold-because-a-label-has-been-applied-to-a-folder-or-item) section in this article.</span></span>

<span data-ttu-id="925a3-p108">保留中のメールボックスを管理するには、保留中の変更、一時的または恒久的に、保留リストを削除するまたは Office 365 のリテンション ・ ポリシーからメールボックスを除外するなどのタスクを実行できるように、メールボックスに配置されている保留リストの種類を識別する必要があります。これらの場合、最初に、メールボックスに配置する保留リストの種類を識別します。複数の保留などさまざまな種類の保留の 1 つのメールボックスを配置するためすべての保留が削除または変更するそれらを保持する場合、メールボックスの配置を特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="925a3-p108">To manage mailboxes on hold, you may have to identify the type of hold that's placed on a mailbox so that you can perform tasks such as changing the hold duration, temporarily or permanently removing the hold, or excluding a mailbox from a Office 365 retention policy. In these cases, the first step is to identify the type of hold placed on the mailbox. And because multiple holds (and different types of holds) can be placed on a single mailbox, you'll have to identify all holds placed on a mailbox if you want to remove or change those holds.</span></span>

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a><span data-ttu-id="925a3-127">手順 1: は、メールボックスに保留リストの GUID を取得します。</span><span class="sxs-lookup"><span data-stu-id="925a3-127">Step 1: Obtaining the GUID for holds placed on a mailbox</span></span>

<span data-ttu-id="925a3-p109">メールボックスに配置されている保留リストの GUID を取得するのには、Exchange オンライン PowerShell では、次の 2 つのコマンドレットを実行できます。GUID を取得した後は、手順 2 で特定の保留リストを識別するのに使用します。訴訟を保持していない識別される GUID で注意してください。証拠保全が有効またはメールボックスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="925a3-p109">You can run the following two cmdlets in Exchange Online PowerShell to get the GUID of the holds that are placed on a mailbox. After you obtain a GUID, you use it to identify the specific hold in Step 2. Note that Litigation Holds are not identified by a GUID. Litigation Holds are either enabled or disabled for a mailbox.</span></span>

- <span data-ttu-id="925a3-p110">**Get メールボックス**- を保持するメールボックスの証拠保全が有効かどうかを判断するのには、電子的証拠開示の Guid を取得するのには、このコマンドレットを使用して、インプレースを保持している、Office 365 保存ポリシーのメールボックスに明示的に割り当てられています。このコマンドレットの出力は、メールボックスは、組織全体のリテンション ・ ポリシーから明示的に除外されているかどうかも表示されます。</span><span class="sxs-lookup"><span data-stu-id="925a3-p110">**Get-Mailbox** - Use this cmdlet to determine whether Litigation Hold is enabled for a mailbox and to get the GUIDs for eDiscovery holds, In-Place Holds, and Office 365 retention policies that are specifically assigned to a mailbox. The output of this cmdlet will also indicate if a mailbox has been explicitly excluded from an organization-wide retention policy.</span></span>

- <span data-ttu-id="925a3-134">**Get OrganizationConfig** - このコマンドレットを使用して、組織全体の保存ポリシーの Guid を取得します。</span><span class="sxs-lookup"><span data-stu-id="925a3-134">**Get-OrganizationConfig** - Use this cmdlet to get the GUIDs for organization-wide retention policies.</span></span>

<span data-ttu-id="925a3-135">オンライン PowerShell を Exchange に接続するには、 [Exchange オンライン PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="925a3-135">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

### <a name="get-mailbox"></a><span data-ttu-id="925a3-136">Get-Mailbox</span><span class="sxs-lookup"><span data-stu-id="925a3-136">Get-Mailbox</span></span>

<span data-ttu-id="925a3-137">保持し、Office 365 のメールボックスに適用されるリテンション ・ ポリシーに関する情報を取得するのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="925a3-137">Run the following command to get information about the holds and Office 365 retention policies applied to a mailbox.</span></span>

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="925a3-138">InPlaceHolds プロパティの値が多すぎますがあり、それらのすべてが表示されます、実行できます、`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`コマンドを別の行に各 GUID を表示します。</span><span class="sxs-lookup"><span data-stu-id="925a3-138">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="925a3-139">次の表では、 **Get メールボックス**コマンドレットを実行すると、 *InPlaceHolds*プロパティの値に基づいて保留の種類を識別する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="925a3-139">The following table describes how to identify different types of holds based on the values in the *InPlaceHolds* property when you run the **Get-Mailbox** cmdlet.</span></span>


|<span data-ttu-id="925a3-140">ホールドの種類</span><span class="sxs-lookup"><span data-stu-id="925a3-140">Hold type</span></span>  |<span data-ttu-id="925a3-141">値の例</span><span class="sxs-lookup"><span data-stu-id="925a3-141">Example value</span></span>  |<span data-ttu-id="925a3-142">保留リストを識別する方法</span><span class="sxs-lookup"><span data-stu-id="925a3-142">How to identify the hold</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="925a3-143">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="925a3-143">Litigation Hold</span></span>     |    `True`     |     <span data-ttu-id="925a3-144">証拠保全が有効になっているメールボックスの*LitigationHoldEnabled*プロパティに設定されている場合`True`。</span><span class="sxs-lookup"><span data-stu-id="925a3-144">Litigation Hold is enabled for a mailbox if the *LitigationHoldEnabled* property is set to `True`.</span></span>    |
|<span data-ttu-id="925a3-145">電子的証拠開示の保留中</span><span class="sxs-lookup"><span data-stu-id="925a3-145">eDiscovery hold</span></span>     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   <span data-ttu-id="925a3-p111">*InPlaceHolds プロパティ*には、セキュリティとコンプライアンスの中心で電子的証拠開示のサポート案件に関連付けられている保留状態の GUID が含まれています。これは、GUID が始まるためにの電子的証拠開示の保留リストを確認できます、 `UniH` (統一保持を示します) をプレフィックスします。</span><span class="sxs-lookup"><span data-stu-id="925a3-p111">The *InPlaceHolds property* contains the GUID of any hold associated with an eDiscovery case in the Security & Compliance Center. You can tell this is an eDiscovery hold because the GUID starts with the `UniH` prefix (which denotes a Unified Hold).</span></span>      |
|<span data-ttu-id="925a3-148">インプレース保持</span><span class="sxs-lookup"><span data-stu-id="925a3-148">In-Place Hold</span></span>     |     `c0ba3ce811b6432a8751430937152491` <br/> <span data-ttu-id="925a3-149">または</span><span class="sxs-lookup"><span data-stu-id="925a3-149">or</span></span> <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     <span data-ttu-id="925a3-p112">*InPlaceHolds*プロパティには、メールボックスに配置されている埋め込みの保持の GUID が含まれています。これは、埋め込みを保持するため、GUID は、プレフィックスを持つ起動しないか、または最初にことがわかります、`cld`のプレフィックスです。</span><span class="sxs-lookup"><span data-stu-id="925a3-p112">The *InPlaceHolds* property contains the GUID of the In-Place Hold that's placed on the mailbox. You can tell this is an In-Place Hold because the GUID either doesn't start with a prefix or it starts with the `cld` prefix.</span></span>     |
|<span data-ttu-id="925a3-152">Office 365 のメールボックスに適用される具体的にはリテンション ・ ポリシー</span><span class="sxs-lookup"><span data-stu-id="925a3-152">Office 365 retention policy specifically applied to the mailbox</span></span>     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> <span data-ttu-id="925a3-153">または</span><span class="sxs-lookup"><span data-stu-id="925a3-153">or</span></span> <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     <span data-ttu-id="925a3-p113">InPlaceHolds プロパティには、メールボックスに適用されている任意の特定の場所の保存ポリシーの Guid が含まれています。リテンション ・ ポリシーを識別するには、GUID が始まるため、`mbx`または`skp`のプレフィックスです。`skp`プレフィックスは、ユーザーのメールボックス内のビジネス会話を Skype にリテンション ・ ポリシーが適用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="925a3-p113">The InPlaceHolds property contains GUIDs of any specific location retention policy that's applied to the mailbox. You can identify retention policies because the GUID starts with the `mbx` or the `skp` prefix. The `skp` prefix indicates that the retention policy is applied to Skype for Business conversations in the user's mailbox.</span></span>    |
|<span data-ttu-id="925a3-157">組織の Office 365 のリテンション ・ ポリシーから除外</span><span class="sxs-lookup"><span data-stu-id="925a3-157">Excluded from an organization-wide Office 365 retention policy</span></span>     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     <span data-ttu-id="925a3-158">メールボックスが除外されているリテンション ・ ポリシーの GUID が InPlaceHolds のプロパティに表示され、によって識別されるメールボックスが組織全体にわたる Office 365 のリテンション ・ ポリシーから除外されている場合、`-mbx`のプレフィックスです。</span><span class="sxs-lookup"><span data-stu-id="925a3-158">If a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy the mailbox is excluded from is displayed in the InPlaceHolds property and is identified by the `-mbx` prefix.</span></span>    |

### <a name="get-organizationconfig"></a><span data-ttu-id="925a3-159">Get OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="925a3-159">Get-OrganizationConfig</span></span>
<span data-ttu-id="925a3-p114">**Get メールボックス**コマンドレットを実行するときに*InPlaceHolds*プロパティが空の場合もある可能性があります 1 つまたは複数のメールボックスに適用される組織の Office 365 リテンション ・ ポリシーです。次のコマンドを実行 Exchange オンライン組織全体の Office 365 の保存ポリシーの Guid の一覧を取得する PowerShell。</span><span class="sxs-lookup"><span data-stu-id="925a3-p114">If the *InPlaceHolds* property is empty when you run the **Get-Mailbox** cmdlet, there still may be one or more organization-wide Office 365 retention policies applied to the mailbox. Run the following command in Exchange Online PowerShell to get a list of GUIDs for organization-wide Office 365 retention policies.</span></span>

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> <span data-ttu-id="925a3-162">InPlaceHolds プロパティの値が多すぎますがあり、それらのすべてが表示されます、実行できます、`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`コマンドを別の行に各 GUID を表示します。</span><span class="sxs-lookup"><span data-stu-id="925a3-162">If there are too many values in the InPlaceHolds property and not all of them are displayed, you can run the `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command to display each GUID on a separate line.</span></span>

<span data-ttu-id="925a3-163">次の表では、組織全体を保持し、 **Get OrganizationConfig**コマンドレットを実行するときに、 *InPlaceHolds*プロパティに含まれている Guid に基づいて、それぞれの種類を識別する方法のさまざまな種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="925a3-163">The following table describes the different types of organization-wide holds and how to identify each type based on the GUIDs contained in *InPlaceHolds* property when you run the **Get-OrganizationConfig** cmdlet.</span></span>


|<span data-ttu-id="925a3-164">ホールドの種類</span><span class="sxs-lookup"><span data-stu-id="925a3-164">Hold type</span></span>  |<span data-ttu-id="925a3-165">値の例</span><span class="sxs-lookup"><span data-stu-id="925a3-165">Example value</span></span>  |<span data-ttu-id="925a3-166">説明</span><span class="sxs-lookup"><span data-stu-id="925a3-166">Description</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="925a3-167">Office 365 のリテンション ・ ポリシーでは、チャットを Exchange メールボックス、Exchange のパブリック フォルダー、およびチームに適用</span><span class="sxs-lookup"><span data-stu-id="925a3-167">Office 365 retention policies applied to Exchange mailboxes, Exchange public folders, and Teams chats</span></span>    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   <span data-ttu-id="925a3-p115">Exchange メールボックス、Exchange のパブリック フォルダーを組織全体の保存ポリシーが適用され、マイクロソフトのチームでの 1xN チャットで始まる Guid によって識別される、`mbx`のプレフィックスです。1xN チャットが個別のチャット参加者のメールボックスに格納されている注意してください。</span><span class="sxs-lookup"><span data-stu-id="925a3-p115">Organization-wide retention policies applied to Exchange mailboxes, Exchange public folders, and 1xN chats in Microsoft Teams are identified by GUIDs that start with the `mbx` prefix. Note that 1xN chats are stored in the mailbox of the individual chat participants.</span></span>      |
|<span data-ttu-id="925a3-170">Office 365 の保持ポリシーが Office 365 のグループやチームのチャネル メッセージに適用</span><span class="sxs-lookup"><span data-stu-id="925a3-170">Office 365 retention policy applied to Office 365 Groups and Teams channel messages</span></span>     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    <span data-ttu-id="925a3-p116">組織全体の保存ポリシーを Office 365 のグループとマイクロソフトのチームでのチャネルのメッセージに適用されるで始まる Guid によって識別される、`grp`のプレフィックスです。マイクロソフト チームに関連付けられているグループのメールボックスにチャネルのメッセージが格納されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="925a3-p116">Organization-wide retention policies applied to Office 365 groups and channel messages in Microsoft Teams are identified by GUIDs that start with the `grp` prefix. Note that channel messages are stored in the group mailbox that is associated with a Microsoft Team.</span></span>     |

<span data-ttu-id="925a3-173">詳細情報保存ポリシーがマイクロソフトのチームに適用される、チームの場所」セクション[の保存ポリシーの概要](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="925a3-173">For more information retention policies applied to Microsoft Teams, see the "Teams location" section [Overview of retention policies](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations).</span></span>

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a><span data-ttu-id="925a3-174">リテンション ・ ポリシーの InPlaceHolds の値の形式を理解します。</span><span class="sxs-lookup"><span data-stu-id="925a3-174">Understanding the format of the InPlaceHolds value for retention policies</span></span>

<span data-ttu-id="925a3-p117">だけでなく、mbx、skp、(グループ) を識別するプレフィックスとして Office 365 のリテンション ・ ポリシーの InPlaceHolds プロパティ内の項目、値には、ポリシーに構成されている保存操作の種類を識別するサフィックスも含まれています。たとえば、アクションのサフィックスは次の例で太字で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="925a3-p117">In addition to the prefix (mbx, skp, or grp) that identifies an item in the InPlaceHolds property as an Office 365 retention policy, the value also contains a suffix that identifies the type of retention action that's configured for the policy. For example, the action suffix is highlighted in bold type in the following examples:</span></span>

   <span data-ttu-id="925a3-177">`skp127d7cf1076947929bf136b7a2a8c36f`**: 1**</span><span class="sxs-lookup"><span data-stu-id="925a3-177">`skp127d7cf1076947929bf136b7a2a8c36f`**:1**</span></span>

   <span data-ttu-id="925a3-178">`mbx7cfb30345d454ac0a989ab3041051209`**: 2**</span><span class="sxs-lookup"><span data-stu-id="925a3-178">`mbx7cfb30345d454ac0a989ab3041051209`**:2**</span></span>

   <span data-ttu-id="925a3-179">`grp1a0a132ee8944501a4bb6a452ec31171`**: 3**</span><span class="sxs-lookup"><span data-stu-id="925a3-179">`grp1a0a132ee8944501a4bb6a452ec31171`**:3**</span></span>

<span data-ttu-id="925a3-180">次の表には、3 つの保存期間のアクションが定義されています。</span><span class="sxs-lookup"><span data-stu-id="925a3-180">The following table defines the three possible retention actions:</span></span>

|<span data-ttu-id="925a3-181">値</span><span class="sxs-lookup"><span data-stu-id="925a3-181">Value</span></span>  |<span data-ttu-id="925a3-182">説明</span><span class="sxs-lookup"><span data-stu-id="925a3-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="925a3-183">**1**</span><span class="sxs-lookup"><span data-stu-id="925a3-183">**1**</span></span>     | <span data-ttu-id="925a3-184">項目を削除するのには、リテンション ・ ポリシーが構成されていることを示します。ポリシーは、アイテムを保持しません。</span><span class="sxs-lookup"><span data-stu-id="925a3-184">Indicates the retention policy is configured to delete items; the policy doesn't retain items.</span></span>        |
|<span data-ttu-id="925a3-185">**2**</span><span class="sxs-lookup"><span data-stu-id="925a3-185">**2**</span></span>    |    <span data-ttu-id="925a3-186">項目を保持するためにリテンション ・ ポリシーが構成されていることを示します。ポリシーは、保存期間が終了した後、アイテムを削除しません。</span><span class="sxs-lookup"><span data-stu-id="925a3-186">Indicates the retention policy is configured to hold items; the policy doesn't delete items after the retention period expires.</span></span>     |
|<span data-ttu-id="925a3-187">**3**</span><span class="sxs-lookup"><span data-stu-id="925a3-187">**3**</span></span>     |   <span data-ttu-id="925a3-188">項目を保持し、保存期間が終了した後それらを削除する保持ポリシーが構成されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="925a3-188">Indicates the retention policy is configured to hold items and then delete them after the retention period expires.</span></span>      |

<span data-ttu-id="925a3-189">保存アクションの詳細については、[リテンション ・ ポリシーの](retention-policies.md#retaining-content-for-a-specific-period-of-time)概要」を参照する土留め内容] 特定の期間を参照してください。</span><span class="sxs-lookup"><span data-stu-id="925a3-189">For more information about retention actions, see the "Retaining content for a specific period of time" section in [Overview of retention policies](retention-policies.md#retaining-content-for-a-specific-period-of-time).</span></span>
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a><span data-ttu-id="925a3-190">手順 2: 保留リストを識別する GUID を使用してください。</span><span class="sxs-lookup"><span data-stu-id="925a3-190">Step 2: Using the GUID to identify the hold</span></span>

<span data-ttu-id="925a3-p118">メールボックスに適用される保留リストの GUID を取得したら、次に、その GUID を使用して保留リストを特定します。次のセクションでは、保留リストの GUID を使用して保留リスト (およびその他の情報) の名前を識別する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="925a3-p118">After you obtain the GUID for a hold that is applied to a mailbox, the next step is to use that GUID to identify the hold. The following sections show how to identify the name of the hold (and other information) by using the hold GUID.</span></span>

### <a name="ediscovery-holds"></a><span data-ttu-id="925a3-193">電子的証拠開示を保持します。</span><span class="sxs-lookup"><span data-stu-id="925a3-193">eDiscovery holds</span></span>

<span data-ttu-id="925a3-p119">メールボックスに適用されている電子的証拠開示の保留リストを識別するには、セキュリティとコンプライアンス センター PowerShell では、次のコマンドを実行します。(UniH プレフィックス) などではない GUID を使用して、電子的証拠開示には、手順 1 で識別することを保持します。最初のコマンドは、保留リストに関する情報を含む変数を作成します。この変数は、他のコマンドで使用されます。2 番目のコマンドは、保留リストに関連付けられて、電子的証拠開示大文字と小文字の名前を表示します。3 番目のコマンドは、保留リストの名前と保留リストに適用するメールボックスの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="925a3-p119">Run the following commands in Security & Compliance Center PowerShell to identify an eDiscovery hold that's applied to the mailbox. Use the GUID (not including the UniH prefix) for the eDiscovery hold that you identified in Step 1. The first command creates a variable that contains information about the hold; this variable is used in the other commands. The second command displays the name of the eDiscovery case the hold is associated with. The third command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

<span data-ttu-id="925a3-199">セキュリティとコンプライアンス センター PowerShell に接続するには、 [Office 365 のセキュリティとコンプライアンス センター PowerShell への接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="925a3-199">To connect to Security & Compliance Center PowerShell, see  [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

### <a name="in-place-holds"></a><span data-ttu-id="925a3-200">インプレース ホールド</span><span class="sxs-lookup"><span data-stu-id="925a3-200">In-Place Holds</span></span>

<span data-ttu-id="925a3-p120">メールボックスに適用されている埋め込みの保持を識別する、Exchange オンライン PowerShell では、次のコマンドを実行します。手順 1 で特定した埋め込み保持の GUID を使用します。コマンドには、保留リストの名前と保留リストに適用するメールボックスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="925a3-p120">Run the following command in Exchange Online PowerShell to identify the In-Place Hold that's applied to the mailbox. Use the GUID for the In-Place Hold that you identified in Step 1. The command displays the name of the hold and a list of the mailboxes the hold applies to.</span></span>

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
<span data-ttu-id="925a3-204">始まる埋め込み保持の場合はその GUID を控えておきます、`cld`プレフィックスを前のコマンドを実行するときにプレフィックスを含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="925a3-204">Note that if the GUID for the In-Place Hold starts with the `cld` prefix, be sure to include the prefix when running the previous command.</span></span>

### <a name="office-365-retention-policies"></a><span data-ttu-id="925a3-205">Office 365 のリテンション ・ ポリシー</span><span class="sxs-lookup"><span data-stu-id="925a3-205">Office 365 retention policies</span></span>

<span data-ttu-id="925a3-p121">次のコマンドを実行セキュリティとコンプライアンス センター PowerShell で id に、メールボックスに適用されている Office 365 の保持ポリシー (組織全体または特定の場所)。(Mbx、skp、またはグループのプレフィックスまたはサフィックスの操作) などではない、ステップ 1 で特定した GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="925a3-p121">Run the following command in Security & Compliance Center PowerShell to identity the Office 365 retention policy (organization-wide or specific location) that's applied to the mailbox. Use the GUID (not including the mbx, skp, or grp prefix or the action suffix) that you identified in Step 1.</span></span>

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a><span data-ttu-id="925a3-208">上の特定のメールボックス フォルダーまたはアイテムに保存期間のラベルが適用されているためにの保持します。</span><span class="sxs-lookup"><span data-stu-id="925a3-208">Identifying mailboxes on hold because a retention label has been applied to a folder or item</span></span>

<span data-ttu-id="925a3-p122">ユーザーがコンテンツを保持または保持のフォルダーまたはメールボックス内のアイテムのコンテンツを削除し、構成されている保存期間のラベルを適用するたびに、 *ComplianceTagHoldApplied*のメールボックスのプロパティが**True**に設定します。このような場合、メールボックスは、保留中の場合と同様に証拠保全がまたは Office 365 のリテンション ・ ポリシーに割り当てられていると見なされます。*ComplianceTagHoldApplied*プロパティを**True**に設定すると、次の項目が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="925a3-p122">Whenever a user applies a retention label that's configured to retain content or retain and then delete content to any folder or item in their mailbox, the *ComplianceTagHoldApplied* mailbox property is set to **True**. When this happens, the mailbox is considered to be on hold, just as if it was placed on Litigation Hold or assigned to an Office 365 retention policy. When the *ComplianceTagHoldApplied* property is set to **True**, the following things may occur:</span></span>

- <span data-ttu-id="925a3-212">メールボックスまたはユーザーの Office 365 のユーザー アカウントを削除すると、メールボックス、[メールボックスを非アクティブ](inactive-mailboxes-in-office-365.md)になります。</span><span class="sxs-lookup"><span data-stu-id="925a3-212">If the mailbox or the user's Office 365 user account is deleted, the mailbox becomes an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span>
- <span data-ttu-id="925a3-213">(プライマリ メールボックスまたはアーカイブ メールボックスを有効になっている場合) のメールボックスを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="925a3-213">You won't be able to disable the mailbox (either the primary mailbox or the archive mailbox, if it's enabled).</span></span>
- <span data-ttu-id="925a3-p123">メールボックス内のアイテムは、予想以上に長く保持することがあります。これは、保留中のメールボックスがあり、したがってアイテムを削除しないため (パージ) します。</span><span class="sxs-lookup"><span data-stu-id="925a3-p123">Items in the mailbox may be retained longer than expected. This is because the mailbox is on hold and therefore no items will be permanently deleted (purged).</span></span>

<span data-ttu-id="925a3-216">*ComplianceTagHoldApplied*プロパティの値を表示するには、Exchange オンライン PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="925a3-216">To view the value of the *ComplianceTagHoldApplied* property, run the following command in Exchange Online PowerShell:</span></span>

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

<span data-ttu-id="925a3-217">保存ラベルの詳細については、 [Office 365 の概要の保存期間のラベル](labels.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="925a3-217">For more information about retention labels, see [Overview of Office 365 retention labels](labels.md).</span></span>

## <a name="managing-mailboxes-on-delay-hold"></a><span data-ttu-id="925a3-218">遅延を管理するメールボックスを保持します。</span><span class="sxs-lookup"><span data-stu-id="925a3-218">Managing mailboxes on delay hold</span></span>

<span data-ttu-id="925a3-p124">保留中の任意の種類がメールボックスから削除されると、 *DelayHoldApplied*のメールボックスのプロパティの値が**True**に設定します。次に管理フォルダー アシスタントのメールボックスを処理し、保留リストが削除されたことを検出したとき発生します。これは、*遅延の保持*と呼ばれ、データが完全に削除されることを防止するのには 30 日間、保留中の実際の削除を延期することを意味メールボックスからには、(削除) します。これは、管理者を検索したり、保留リストが実際に削除された後にパージされるメールボックス アイテムをリカバリできます。遅延ホールドがメールボックスに配置されると、メールボックスと見なされます上にある、無制限の期間の保持と証拠保全上にメールボックスがあったかどうか。30 日間、遅延の保持期限が切れる、および Office 365 は、( *DelayHoldApplied*プロパティを**False**に設定) によって遅延保持を削除するのには自動的に試みます保留リストが実際に削除されるようにします。*DelayHoldApplied*プロパティを**False**には後の削除のマークされているアイテムが削除されます、メールボックスの管理フォルダー アシスタントによって処理される次の時間。</span><span class="sxs-lookup"><span data-stu-id="925a3-p124">After any type of hold is removed from a mailbox, the value of the *DelayHoldApplied* mailbox property is set to **True**. This occurs the next time the Managed Folder Assistant processes the mailbox and detects that a hold has been removed. This is called a *delay hold* and means that the actual removal of the hold is delayed for 30 days to prevent data from being permanently deleted (purged) from the mailbox. This gives admins an opportunity to search for or recover mailbox items that will be purged after the hold is actually removed. When a delay hold is placed on the mailbox, the mailbox is still considered to be on hold for an unlimited duration, as if the mailbox was on Litigation Hold. After 30 days, the delay hold expires, and Office 365 will automatically attempt to remove the delay hold (by setting the *DelayHoldApplied* property to **False**) so that the hold will be actually removed. After the *DelayHoldApplied* property to **False**, items that are marked for removal will be purged the next time the mailbox is processed by the Managed Folder Assistant.</span></span>

<span data-ttu-id="925a3-226">メールボックスの*DelayHoldApplied*プロパティの値を表示するには、Exchange オンライン PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="925a3-226">To view the value for the *DelayHoldApplied* property for a mailbox, run the following command in Exchange Online PowerShell.</span></span>

```
Get-Mailbox <username> | FL DelayHoldApplied
```

<span data-ttu-id="925a3-227">期限が切れる前に、遅延の保留リストを削除するには、Exchange オンライン PowerShell で次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="925a3-227">To remove the delay hold before it expires, you can run the following command in Exchange Online PowerShell:</span></span> 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
<span data-ttu-id="925a3-228">する必要があります法的保持義務の役割を割り当てる Exchange オンライン、 *RemoveDelayHoldApplied*パラメーターを使用するに注意してください。</span><span class="sxs-lookup"><span data-stu-id="925a3-228">Note that you must be assigned the Legal Hold role in Exchange Online to use the *RemoveDelayHoldApplied* parameter</span></span> 

<span data-ttu-id="925a3-229">遅延の保持を非アクティブなメールボックスを削除するには、Exchange オンライン PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="925a3-229">To remove the delay hold on an inactive mailbox, run the following command in Exchange Online PowerShell:</span></span>

```
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

> [!TIP]
> <span data-ttu-id="925a3-p125">前のコマンドで、アクティブでないメールボックスを指定する最良の方法では、その識別名、または Exchange の GUID 値を使用します。これらの値のいずれかの方法とは、誤って正しくないメールボックスを指定することを防止できます。</span><span class="sxs-lookup"><span data-stu-id="925a3-p125">The best way to specify an inactive mailbox in the previous command is to use its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="925a3-232">次の手順</span><span class="sxs-lookup"><span data-stu-id="925a3-232">Next steps</span></span>

<span data-ttu-id="925a3-p126">メールボックスに適用される保留リストを識別した後、非アクティブなメールボックスのポリシーから除外、一時的に、保留リストの期間の変更など、保留リストを完全に削除、または Office 365 のリテンション ・ ポリシーの場合にタスクを実行できます。保留リストに関連するタスクを実行する方法の詳細については、次のトピックのいずれかを参照してください。</span><span class="sxs-lookup"><span data-stu-id="925a3-p126">After you identify the holds that are applied to a mailbox, you can perform tasks such as changing the duration of the hold, temporarily or permanently removing the hold, or in the case of Office 365 retention policies, excluding an inactive mailbox from the policy. For more information about performing tasks related to holds, see the one of the following topics:</span></span>

- <span data-ttu-id="925a3-p127">実行、[セット RetentionCompliancePolicy AddExchangeLocationException\<ユーザー メールボックス >](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)で組織全体にわたる Office 365 のリテンション ・ ポリシーからメールボックスを除外するには、セキュリティとコンプライアンス センター PowerShell コマンドです。このコマンドのみ使えること・ リテンション ・ ポリシーの*ExchangeLocation*プロパティの値に注意してください`All`。</span><span class="sxs-lookup"><span data-stu-id="925a3-p127">Run the [Set-RetentionCompliancePolicy -AddExchangeLocationException \<user mailbox>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps) command in Security & Compliance Center PowerShell to exclude a mailbox from an organization-wide Office 365 retention policy. Note that this command can only be used for retention policies where the value for the *ExchangeLocation* property equals `All`.</span></span>

- <span data-ttu-id="925a3-237">実行、[セット-メールボックス ExcludeFromOrgHolds\<プレフィックスまたはサフィックスのない GUID を保持する >](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)組織全体にわたる Office 365 のリテンション ・ ポリシーからがアクティブでないメールボックスを除外するのには、Exchange オンライン PowerShell のコマンドです。</span><span class="sxs-lookup"><span data-stu-id="925a3-237">Run the [Set-Mailbox -ExcludeFromOrgHolds \<hold GUID without prefix or suffix>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps) command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide Office 365 retention policy.</span></span>

- [<span data-ttu-id="925a3-238">Office 365 での非アクティブなメールボックスの保持期間を変更します。</span><span class="sxs-lookup"><span data-stu-id="925a3-238">Change the hold duration for an inactive mailbox in Office 365</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="925a3-239">Office 365 で、非アクティブなメールボックスを削除します。</span><span class="sxs-lookup"><span data-stu-id="925a3-239">Delete an inactive mailbox in Office 365</span></span>](delete-an-inactive-mailbox.md)

- <span data-ttu-id="925a3-240">[保留中のクラウド ベースのメールボックスの [回復可能なアイテム] フォルダーのアイテムを削除する](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)</span><span class="sxs-lookup"><span data-stu-id="925a3-240">[Delete items in the Recoverable Items folder of cloud-based mailboxes on hold](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)</span></span>
