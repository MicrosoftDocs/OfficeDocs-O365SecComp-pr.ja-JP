---
title: Office 365 開発/テスト環境における GDPR の検出、保護、および報告
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
description: Office 365 の GDPR 機能をデモします。
ms.openlocfilehash: aea1fec29da352285a59ac9286fc053ca10ec746
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243008"
---
# <a name="gdpr-discovery-protection-and-reporting-in-the-office-365-devtest-environment"></a><span data-ttu-id="9622d-103">Office 365 開発/テスト環境における GDPR の検出、保護、および報告</span><span class="sxs-lookup"><span data-stu-id="9622d-103">GDPR discovery, protection, and reporting in the Office 365 dev/test environment</span></span>

 <span data-ttu-id="9622d-104">**概要:** Office 365 の GDPR 機能をデモします。</span><span class="sxs-lookup"><span data-stu-id="9622d-104">**Summary:** Demonstrate GDPR capabilities in Office 365.</span></span> 
  
<span data-ttu-id="9622d-105">この記事では、Office 365 開発/テスト環境で一般データ保護規則 (GDPR) 用に個人を特定できる情報 (PII) の検出、保護、および報告を構成してデモする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9622d-105">This article describes how you configure and demonstrate personally identifiable information (PII) discovery, protection, and reporting for the General Data Protection Regulation (GDPR) in an Office 365 dev/test environment.</span></span>
  
## <a name="phase-1-create-and-configure-your-trial-office-365-subscription"></a><span data-ttu-id="9622d-106">フェーズ 1: 試用版の Office 365 サブスクリプションを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="9622d-106">Phase 1: Create and configure your trial Office 365 subscription</span></span>

<span data-ttu-id="9622d-107">まず、「[Office 365 開発/テスト環境のフェーズ 2](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription)」の記事内の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9622d-107">First, follow the steps in [Phase 2 of the Office 365 dev/test environment](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription) article.</span></span>

<span data-ttu-id="9622d-108">次に、以下の手順を使用して、電子情報開示マネージャーを構成します。</span><span class="sxs-lookup"><span data-stu-id="9622d-108">Next, use these steps to configure the eDiscovery manager:</span></span>

