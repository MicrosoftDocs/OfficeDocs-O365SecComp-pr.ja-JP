---
title: Office 365 での非アクティブなメールボックスの保持期間を変更します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: Office 365 のメールボックスを無効になりましたが後、は、保留中または非アクティブなメールボックスに割り当てられている Office 365 の保持ポリシーの期間を変更できます。保留期間は、[回復可能なアイテムのフォルダーが保持されているどのくらいの時間の項目を定義します。
ms.openlocfilehash: 22bd9f9294b625a38d243f6235097d1aee437121
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532185"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="0cf91-104">Office 365 での非アクティブなメールボックスの保持期間を変更します。</span><span class="sxs-lookup"><span data-stu-id="0cf91-104">Change the hold duration for an inactive mailbox in Office 365</span></span>

<span data-ttu-id="0cf91-p102">非アクティブなメールボックスは、退職して組織を離れた元従業員の電子メールを保持するために使用します。訴訟ホールド、インプレース ホールド、Office 365 アイテム保持ポリシー、または電子情報開示ケースと関連付けられているホールドがメールボックスに設定され、それに対応する Office 365 ユーザー アカウントが削除されると、そのメールボックスは非アクティブになります。非アクティブなメールボックスのコンテンツは、非アクティブになる前にメールボックスに設定された保持期間の間、保持されます。保持期間は、[回復可能なアイテム] フォルダー内のアイテムを保持する期間を定義します。[回復可能なアイテム] フォルダー内のアイテムの保持期間が過ぎると、アイテムは非アクティブなメールボックスから完全に削除 (消去) されます。メールボックスが非アクティブになった後でも、非アクティブなメールボックスに割り当てられているホールドや Office 365 アイテム保持ポリシーの期間を変更できます。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p102">An inactive mailbox is used to retain a former employee's email after he or she leaves your organization. A mailbox becomes inactive when a Litigation Hold, an In-Place Hold, an Office 365 retention policy, or a hold that's associated with an eDiscovery case is placed on the mailbox, and the corresponding Office 365 user account is deleted. The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. The hold duration defines how long items in the Recoverable Items folder are held. When the hold duration expires for an item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox. After a mailbox is made inactive, you can change the duration of the hold or Office 365 retention policy assigned to the inactive mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0cf91-p103">2017 年 7 月 1 日に終了する予定だった、メールボックスを非アクティブにするために新しいインプレース ホールドを作成できる期間を延長しました。しかし、今年の終わりごろまたは来年の初めごろには、新しいインプレース ホールドを Exchange Online 内で作成することはできなくなります。その時点で、非アクティブのメールボックスを作成するために使用できるのは、訴訟ホールドと Office 365 アイテム保持ポリシーだけになります。ただし、インプレース ホールドにある既存の非アクティブなメールボックスは引き続きサポートされます。また、引き続き非アクティブなメールボックスのインプレース ホールドを管理することができます。これには、インプレース ホールドの期間を変更すること、およびそのインプレース ホールドを削除することによって非アクティブなメールボックスを完全に削除することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p103">We've postponed the July 1, 2017 deadline for creating new In-Place Holds to make a mailbox inactive. But later this year or early next year, you won't be able to create new In-Place Holds in Exchange Online. At that time, only Litigation Holds and Office 365 retention policies can be used to create an inactive mailbox. However, existing inactive mailboxes that are on In-Place Hold will still be supported, and you can continue to manage the In-Place Holds on inactive mailboxes. This includes changing the duration of an In-Place Hold and permanently deleting an inactive mailbox by removing the In-Place Hold.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="0cf91-116">はじめに</span><span class="sxs-lookup"><span data-stu-id="0cf91-116">Before you begin</span></span>

- <span data-ttu-id="0cf91-p104">証拠保全を非アクティブなメールボックスの保持期間を変更するのには Exchange のオンライン PowerShell を使用する必要があります。Exchange 管理センター (EAC) を使用することはできません。ですが、埋め込みの保持の保持期間を変更するのには Exchange オンライン PowerShell または、EAC を使用することができます。Office 365 のセキュリティを使用することができます&amp;センターのコンプライアンスやセキュリティ&amp;コンプライアンス センターの PowerShell Office 365 の保持ポリシーの保持期間を変更します。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p104">You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox. You can't use the Exchange admin center (EAC). But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold. You can use the Office 365 Security &amp; Compliance Center or the Security &amp; Compliance Center PowerShell to change the hold duration for an Office 365 retention policy.</span></span>
    
- <span data-ttu-id="0cf91-121">Exchange オンライン PowerShell またはセキュリティに接続する&amp;コンプライアンス センター PowerShell、次のトピックのいずれかを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cf91-121">To connect to Exchange Online PowerShell or Security &amp; Compliance Center PowerShell, see one of the following topics:</span></span>
    
  - [<span data-ttu-id="0cf91-122">Exchange Online PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="0cf91-122">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [<span data-ttu-id="0cf91-123">Office 365 のセキュリティへの接続&amp;コンプライアンス センター PowerShell</span><span class="sxs-lookup"><span data-stu-id="0cf91-123">Connect to Office 365 Security &amp; Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
- <span data-ttu-id="0cf91-p105">電子情報開示ケースに関連付けられているホールドは無限ホールド、つまり変更できるホールド期間がない点にご注意ください。アイテムは、ホールドが削除されて非アクティブなメールボックスが削除されるまで無限に保持されます。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p105">Note that holds associated with eDiscovery cases are infinite holds, which means there is no hold duration that can be changed. Items are held forever or until the hold is removed and the inactive mailbox is deleted.</span></span>
    
- <span data-ttu-id="0cf91-126">非アクティブなメールボックスの詳細については、 [Office 365 でアクティブでないメールボックス](inactive-mailboxes-in-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cf91-126">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="0cf91-127">手順 1: 非アクティブなメールボックスに設定されているホールドを特定する</span><span class="sxs-lookup"><span data-stu-id="0cf91-127">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="0cf91-128">異なる種類のホールドや 1 つ以上の Office 365 アイテム保持ポリシーが非アクティブなメールボックスにある可能性があるため、最初の手順では、非アクティブなメールボックスにあるホールドを特定します。</span><span class="sxs-lookup"><span data-stu-id="0cf91-128">Because different types of holds or one or more Office 365 retention policies might be placed on an inactive mailbox, the first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="0cf91-129">Exchange Online PowerShell で次のコマンドを実行して、組織内のすべての非アクティブなメールボックスのホールドの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="0cf91-129">Run the following command in Exchange Online PowerShell to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
<span data-ttu-id="0cf91-p106">**True**の場合、 **LitigationHoldEnabled**プロパティの値は、証拠保全が非アクティブなメールボックスであることを示します。埋め込みを保持する、電子的証拠開示、または Office 365 のリテンション ・ ポリシーがアクティブでないメールボックスに配置されます、 **InPlaceHolds**プロパティの値として保持、または保持ポリシーの GUID が表示されます。たとえば、次に示します 5 の非アクティブなメールボックスの結果。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p106">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold, eDiscovery hold, or Office 365 retention policy is placed on an inactive mailbox, a GUID for the hold or retention policy is displayed as the value for the **InPlaceHolds** property. For example, the following shows results for 5 inactive mailboxes.</span></span> 
  
||
|:-----|
|
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```
   
<span data-ttu-id="0cf91-133">次の表は、各メールボックスを非アクティブにするのに使用された 5 つの異なる種類のホールドを示しています。</span><span class="sxs-lookup"><span data-stu-id="0cf91-133">The following table identifies the five different hold types that were used to make each mailbox inactive.</span></span>
  
|<span data-ttu-id="0cf91-134">**非アクティブなメールボックス**</span><span class="sxs-lookup"><span data-stu-id="0cf91-134">**Inactive mailbox**</span></span>|<span data-ttu-id="0cf91-135">**ホールドの種類**</span><span class="sxs-lookup"><span data-stu-id="0cf91-135">**Hold type**</span></span>|<span data-ttu-id="0cf91-136">**非アクティブなメールボックスのホールドを識別する方法**</span><span class="sxs-lookup"><span data-stu-id="0cf91-136">**How to identify the hold on the inactive mailbox**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0cf91-137">Ann Beebe</span><span class="sxs-lookup"><span data-stu-id="0cf91-137">Ann Beebe</span></span>  <br/> |<span data-ttu-id="0cf91-138">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="0cf91-138">Litigation Hold</span></span>  <br/> |<span data-ttu-id="0cf91-139">*LitigationHoldEnabled*  プロパティが  `True` に設定されています。</span><span class="sxs-lookup"><span data-stu-id="0cf91-139">The  *LitigationHoldEnabled*  property is set to  `True`.</span></span>  <br/> |
|<span data-ttu-id="0cf91-140">Pilar Pinilla</span><span class="sxs-lookup"><span data-stu-id="0cf91-140">Pilar Pinilla</span></span>  <br/> |<span data-ttu-id="0cf91-141">インプレース ホールド</span><span class="sxs-lookup"><span data-stu-id="0cf91-141">In-Place Hold</span></span>  <br/> |<span data-ttu-id="0cf91-p107">*InPlaceHolds*  プロパティには非アクティブなメールボックスに設定されたインプレース ホールドの GUID が含まれています。ID がプレフィックスから始まっていないため、これはインプレース ホールドだとわかります。  </span><span class="sxs-lookup"><span data-stu-id="0cf91-p107">The  *InPlaceHolds*  property contains the GUID of the In-Place Hold that's placed on the inactive mailbox. You can tell this is an In-Place Hold because the ID doesn't start with a prefix.  </span></span><br/> <span data-ttu-id="0cf91-144">Exchange Online PowerShell で  \`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID></span><span class="sxs-lookup"><span data-stu-id="0cf91-144">You can use the  \`Get-MailboxSearch -InPlaceHoldIdentity <hold GUID></span></span> | <span data-ttu-id="0cf91-145">FL\` コマンドを使用して、非アクティブのメールボックスのインプレース ホールドについての情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="0cf91-145">FL\` command in Exchange Online PowerShell to get information about the In-Place Hold on the inactive mailbox.</span></span>  <br/> |
|<span data-ttu-id="0cf91-146">Mario Necaise</span><span class="sxs-lookup"><span data-stu-id="0cf91-146">Mario Necaise</span></span>  <br/> |<span data-ttu-id="0cf91-147">セキュリティで Office 365 保持ポリシーを組織全体にわたる&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="0cf91-147">Organization-wide Office 365 retention policy in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="0cf91-p108">*InPlaceHolds*プロパティは空です。これは、非アクティブなメールボックスを 1 つまたは複数の組織全体または (全体で Exchange) Office 365 の保存のポリシーを適用することを示します。この例では、実行することができます、' Get OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="0cf91-p108">The  *InPlaceHolds*  property is empty. This indicates that one or more organization-wide or (Exchange-wide) Office 365 retention policy is applied to the inactive mailbox. In this case, you can run the  \`Get-OrganizationConfig</span></span> | <span data-ttu-id="0cf91-151">選択オブジェクト-ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> <br/>To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.  <br/><br/> `Get RetentionCompliancePolicy<retention policy GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="0cf91-151">Select-Object -ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> <br/>To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix></span></span> | <span data-ttu-id="0cf91-152">FL 名 '</span><span class="sxs-lookup"><span data-stu-id="0cf91-152">FL Name\`</span></span><br/><br/>
|<span data-ttu-id="0cf91-153">Carol Olson</span><span class="sxs-lookup"><span data-stu-id="0cf91-153">Carol Olson</span></span>  <br/> |<span data-ttu-id="0cf91-154">セキュリティの保持ポリシーを office 365&amp;コンプライアンス センターは、特定のメールボックスに適用</span><span class="sxs-lookup"><span data-stu-id="0cf91-154">Office 365 retention policy in the Security &amp; Compliance Center applied to specific mailboxes</span></span>  <br/> |<span data-ttu-id="0cf91-p109">*InPlaceHolds*  プロパティに、非アクティブなメールボックスに適用されている Office 365 アイテム保持ポリシーの GUID が含まれています。GUID が  `mbx` プレフィックスで始まっているため、これは特定のメールボックスに適用されたアイテム保持ポリシーであることがわかります。非アクティブなメールボックスに適用されている保持ポリシーの GUID が  `skp` プレフィックスで始まる場合、保持ポリシーが Skype for Business の会話に適用されることを示していることに注意してください。  </span><span class="sxs-lookup"><span data-stu-id="0cf91-p109">The  *InPlaceHolds*  property contains the GUID of the Office 365 retention policy that's applied to the inactive mailbox. You can tell this is a retention policy that applied to specific mailboxes because the GUID starts with the  `mbx` prefix. Note that if GUID of the retention policy applied to the inactive mailbox started with the  `skp` prefix, that would indicate that the retention policy is applied to Skype for Business conversations.  </span></span><br/><br/> <span data-ttu-id="0cf91-158">セキュリティの次のコマンドを実行する非アクティブなメールボックスに適用されている保持ポリシーを Office 365 の id、&amp;コンプライアンス センター PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0cf91-158">To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.</span></span><br/><br/> <span data-ttu-id="0cf91-159">' Get RetentionCompliancePolicy<retention policy GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="0cf91-159">\`Get-RetentionCompliancePolicy <retention policy GUID without prefix></span></span> | <span data-ttu-id="0cf91-160">FL 名` <br/><br/>Be sure to remove the  `mbx` or  `skp' このコマンドを実行するときにプレフィックスです。</span><span class="sxs-lookup"><span data-stu-id="0cf91-160">FL Name` <br/><br/>Be sure to remove the  `mbx` or  `skp\` prefix when you run this command.</span></span>  <br/> |
|<span data-ttu-id="0cf91-161">Abraham McMahon</span><span class="sxs-lookup"><span data-stu-id="0cf91-161">Abraham McMahon</span></span>  <br/> |<span data-ttu-id="0cf91-162">電子的証拠開示の場合は、セキュリティの保持&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="0cf91-162">eDiscovery case hold in the Security &amp; Compliance Center</span></span>  <br/> |<span data-ttu-id="0cf91-p110">*InPlaceHolds*  プロパティに、非アクティブなメールボックスに設定されている電子情報開示ケース ホールドの GUID が含まれています。GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。  </span><span class="sxs-lookup"><span data-stu-id="0cf91-p110">The  *InPlaceHolds*  property contains the GUID of the eDiscovery case hold that's placed on the inactive mailbox. You can tell this is an eDiscovery case hold because the GUID starts with the  `UniH` prefix.  </span></span><br/> <span data-ttu-id="0cf91-p111">使用することができます、`Get-CaseHoldPolicy`セキュリティのコマンドレット&amp;コンプライアンス センターの PowerShell に非アクティブなメールボックスの保留リストが関連付けられている場合は電子的証拠開示に関する情報を取得します。コマンドを実行することができますたとえば、' Get CaseHoldPolicy<hold GUID without prefix></span><span class="sxs-lookup"><span data-stu-id="0cf91-p111">You can use the  `Get-CaseHoldPolicy` cmdlet in Security &amp; Compliance Center PowerShell to get information about the eDiscovery case that the hold on the inactive mailbox is associated with. For example, you can run the command  \`Get-CaseHoldPolicy <hold GUID without prefix></span></span> | <span data-ttu-id="0cf91-167">FL 名` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.  <br/><br/> `$CaseHold = Get CaseHoldPolicy <hold GUID without prefix> `<br/><br/> `Get ComplianceCase $CaseHold.CaseId</span><span class="sxs-lookup"><span data-stu-id="0cf91-167">FL Name` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId</span></span> | <span data-ttu-id="0cf91-168">FL 名 '</span><span class="sxs-lookup"><span data-stu-id="0cf91-168">FL Name\`</span></span><br/><br/><br/> <span data-ttu-id="0cf91-p112">**注:** 非アクティブなメールボックスを保持している電子的証拠開示を使用してお勧めしません。電子的証拠開示の場合は、法的な問題に関連する場合は、特定の期限付きにするためです。いくつかの時点では、訴訟事件を終了可能性がありますが、サポート案件に関連付けられている保留リストを削除して電子的証拠開示の場合を閉じる (または削除) します。実際には、非アクティブなメールボックスに配置されている保留リストは、電子的証拠開示のサポート案件に関連付けられていると保留を解除、または電子的証拠開示のケースが閉じられるか、削除、非アクティブなメールボックス完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p112">**Note:** We don't recommend using eDiscovery holds for inactive mailboxes. That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. At some point, a legal case will probably end and the holds associated with the case will be removed and the eDiscovery case will be closed (or deleted). In fact, if a hold that's placed on an inactive mailbox is associated with an eDiscovery case, and the hold is released or the eDiscovery case is closed or deleted, the inactive mailbox will be permanently deleted.</span></span> 

<span data-ttu-id="0cf91-173">Office 365 のリテンション ・ ポリシーの詳細については、[保存ポリシーの概要](retention-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cf91-173">For more information about Office 365 retention policies, see [Overview of retention policies](retention-policies.md).</span></span>
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a><span data-ttu-id="0cf91-174">手順 2: 非アクティブなメールボックスの保持期間を変更する</span><span class="sxs-lookup"><span data-stu-id="0cf91-174">Step 2: Change the hold duration for an inactive mailbox</span></span>

<span data-ttu-id="0cf91-175">非アクティブなメールボックスに設定されているホールドの種類 (および複数のホールドがあるかどうか) を特定したら、次は、保持期間を変更します。</span><span class="sxs-lookup"><span data-stu-id="0cf91-175">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to change the duration for the hold.</span></span> 
  
### <a name="change-the-duration-for-a-litigation-hold"></a><span data-ttu-id="0cf91-176">訴訟ホールドの期間を変更する</span><span class="sxs-lookup"><span data-stu-id="0cf91-176">Change the duration for a Litigation Hold</span></span>

<span data-ttu-id="0cf91-p113">Exchange Online PowerShell を使用して、非アクティブなメールボックスに配置されている訴訟ホールドの保持期間を変更する方法を次に示します。EAC を使用することはできません。保持期間を変更するには、次のコマンドを実行します。この例では、保持期間を無期限に変更しています。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p113">Here's how to use Exchange Online PowerShell to change the hold duration for a Litigation Hold that is placed on an inactive mailbox. You can't use the EAC. Run the following command to change the hold duration. In this example, the hold duration is changed to an unlimited period of time.</span></span>
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

<span data-ttu-id="0cf91-181">結果として、非アクティブなメールボックス内のアイテムは、無期限に、あるいは、ホールドが削除されるか保持期間が別の値に変更されるまで、保持されます。</span><span class="sxs-lookup"><span data-stu-id="0cf91-181">The result is that items in the inactive mailbox are retained indefinitely or until the hold is removed or the hold duration is changed to a different value.</span></span>
  
> [!TIP]
> <span data-ttu-id="0cf91-p114">非アクティブなメールボックスを特定する最もよい方法は、 **Distinguished Name** または **Exchange GUID** の値を使用することです。これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを避けられます。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p114">The best way to identify an inactive mailbox is by using its **Distinguished Name** or **Exchange GUID** value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="change-the-duration-for-an-in-place-hold"></a><span data-ttu-id="0cf91-184">インプレース ホールドの期間を変更する</span><span class="sxs-lookup"><span data-stu-id="0cf91-184">Change the duration for an In-Place Hold</span></span>

 <span data-ttu-id="0cf91-185">インプレース ホールドの保持期間の変更は、EAC か Exchange Online PowerShell を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="0cf91-185">You can use the EAC or Exchange Online PowerShell to change the hold duration for an In-Place Hold.</span></span> 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a><span data-ttu-id="0cf91-186">EAC を使用して保持期間を変更する</span><span class="sxs-lookup"><span data-stu-id="0cf91-186">Use the EAC to change the hold duration</span></span>

1. <span data-ttu-id="0cf91-p115">変更する埋め込みのままの名前がわかっている場合は、次の手順に進みます。それ以外の場合、非アクティブなメールボックスに配置されている埋め込みのままの名前を取得するのには次のコマンドを実行します。埋め込み保持[手順 1](#step-1-identify-the-holds-on-an-inactive-mailbox)で取得した GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p115">If you know the name of the In-Place Hold that you want to change, go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="0cf91-190">**コンプライアンス管理**には、EAC で\>**インプレース電子情報開示&amp;を保持**。</span><span class="sxs-lookup"><span data-stu-id="0cf91-190">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="0cf91-191">埋め込みの保留、変更する] を選択し、[**編集**] をクリックして![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="0cf91-191">Select the In-Place Hold you want to change, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="0cf91-192">**インプレース電子情報開示&amp;を保持**プロパティ] ページで、**場所に保持**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0cf91-192">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**.</span></span> 
    
5. <span data-ttu-id="0cf91-193">現在の保持期間に基づいて、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="0cf91-193">Do one of the following based on the current hold duration:</span></span>
    
1. <span data-ttu-id="0cf91-194">無制限にアイテムを保持する場合は、 **[無期限に保持]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0cf91-194">Click **Hold indefinitely** to hold items for an unlimited period of time.</span></span> 
    
2. <span data-ttu-id="0cf91-p116">特定の期間のアイテムを保持するために **、受信した日を基準にして項目を保持する日数を指定してください**] をクリックします。項目を保持する日数を入力します。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p116">Click **Specify number of days to hold items relative to their received date** to hold items for a specific period. Type the number of days that you want to hold items for.</span></span> 
    
    ![インプレース ホールド期間の変更に関するスクリーン ショット](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. <span data-ttu-id="0cf91-198">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0cf91-198">Click **Save**.</span></span>
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a><span data-ttu-id="0cf91-199">Exchange Online PowerShell を使用して保持期間を変更する</span><span class="sxs-lookup"><span data-stu-id="0cf91-199">Use Exchange Online PowerShell to change the hold duration</span></span>

1. <span data-ttu-id="0cf91-p117">変更する埋め込みのままの名前がわかっている場合は、次の手順に進みます。それ以外の場合、非アクティブなメールボックスに配置されている埋め込みのままの名前を取得するのには次のコマンドを実行します。埋め込み保持[手順 1](#step-1-identify-the-holds-on-an-inactive-mailbox)で取得した GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p117">If you know the name of the In-Place Hold that you want to change, go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. <span data-ttu-id="0cf91-p118">保持期間を変更するには、次のコマンドを実行します。この例では、ホールド期間を 2,555 日 (約 7 年間) に変更します。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p118">Run the following command to change the hold duration. In this example, the hold duration is changed to 2,555 days (approximately 7 years).</span></span> 
    
    ```
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     <span data-ttu-id="0cf91-205">保持期間を無制限の期間に変更するには、 _-ItemHoldPeriod unlimited_ を使用します。</span><span class="sxs-lookup"><span data-stu-id="0cf91-205">To change the hold duration to an unlimited period of time, use  _-ItemHoldPeriod unlimited_.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="0cf91-206">詳細情報</span><span class="sxs-lookup"><span data-stu-id="0cf91-206">More information</span></span>

- <span data-ttu-id="0cf91-p119">**非アクティブなメールボックス内のアイテムの保持期間はどのように計算されますか。** 保持期間は、メールボックス アイテムを受信または作成した最初の日付から計算されます。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p119">**How is the hold duration calculated for an item in an inactive mailbox?** The duration is calculated from the original date a mailbox item was received or created.</span></span> 
    
- <span data-ttu-id="0cf91-p120">**保持期間を過ぎるとどうなりますか。**[回復可能なアイテム] フォルダー内のアイテムの保持期間を過ぎると、アイテムは非アクティブなメールボックスから完全に削除 (消去) されます。非アクティブなメールボックスに設定されたホールドの保持期間が指定されていない場合、(非アクティブなメールボックスの保持期間が変更されない限り) [回復可能なアイテム] フォルダー内のアイテムは削除されません。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p120">**What happens when the hold duration expires?** When the hold duration expires for a mailbox item in the Recoverable Items folder, the item is permanently deleted (purged) from the inactive mailbox. If there is no duration specified for the hold placed on the inactive mailbox, items in the Recoverable Items folder are never purged (unless the hold duration for the inactive mailbox is changed).</span></span> 
    
- <span data-ttu-id="0cf91-p121">**Exchange アイテム保持ポリシーの処理は、非アクティブなメールボックスに対しても継続されますか。** メールボックスが非アクティブになったときにメールボックスに Exchange アイテム保持ポリシー (Exchange Online の機能であるメッセージング レコード管理 (MRM)) が適用されていた場合は、その非アクティブなメールボックスに対して削除ポリシー ( **Delete** 保持アクションが設定された保持タグ) の処理が継続されます。つまり、保持期間を過ぎると、削除ポリシーのタグが付けられたアイテムは [回復可能なアイテム] フォルダーに移動されます。その後、保持期間を過ぎると、それらのアイテムは非アクティブなメールボックスから消去されます。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p121">**Is an Exchange retention policy still processed on inactive mailboxes?** If an Exchange retention policy (the messaging records management, or MRM, feature in Exchange Online) was applied to a mailbox when it was made inactive, the deletion policies (which are retention tags configured with a **Delete** retention action) will continue to be processed on the inactive mailbox. That means items that are tagged with a deletion policy are moved to the Recoverable Items folder when the retention period expires. Those items are then purged from the inactive mailbox when the hold duration for an item expires.</span></span> 
    
    <span data-ttu-id="0cf91-p122">逆に、非アクティブなメールボックスに割り当てられた保持ポリシーにアーカイブ ポリシー ( **MoveToArchive** 保持アクションが設定された保持タグ) が含まれている場合、それらはすべて無視されます。つまり、非アクティブなメールボックス内のアーカイブ ポリシーのタグが付けられたアイテムは、保持期間を過ぎてもプライマリ メールボックスに残ります。それらのアイテムは、アーカイブ メールボックスやアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されません。ユーザーは非アクティブなメールボックスにサインインできないので、アーカイブ ポリシーを処理するためにデータセンターのリソースを消費する理由はありません。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p122">Conversely, any archive policies (which are retention tags configured with a **MoveToArchive** retention action) that are included in the retention policy assigned to an inactive mailbox are ignored. That means items in an inactive mailbox that are tagged with an archive policy remain in the primary mailbox when the retention period expires. They're not moved to the archive mailbox or to the Recoverable Items folder in the archive mailbox. Because a user can't sign in to an inactive mailbox, there's no reason to consume datacenter resources to process archive policies.</span></span> 
    
- <span data-ttu-id="0cf91-p123">**新しい保持期間を確認するには、次のコマンドのいずれかを実行します。** 最初のコマンドは訴訟ホールド用で、2 番目はインプレース ホールド用です。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p123">**To check the new hold duration, run one of the following commands.** The first command is for Litigation Hold; the second is for In-Place Hold.</span></span> 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- <span data-ttu-id="0cf91-p124">**通常のメールボックスのように、管理フォルダー アシスタント (MFA) は非アクティブなメールボックスも処理します。** Exchange Online の場合、MFA は約 7 日に 1 度メールボックスを処理します。非アクティブなメールボックスの保持期間を変更したなら、 **Start-ManagedFolderAssistant** コマンドレットを使用して、非アクティブなメールボックスの新しい保持期間の処理を直ちに開始します。次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p124">**Like regular mailboxes, the Managed Folder Assistant (MFA) also processes inactive mailboxes.** In Exchange Online, the MFA processes mailboxes approximately once every 7 days. After you change the hold duration for an inactive mailbox, you can use the **Start-ManagedFolderAssistant** cmdlet to immediately start processing the new hold duration for the inactive mailbox. Run the following command.</span></span> 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- <span data-ttu-id="0cf91-p125">**非アクティブなメールボックスに対して多数のホールドが設定されている場合、一部のホールドの GUID は表示されません。** 非アクティブなメールボックスに設定されているすべてのホールド (訴訟ホールドを除く) の GUID を表示するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0cf91-p125">**If a lot of holds are placed on an inactive mailbox, not all of the hold GUIDs will be displayed.** You can run the following command to display the GUIDs for all holds (except Litigation Holds) that are placed on an inactive mailbox.</span></span> 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
