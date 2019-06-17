---
title: 情報障壁の概要
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 情報バリアを使用して、組織内の Microsoft Teams を使用して通信のコンプライアンスを確保します。
ms.openlocfilehash: a2c202d08f1de60f92f13b2ac4c2b9d3c7f900e8
ms.sourcegitcommit: eeb51470d8996e93fac28d7f12c6117e2aeb0cf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2019
ms.locfileid: "34935939"
---
# <a name="information-barriers-preview"></a><span data-ttu-id="4aaf5-103">情報バリア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="4aaf5-103">Information barriers (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="4aaf5-104">概要</span><span class="sxs-lookup"><span data-stu-id="4aaf5-104">Overview</span></span>

<span data-ttu-id="4aaf5-105">Microsoft クラウドサービスには、強力なコミュニケーションとコラボレーションの機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="4aaf5-106">しかし、2つのグループ間の通信を制限して、組織内での利息の競合を回避する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="4aaf5-107">または、内部情報を保護するために、組織内の特定のユーザー間の通信を制限する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="4aaf5-108">Microsoft 365 は、グループと組織間での通信とコラボレーションを可能にするため、必要に応じて特定のユーザーグループ間の通信を制限する方法がありますか。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="4aaf5-109">情報バリアを使用して、できることはありません。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-109">With information barriers, you can!</span></span> 

<span data-ttu-id="4aaf5-110">情報バリアは、Microsoft Teams から始めて、今すぐプレビュー段階にあります。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-110">Information barriers are in preview now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="4aaf5-111">これらの機能が組織で使用可能な場合、コンプライアンス管理者または情報障壁管理者は、Microsoft Teams のユーザーグループ間の通信を許可または禁止するポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-111">When these features are available for your organization, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="4aaf5-112">情報バリアポリシーは、次のような状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="4aaf5-113">1日の販売者は、マーケティングチームで他のユーザーを呼び出すことはできません</span><span class="sxs-lookup"><span data-stu-id="4aaf5-113">A day trader cannot call someone on the marketing team</span></span>
- <span data-ttu-id="4aaf5-114">機密企業情報に従事している財務担当者は、組織内の特定のグループからの通話を受信できません</span><span class="sxs-lookup"><span data-stu-id="4aaf5-114">Finance personnel working on confidential company information cannot receive calls from certain groups within their organization</span></span>
- <span data-ttu-id="4aaf5-115">組織内の特定のグループに属するユーザーとの通信を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-115">An internal team with trade secret material cannot call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="4aaf5-116">研究チームは、製品開発チームとの通話またはオンラインチャットのみを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-116">A research team can only call or chat online with a product development team</span></span>

<span data-ttu-id="4aaf5-117">これらのすべてのシナリオ例 (およびその他) については、Microsoft Teams での通信を禁止または許可するように情報バリアポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-117">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="4aaf5-118">このようなポリシーを使用すると、ユーザーが不要な通話やチャットを行うことができなくなり、Microsoft Teams 内の特定のグループとのみ通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-118">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="4aaf5-119">情報バリアポリシーが有効になっていると、そのポリシーの対象となっているユーザーが Microsoft Teams 内の他のユーザーと通信しようとするたびに、チェックが行われて、通信 (情報バリアポリシーによって定義されている) を回避 (または許可) します。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-119">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="4aaf5-120">情報の障壁に関するユーザーの作業の詳細については、「 [Microsoft Teams の情報障壁](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-120">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="4aaf5-121">情報バリアは、SharePoint Online または OneDrive を使用した電子メール通信やファイル共有には適用されません。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-121">Information barriers will not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="4aaf5-122">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="4aaf5-122">Required licenses and permissions</span></span>

<span data-ttu-id="4aaf5-123">**現時点では、情報バリア機能はプライベートプレビューに**あります。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-123">**Currently, the information barrier feature is in private preview**.</span></span> <span data-ttu-id="4aaf5-124">これらの機能が一般公開されると、次のようなサブスクリプションに含まれます。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-124">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="4aaf5-125">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4aaf5-125">Microsoft 365 E5</span></span>
- <span data-ttu-id="4aaf5-126">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="4aaf5-126">Office 365 E5</span></span>
- <span data-ttu-id="4aaf5-127">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="4aaf5-127">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="4aaf5-128">Microsoft 365 E5 情報の保護とコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="4aaf5-128">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="4aaf5-129">詳細については、「[コンプライアンスソリューション](https://products.office.com/business/security-and-compliance/compliance-solutions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-129">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="4aaf5-130">[情報バリアポリシーを定義または編集](information-barriers-policies.md)するには、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-130">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="4aaf5-131">Microsoft 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="4aaf5-131">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="4aaf5-132">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="4aaf5-132">Office 365 global administrator</span></span>
- <span data-ttu-id="4aaf5-133">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="4aaf5-133">Compliance administrator</span></span>
- <span data-ttu-id="4aaf5-134">情報障壁管理者</span><span class="sxs-lookup"><span data-stu-id="4aaf5-134">Information barriers administrator</span></span>

<span data-ttu-id="4aaf5-135">情報バリアポリシーを定義、検証、または編集するには、PowerShell コマンドレットを熟知している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-135">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="4aaf5-136">[How to 情報](information-barriers-policies.md)には PowerShell コマンドレットの例がいくつか用意されていますが、パラメーターなどの追加の詳細については、組織のために知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-136">Although we provide several examples of PowerShell cmdlets in the [how-to information](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4aaf5-137">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4aaf5-137">Next steps</span></span>

- [<span data-ttu-id="4aaf5-138">Microsoft Teams の情報障壁の詳細を知る</span><span class="sxs-lookup"><span data-stu-id="4aaf5-138">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="4aaf5-139">情報バリアポリシーに使用できる属性を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4aaf5-139">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="4aaf5-140">情報バリアのポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="4aaf5-140">Define policies for information barriers</span></span>](information-barriers-policies.md) 

