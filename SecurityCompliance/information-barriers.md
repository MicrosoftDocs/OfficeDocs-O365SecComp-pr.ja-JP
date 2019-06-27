---
title: 情報障壁の概要
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/26/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 情報バリアを使用して、組織内の Microsoft Teams を使用して通信のコンプライアンスを確保します。
ms.openlocfilehash: 6565fc28d70ac6ff9a6f4df6edc75b89d19ae29a
ms.sourcegitcommit: 1c254108c522d0cb44023565268b5041d07748aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2019
ms.locfileid: "35279475"
---
# <a name="information-barriers-preview"></a><span data-ttu-id="b63dc-103">情報バリア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="b63dc-103">Information barriers (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="b63dc-104">概要</span><span class="sxs-lookup"><span data-stu-id="b63dc-104">Overview</span></span>

<span data-ttu-id="b63dc-105">Microsoft クラウドサービスには、強力なコミュニケーションとコラボレーションの機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b63dc-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="b63dc-106">しかし、2つのグループ間の通信を制限して、組織内での利息の競合を回避する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="b63dc-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="b63dc-107">または、内部情報を保護するために、組織内の特定のユーザー間の通信を制限する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b63dc-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="b63dc-108">Microsoft 365 は、グループと組織間での通信とコラボレーションを可能にするため、必要に応じて特定のユーザーグループ間の通信を制限する方法がありますか。</span><span class="sxs-lookup"><span data-stu-id="b63dc-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="b63dc-109">情報バリアを使用して、できることはありません。</span><span class="sxs-lookup"><span data-stu-id="b63dc-109">With information barriers, you can!</span></span> 

<span data-ttu-id="b63dc-110">情報バリアは、Microsoft Teams から始めて、今すぐプレビュー段階にあります。</span><span class="sxs-lookup"><span data-stu-id="b63dc-110">Information barriers are in preview now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="b63dc-111">これらの機能が組織で使用可能な場合、コンプライアンス管理者または情報障壁管理者は、Microsoft Teams のユーザーグループ間の通信を許可または禁止するポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="b63dc-111">When these features are available for your organization, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="b63dc-112">情報バリアポリシーは、次のような状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b63dc-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="b63dc-113">1日の販売者は、マーケティングチームで他のユーザーを呼び出すことはできません</span><span class="sxs-lookup"><span data-stu-id="b63dc-113">A day trader cannot call someone on the marketing team</span></span>
- <span data-ttu-id="b63dc-114">機密企業情報に従事している財務担当者は、組織内の特定のグループからの通話を受信できません</span><span class="sxs-lookup"><span data-stu-id="b63dc-114">Finance personnel working on confidential company information cannot receive calls from certain groups within their organization</span></span>
- <span data-ttu-id="b63dc-115">組織内の特定のグループに属するユーザーとの通信を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="b63dc-115">An internal team with trade secret material cannot call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="b63dc-116">研究チームは、製品開発チームとの通話またはオンラインチャットのみを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b63dc-116">A research team can only call or chat online with a product development team</span></span>

<span data-ttu-id="b63dc-117">これらのすべてのシナリオ例 (およびその他) については、Microsoft Teams での通信を禁止または許可するように情報バリアポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="b63dc-117">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="b63dc-118">このようなポリシーを使用すると、ユーザーが不要な通話やチャットを行うことができなくなり、Microsoft Teams 内の特定のグループとのみ通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b63dc-118">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="b63dc-119">情報バリアポリシーが有効になっていると、そのポリシーの対象となっているユーザーが Microsoft Teams 内の他のユーザーと通信しようとするたびに、チェックが行われて、通信 (情報バリアポリシーによって定義されている) を回避 (または許可) します。</span><span class="sxs-lookup"><span data-stu-id="b63dc-119">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="b63dc-120">情報の障壁に関するユーザーの作業の詳細については、「 [Microsoft Teams の情報障壁](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b63dc-120">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="b63dc-121">情報バリアは、SharePoint Online または OneDrive を使用した電子メール通信やファイル共有には適用されません。</span><span class="sxs-lookup"><span data-stu-id="b63dc-121">Information barriers do not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span> <span data-ttu-id="b63dc-122">さらに、情報バリアは、[コンプライアンスの境界](set-up-compliance-boundaries.md)から独立しています。</span><span class="sxs-lookup"><span data-stu-id="b63dc-122">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="b63dc-123">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b63dc-123">Required licenses and permissions</span></span>

