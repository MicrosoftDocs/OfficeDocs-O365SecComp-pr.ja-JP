---
title: 情報障壁の概要
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 情報バリアを使用して、組織内の Microsoft Teams を使用して通信のコンプライアンスを確保します。
ms.openlocfilehash: e52a62ca0b80aed577be1978b81c8a01ac2371b9
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668316"
---
# <a name="information-barriers-preview"></a><span data-ttu-id="061ab-103">情報バリア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="061ab-103">Information barriers (Preview)</span></span>

<span data-ttu-id="061ab-104">Microsoft クラウドサービスには、強力なコミュニケーションとコラボレーションの機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="061ab-104">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="061ab-105">しかし、2つのグループ間の通信を制限して、組織内での利息の競合を回避する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="061ab-105">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="061ab-106">または、内部情報を保護するために、組織内の特定のユーザー間の通信を制限する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="061ab-106">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="061ab-107">Microsoft 365 は、グループと組織間での通信とコラボレーションを可能にするため、必要に応じて特定のユーザーグループ間の通信を制限する方法がありますか。</span><span class="sxs-lookup"><span data-stu-id="061ab-107">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="061ab-108">情報バリアを使用して、できることはありません。</span><span class="sxs-lookup"><span data-stu-id="061ab-108">With information barriers, you can!</span></span> 

<span data-ttu-id="061ab-109">情報バリアは、Microsoft Teams から始めて、今すぐプレビュー段階にあります。</span><span class="sxs-lookup"><span data-stu-id="061ab-109">Information barriers are in preview now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="061ab-110">これらの機能が組織で使用可能な場合、コンプライアンス管理者または情報障壁管理者は、Microsoft Teams のユーザーグループ間の通信を許可または禁止するポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="061ab-110">When these features are available for your organization, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="061ab-111">情報バリアポリシーは、次のような状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="061ab-111">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="061ab-112">1日の販売者は、マーケティングチームで他のユーザーを呼び出すことはできません</span><span class="sxs-lookup"><span data-stu-id="061ab-112">A day trader cannot call someone on the marketing team</span></span>
- <span data-ttu-id="061ab-113">機密企業情報に従事している財務担当者は、組織内の特定のグループからの通話を受信できません</span><span class="sxs-lookup"><span data-stu-id="061ab-113">Finance personnel working on confidential company information cannot receive calls from certain groups within their organization</span></span>
- <span data-ttu-id="061ab-114">組織内の特定のグループに属するユーザーとの通信を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="061ab-114">An internal team with trade secret material cannot call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="061ab-115">研究チームは、製品開発チームとの通話またはオンラインチャットのみを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="061ab-115">A research team can only call or chat online with a product development team</span></span>

<span data-ttu-id="061ab-116">これらのすべてのシナリオ例 (およびその他) については、Microsoft Teams での通信を禁止または許可するように情報バリアポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="061ab-116">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="061ab-117">このようなポリシーを使用すると、ユーザーが不要な通話やチャットを行うことができなくなり、Microsoft Teams 内の特定のグループとのみ通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="061ab-117">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="061ab-118">情報バリアポリシーが有効になっていると、そのポリシーの対象となっているユーザーが Microsoft Teams 内の他のユーザーと通信しようとするたびに、チェックが行われて、通信 (情報バリアポリシーによって定義されている) を回避 (または許可) します。</span><span class="sxs-lookup"><span data-stu-id="061ab-118">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> 

> [!NOTE]
> <span data-ttu-id="061ab-119">情報バリアは、SharePoint Online または OneDrive を使用した電子メール通信やファイル共有には適用されません。</span><span class="sxs-lookup"><span data-stu-id="061ab-119">Information barriers will not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span>

<span data-ttu-id="061ab-120">情報バリアポリシーは、次の種類の通信アクティビティに適用されます。</span><span class="sxs-lookup"><span data-stu-id="061ab-120">Information barrier policies apply to the following kinds of communication activities:</span></span>