1. <span data-ttu-id="9622d-109">全体管理者アカウントを使用して、Office 365 試用版テナントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="9622d-109">Sign in to your Office 365 trial tenant with your global administrator account.</span></span>
2. <span data-ttu-id="9622d-110">Office 365 のホーム ページで、**[セキュリティとコンプライアンス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-110">From the Office 365 home page, click **Security & Compliance**.</span></span>
3. <span data-ttu-id="9622d-111">新しい [セキュリティとコンプライアンス] タブで、**[アクセス許可]** > **[電子情報開示マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-111">From the new Security & Compliance tab, click **Permissions** > **eDiscovery Manager**.</span></span>
4. <span data-ttu-id="9622d-112">電子情報開示マネージャーの **[編集]** をクリックしてから、**[電子情報開示マネージャーの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-112">Click **Edit** for eDiscovery Manager, and then click **Choose eDiscovery Manager**.</span></span>
5. <span data-ttu-id="9622d-113">**[+ 追加]** をクリックして、自分の全体管理者アカウント名を探し、そのアカウントを電子情報開示マネージャーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="9622d-113">Click **+ Add**, search for your global administrator account name and add your global administrator account as an eDiscovery Manager.</span></span>
6. <span data-ttu-id="9622d-114">**[完了]** > **[保存]** > **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-114">Click **Done** > **Save** > **Close**.</span></span>
  
## <a name="phase-2-add-personally-identifiable-information-to-your-tenant"></a><span data-ttu-id="9622d-115">フェーズ 2: 個人を特定できる情報をテナントに追加する</span><span class="sxs-lookup"><span data-stu-id="9622d-115">Phase 2: Add personally identifiable information to your tenant</span></span>

<span data-ttu-id="9622d-116">このフェーズでは、国際銀行口座番号 (IBAN) の事例用として PII を含むドキュメントを作成し、Office 365 開発/テスト環境内の SharePoint Online サイトに保存します。</span><span class="sxs-lookup"><span data-stu-id="9622d-116">In this phase, you create a document with PII for a set of example International Banking Account Numbers (IBANs) and store it on a SharePoint Online site in your Office 365 dev/test environment.</span></span>

1. <span data-ttu-id="9622d-117">ローカル コンピューターで、Microsoft Word を開きます。</span><span class="sxs-lookup"><span data-stu-id="9622d-117">On your local computer, open Microsoft Word.</span></span>
2. <span data-ttu-id="9622d-118">Word ファイルに次の表を貼り付け、そのファイルを 'IBANs.docx' としてローカル コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="9622d-118">Paste the following table in the Word file and save it as ‘IBANs.docx’ on your local computer.</span></span>
    
    <span data-ttu-id="9622d-119">番号</span><span class="sxs-lookup"><span data-stu-id="9622d-119">Number</span></span>  |<span data-ttu-id="9622d-120">国</span><span class="sxs-lookup"><span data-stu-id="9622d-120">Country</span></span>  |<span data-ttu-id="9622d-121">コード</span><span class="sxs-lookup"><span data-stu-id="9622d-121">Code</span></span> |<span data-ttu-id="9622d-122">IBAN</span><span class="sxs-lookup"><span data-stu-id="9622d-122">IBAN</span></span>  |
    |---------|---------|---------|---------|
    |<span data-ttu-id="9622d-123">1</span><span class="sxs-lookup"><span data-stu-id="9622d-123">1</span></span>     |  <span data-ttu-id="9622d-124">オーストリア SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-124">Austria SEPA</span></span>      | <span data-ttu-id="9622d-125">AT</span><span class="sxs-lookup"><span data-stu-id="9622d-125">AT</span></span>            |<span data-ttu-id="9622d-126">AT611904300234573201</span><span class="sxs-lookup"><span data-stu-id="9622d-126">AT611904300234573201</span></span>       |
    |<span data-ttu-id="9622d-127">2</span><span class="sxs-lookup"><span data-stu-id="9622d-127">2</span></span>     |  <span data-ttu-id="9622d-128">ブルガリア SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-128">Bulgaria SEPA</span></span>       |<span data-ttu-id="9622d-129">BG</span><span class="sxs-lookup"><span data-stu-id="9622d-129">BG</span></span>    |<span data-ttu-id="9622d-130">BG80BNBG96611020345678</span><span class="sxs-lookup"><span data-stu-id="9622d-130">BG80BNBG96611020345678</span></span>      |
    |<span data-ttu-id="9622d-131">3</span><span class="sxs-lookup"><span data-stu-id="9622d-131">3</span></span>     |  <span data-ttu-id="9622d-132">デンマーク SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-132">Denmark SEPA</span></span>      |   <span data-ttu-id="9622d-133">DK</span><span class="sxs-lookup"><span data-stu-id="9622d-133">DK</span></span>      |<span data-ttu-id="9622d-134">DK5000400440116243</span><span class="sxs-lookup"><span data-stu-id="9622d-134">DK5000400440116243</span></span>      |
    |<span data-ttu-id="9622d-135">4</span><span class="sxs-lookup"><span data-stu-id="9622d-135">4</span></span>     |  <span data-ttu-id="9622d-136">フィンランド SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-136">Finland SEPA</span></span>      |   <span data-ttu-id="9622d-137">FI</span><span class="sxs-lookup"><span data-stu-id="9622d-137">FI</span></span>      |<span data-ttu-id="9622d-138">FI2112345600000785</span><span class="sxs-lookup"><span data-stu-id="9622d-138">FI2112345600000785</span></span>         |
    |<span data-ttu-id="9622d-139">5</span><span class="sxs-lookup"><span data-stu-id="9622d-139">5</span></span>     |  <span data-ttu-id="9622d-140">フランス SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-140">France SEPA</span></span>       |   <span data-ttu-id="9622d-141">FR</span><span class="sxs-lookup"><span data-stu-id="9622d-141">FR</span></span>      |<span data-ttu-id="9622d-142">FR1420041010050500013M02606</span><span class="sxs-lookup"><span data-stu-id="9622d-142">FR1420041010050500013M02606</span></span>         |
    |<span data-ttu-id="9622d-143">6</span><span class="sxs-lookup"><span data-stu-id="9622d-143">6</span></span>     |  <span data-ttu-id="9622d-144">ドイツ SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-144">Germany SEPA</span></span>      |   <span data-ttu-id="9622d-145">DE</span><span class="sxs-lookup"><span data-stu-id="9622d-145">DE</span></span>      |<span data-ttu-id="9622d-146">DE89370400440532013000</span><span class="sxs-lookup"><span data-stu-id="9622d-146">DE89370400440532013000</span></span>         |
    |<span data-ttu-id="9622d-147">7</span><span class="sxs-lookup"><span data-stu-id="9622d-147">7</span></span>     |  <span data-ttu-id="9622d-148">ギリシャ SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-148">Greece SEPA</span></span>       |   <span data-ttu-id="9622d-149">GR</span><span class="sxs-lookup"><span data-stu-id="9622d-149">GR</span></span>      |<span data-ttu-id="9622d-150">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="9622d-150">GR1601101250000000012300695</span></span>         |
    |<span data-ttu-id="9622d-151">8</span><span class="sxs-lookup"><span data-stu-id="9622d-151">8</span></span>     |  <span data-ttu-id="9622d-152">イタリア SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-152">Italy SEPA</span></span>       |    <span data-ttu-id="9622d-153">IT</span><span class="sxs-lookup"><span data-stu-id="9622d-153">IT</span></span>     |<span data-ttu-id="9622d-154">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="9622d-154">GR1601101250000000012300695</span></span>         |
    |<span data-ttu-id="9622d-155">9</span><span class="sxs-lookup"><span data-stu-id="9622d-155">9</span></span>     |  <span data-ttu-id="9622d-156">オランダ SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-156">Netherlands SEPA</span></span>      |   <span data-ttu-id="9622d-157">NL</span><span class="sxs-lookup"><span data-stu-id="9622d-157">NL</span></span>      |    <span data-ttu-id="9622d-158">NL91ABNA0417164300</span><span class="sxs-lookup"><span data-stu-id="9622d-158">NL91ABNA0417164300</span></span>     |
    |<span data-ttu-id="9622d-159">10</span><span class="sxs-lookup"><span data-stu-id="9622d-159">10</span></span>     | <span data-ttu-id="9622d-160">ポーランド SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-160">Poland SEPA</span></span>       |  <span data-ttu-id="9622d-161">PL</span><span class="sxs-lookup"><span data-stu-id="9622d-161">PL</span></span>       | <span data-ttu-id="9622d-162">PL27114020040000300201355387</span><span class="sxs-lookup"><span data-stu-id="9622d-162">PL27114020040000300201355387</span></span>        |

<span data-ttu-id="9622d-163">メモ:- このサンプル データ セットは、公開されている情報から得られたもので、テスト目的でのみ使用することを意図しています。</span><span class="sxs-lookup"><span data-stu-id="9622d-163">Note:- This sample data set is derived from publicly available information and is intended to be used for test purposes only.</span></span>

3. <span data-ttu-id="9622d-164">ブラウザーの新しいタブで、「**https://**\<YourTenantName\>**.sharepoint.com**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9622d-164">In a new tab of your browser, type:  **https://**\<YourTenantName\>**.sharepoint.com**</span></span>
4. <span data-ttu-id="9622d-p101">**[ドキュメント]** をクリックして、このサイトのドキュメント ライブラリを開きます。新しいリスト エクスペリエンス ツアーのプロンプトが表示されたら、終了するまで **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-p101">Click **Documents** to open the document library for this site. If you’re prompted for a new list experience tour, click **Next** until it’s finished.</span></span>
5.  <span data-ttu-id="9622d-167">**[アップロード]** > **[ファイル]** をクリックして、手順 2 で作成した IBANs.docx を選択します。</span><span class="sxs-lookup"><span data-stu-id="9622d-167">Click **Upload** > **Files** and select the IBANs.docx you created in step 2.</span></span>

  
## <a name="phase-3-demonstrate-data-discovery"></a><span data-ttu-id="9622d-168">フェーズ 3: データ検出をデモする</span><span class="sxs-lookup"><span data-stu-id="9622d-168">Phase 3: Demonstrate data discovery</span></span>

<span data-ttu-id="9622d-169">このフェーズでは、IBAN を含むコンテンツに基づいて、フェーズ 2 で作成して保存したドキュメントを検索するデモを示します。</span><span class="sxs-lookup"><span data-stu-id="9622d-169">In this phase, you demonstrate search to find the document created and stored in Phase 2, based on its content containing IBANs.</span></span>

1. <span data-ttu-id="9622d-170">[セキュリティとコンプライアンス] タブで、**[ホーム]** をクリックしてから、**[検索と調査]** > **[コンテンツ検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-170">From the Security & Compliance tab, click **Home**, and then click **Search & investigation** > **Content search**.</span></span>
2. <span data-ttu-id="9622d-171">**+** をクリックすることで、新しい検索項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="9622d-171">Create a new search item by clicking on **+**.</span></span>
3. <span data-ttu-id="9622d-172">新しいウィンドウで、次の情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="9622d-172">In a new window, provide the following information:</span></span>  
    <span data-ttu-id="9622d-p102">a. 名前: IBAN 検索</span><span class="sxs-lookup"><span data-stu-id="9622d-p102">a. Name: IBAN Search</span></span>  
    <span data-ttu-id="9622d-p103">b. 何を検索しますか?: **検索する特定のサイトを選択** (**+** をクリック) してから、サイトの URL (**https://**\<YourTenantName\>**.sharepoint.com/**) を入力します。</span><span class="sxs-lookup"><span data-stu-id="9622d-p103">b. Where do you want us to look?: **Choose specific sites to search** (click **+**), and then enter the site's URL: **https://**\<YourTenantName\>**.sharepoint.com/**</span></span>  
    <span data-ttu-id="9622d-p104">c. **[追加]** をクリックしてから、**[OK]** をクリックします。警告が表示されたら、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-p104">c. Click **Add**, and then click **OK**. If you see a Warning, click **OK**.</span></span>  
    <span data-ttu-id="9622d-p105">d. **[新しい検索]** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-p105">d. Click **Next** on a **New search** window.</span></span>  
    <span data-ttu-id="9622d-p106">e. **何を検索しますか?**: **SensitiveType:"国際銀行口座番号 (IBAN)"** に対して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-p106">e. For **What do you want us to look for?**: **SensitiveType:"International Banking Account Number (IBAN)"**, and then click **Search**.</span></span>

4. <span data-ttu-id="9622d-184">**IBAN 検索**の結果に少なくとも 1 つの項目が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9622d-184">Make sure you see at least one item listed in the **IBAN Search** results.</span></span>


## <a name="phase-4-create-a-custom-sensitive-information-type-via-powershell"></a><span data-ttu-id="9622d-185">フェーズ 4: PowerShell 経由でカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="9622d-185">Phase 4: Create a custom sensitive information type via PowerShell</span></span>

<span data-ttu-id="9622d-p107">このフェーズでは、Microsoft PowerShell を使用して、架空の Contoso 社のカスタムの機密情報の種類を作成します。Contoso 社では、Contoso 顧客番号 (CCN) を使用して、顧客データベース内の各顧客を識別しています。CCN の構造は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9622d-p107">In this phase, you create a custom sensitive information type for the fictional Contoso Corporation using Microsoft PowerShell.  Contoso uses a Contoso Customer Number (CCN) to identify each customer in their customer database. A CCN consists of the following structure:</span></span>
- <span data-ttu-id="9622d-189">レコードが作成された年を表す 2 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="9622d-189">Two digits to represent the year that the record was created.</span></span>
    - <span data-ttu-id="9622d-190">Contoso 社は 2002 年に設立されました。そのため、最小値は 02 です。</span><span class="sxs-lookup"><span data-stu-id="9622d-190">Contoso was founded in 2002; therefore, the earliest possible value would be 02.</span></span> 
- <span data-ttu-id="9622d-191">レコードを作成したパートナー代理店を表す 3 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="9622d-191">Three digits to represent the partner agency that created the record.</span></span>
    - <span data-ttu-id="9622d-192">使用可能な代理店の値の範囲は 000 ～ 999 です。</span><span class="sxs-lookup"><span data-stu-id="9622d-192">Possible agency values range from 000 to 999.</span></span> 
- <span data-ttu-id="9622d-193">基幹業務を表す英字。</span><span class="sxs-lookup"><span data-stu-id="9622d-193">An alphabetic character to represent the line of business.</span></span>
    - <span data-ttu-id="9622d-194">使用可能な値は a ～ z で、大文字と小文字を区別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9622d-194">Possible values are a-z and should be case insensitive.</span></span>
- <span data-ttu-id="9622d-195">4 桁のシリアル番号。</span><span class="sxs-lookup"><span data-stu-id="9622d-195">A four-digit serial number.</span></span> 
    - <span data-ttu-id="9622d-196">使用可能なシリアル番号の値の範囲は、0000 ～ 9999 です。</span><span class="sxs-lookup"><span data-stu-id="9622d-196">Possible serial number values range from 0000 to 9999.</span></span>   

<span data-ttu-id="9622d-p108">Contoso では、必ず、内部対応、外部対応、ドキュメント、およびその他の形式で CCN を使用して顧客を参照しています。また、この形式の個人を識別できる情報の使用に対して保護が適用されるように、Office 365 コンテンツ内の CCN の使用を検出するためのカスタムの機密項目の種類が必要です。</span><span class="sxs-lookup"><span data-stu-id="9622d-p108">Contoso always refers to customers by using a CCN in internal correspondence, external correspondence, documents, and other forms. Contoso needs a custom sensitive item type to detect the use of CCNs in Office 365 content so that they may apply protection to the use of this form of personal identifiable information.</span></span>

1. <span data-ttu-id="9622d-199">「[多要素認証を使用してセキュリティ/コンプライアンス センターの PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps)」の手順を使用して、全体管理者アカウントの UPN でセキュリティ/コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="9622d-199">Use the instructions in [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) and connect to the Security & Compliance Center with UPN of your global administrator account.</span></span>
2. <span data-ttu-id="9622d-200">次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9622d-200">Run the following PowerShell commands.</span></span>

     ```
    #Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName#Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName
    ```
3. <span data-ttu-id="9622d-201">次の PowerShell コマンドを実行して、生成された GUID を表示順にコンピューター上で開いているメモ帳のインスタンスにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9622d-201">Run the following PowerShell commands and copy the generated GUIDs to an open instance of Notepad on your computer in the order in which they are listed.</span></span>
    ```
    #Generate three unique GUIDs
    Write-Host "GUID1 = "([guid]::NewGuid().Guid)
    Write-Host "GUID2 = "([guid]::NewGuid().Guid)
    Write-Host "GUID3 = "([guid]::NewGuid().Guid)
    ```
4. <span data-ttu-id="9622d-202">ローカル コンピューターで、メモ帳の別のインスタンスを開いて、次の内容を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9622d-202">On your local computer, open another instance of Notepad and paste in the following content:</span></span>

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <RulePackage xmlns="http://schemas.microsoft.com/office/2011/mce"> 
    <RulePack id="GUID1">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="GUID2" />
    <Details defaultLangCode="en"> 
    <LocalizedDetails langcode="en"> 
    <PublisherName>Contoso Ltd.</PublisherName> 
    <Name>Contoso Rule Package</Name> 
    <Description>Defines Contoso's custom set of classification rules</Description>
    </LocalizedDetails>
    </Details>
    </RulePack>
    <Rules>
    <!-- Contoso Customer Number (CCN) -->
    <Entity id="GUID3" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
    <IdMatch idRef="Regex_contoso_ccn" />
    <Match idRef="Keyword_contoso_ccn" />
    <Match idRef="Regex_eu_date" />
    </Pattern>
    </Entity>
    <Regex id="Regex_contoso_ccn">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</Regex>
    <Keyword id="Keyword_contoso_ccn">
    <Group matchStyle="word">
    <Term caseSensitive="false">customer number</Term>
    <Term caseSensitive="false">customer no</Term>
    <Term caseSensitive="false">customer #</Term>
    <Term caseSensitive="false">customer#</Term>
    <Term caseSensitive="false">Contoso customer</Term>
    </Group>
    </Keyword>
    <Regex id="Regex_eu_date"> (0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)? |feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|apr(ile|il)?|abr(il)?|avril |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)? |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}</Regex>
    <LocalizedStrings>
    <Resource idRef="GUID3">
    <Name default="true" langcode="en-us">Contoso Customer Number (CCN)</Name>
    <Description default="true" langcode="en-us">Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</Description>
    </Resource>
    </LocalizedStrings>
    </Rules>
    </RulePackage>
    ```
5. <span data-ttu-id="9622d-203">手順 4 の XML テキスト内の GUID1、GUID2、および GUID3 の値を手順 3 の値に置換し、その内容を ContosoCCN.xml という名前でローカル コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="9622d-203">Replace the values of GUID1, GUID2, and GUID3 in the XML text of step 4 with their values from step 3, and then save the contents on your local computer with the name ContosoCCN.xml.</span></span>
6. <span data-ttu-id="9622d-204">ContosoCCN.xml ファイルへのパスを入力して、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9622d-204">Fill in the path to your ContosoCCN.xml file and run the following commands.</span></span>
    ```
    #Create new Sensitive Information Type
    $path="<path to the ContosoCCN.xml file, such as C:\Scripts\ContosoCCN.xml>"
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path $path -Encoding Byte -ReadCount 0)
    ```
7. <span data-ttu-id="9622d-p109">[セキュリティとコンプライアンス] タブで、**[分類]** > **[機密情報の種類]** をクリックします。リストに Contoso 顧客番号 (CCN) が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="9622d-p109">From the Security & Compliance tab, click **Classifications** > **Sensitive information types**. You should see the Contoso Customer Number (CCN) in the list.</span></span>

## <a name="phase-5-demonstrate-data-protection"></a><span data-ttu-id="9622d-207">フェーズ 5: データ保護をデモする</span><span class="sxs-lookup"><span data-stu-id="9622d-207">Phase 5: Demonstrate data protection</span></span>

<span data-ttu-id="9622d-208">Office 365 の個人情報の保護には、データ損失防止 (DLP) 機能の使用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9622d-208">Protection of personal information in Office 365 includes using data loss prevention (DLP) capabilities.</span></span>  <span data-ttu-id="9622d-209">DLP ポリシーにより、Office 365 全体で自動的に機密情報を保護できます。</span><span class="sxs-lookup"><span data-stu-id="9622d-209">With DLP policies, you can automatically protect sensitive information across Office 365.</span></span>

<span data-ttu-id="9622d-p111">保護を適用するための複数の方法があります。環境内の EU 居住者データの保存場所と従業員によるその処理方法の教育と認識の向上は、Office 365 DLP を使用した情報保護の 1 つのレベルを表しています。</span><span class="sxs-lookup"><span data-stu-id="9622d-p111">There are multiple ways you can apply the protection. Educating and raising awareness to where EU resident data is stored in your environment and how your employees are permitted to handle it represents one level of information protection using Office 365 DLP.</span></span>

<span data-ttu-id="9622d-212">このフェーズでは、新しい DLP ポリシーを作成して、フェーズ 2 で SharePoint Online に保存した IBANs.docx ファイルに適用する方法と IBAN を含む電子メールを送信するタイミングをデモします。</span><span class="sxs-lookup"><span data-stu-id="9622d-212">In this phase, you create a new DLP policy and demonstrate how it gets applied to the IBANs.docx file you stored in SharePoint Online in Phase 2 and when you attempt to send an email containing IBANs.</span></span>

1. <span data-ttu-id="9622d-213">ブラウザーの [セキュリティとコンプライアンス] タブで、**[ホーム]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-213">From the Security & Compliance tab of your browser, click **Home**.</span></span>
2. <span data-ttu-id="9622d-214">**[データ損失防止]** > **[ポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-214">Click **Data loss prevention** > **Policy**.</span></span>
3. <span data-ttu-id="9622d-215">**[+ ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-215">Click **+ Create a policy**.</span></span>
4. <span data-ttu-id="9622d-216">**[テンプレートで開始またはカスタム ポリシーの作成]** で、**[カスタム]** > **[カスタム ポリシー]** > **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-216">In **Start with a template or create a custom policy**, click **Custom** > **Custom policy** > **Next**.</span></span>
5. <span data-ttu-id="9622d-p112">**[ポリシーに名前を付ける]** で、次の詳細を入力してから、**[次へ]** をクリックします。a. 名前: **EU 市民 PII ポリシー** b. 説明: **欧州市民の個人を特定できる情報を保護する**</span><span class="sxs-lookup"><span data-stu-id="9622d-p112">In **Name your policy**, provide the following details and then click **Next**:  a. Name: **EU Citizen PII Policy** b. Description: **Protect the personally identifiable information of European citizens**</span></span>
6. <span data-ttu-id="9622d-p113">**[場所の選択]** で、**[Office 365 のすべての場所]** を選択します。これに、Exchange 電子メール、OneDrive ドキュメント、および SharePoint ドキュメントの内容が追加されます。その後で、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-p113">In **Choose locations**, select **All locations in Office 365**. This will include content in Exchange email and OneDrive and SharePoint documents. And then click **Next**.</span></span>
7. <span data-ttu-id="9622d-223">**[保護するコンテンツの種類のカスタマイズ]** で、**[含まれているコンテンツを検索する:]** をクリックしてから、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-223">In **Customize the type of content you want to protect**, click **Find content that contains:** and then click **Edit**.</span></span>
8. <span data-ttu-id="9622d-224">**[保護するコンテンツの種類の選択]** で、**[追加]** > **[機密情報の種類]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-224">In **Choose the types of content to protect**, click **Add** > **Sensitive info types**.</span></span>
9. <span data-ttu-id="9622d-225">**[機密情報の種類]** で、**[+ 追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-225">In **Sensitive info types**, click **+ Add**.</span></span>
10. <span data-ttu-id="9622d-226">**[機密情報の種類]** で、**IBAN** を検索して、**[国際銀行口座番号 (IBAN)]** チェック ボックスをオンにしてから、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-226">In **Sensitive info types**, search for **IBAN**, select the check box for **International Banking Account Number (IBAN)**, and then click **Add**.</span></span>
11. <span data-ttu-id="9622d-227">**国際銀行口座番号 (IBAN)** 機密情報の種類が追加されたことを確認してから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-227">Confirm that the **International Banking Account Number (IBAN)** sensitive information type was added, and then click **Done**.</span></span>
12. <span data-ttu-id="9622d-228">**[含まれるコンテンツ]** で、機密情報の種類が追加されたことを確認してから、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-228">In **Content contains**, confirm that the sensitive information types were added and then click **Save**.</span></span>
13. <span data-ttu-id="9622d-229">**[保護するコンテンツの種類のカスタマイズ]** で、**[含まれているコンテンツを検索する:]** に **国際銀行口座番号 (IBAN)** が含まれていることを確認してから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-229">In **Customize the type of content you want to protect**, confirm  **Find content that contains:** contains the **International Banking Account Number (IBAN)**, and then click **Next**.</span></span>
14. <span data-ttu-id="9622d-230">**[共有されているコンテンツが含まれる時期の検出:（Detect when content that's being shared contains:）]** で、値を **10** から **1** に変更してから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-230">In **Detect when content that's being shared contains:**, change the value from **10** to **1**, and then click **Next**.</span></span>
15. <span data-ttu-id="9622d-231">**[ポリシーを有効にしますか、または最初にテストしますか?]** で、次の設定を選択してから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-231">In **Do you want to turn on the policy or test things out first?**, choose the following settings, and then click **Next**.</span></span>  
    <span data-ttu-id="9622d-p114">a. **[最初にテストする]** のオプションを選択する</span><span class="sxs-lookup"><span data-stu-id="9622d-p114">a. Select the option for **I'd like to test it out first**</span></span>  
    <span data-ttu-id="9622d-p115">b. **[テスト モードでポリシー ヒントを表示する]** チェック ボックスをオンにする</span><span class="sxs-lookup"><span data-stu-id="9622d-p115">b. Select the check box for **Show policy tips while in test mode**</span></span> 
16. <span data-ttu-id="9622d-p116">**[設定の確認]** で、設定の確認後に **[作成]** をクリックします。メモ: 新しい DLP ポリシーを作成したら、それが有効になるまでしばらく時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="9622d-p116">In **Review your settings**, click **Create** after reviewing the settings. NOTE: After you create a new DLP policy, it will take a while for it to take effect.</span></span>
17. <span data-ttu-id="9622d-238">ローカル コンピューター上で、ブラウザーのプライベート インスタンスを開きます。</span><span class="sxs-lookup"><span data-stu-id="9622d-238">On your local computer, open a private instance of your browser.</span></span>
18. <span data-ttu-id="9622d-239">アドレス バーに、「**https://**\<YourTenantName\>**.sharepoint.com**」と入力して、全体管理者アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="9622d-239">In the address bar, type **https://**\<YourTenantName\>**.sharepoint.com** and sign in using your global administrator account.</span></span>
19. <span data-ttu-id="9622d-240">**[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-240">Click **Documents**.</span></span>
20. <span data-ttu-id="9622d-p117">'IBANs.docx' という名前のファイルをクリックします。'IBANs.docx のポリシー ヒント' が表示されるはずです。IBANs.docx ファイルは、DLP ポリシーに違反している外部の受信者と共有されています。</span><span class="sxs-lookup"><span data-stu-id="9622d-p117">Click the file named ‘IBANs.docx’. You should see ‘Policy tip for IBANs.docx’.  The IBANs.docx file was shared with external recipients, which violates the DLP policy.</span></span> 
21. <span data-ttu-id="9622d-244">アドレス バーに、「`https://outlook.office365.com`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9622d-244">In the address bar, type: `https://outlook.office365.com`</span></span>
22. <span data-ttu-id="9622d-245">**[新規]** - **[電子メール メッセージ]** をクリックして、次の項目を入力します。</span><span class="sxs-lookup"><span data-stu-id="9622d-245">Click **New** - **Email message** and provide the following:</span></span>  
    - <span data-ttu-id="9622d-246">**宛先:** \<個人用電子メール アドレス\></span><span class="sxs-lookup"><span data-stu-id="9622d-246">**To:** \<a personal email address\></span></span>  
    - <span data-ttu-id="9622d-247">**件名:** GDPR テスト</span><span class="sxs-lookup"><span data-stu-id="9622d-247">**Subject:** GDPR Test</span></span>  
    - <span data-ttu-id="9622d-248">**本文:** 下に示す値の表にコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="9622d-248">**Body:** Copy in the table of values shown below.</span></span>
  
        |<span data-ttu-id="9622d-249">番号</span><span class="sxs-lookup"><span data-stu-id="9622d-249">Number</span></span>  |<span data-ttu-id="9622d-250">国</span><span class="sxs-lookup"><span data-stu-id="9622d-250">Country</span></span>  |<span data-ttu-id="9622d-251">コード</span><span class="sxs-lookup"><span data-stu-id="9622d-251">Code</span></span> |<span data-ttu-id="9622d-252">IBAN</span><span class="sxs-lookup"><span data-stu-id="9622d-252">IBAN</span></span>  |
        |---------|---------|---------|---------|
        |<span data-ttu-id="9622d-253">1</span><span class="sxs-lookup"><span data-stu-id="9622d-253">1</span></span>     |  <span data-ttu-id="9622d-254">オーストリア SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-254">Austria SEPA</span></span>      | <span data-ttu-id="9622d-255">AT</span><span class="sxs-lookup"><span data-stu-id="9622d-255">AT</span></span>            |<span data-ttu-id="9622d-256">AT611904300234573201</span><span class="sxs-lookup"><span data-stu-id="9622d-256">AT611904300234573201</span></span>       |
        |<span data-ttu-id="9622d-257">2</span><span class="sxs-lookup"><span data-stu-id="9622d-257">2</span></span>     |  <span data-ttu-id="9622d-258">ブルガリア SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-258">Bulgaria SEPA</span></span>       |<span data-ttu-id="9622d-259">BG</span><span class="sxs-lookup"><span data-stu-id="9622d-259">BG</span></span>    |<span data-ttu-id="9622d-260">BG80BNBG96611020345678</span><span class="sxs-lookup"><span data-stu-id="9622d-260">BG80BNBG96611020345678</span></span>      |
        |<span data-ttu-id="9622d-261">3</span><span class="sxs-lookup"><span data-stu-id="9622d-261">3</span></span>     |  <span data-ttu-id="9622d-262">デンマーク SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-262">Denmark SEPA</span></span>      |   <span data-ttu-id="9622d-263">DK</span><span class="sxs-lookup"><span data-stu-id="9622d-263">DK</span></span>      |<span data-ttu-id="9622d-264">DK5000400440116243</span><span class="sxs-lookup"><span data-stu-id="9622d-264">DK5000400440116243</span></span>      |
        |<span data-ttu-id="9622d-265">4</span><span class="sxs-lookup"><span data-stu-id="9622d-265">4</span></span>     |  <span data-ttu-id="9622d-266">フィンランド SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-266">Finland SEPA</span></span>      |   <span data-ttu-id="9622d-267">FI</span><span class="sxs-lookup"><span data-stu-id="9622d-267">FI</span></span>      |<span data-ttu-id="9622d-268">FI2112345600000785</span><span class="sxs-lookup"><span data-stu-id="9622d-268">FI2112345600000785</span></span>         |
        |<span data-ttu-id="9622d-269">5</span><span class="sxs-lookup"><span data-stu-id="9622d-269">5</span></span>     |  <span data-ttu-id="9622d-270">フランス SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-270">France SEPA</span></span>       |   <span data-ttu-id="9622d-271">FR</span><span class="sxs-lookup"><span data-stu-id="9622d-271">FR</span></span>      |<span data-ttu-id="9622d-272">FR1420041010050500013M02606</span><span class="sxs-lookup"><span data-stu-id="9622d-272">FR1420041010050500013M02606</span></span>         |
        |<span data-ttu-id="9622d-273">6</span><span class="sxs-lookup"><span data-stu-id="9622d-273">6</span></span>     |  <span data-ttu-id="9622d-274">ドイツ SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-274">Germany SEPA</span></span>      |   <span data-ttu-id="9622d-275">DE</span><span class="sxs-lookup"><span data-stu-id="9622d-275">DE</span></span>      |<span data-ttu-id="9622d-276">DE89370400440532013000</span><span class="sxs-lookup"><span data-stu-id="9622d-276">DE89370400440532013000</span></span>         |
        |<span data-ttu-id="9622d-277">7</span><span class="sxs-lookup"><span data-stu-id="9622d-277">7</span></span>     |  <span data-ttu-id="9622d-278">ギリシャ SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-278">Greece SEPA</span></span>       |   <span data-ttu-id="9622d-279">GR</span><span class="sxs-lookup"><span data-stu-id="9622d-279">GR</span></span>      |<span data-ttu-id="9622d-280">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="9622d-280">GR1601101250000000012300695</span></span>         |
        |<span data-ttu-id="9622d-281">8</span><span class="sxs-lookup"><span data-stu-id="9622d-281">8</span></span>     |  <span data-ttu-id="9622d-282">イタリア SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-282">Italy SEPA</span></span>       |    <span data-ttu-id="9622d-283">IT</span><span class="sxs-lookup"><span data-stu-id="9622d-283">IT</span></span>     |<span data-ttu-id="9622d-284">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="9622d-284">GR1601101250000000012300695</span></span>         |
        |<span data-ttu-id="9622d-285">9</span><span class="sxs-lookup"><span data-stu-id="9622d-285">9</span></span>     |  <span data-ttu-id="9622d-286">オランダ SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-286">Netherlands SEPA</span></span>      |   <span data-ttu-id="9622d-287">NL</span><span class="sxs-lookup"><span data-stu-id="9622d-287">NL</span></span>      |   <span data-ttu-id="9622d-288">NL91ABNA0417164300</span><span class="sxs-lookup"><span data-stu-id="9622d-288">NL91ABNA0417164300</span></span>      |
        |<span data-ttu-id="9622d-289">10</span><span class="sxs-lookup"><span data-stu-id="9622d-289">10</span></span>     | <span data-ttu-id="9622d-290">ポーランド SEPA</span><span class="sxs-lookup"><span data-stu-id="9622d-290">Poland SEPA</span></span>       |  <span data-ttu-id="9622d-291">PL</span><span class="sxs-lookup"><span data-stu-id="9622d-291">PL</span></span>       | <span data-ttu-id="9622d-292">PL27114020040000300201355387</span><span class="sxs-lookup"><span data-stu-id="9622d-292">PL27114020040000300201355387</span></span>        |

<span data-ttu-id="9622d-293">メモ:- このサンプル データ セットは、公開されている情報から得られたもので、テスト目的でのみ使用することを意図しています。</span><span class="sxs-lookup"><span data-stu-id="9622d-293">Note:- This sample data set is derived from publicly available information and is intended to be used for test purposes only.</span></span>

23. <span data-ttu-id="9622d-294">電子メールの本文に IBAN が含まれ、メッセージ ウィンドウの上部にポリシー ヒントが表示されることが DLP ポリシーで認識されたことが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9622d-294">You will see that the DLP policy recognized that body of the email contains IBANs and provides you with the policy tip at the top of the message window.</span></span>
24. <span data-ttu-id="9622d-295">ブラウザーのプライベート インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9622d-295">Close the private instance of your browser.</span></span>


## <a name="phase-6-demonstrate-reporting"></a><span data-ttu-id="9622d-296">フェーズ 6: レポート機能をデモする</span><span class="sxs-lookup"><span data-stu-id="9622d-296">Phase 6: Demonstrate reporting</span></span>
 
<span data-ttu-id="9622d-297">このフェーズでは、フェーズ 5 で構成した DLP ポリシーに基づいて Office 365 のレポート機能をデモします。</span><span class="sxs-lookup"><span data-stu-id="9622d-297">In this phase, you demonstrate Office 365 reporting based on the DLP policy configured in Phase 5.</span></span>

   1. <span data-ttu-id="9622d-298">ブラウザーの [セキュリティとコンプライアンス] タブで、**[ホーム]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-298">From the Security & Compliance tab of your browser, click **Home**.</span></span>
   2. <span data-ttu-id="9622d-299">**[レポート]** > **[ダッシュボード]** > **[DLP ポリシー一致]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9622d-299">Click **Reports** > **Dashboard** > **DLP policy matches**.</span></span>
   3. <span data-ttu-id="9622d-p118">DLP ポリシーは、組織の機密情報の特定と保護に役立ちます。たとえば、レポートには、SharePoint Online に保存された IBAN を含むドキュメントがポリシーで特定されたことが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9622d-p118">Your DLP policy helps identify and protect organization's sensitive information. For example, in the report you will see that the policy identified the document that contains IBANs stored in SharePoint Online.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9622d-302">関連項目</span><span class="sxs-lookup"><span data-stu-id="9622d-302">See Also</span></span>

[<span data-ttu-id="9622d-303">GDPR のための Office 365 の情報保護</span><span class="sxs-lookup"><span data-stu-id="9622d-303">Office 365 Information Protection for GDPR</span></span>](office-365-information-protection-for-gdpr.md)

[<span data-ttu-id="9622d-304">Microsoft 365 に関する GDPR</span><span class="sxs-lookup"><span data-stu-id="9622d-304">GDPR for Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/compliance/gdpr?toc=/microsoft-365/enterprise/toc.json)
