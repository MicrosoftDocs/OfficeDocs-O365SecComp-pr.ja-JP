---
title: 組織用に監督ポリシーを構成する
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: 監督機関による監査ポリシーを設定すると、確認のため、従業員の通信をキャプチャします。
ms.openlocfilehash: a919d65f5c0967a44ac12b7e02d477dac2113704
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532826"
---
# <a name="configure-supervision-policies-for-your-organization"></a><span data-ttu-id="f206c-103">組織用に監督ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="f206c-103">Configure supervision policies for your organization</span></span>

<span data-ttu-id="f206c-104">監督ポリシーを使用すると、内部または外部の校閲者による、従業員の通信をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="f206c-104">Use supervision policies to capture employee communications for examination by internal or external reviewers.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f206c-p101">監督ポリシーを使用して、組織に、Office 365 の E5 のサブスクリプションが必要です。しない計画して監視を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。</span><span class="sxs-lookup"><span data-stu-id="f206c-p101">Using supervision policies requires an Office 365 E5 subscription for your organization. If you don't have that plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="f206c-107">設定し、Office 365 の組織の監視を使用してこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f206c-107">Follow these steps to set up and use supervision in your Office 365 organization:</span></span> 
  
- [<span data-ttu-id="f206c-108">監督のグループを設定します</span><span class="sxs-lookup"><span data-stu-id="f206c-108">Set up groups for Supervision</span></span>](configure-supervision-policies.md#exampledist)
    
    <span data-ttu-id="f206c-p102">監督の使用を開始する前に、ユーザーは、通信内容を確認し、それらのレビューを実行する人を決定します。監督の動作を確認するのには、いくつかのユーザーを開始する場合は、ここではグループの設定を省略できます。</span><span class="sxs-lookup"><span data-stu-id="f206c-p102">Before you start using supervision, determine who will have their communications reviewed and who will perform those reviews. If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>
    
- [<span data-ttu-id="f206c-111">監督で利用できるように、組織</span><span class="sxs-lookup"><span data-stu-id="f206c-111">Make supervision available in your organization</span></span>](configure-supervision-policies.md#SRavailable)
    
    <span data-ttu-id="f206c-p103">自身に追加、監督機関による監査の役割のグループ ポリシーを設定することができますように。セキュリティ**データの管理**下にある**監督**ページにアクセスできますがこの役割を割り当てられているすべての人&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="f206c-p103">Add yourself to the Supervisory Review role group so you can set up policies. Anyone who has this role assigned can access the **Supervision** page under **Data Governance** in the Security &amp; Compliance Center.</span></span> 
    
- [<span data-ttu-id="f206c-114">監督ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="f206c-114">Set up a supervision policy</span></span>](configure-supervision-policies.md#setupsuper)
    
    <span data-ttu-id="f206c-p104">セキュリティの監視ポリシーを作成します&amp;コンプライアンス センターです。これらのポリシーでは、通信は、組織の見直しの対象とし、レビューを実行する必要がありますを指定を定義します。Facebook、Twitter など) などのサード パーティ プラットフォームの通信と、電子メールの通信が含まれます</span><span class="sxs-lookup"><span data-stu-id="f206c-p104">You'll create supervision policies in the Security &amp; Compliance Center. These policies define which communications are subject to review in your organization, and specifies who should perform reviews. Communications include email as well as 3rd-party platform communications (such as Facebook, Twitter, etc.)</span></span>
    
- [<span data-ttu-id="f206c-118">監督 policy によって指定された通信を確認するために Outlook web app を使用します。</span><span class="sxs-lookup"><span data-stu-id="f206c-118">Use Outlook web app to review communications identified by a supervision policy</span></span>](configure-supervision-policies.md#UseOutlook)
    
    <span data-ttu-id="f206c-p105">監督を追加で、レビュー担当者にアクセス Outlook web app での監視機能を評価し、各項目を分類することができます。デスクトップのバージョンの Outlook のサポートがもうすぐ完成です。</span><span class="sxs-lookup"><span data-stu-id="f206c-p105">The Supervision add-in gives reviewers access to the supervision functionality right within Outlook web app so they can assess and categorize each item. Support for the desktop version of Outlook is coming soon.</span></span>
    
- <span data-ttu-id="f206c-121">**監督レポートを実行します。**</span><span class="sxs-lookup"><span data-stu-id="f206c-121">**Run the supervision report**</span></span>
    
    <span data-ttu-id="f206c-p106">監督レポートを使用して、ポリシーとレビュー担当者のレベルでのレビュー」アクティビティを参照してください。ポリシーごとに、レビュー」アクティビティの現在の状態で、ライブの統計情報を表示することも。詳細については、[監督のレポート](supervision-reports.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f206c-p106">Use the supervision reports to see the review activity at the policy and reviewer level. For each policy, you can also view live statistics on the current state of review activity. For details, see [Supervision reports](supervision-reports.md).</span></span>
    
## <a name="set-up-groups-for-supervision"></a><span data-ttu-id="f206c-125">監督のグループを設定します</span><span class="sxs-lookup"><span data-stu-id="f206c-125">Set up groups for Supervision</span></span>
<span data-ttu-id="f206c-126"><a name="exampledist"> </a></span><span class="sxs-lookup"><span data-stu-id="f206c-126"></span></span>

 <span data-ttu-id="f206c-p107">監督ポリシーを作成する場合、通信の確認を持って、それらのレビューを実行する人を決定します。ポリシーでは、個人またはグループのユーザーを識別するのに電子メール アドレスを使用します。セットアップを簡略化するのには、通信が確認されたユーザーのグループとは、それらの通信を確認するユーザーのグループを作成します。グループを使用している場合、いくつかを必要があります-たとえば、人の 2 つの異なるグループ間の通信を監視する場合、または管理するしようとしていないグループを指定する場合は、します。このしくみの詳細については、[配布グループの使用例](configure-supervision-policies.md#GroupExample)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f206c-p107">When you create a supervision policy, you'll determine who will have their communications reviewed and who will perform those reviews. In the policy, you'll use email addresses to identify individuals or groups of people. To simplify your setup, create groups for people who will have their communication reviewed and groups for people who will review those communications. If you're using groups, you might need several—for example, if you want to monitor communications between two distinct groups of people, or if you want to specify a group that isn't going to be supervised. See [Example distribution groups](configure-supervision-policies.md#GroupExample) for details about how this works.</span></span> 
  
<span data-ttu-id="f206c-p108">Exchange 管理センターで配布グループを設定します間または組織内のグループ内での通信を監督する (**受信者**に\>**グループ**)。配布グループを設定する方法の詳細については、[配布グループの管理](http://go.microsoft.com/fwlink/?LinkId=613635)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f206c-p108">To supervise communications between or within groups in your organization, set up distribution groups in the Exchange admin center (go to **recipients** \> **groups**). For more information about setting up distribution groups, see [Manage distribution groups](http://go.microsoft.com/fwlink/?LinkId=613635)</span></span>
  
> [!NOTE]
> <span data-ttu-id="f206c-p109">使用できます動的配布グループまたはセキュリティ グループを監督したい場合。組織に合わせてこれらかどうかを判断するには、必要があります、[メールが有効なセキュリティ グループの管理](http://go.microsoft.com/fwlink/?LinkId=627033)、および[動的配布グループの管理](http://go.microsoft.com/fwlink/?LinkId=627058)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f206c-p109">You can also use dynamic distribution groups or security groups for supervision if you prefer. To help you decide if these better fit your organization needs, see [Manage mail-enabled security groups](http://go.microsoft.com/fwlink/?LinkId=627033), and [Manage dynamic distribution groups](http://go.microsoft.com/fwlink/?LinkId=627058).</span></span> 
  
### <a name="example-distribution-groups"></a><span data-ttu-id="f206c-136">配布グループの例</span><span class="sxs-lookup"><span data-stu-id="f206c-136">Example distribution groups</span></span>
<span data-ttu-id="f206c-137"><a name="GroupExample"> </a></span><span class="sxs-lookup"><span data-stu-id="f206c-137"></span></span>

<span data-ttu-id="f206c-138">この例には、contoso 社の財務国際と呼ばれる、金融機関に設定されている配布グループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f206c-138">This example includes a distribution group that has been set up for a financial organization called Contoso Financial International.</span></span> 
  
<span data-ttu-id="f206c-p110">Contoso Financial International では、米国のブローカー間の通信のサンプリングを監視する必要があります。しかし、そのグループ内の法令遵守責任者を監視する必要はありません。この例の場合、次のグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f206c-p110">In Contoso Financial International, a sampling of communications between brokers in the United States must be supervised. However, compliance officers within that group do not require supervision. For this example, we can create the following groups:</span></span>
  
|<span data-ttu-id="f206c-142">**セットアップする配布グループ**</span><span class="sxs-lookup"><span data-stu-id="f206c-142">**Set up this distribution group**</span></span>|<span data-ttu-id="f206c-143">**グループのアドレス (エイリアス)**</span><span class="sxs-lookup"><span data-stu-id="f206c-143">**Group address (alias)**</span></span>|<span data-ttu-id="f206c-144">**説明**</span><span class="sxs-lookup"><span data-stu-id="f206c-144">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f206c-145">米国のブローカー全員</span><span class="sxs-lookup"><span data-stu-id="f206c-145">All US brokers</span></span>  <br/> |<span data-ttu-id="f206c-146">US_Brokers@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="f206c-146">US_Brokers@Contoso.com</span></span>  <br/> |<span data-ttu-id="f206c-147">このグループには Contoso に勤務し米国を拠点とするブローカー全員の電子メール アドレスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f206c-147">This group includes email addresses for all US-based brokers who work for Contoso.</span></span>  <br/> |
|<span data-ttu-id="f206c-148">米国の法令遵守責任者全員</span><span class="sxs-lookup"><span data-stu-id="f206c-148">All US compliance officers</span></span>  <br/> |<span data-ttu-id="f206c-149">US_Compliance@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="f206c-149">US_Compliance@Contoso.com</span></span>  <br/> |<span data-ttu-id="f206c-p111">このグループには、contoso 社のすべての英語ベースのコンプライアンス担当者の電子メール アドレスが含まれます。このグループがすべての米国のブローカーのサブセットであるため、監督のポリシーから控除コンプライアンス責任者にこのエイリアスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f206c-p111">This group includes email addresses for all US-based compliance officers who work for Contoso. Because this group is a subset of all US-based brokers, you can use this alias to exempt compliance officers from a supervision policy.</span></span>  <br/> |
   
<span data-ttu-id="f206c-152">[監督ポリシーの設定](configure-supervision-policies.md#setupsuper)] セクションでは、ポリシーを構成するときに、これらのグループを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f206c-152">The [Set up a supervision policy](configure-supervision-policies.md#setupsuper) section describes how you can use these groups when you configure the policy.</span></span> 
  
## <a name="make-supervision-available-in-your-organization"></a><span data-ttu-id="f206c-153">監督で利用できるように、組織</span><span class="sxs-lookup"><span data-stu-id="f206c-153">Make supervision available in your organization</span></span>
<span data-ttu-id="f206c-154"><a name="SRavailable"> </a></span><span class="sxs-lookup"><span data-stu-id="f206c-154"></span></span>

<span data-ttu-id="f206c-155">セキュリティの**監視**をメニュー オプションとして利用可能に&amp;コンプライアンス ・ センターを割り当てる必要があります監督のレビューの管理者の役割です。</span><span class="sxs-lookup"><span data-stu-id="f206c-155">To make **Supervision** available as a menu option in the Security &amp; Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span> 
  
<span data-ttu-id="f206c-156">これを行うには、監督機関による監査の役割グループのメンバーとして追加自分でするか、新しい役割グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="f206c-156">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a new role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="f206c-157">監督機関による監査の役割グループにメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="f206c-157">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="f206c-158">サインイン[https://protection.office.com](https://protection.office.com)組織の Office 365 の管理者アカウントの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="f206c-158">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="f206c-159">セキュリティ&amp;コンプライアンス センターでは、**アクセス許可**に移動します。</span><span class="sxs-lookup"><span data-stu-id="f206c-159">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
3. <span data-ttu-id="f206c-160">**監督機関による監査**の役割グループを選択し、編集アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f206c-160">Select the **Supervisory Review** role group and then click the Edit icon.</span></span> 
    
4. <span data-ttu-id="f206c-161">[**メンバー** ] セクションでは、組織の監督を管理する人を追加します。</span><span class="sxs-lookup"><span data-stu-id="f206c-161">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span> 
    
### <a name="create-a-new-role-group"></a><span data-ttu-id="f206c-162">新しい役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="f206c-162">Create a new role group</span></span>

1. <span data-ttu-id="f206c-163">サインイン[https://protection.office.com](https://protection.office.com)組織の Office 365 の管理者アカウントの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="f206c-163">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="f206c-164">セキュリティ&amp;コンプライアンス ・ センターは、**アクセス許可**に移動し、し、[追加] をクリックして ( **+**)。</span><span class="sxs-lookup"><span data-stu-id="f206c-164">In the Security &amp; Compliance Center, go to **Permissions** and then click Add ( **+**).</span></span>
    
3. <span data-ttu-id="f206c-p112">[**役割**] セクションの [追加] をクリックします ( **+**) をスクロールして [**レビュー管理者を監督**します。この役割を役割グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="f206c-p112">In the **Roles** section, click Add ( **+**) and scroll down to **Supervisory Review Administrator**. Add this role to the role group.</span></span>
    
4. <span data-ttu-id="f206c-167">[**メンバー** ] セクションでは、組織の監督を管理する人を追加します。</span><span class="sxs-lookup"><span data-stu-id="f206c-167">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span> 
    
<span data-ttu-id="f206c-168">役割グループおよびアクセス許可の詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="f206c-168">For more information about role groups and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center ](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="set-up-a-supervision-policy"></a><span data-ttu-id="f206c-169">監督ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="f206c-169">Set up a supervision policy</span></span>
<span data-ttu-id="f206c-170"><a name="setupsuper"> </a></span><span class="sxs-lookup"><span data-stu-id="f206c-170"></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f206c-171">監督ポリシーを作成する前に、既存の監督機関による監査ポリシーをまず削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f206c-171">Before creating a supervision policy, you must first remove any existing supervisory review policies.</span></span> 
  
1. <span data-ttu-id="f206c-172">サインイン[https://protection.office.com](https://protection.office.com)組織の Office 365 の管理者アカウントの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="f206c-172">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="f206c-173">セキュリティ&amp;コンプライアンス部門、**データの管理**] をクリックしてに移動\>**監督**します。</span><span class="sxs-lookup"><span data-stu-id="f206c-173">In the Security &amp; Compliance Center, go to click **Data governance** \> **Supervision**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f206c-p113">機能の以前のバージョンは、**監督機関による監査 (引退直後)** とは、左側のナビゲーションに表示ことがあります。このバージョンすぐに廃止され削除します。**監督**と呼ばれる新しいバージョンは、その場所にかかります。</span><span class="sxs-lookup"><span data-stu-id="f206c-p113">The previous version of the feature may show in the left-hand navigation as **Supervisory Review (retiring soon)**. This version will soon be deprecated and removed. The new version called **Supervision** will take its place.</span></span> 
  
3. <span data-ttu-id="f206c-177">**作成**] をクリックし、ポリシーの以下のページを設定するウィザードの指示します。</span><span class="sxs-lookup"><span data-stu-id="f206c-177">Click **Create** and then follow the wizard to set up the following pages of the policy.</span></span> 
    
### <a name="policy-name-and-description"></a><span data-ttu-id="f206c-178">ポリシーの名前と説明</span><span class="sxs-lookup"><span data-stu-id="f206c-178">Policy name and description</span></span>

<span data-ttu-id="f206c-p114">名前とポリシーの説明を入力します。例として、Contoso の米国のブローカーのポリシーという名前をします。</span><span class="sxs-lookup"><span data-stu-id="f206c-p114">Enter a name and a description for your policy. For example purposes, we'll name the policy Contoso US Brokers.</span></span>
  
### <a name="choose-users-to-supervise"></a><span data-ttu-id="f206c-181">監督するユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="f206c-181">Choose users to supervise</span></span>

- <span data-ttu-id="f206c-p115">ユーザーの選択ボックスで、**これらのユーザーまたはグループの監視**または監督するが通信をグループ化します。この例では Contoso の米国のブローカーのラボ、US_Brokers@Contoso.com グループは、ここを選択します。</span><span class="sxs-lookup"><span data-stu-id="f206c-p115">In the **Supervise these users or groups** box, choose the users or groups whose communications your want to supervise. Sticking with our example for Contoso US Brokers, we'll choose the group US_Brokers@Contoso.com here.</span></span> 
    
- <span data-ttu-id="f206c-p116">監督するグループを選択した場合は、監視対象外とするグループのメンバーを選択するのには、**これらのユーザーを除外する**] ボックスを使用できます。例を使用すると、私たち US_Compliance@Contoso.com グループは、ここを除外します。</span><span class="sxs-lookup"><span data-stu-id="f206c-p116">If you chose a group to supervise, you can use the **Exclude these users** box to choose members of the group who are exempt from supervision . Using the example , we'll exclude the group US_Compliance@Contoso.com here.</span></span> 
    
### <a name="choose-communications-to-review"></a><span data-ttu-id="f206c-186">通信を確認するを選択します。</span><span class="sxs-lookup"><span data-stu-id="f206c-186">Choose communications to review</span></span>
<span data-ttu-id="f206c-187"><a name="CommsToReview"> </a></span><span class="sxs-lookup"><span data-stu-id="f206c-187"></span></span>

<span data-ttu-id="f206c-p117">既定では、**方向は、** 条件が表示され、削除することはできません。レビュー (特定の単語または語句を含むコンテンツを確認するのみ) などをさらにスコープを設定する場合は、**条件の追加**] をクリックします。必要な場合は、複数の条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f206c-p117">By default, the **Direction is** condition is displayed and can't be removed. If you want to scope the review further (such as only reviewing content that contains certain words or phrases), click **Add a condition**. You can specify multiple conditions if needed.</span></span>
  
<span data-ttu-id="f206c-p118">選択する条件は、組織 (Facebook のドロップ ボックスのような) の電子メールおよびサード ・ パーティの両方のソースからの通信に適用されます。サード パーティ製の通信を Office 365 の組織にインポートする方法の詳細は、 [Office 365 のサード ・ パーティ製データのアーカイブ](https://technet.microsoft.com/EN-US/library/mt621583.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f206c-p118">The conditions you choose will apply to communications from both email and 3rd-party sources in your organization (like from Facebook or DropBox). For details about importing 3rd-party communications into your Office 365 organization, see [Archiving third-party data in Office 365](https://technet.microsoft.com/EN-US/library/mt621583.aspx).</span></span>
  
<span data-ttu-id="f206c-193">次の表は、各条件の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="f206c-193">The following table explains more about each condition.</span></span>
  
|<span data-ttu-id="f206c-194">**条件**</span><span class="sxs-lookup"><span data-stu-id="f206c-194">**Condition**</span></span>|<span data-ttu-id="f206c-195">**この条件の使用方法**</span><span class="sxs-lookup"><span data-stu-id="f206c-195">**How to use this condition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f206c-196">方向</span><span class="sxs-lookup"><span data-stu-id="f206c-196">Direction is</span></span>  <br/> |<span data-ttu-id="f206c-197">**受信**が確認**して****から**人を監督する指定したユーザーが、ポリシーに含まれていない送信される通信を選択します。</span><span class="sxs-lookup"><span data-stu-id="f206c-197">Choose **Inbound** to review communications that are sent **to** the people you chose to supervise **from** people not included in the policy.</span></span>  <br/> <span data-ttu-id="f206c-198">通信を確認する場合に**送信**を選択して**から**届くところに指定したユーザーに送信される * * に * * ユーザーがポリシーに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="f206c-198">Choose **Outbound** if you want to review communications that are sent **from** the people you chose to supervise ** to ** people not included in the policy.</span></span>  <br/> <span data-ttu-id="f206c-199">ポリシーで特定した人**との間**の通信を確認するのには、**内部**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f206c-199">Choose **Internal** to review communications sent **between** the people you identified in the policy.</span></span>  <br/> |
|<span data-ttu-id="f206c-200">メッセージには、これらの単語のいずれかが含まれています</span><span class="sxs-lookup"><span data-stu-id="f206c-200">Message contains any of these words</span></span>  <br/> <span data-ttu-id="f206c-201">メッセージには、除外対象の語句が含まれています</span><span class="sxs-lookup"><span data-stu-id="f206c-201">Message contains none of these words</span></span>  <br/> |<span data-ttu-id="f206c-p119">特定の単語や語句を含めるか除外では、メッセージと、ポリシーを適用するには、別の行に各単語または語句を入力します。入力した単語の各行が個別に適用する (これらの行の 1 つだけをメッセージに適用するポリシーを適用する必要があります)。単語または語句を入力する方法の詳細については、[一致する単語とフレーズを e メールまたは添付ファイル](configure-supervision-policies.md#Matchwords)は、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f206c-p119">To apply the policy when certain words or phrases are included or excluded in a message, enter each word or phrase on a separate line. Each line of words you enter will be applied separately (only one of these lines must apply for the policy to apply to the message). For more information about entering words or phrases, see the next section [Matching words and phrases to emails or attachments](configure-supervision-policies.md#Matchwords).  </span></span><br/> |
|<span data-ttu-id="f206c-205">これらの単語のいずれかの添付ファイルが含まれています</span><span class="sxs-lookup"><span data-stu-id="f206c-205">Attachment contains any of these words</span></span>  <br/> <span data-ttu-id="f206c-206">添付ファイルには、除外対象の語句が含まれています</span><span class="sxs-lookup"><span data-stu-id="f206c-206">Attachment contains none of these words</span></span>  <br/> |<span data-ttu-id="f206c-p120">ポリシーを適用するには、特定の単語や語句を含めるか除外では、メッセージの添付ファイル (Word ドキュメントなど) にするには、別の行に各単語または語句を入力します。入力した単語の各行が個別に適用する (1 行だけを添付ファイルに適用するポリシーを適用する必要があります)。単語または語句を入力する方法の詳細については、[一致する単語とフレーズを e メールまたは添付ファイル](configure-supervision-policies.md#Matchwords)は、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f206c-p120">To apply the policy when certain words or phrases are included or excluded in a message attachment (such as a Word document), enter each word or phrase on a separate line. Each line of words you enter will be applied separately (only one line must apply for the policy to apply to the attachment). For more information about entering words or phrases, see the next section [Matching words and phrases to emails or attachments](configure-supervision-policies.md#Matchwords).  </span></span><br/> |
|<span data-ttu-id="f206c-210">添付ファイルは、これらのファイルの種類のいずれか</span><span class="sxs-lookup"><span data-stu-id="f206c-210">Attachment is any of these file types</span></span>  <br/> <span data-ttu-id="f206c-211">添付ファイルは、これらのファイルの種類の [なし]</span><span class="sxs-lookup"><span data-stu-id="f206c-211">Attachment is none of these file types</span></span>  <br/> |<span data-ttu-id="f206c-p121">特定の種類の添付ファイルをエクスクルードまたはインクルードするための通信を監視するには、ファイルの拡張子 (.exe、.pdf など) を入力します。複数のファイル拡張子を含めたり除外したりする場合は、別々 の行に入力します。1 つだけの添付ファイルの拡張子は、ポリシーを適用するのと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f206c-p121">To supervise communications that include or exclude specific types of attachments, enter the file extensions (such as .exe or .pdf). If you want to include or exclude multiple file extensions, enter these on separate lines. Only one attachment extension needs to match for the policy to apply.</span></span>  <br/> |
|<span data-ttu-id="f206c-215">メッセージ サイズが基準より大きい</span><span class="sxs-lookup"><span data-stu-id="f206c-215">Message size is larger than</span></span>  <br/> <span data-ttu-id="f206c-216">メッセージのサイズがより大きい</span><span class="sxs-lookup"><span data-stu-id="f206c-216">Message size is not larger than</span></span>  <br/> |<span data-ttu-id="f206c-p122">特定のサイズを基にメッセージを確認するには、見直しの対象とされる前にメッセージが表示できる最大値または最小サイズを指定するのにこれらの条件を使用します。**大きいメッセージ サイズ**を指定する場合など、 \> **1.0 MB**、すべてのメッセージを 1.01 MB と大きいはレビューの対象になります。バイト、キロバイト、メガバイト、またはギガバイトこの条件を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f206c-p122">To review messages based on a certain size, use these conditions to specify the maximum or minimum size a message can be before it is subject to review. For example, if you specify **Message size is larger than** \> **1.0 MB**, all messages that are 1.01 MB and larger will be subject to review. You can choose bytes, kilobytes, megabytes, or gigabytes for this condition.  </span></span><br/> |
|<span data-ttu-id="f206c-220">添付ファイルのサイズがより大きい</span><span class="sxs-lookup"><span data-stu-id="f206c-220">Attachment is larger than</span></span>  <br/> <span data-ttu-id="f206c-221">大きい添付ファイルではありません。</span><span class="sxs-lookup"><span data-stu-id="f206c-221">Attachment is not larger than</span></span>  <br/> |<span data-ttu-id="f206c-p123">添付ファイルのサイズを基にメッセージを確認するには、最大値または最小サイズの添付ファイルがメッセージの前にすることができ、見直しの対象とは、その添付ファイルを指定します。**大きい添付ファイル**を指定する場合など、 \> **2.0 MB**、すべてのメッセージの添付ファイルを 2.01 MB と上のレビューの対象になります。バイト、キロバイト、メガバイト、またはギガバイトこの条件を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f206c-p123">To review messages based on the size of their attachments, specify the maximum or minimum size an attachment can be before the message and its attachments are subject to review. For example, if you specify **Attachment is larger than** \> **2.0 MB**, all messages with attachments 2.01 MB and over will be subject to review. You can choose bytes, kilobytes, megabytes, or gigabytes for this condition.  </span></span><br/> |
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a><span data-ttu-id="f206c-225">電子メールや添付ファイルに一致する単語や語句</span><span class="sxs-lookup"><span data-stu-id="f206c-225">Matching words and phrases to emails or attachments</span></span>
<span data-ttu-id="f206c-226"><a name="Matchwords"> </a></span><span class="sxs-lookup"><span data-stu-id="f206c-226"></span></span>

<span data-ttu-id="f206c-p124">入力した単語の各行が個別に適用する (電子メールまたは添付ファイルに適用するポリシーの条件の 1 つだけの行を適用する必要があります)。などみましょう条件を使用して、**メッセージには、これらの単語のいずれかが含まれています**が、キーワード「銀行」、「内部者取引」と別々 行にします。ポリシーは、「銀行」の単語または語句「内部者取引」を含むすべてのメッセージに適用されます。このポリシーの条件を適用するためこれらの単語または語句の 1 つだけ必要があります。メッセージまたは添付ファイル内の単語は、入力した内容を正確に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f206c-p124">Each line of words you enter will be applied separately (only one line must apply for the policy condition to apply to the email or attachment). For example, let's use the condition, **Message contains any of these words**, with the keywords "banker" and "insider trading" on separate lines. The policy will apply to any messages that includes the word "banker" or the phrase "insider trading". Only one of these words or phrases must occur for this policy condition to apply. Words in the message or attachment must exactly match what you enter.</span></span>
  
#### <a name="entering-multiple-conditions"></a><span data-ttu-id="f206c-232">複数の条件の入力</span><span class="sxs-lookup"><span data-stu-id="f206c-232">Entering multiple conditions</span></span>
<span data-ttu-id="f206c-233"><a name="Matchwords"> </a></span><span class="sxs-lookup"><span data-stu-id="f206c-233"></span></span>

<span data-ttu-id="f206c-p125">場合は複数の条件を入力すると、Office 365 を使用してすべての条件一緒コミュニケーション アイテムにポリシーを適用するタイミングを決定します。複数の条件を設定すると、すべて満たさなければならないのポリシーを適用するには、例外を入力する場合を除き、します。たとえば、メッセージが「取引」、という単語を含む、2 MB より大きい場合に適用するポリシーを作成する必要があります。ただし場合は、メッセージには、「財務の Contoso 社の承認済み」の単語も含まれていますポリシーが適用されません。したがって、この例では、3 つの条件としています。</span><span class="sxs-lookup"><span data-stu-id="f206c-p125">If you enter multiple conditions, Office 365 uses all the conditions together to determine when to apply the policy to communication items. When you set up multiple conditions, they must all be met for the policy to apply, unless you enter an exception. For example, let's say you need to create a policy that should apply if a message contains the word "trade", and is larger than 2MB. However, if the message also contains the words "Approved by Contoso financial", the policy should not apply. Thus, in this case, the three conditions would be as follows:</span></span> 
  
- <span data-ttu-id="f206c-239">**メッセージには、これらの単語のいずれかが含まれている**、「取引」のキーワード</span><span class="sxs-lookup"><span data-stu-id="f206c-239">**Message contains any of these words**, with the keywords "trade"</span></span>
    
- <span data-ttu-id="f206c-240">**メッセージのサイズがより大きい**、値が 2 MB</span><span class="sxs-lookup"><span data-stu-id="f206c-240">**Message size is larger than**, with the value 2 MB</span></span>
    
- <span data-ttu-id="f206c-241">**メッセージには、除外対象の語句が含まれている**キーワード「contoso 社の財務チームは、承認済み」と。</span><span class="sxs-lookup"><span data-stu-id="f206c-241">**Message contains none of these words**, with the keywords "Approved by Contoso financial team".</span></span>
    
### <a name="specify-percentage-to-review"></a><span data-ttu-id="f206c-242">確認する割合を指定します。</span><span class="sxs-lookup"><span data-stu-id="f206c-242">Specify percentage to review</span></span>
<span data-ttu-id="f206c-243"><a name="CommsToReview"> </a></span><span class="sxs-lookup"><span data-stu-id="f206c-243"></span></span>

<span data-ttu-id="f206c-p126">確認するのにはコンテンツの量を削減する場合は、パーセント値を指定します。選択した条件に一致した合計からコンテンツ量が無作為に選択すること。校閲者がすべての項目を確認する場合は、 **100%**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f206c-p126">If you want to reduce the amount of content to review, specify a percentage. We'll randomly select that amount of content from the total that matched the conditions you chose. If you want reviewers to review all items, enter **100%**.</span></span>
  
### <a name="choose-reviewers"></a><span data-ttu-id="f206c-247">レビュー担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="f206c-247">Choose reviewers</span></span>
<span data-ttu-id="f206c-248"><a name="CommsToReview"> </a></span><span class="sxs-lookup"><span data-stu-id="f206c-248"></span></span>

<span data-ttu-id="f206c-p127">ユーザーとグループを選択する、アプリケーションを使用、監督 Outlook web app でこのポリシーによって返される通信を検査します。内部または外部の校閲者の電子メール アドレスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="f206c-p127">The users and groups you choose will use the Supervision app in Outlook web app to examine the communications that are returned by this policy. You can include email addresses for internal or external reviewers.</span></span> 
  
### <a name="review-your-settings"></a><span data-ttu-id="f206c-251">設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="f206c-251">Review your settings</span></span>
<span data-ttu-id="f206c-252"><a name="CommsToReview"> </a></span><span class="sxs-lookup"><span data-stu-id="f206c-252"></span></span>

<span data-ttu-id="f206c-p128">監督ポリシーのすべてのセクションが完了したら後、は、設定を確認して、**完了**ポリシーを保存する] をクリックします。通信のキャプチャを開始するようにポリシーのいくつかの時間がかかる場合があります。監督は、校閲者は、Outlook web app でアクセスできる共有フォルダーに、確認のためのすべての通信を提供します。</span><span class="sxs-lookup"><span data-stu-id="f206c-p128">After you've completed all sections of the supervision policy, review your settings and then click **Finish** to save your policy. It might take a few hours for the policy to start capturing communications. Supervision delivers all communications for review into a shared folder that reviewers can access in Outlook web app.</span></span> 
  
## <a name="use-outlook-web-app-to-review-communications-identified-by-a-supervision-policy"></a><span data-ttu-id="f206c-256">監督 policy によって指定された通信を確認するために Outlook web app を使用します。</span><span class="sxs-lookup"><span data-stu-id="f206c-256">Use Outlook web app to review communications identified by a supervision policy</span></span>
<span data-ttu-id="f206c-257"><a name="UseOutlook"> </a></span><span class="sxs-lookup"><span data-stu-id="f206c-257"></span></span>

<span data-ttu-id="f206c-p129">通信を確認するための監視アドインを Outlook web app のレビュー担当者を使用します。アドインが自動的にインストール Outlook web app で、ポリシーで指定したすべての校閲者の。デスクトップのバージョンの Outlook のサポートがもうすぐ完成です。</span><span class="sxs-lookup"><span data-stu-id="f206c-p129">Reviewers will use the Supervision add-in for Outlook web app to review communications. The add-in is installed automatically in Outlook web app for all reviewers you specified in the policy. Support for the desktop version of Outlook is coming soon.</span></span>
  
 <span data-ttu-id="f206c-261">**Outlook web app での通信を確認します。**</span><span class="sxs-lookup"><span data-stu-id="f206c-261">**Reviewing communications in Outlook web app**</span></span>
  
1. <span data-ttu-id="f206c-262">Outlook web app で展開し、**監督 -\<ポリシー名\>** フォルダー。</span><span class="sxs-lookup"><span data-stu-id="f206c-262">In Outlook web app, expand the **Supervision - \<policy name\>** folder.</span></span> 
    
2. <span data-ttu-id="f206c-263">**\<ポリシー名\>** サブフォルダー、校閲者は、その監督のポリシーによって識別されるすべての通信を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f206c-263">In the **\<policy name\>** subfolder, reviewers will see all the communications identified by that supervision policy.</span></span> 
    
    ![監督でアドインを Outlook web app の選択監督ポリシーのサブフォルダーを表示](media/eef329bf-2bd0-477e-a715-76ca19b3347f.jpg)
  
3. <span data-ttu-id="f206c-265">確認し、**監督**のアドインをクリックしてアイテムを開きます。</span><span class="sxs-lookup"><span data-stu-id="f206c-265">Open an item to review and click the **Supervision** add-in.</span></span> 
    
4. <span data-ttu-id="f206c-p130">アドインを使用して、**準拠**や**非準拠**、 **Questionable、** **解決済み**として、項目を分類します。アイテムを分類して後で対応するサブフォルダーに移動されます、**\<ポリシー名\>** フォルダー。</span><span class="sxs-lookup"><span data-stu-id="f206c-p130">Use the add-in to classify the item as **Compliant**, **Non-Compliant**, **Questionable,** or **Resolved**. After you've classified an item, it will be moved to the corresponding subfolder under the **\<policy name\>** folder.</span></span> 
    

