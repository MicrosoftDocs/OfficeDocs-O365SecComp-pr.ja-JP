---
title: 代理管理の FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: このトピックでは、代理で Office 365 の管理タスクを実行する (他のテナント (企業) のために Exchange Online Protection (EOP) を管理する機能を含む) Microsoft パートナーとリセラーを対象に、よく寄せられる質問とその答えを取り上げます。
ms.openlocfilehash: 61f939932ab221343b67f87dd5c63f6697e70026
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670442"
---
# <a name="delegated-administration-faq"></a><span data-ttu-id="48462-103">代理管理の FAQ</span><span class="sxs-lookup"><span data-stu-id="48462-103">Delegated administration FAQ</span></span>

<span data-ttu-id="48462-104">このトピックでは、代理で Office 365 の管理タスクを実行する (他のテナント (企業) のために Exchange Online Protection (EOP) を管理する機能を含む) Microsoft パートナーとリセラーを対象に、よく寄せられる質問とその答えを取り上げます。</span><span class="sxs-lookup"><span data-stu-id="48462-104">This topic provides frequently asked questions and answers for Microsoft partners and resellers who want to perform delegated Office 365 administration tasks, including the ability to manage Exchange Online Protection (EOP) for other tenants (companies).</span></span>
  
 <span data-ttu-id="48462-105">**Q. わたしはリセラーで、お客様のテナントを管理する必要があります。どのようにしたらいいですか？**</span><span class="sxs-lookup"><span data-stu-id="48462-105">**Q. I'm a reseller and I need to manage my customer's tenants; how does this work?**</span></span>
  
<span data-ttu-id="48462-106">A.</span><span class="sxs-lookup"><span data-stu-id="48462-106">A.</span></span> <span data-ttu-id="48462-107">microsoft のパートナーまたは販売店で、microsoft advisor にサインアップする場合は、管理センター内でテナントを管理するためのアクセス許可を要求できます。</span><span class="sxs-lookup"><span data-stu-id="48462-107">If you are a Microsoft partner or reseller, and you've signed up to be a Microsoft advisor, you can request permission to administer their tenant within the admin center.</span></span> <span data-ttu-id="48462-108">これは委任された管理と呼ばれ、組織内の管理者であるかのように、Office 365 テナント (EOP 設定を含む) を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="48462-108">This is known as delegated administration, and it allows you to manage their Office 365 tenant (including EOP settings) as if you were an administrator within their organization.</span></span> <span data-ttu-id="48462-109">委任された管理を実行する手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="48462-109">The steps for performing delegated administration are as follows:</span></span>
  
1. <span data-ttu-id="48462-110">[Microsoft Office 365 アドバイザー](https://aka.ms/cloudbenefits) としてサインアップします。</span><span class="sxs-lookup"><span data-stu-id="48462-110">Sign up to be a [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).</span></span>
    
2. <span data-ttu-id="48462-p102">Office 365 の代理管理を行うためにサインアップします。カスタマーのアカウント管理を開始する前に、カスタマーから代理管理者としての承認を得る必要があります。承認を得るには、最初に[代理管理の提供をカスタマーに送ります](https://go.microsoft.com/fwlink/?LinkId=396829)。(後でカスタマーに代理管理を提供することもできます。)</span><span class="sxs-lookup"><span data-stu-id="48462-p102">Sign up for Office 365 delegated administration. Before you can start administering a customer's account, they must authorize you as a delegated administrator. To obtain their approval, you first [send them an offer for delegated administration](https://go.microsoft.com/fwlink/?LinkId=396829). (You can also offer delegated administration to your customer at a later time.)</span></span> 
    
3. <span data-ttu-id="48462-115">「[代理管理者を追加または削除する](https://go.microsoft.com/fwlink/?LinkId=396831)」に記されている手順により、代理管理者アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="48462-115">Create the delegated admin account using the steps documented in [Add or delete a delegated admin](https://go.microsoft.com/fwlink/?LinkId=396831).</span></span>
    
<span data-ttu-id="48462-116">Office 365 代理管理のセットアップ方法について詳しくは、「[パートナー: ビジネスを構築して Office 365 パートナー アカウントを管理する](https://go.microsoft.com/fwlink/?LinkId=301485)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48462-116">Visit [Partners: Build your business and administer your Office 365 partner account](https://go.microsoft.com/fwlink/?LinkId=301485) for more information about how to set up Office 365 delegated administration.</span></span> 
  
 <span data-ttu-id="48462-117">**Q. わたしはリセラーではなく顧客です。どのようにすれば、自分のサブ テナントの代理管理者をセットアップできますか？**</span><span class="sxs-lookup"><span data-stu-id="48462-117">**Q. I'm a customer, not a reseller, how can set up delegated administrator for my sub-tenants?**</span></span>
  
<span data-ttu-id="48462-p103">A. 現時点で、代理管理が行えるのはリセラーとパートナーのみです。しかし、サブ テナント (企業) に適用するのに役立つ Windows PowerShell のサンプル スクリプトが用意されています。詳細については、「[EOP 設定を複数のテナントに適用するスクリプトのサンプル](sample-script-for-applying-eop-settings-to-multiple-tenants.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48462-p103">A. Delegated administration is only available for resellers and partners at this time. However, we've provided a sample Windows PowerShell script that will help you apply policies to your sub-tenants (companies). For more information, see [Sample script for applying EOP settings to multiple tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span></span>
  
 <span data-ttu-id="48462-122">**Q. サブ テナント管理者がわたしのポリシーを変更できないようにすることができますか？**</span><span class="sxs-lookup"><span data-stu-id="48462-122">**Q. Can I prevent my sub-tenant admin from modifying my policy?**</span></span>
  
<span data-ttu-id="48462-p104">A. 現在、Office 365 にその機能はありません。</span><span class="sxs-lookup"><span data-stu-id="48462-p104">A. Office 365 does not currently have this capability.</span></span>
  
 <span data-ttu-id="48462-125">**Q. 自分のすべてのサブ テナントを統合したレポートを取得できますか？**</span><span class="sxs-lookup"><span data-stu-id="48462-125">**Q. Can I get consolidated reporting across all of my sub-tenants?**</span></span>
  
<span data-ttu-id="48462-126">A.</span><span class="sxs-lookup"><span data-stu-id="48462-126">A.</span></span> <span data-ttu-id="48462-127">この時点では、管理対象の会社を超えた統合されたレポートは、micrsoft 365 admin center レポートでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="48462-127">Consolidated reporting across the companies you manage is not available for the Micrsoft 365 admin center reports at this time.</span></span> <span data-ttu-id="48462-128">ただしこれは、リモート Windows PowerShell または[レポート Web サービス](https://go.microsoft.com/fwlink/?LinkId=279926)を使用すると実行できます。</span><span class="sxs-lookup"><span data-stu-id="48462-128">However, this can be done via remote Windows PowerShell or the [reporting web service](https://go.microsoft.com/fwlink/?LinkId=279926).</span></span> 
  