- <span data-ttu-id="061ab-121">ユーザーを検索する</span><span class="sxs-lookup"><span data-stu-id="061ab-121">Searching for user</span></span>
- <span data-ttu-id="061ab-122">チームへのメンバーの追加</span><span class="sxs-lookup"><span data-stu-id="061ab-122">Adding a member to a team</span></span>
- <span data-ttu-id="061ab-123">他のユーザーとのチャットセッションの開始</span><span class="sxs-lookup"><span data-stu-id="061ab-123">Starting a chat session with someone</span></span>
- <span data-ttu-id="061ab-124">グループチャットの開始</span><span class="sxs-lookup"><span data-stu-id="061ab-124">Starting a group chat</span></span> 
- <span data-ttu-id="061ab-125">会議への参加を招待する</span><span class="sxs-lookup"><span data-stu-id="061ab-125">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="061ab-126">画面の共有</span><span class="sxs-lookup"><span data-stu-id="061ab-126">Sharing a screen</span></span> 
- <span data-ttu-id="061ab-127">電話をかける</span><span class="sxs-lookup"><span data-stu-id="061ab-127">Placing a call</span></span>

<span data-ttu-id="061ab-128">関与する人物が、アクティビティを阻止する情報バリアポリシーに含まれている場合、それらを続行することはできません。</span><span class="sxs-lookup"><span data-stu-id="061ab-128">If the people involved are included in an information barrier policy that prevents the activity, they will not be able to proceed.</span></span> <span data-ttu-id="061ab-129">情報の障壁に関するユーザーの作業の詳細については、「 [Microsoft Teams の情報障壁](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="061ab-129">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

<span data-ttu-id="061ab-130">現在、情報バリアポリシーは、PowerShell コマンドレットを使用して Office 365 で定義および管理されています。</span><span class="sxs-lookup"><span data-stu-id="061ab-130">Currently, information barrier policies are defined and managed in Office 365 by using PowerShell cmdlets.</span></span> <span data-ttu-id="061ab-131">これは、通常、コンプライアンス管理者または全体管理者によって行われ、PowerShell コマンドレット (およびパラメーター) に精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="061ab-131">This is typically done by a compliance administrator or a global administrator, and requires familiarity with PowerShell cmdlets (and parameters).</span></span> <span data-ttu-id="061ab-132">詳細については、「 [PowerShell」 (情報障壁を定義する)](information-barriers-policies.md#powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="061ab-132">To learn more, see [PowerShell (for defining information barriers)](information-barriers-policies.md#powershell).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="061ab-133">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="061ab-133">Required licenses and permissions</span></span>

<span data-ttu-id="061ab-134">**現時点では、情報バリア機能はプライベートプレビューに**あります。</span><span class="sxs-lookup"><span data-stu-id="061ab-134">**Currently, the information barrier feature is in private preview**.</span></span> <span data-ttu-id="061ab-135">これらの機能が一般公開されると、次のようなサブスクリプションに含まれます。</span><span class="sxs-lookup"><span data-stu-id="061ab-135">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="061ab-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="061ab-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="061ab-137">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="061ab-137">Office 365 E5</span></span>
- <span data-ttu-id="061ab-138">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="061ab-138">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="061ab-139">Microsoft 365 E5 情報の保護とコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="061ab-139">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="061ab-140">詳細については、「[コンプライアンスソリューション](https://products.office.com/business/security-and-compliance/compliance-solutions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="061ab-140">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="061ab-141">[情報バリアポリシーを定義または編集](information-barriers-policies.md)するには、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="061ab-141">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="061ab-142">Microsoft 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="061ab-142">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="061ab-143">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="061ab-143">Office 365 global administrator</span></span>
- <span data-ttu-id="061ab-144">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="061ab-144">Compliance administrator</span></span>
- <span data-ttu-id="061ab-145">情報障壁管理者</span><span class="sxs-lookup"><span data-stu-id="061ab-145">Information barriers administrator</span></span>

<span data-ttu-id="061ab-146">情報バリアポリシーを定義、検証、または編集するには、PowerShell コマンドレットを熟知している必要があります。</span><span class="sxs-lookup"><span data-stu-id="061ab-146">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="061ab-147">[How to 情報](information-barriers-policies.md)には PowerShell コマンドレットの例がいくつか用意されていますが、パラメーターなどの追加の詳細については、組織のために知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="061ab-147">Although we provide several examples of PowerShell cmdlets in the [how-to information](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="061ab-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="061ab-148">Next steps</span></span>

- [<span data-ttu-id="061ab-149">Microsoft Teams の情報障壁の詳細を知る</span><span class="sxs-lookup"><span data-stu-id="061ab-149">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="061ab-150">情報バリアポリシーに使用できる属性を参照してください。</span><span class="sxs-lookup"><span data-stu-id="061ab-150">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="061ab-151">情報バリアのポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="061ab-151">Define policies for information barriers</span></span>](information-barriers-policies.md) 

