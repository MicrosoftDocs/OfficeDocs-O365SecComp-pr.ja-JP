---
title: 情報障壁の概要
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 情報バリアを使用して、組織内の Microsoft Teams を使用して通信のコンプライアンスを確保します。
ms.openlocfilehash: 9750eab3c91b40cc96e16a386dbf59ba767ae877
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394282"
---
# <a name="information-barriers-preview"></a><span data-ttu-id="acbbc-103">情報バリア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="acbbc-103">Information barriers (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="acbbc-104">概要</span><span class="sxs-lookup"><span data-stu-id="acbbc-104">Overview</span></span>

<span data-ttu-id="acbbc-105">Microsoft クラウドサービスには、強力なコミュニケーションとコラボレーションの機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="acbbc-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="acbbc-106">しかし、2つのグループ間の通信を制限して、組織内での利息の競合を回避する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="acbbc-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="acbbc-107">または、内部情報を保護するために、組織内の特定のユーザー間の通信を制限する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="acbbc-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="acbbc-108">Microsoft 365 は、グループと組織間での通信とコラボレーションを可能にするため、必要に応じて特定のユーザーグループ間の通信を制限する方法がありますか。</span><span class="sxs-lookup"><span data-stu-id="acbbc-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="acbbc-109">情報バリアを使用して、できることはありません。</span><span class="sxs-lookup"><span data-stu-id="acbbc-109">With information barriers, you can!</span></span> 

<span data-ttu-id="acbbc-110">情報バリアは、Microsoft Teams から始めて、今すぐプレビュー段階にあります。</span><span class="sxs-lookup"><span data-stu-id="acbbc-110">Information barriers are in preview now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="acbbc-111">これらの機能が組織で使用可能な場合、コンプライアンス管理者または情報障壁管理者は、Microsoft Teams のユーザーグループ間の通信を許可または禁止するポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="acbbc-111">When these features are available for your organization, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="acbbc-112">情報バリアポリシーは、次のような状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="acbbc-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="acbbc-113">1日の販売者は、マーケティングチームで他のユーザーを呼び出すことはできません</span><span class="sxs-lookup"><span data-stu-id="acbbc-113">A day trader cannot call someone on the marketing team</span></span>
- <span data-ttu-id="acbbc-114">機密企業情報に従事している財務担当者は、組織内の特定のグループからの通話を受信できません</span><span class="sxs-lookup"><span data-stu-id="acbbc-114">Finance personnel working on confidential company information cannot receive calls from certain groups within their organization</span></span>
- <span data-ttu-id="acbbc-115">組織内の特定のグループに属するユーザーとの通信を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="acbbc-115">An internal team with trade secret material cannot call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="acbbc-116">研究チームは、製品開発チームとの通話またはオンラインチャットのみを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="acbbc-116">A research team can only call or chat online with a product development team</span></span>