<span data-ttu-id="b63dc-124">**現時点では、情報バリア機能はプライベートプレビューに**あります。</span><span class="sxs-lookup"><span data-stu-id="b63dc-124">**Currently, the information barrier feature is in private preview**.</span></span> <span data-ttu-id="b63dc-125">これらの機能が一般公開されると、次のようなサブスクリプションに含まれます。</span><span class="sxs-lookup"><span data-stu-id="b63dc-125">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="b63dc-126">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b63dc-126">Microsoft 365 E5</span></span>
- <span data-ttu-id="b63dc-127">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="b63dc-127">Office 365 E5</span></span>
- <span data-ttu-id="b63dc-128">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="b63dc-128">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="b63dc-129">Microsoft 365 E5 情報の保護とコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="b63dc-129">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="b63dc-130">詳細については、「[コンプライアンスソリューション](https://products.office.com/business/security-and-compliance/compliance-solutions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b63dc-130">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="b63dc-131">[情報バリアポリシーを定義または編集](information-barriers-policies.md)するには、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b63dc-131">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="b63dc-132">Microsoft 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="b63dc-132">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="b63dc-133">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="b63dc-133">Office 365 global administrator</span></span>
- <span data-ttu-id="b63dc-134">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="b63dc-134">Compliance administrator</span></span>
- <span data-ttu-id="b63dc-135">情報障壁管理者</span><span class="sxs-lookup"><span data-stu-id="b63dc-135">Information barriers administrator</span></span>

<span data-ttu-id="b63dc-136">情報バリアポリシーを定義、検証、または編集するには、PowerShell コマンドレットを熟知している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b63dc-136">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="b63dc-137">[How to 情報](information-barriers-policies.md)には PowerShell コマンドレットの例がいくつか用意されていますが、パラメーターなどの追加の詳細については、組織のために知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="b63dc-137">Although we provide several examples of PowerShell cmdlets in the [how-to information](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="concepts-of-information-barrier-policies"></a><span data-ttu-id="b63dc-138">情報バリアポリシーの概念</span><span class="sxs-lookup"><span data-stu-id="b63dc-138">Concepts of information barrier policies</span></span>

<span data-ttu-id="b63dc-139">情報バリアポリシーの基礎概念を理解しておくと役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="b63dc-139">It's helpful to know the underlying concepts of information barrier policies:</span></span>

- <span data-ttu-id="b63dc-140">**ユーザーアカウントの属性**は、Azure Active Directory (または Exchange Online) で定義されます。</span><span class="sxs-lookup"><span data-stu-id="b63dc-140">**User account attributes** are defined in Azure Active Directory (or Exchange Online).</span></span> <span data-ttu-id="b63dc-141">これらの属性には、部署、役職、場所、チーム名、その他のジョブプロファイルの詳細を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b63dc-141">These attributes can include department, job title, location, team name, and other job profile details.</span></span> 

- <span data-ttu-id="b63dc-142">**セグメント**とは、Office 365 セキュリティ & コンプライアンスセンターで、選択した**ユーザーアカウント属性**を使用して定義された一連のユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="b63dc-142">**Segments** are sets of users that are defined in the Office 365 Security & Compliance Center using a selected **user account attribute**.</span></span> <span data-ttu-id="b63dc-143">([サポートされている属性の一覧](information-barriers-attributes.md)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b63dc-143">(See the [list of supported attributes](information-barriers-attributes.md).)</span></span> 

- <span data-ttu-id="b63dc-144">**情報バリアポリシー**では、通信制限または制限を決定します。</span><span class="sxs-lookup"><span data-stu-id="b63dc-144">**Information barrier policies** determine communication limits or restrictions.</span></span> <span data-ttu-id="b63dc-145">情報バリアポリシーを定義するときは、次の2種類のポリシーから選択します。</span><span class="sxs-lookup"><span data-stu-id="b63dc-145">When you define information barrier policies, you choose from two kinds of policies:</span></span>
    - <span data-ttu-id="b63dc-146">"Block" ポリシーは、あるセグメントが別のセグメントと通信できないようにします。</span><span class="sxs-lookup"><span data-stu-id="b63dc-146">"Block" policies prevent one segment from communicating with another segment.</span></span>
    - <span data-ttu-id="b63dc-147">[許可] ポリシーでは、1つのセグメントが特定の他のセグメントのみと通信できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b63dc-147">"Allow" policies allow one segment to communicate with only certain other segments.</span></span>

- <span data-ttu-id="b63dc-148">**ポリシーアプリケーション**は、すべての情報バリアポリシーが定義された後に実行され、組織に適用する準備が整っています。</span><span class="sxs-lookup"><span data-stu-id="b63dc-148">**Policy application** is done after all information barrier policies are defined, and you are ready to apply them in your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b63dc-149">次のステップ</span><span class="sxs-lookup"><span data-stu-id="b63dc-149">Next steps</span></span>

- [<span data-ttu-id="b63dc-150">Microsoft Teams の情報障壁の詳細を知る</span><span class="sxs-lookup"><span data-stu-id="b63dc-150">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [<span data-ttu-id="b63dc-151">情報バリアポリシーに使用できる属性を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b63dc-151">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="b63dc-152">情報バリアのポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="b63dc-152">Define policies for information barriers</span></span>](information-barriers-policies.md) 