<span data-ttu-id="acbbc-117">これらのすべてのシナリオ例 (およびその他) については、Microsoft Teams での通信を禁止または許可するように情報バリアポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="acbbc-117">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="acbbc-118">このようなポリシーを使用すると、ユーザーが不要な通話やチャットを行うことができなくなり、Microsoft Teams 内の特定のグループとのみ通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="acbbc-118">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="acbbc-119">情報バリアポリシーが有効になっていると、そのポリシーの対象となっているユーザーが Microsoft Teams 内の他のユーザーと通信しようとするたびに、チェックが行われて、通信 (情報バリアポリシーによって定義されている) を回避 (または許可) します。</span><span class="sxs-lookup"><span data-stu-id="acbbc-119">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="acbbc-120">情報の障壁に関するユーザーの作業の詳細については、「 [Microsoft Teams の情報障壁](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acbbc-120">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="acbbc-121">現時点では、情報バリアは、SharePoint Online または OneDrive を使用した電子メール通信やファイル共有には適用されません。</span><span class="sxs-lookup"><span data-stu-id="acbbc-121">Currently, information barriers do not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span> <span data-ttu-id="acbbc-122">さらに、情報バリアは、[コンプライアンスの境界](set-up-compliance-boundaries.md)から独立しています。</span><span class="sxs-lookup"><span data-stu-id="acbbc-122">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p><span data-ttu-id="acbbc-123">情報バリアポリシーを定義して適用する前に、組織の[Exchange アドレス帳ポリシー](https://docs.microsoft.com/en-us/exchange/address-books/address-book-policies/address-book-policies)が有効になっていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="acbbc-123">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/en-us/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span>  

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="acbbc-124">情報バリアで行われる処理</span><span class="sxs-lookup"><span data-stu-id="acbbc-124">What happens with information barriers</span></span>

<span data-ttu-id="acbbc-125">情報バリアポリシーが設定されている場合、他の特定のユーザーとの通信を行わないユーザーは、それらのユーザーを検索、選択、チャット、または呼び出すことができません。</span><span class="sxs-lookup"><span data-stu-id="acbbc-125">When information barrier policies are in place, people who should not communicate with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="acbbc-126">情報の障壁を使用して、承認されていない通信を防止するためのチェックが行われます。</span><span class="sxs-lookup"><span data-stu-id="acbbc-126">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="acbbc-127">最初は、情報の障壁は Microsoft Teams のチャットおよびチャネルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="acbbc-127">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="acbbc-128">Microsoft Teams では、情報バリアポリシーによって、次の種類の承認されていない通信が決定および防止されます。</span><span class="sxs-lookup"><span data-stu-id="acbbc-128">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>
- <span data-ttu-id="acbbc-129">ユーザーを検索する</span><span class="sxs-lookup"><span data-stu-id="acbbc-129">Searching for a user</span></span>
- <span data-ttu-id="acbbc-130">チームへのメンバーの追加</span><span class="sxs-lookup"><span data-stu-id="acbbc-130">Adding a member to a team</span></span>
- <span data-ttu-id="acbbc-131">他のユーザーとのチャットセッションの開始</span><span class="sxs-lookup"><span data-stu-id="acbbc-131">Starting a chat session with someone</span></span>
- <span data-ttu-id="acbbc-132">グループチャットの開始</span><span class="sxs-lookup"><span data-stu-id="acbbc-132">Starting a group chat</span></span>
- <span data-ttu-id="acbbc-133">会議への参加を招待する</span><span class="sxs-lookup"><span data-stu-id="acbbc-133">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="acbbc-134">画面の共有</span><span class="sxs-lookup"><span data-stu-id="acbbc-134">Sharing a screen</span></span>
- <span data-ttu-id="acbbc-135">電話をかける</span><span class="sxs-lookup"><span data-stu-id="acbbc-135">Placing a call</span></span> 

<span data-ttu-id="acbbc-136">関係する人物が、アクティビティを回避するための情報バリアポリシーに含まれている場合、それらのユーザーは処理を続行できません。</span><span class="sxs-lookup"><span data-stu-id="acbbc-136">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="acbbc-137">また、情報バリアポリシーに含まれるすべてのユーザーが Microsoft Teams 内の他のユーザーと通信することをブロックする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="acbbc-137">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="acbbc-138">情報バリアポリシーの影響を受けるユーザーが同じチームまたはグループのチャットに含まれている場合、それらのユーザーはチャットセッションから削除され、グループとの通信が許可されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="acbbc-138">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="acbbc-139">情報の障壁に関するユーザーの作業の詳細については、「 [Microsoft Teams の情報障壁](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acbbc-139">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="acbbc-140">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="acbbc-140">Required licenses and permissions</span></span>

<span data-ttu-id="acbbc-141">**現時点では、情報バリアはプレビュー段階に**あります。</span><span class="sxs-lookup"><span data-stu-id="acbbc-141">**Currently, information barriers are in preview**.</span></span> <span data-ttu-id="acbbc-142">これらの機能が一般公開されると、次のようなサブスクリプションに含まれます。</span><span class="sxs-lookup"><span data-stu-id="acbbc-142">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="acbbc-143">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="acbbc-143">Microsoft 365 E5</span></span>
- <span data-ttu-id="acbbc-144">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="acbbc-144">Office 365 E5</span></span>
- <span data-ttu-id="acbbc-145">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="acbbc-145">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="acbbc-146">Microsoft 365 E5 情報の保護とコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="acbbc-146">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="acbbc-147">詳細については、「[コンプライアンスソリューション](https://products.office.com/business/security-and-compliance/compliance-solutions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acbbc-147">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="acbbc-148">[情報バリアポリシーを定義または編集](information-barriers-policies.md)するには、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="acbbc-148">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="acbbc-149">Microsoft 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="acbbc-149">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="acbbc-150">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="acbbc-150">Office 365 global administrator</span></span>
- <span data-ttu-id="acbbc-151">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="acbbc-151">Compliance administrator</span></span>
- <span data-ttu-id="acbbc-152">IB コンプライアンス管理 (新しい役割)</span><span class="sxs-lookup"><span data-stu-id="acbbc-152">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="acbbc-153">役割とアクセス許可の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acbbc-153">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="acbbc-154">情報バリアポリシーを定義、検証、または編集するには、PowerShell コマンドレットを熟知している必要があります。</span><span class="sxs-lookup"><span data-stu-id="acbbc-154">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="acbbc-155">[「How to](information-barriers-policies.md)」の記事では PowerShell コマンドレットの例をいくつか示していますが、パラメーターなどの追加の詳細については、組織のために知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="acbbc-155">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="acbbc-156">次のステップ</span><span class="sxs-lookup"><span data-stu-id="acbbc-156">Next steps</span></span>

- [<span data-ttu-id="acbbc-157">Microsoft Teams の情報障壁の詳細を知る</span><span class="sxs-lookup"><span data-stu-id="acbbc-157">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [<span data-ttu-id="acbbc-158">情報バリアポリシーに使用できる属性を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acbbc-158">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)

- [<span data-ttu-id="acbbc-159">情報バリアのポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="acbbc-159">Define policies for information barriers</span></span>](information-barriers-policies.md)

- [<span data-ttu-id="acbbc-160">情報バリアポリシーを編集 (または削除) する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="acbbc-160">Edit (or remove) information barrier policies (Preview)</span></span>](information-barriers-edit-segments-policies.md.md) 

