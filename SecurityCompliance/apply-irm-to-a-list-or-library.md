---
title: リストまたはライブラリに Information Rights Management (IRM) を適用する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
description: Information Rights Management (IRM) を使用すると、リストまたはライブラリからダウンロードされたファイルを制御し、保護することができます。
ms.openlocfilehash: ae07136cf128f167695f667cc8a149492287f498
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220417"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a><span data-ttu-id="277b3-103">リストまたはライブラリに Information Rights Management (IRM) を適用する</span><span class="sxs-lookup"><span data-stu-id="277b3-103">Apply Information Rights Management (IRM) to a list or library</span></span>

<span data-ttu-id="277b3-104">Information Rights Management (IRM) を使用すると、リストまたはライブラリからダウンロードされたファイルを制御し、保護することができます。</span><span class="sxs-lookup"><span data-stu-id="277b3-104">You can use Information Rights Management (IRM) to help control and protect files that are downloaded from lists or libraries.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="277b3-105">始める前に</span><span class="sxs-lookup"><span data-stu-id="277b3-105">Before you begin</span></span>

- <span data-ttu-id="277b3-p101">azure information Protection からの azure Rights management サービス (azure RMS) と、オンプレミスの Active Directory Rights management サービス (AD RMS) は、サイトの information Rights management をサポートしています。個別または追加のインストールは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="277b3-p101">The Azure Rights Management service (Azure RMS) from Azure Information Protection, and the on-premises equivalent, Active Directory Rights Management Services (AD RMS), support Information Rights Management for sites. No separate or additional installations are required.</span></span>
    
- <span data-ttu-id="277b3-108">IRM をリストまたはライブラリに適用する前に、サイトの管理者が IRM を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="277b3-108">Before you apply IRM to a list or library it must first be enabled by an administrator for your site.</span></span>
    
- <span data-ttu-id="277b3-109">リストまたはライブラリに IRM を適用するには、そのリストまたはライブラリに対する管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="277b3-109">To apply IRM to a list or library, you must have administrator permissions for that list or library.</span></span>
    
- <span data-ttu-id="277b3-p102">SharePoint Online を使用している場合は、IRM で保護された大規模なファイルをダウンロードするときにタイムアウトが発生することがあります。このような場合は、Office プログラムを使用して irm 保護を適用し、irm を使用しない SharePoint ライブラリに大きなファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="277b3-p102">If you are using SharePoint Online, your users might experience timeouts when downloading larger IRM-protected files. If this happens, then apply IRM protection by using your Office programs, and store larger files in a SharePoint library that does not use IRM.</span></span>
    
> [!NOTE]
> <span data-ttu-id="277b3-112">SharePoint server 2013 を使用している場合は、組織内のユーザーが IRM を使用して保護するすべてのファイルの種類について、サーバー管理者がすべてのフロントエンド Web サーバーにプロテクターをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="277b3-112">If you're using SharePoint Server 2013, a server administrator must install protectors on all front-end Web servers for every file type that the people in your organization want to protect by using IRM.</span></span> 
  
## <a name="apply-irm-to-a-list-or-library"></a><span data-ttu-id="277b3-113">リストまたはライブラリに IRM を適用する</span><span class="sxs-lookup"><span data-stu-id="277b3-113">Apply IRM to a list or library</span></span>
<span data-ttu-id="277b3-114"><a name="__toc256598179"> </a></span><span class="sxs-lookup"><span data-stu-id="277b3-114"></span></span>

![Information Rights Management の設定](media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. <span data-ttu-id="277b3-116">IRM を構成するリストまたはライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="277b3-116">Go to the list or library for which you want to configure IRM.</span></span>
    
2. <span data-ttu-id="277b3-p103">リボンの [**ライブラリ**] タブをクリックし、[**ライブラリの設定**] をクリックします。(リストで作業している場合は、[**リスト**] タブをクリックし、[**リストの設定**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="277b3-p103">On the ribbon, click the **Library** tab, and then click **Library Settings**. (If you are working in a list, click the **List** tab, and then click **List Settings**).</span></span>
    
    ![リボンの [SharePoint ライブラリの設定] ボタン](media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. <span data-ttu-id="277b3-p104">[**権限と管理**] で、[ **Information Rights Management**] をクリックします。Information Rights Management のリンクが表示されない場合は、サイトで IRM が有効になっていない可能性があります。サイトで IRM を有効にできるかどうかを確認するには、サーバー管理者に問い合わせてください。画像ライブラリの Information Rights Management リンクは表示されません。</span><span class="sxs-lookup"><span data-stu-id="277b3-p104">Under **Permissions and Management**, click **Information Rights Management**. If the Information Rights Management link does not appear, IRM might not be enabled for your site. Contact your server administrator to see if it is possible to enable IRM for your site. The Information Rights Management link does not appear for picture libraries.</span></span>
    
4. <span data-ttu-id="277b3-124">[ **Information Rights Management の設定**] ページで、[**このライブラリ内のドキュメントに対するアクセスをダウンロード時に制限**する] チェックボックスをオンにして、このリストまたはライブラリからダウンロードされるドキュメントに制限されたアクセス許可を適用します。</span><span class="sxs-lookup"><span data-stu-id="277b3-124">On the **Information Rights Management Settings** page, select the **Restrict permission to documents in this library on download** check box to apply restricted permission to documents that are downloaded from this list or library.</span></span> 
    
5. <span data-ttu-id="277b3-p105">[**アクセス許可ポリシーのタイトルの作成**] ボックスに、このポリシーを他のポリシーと区別するために後で使用できる、わかりやすい名前を入力します。たとえば、機密扱いの会社のドキュメントが含まれるリストまたはライブラリに制限付きアクセス許可を適用する場合は、「**会社の機密**」と入力できます。</span><span class="sxs-lookup"><span data-stu-id="277b3-p105">In the **Create a permission policy title** box, type a descriptive name for the policy that you can use later to differentiate this policy from other policies. For example, you can type **Company Confidential** if you are applying restricted permission to a list or library that will contain company documents that are confidential.</span></span> 
    
6. <span data-ttu-id="277b3-p106">[**アクセス許可ポリシーの説明を追加**します] ボックスに、このリストまたはライブラリを使用するユーザーに表示される説明を入力します。このリストまたはライブラリでドキュメントをどのように処理するかを説明します。たとえば、これらのドキュメントの情報へのアクセスを内部の従業員に制限する必要がある場合は、[**他の従業員とのみ、このドキュメントの内容について意見**を入力できます。</span><span class="sxs-lookup"><span data-stu-id="277b3-p106">In the **Add a permission policy description** box, type a description that will appear to people who use this list or library that explains how they should handle the documents in this list or library. For example, you can type **Discuss the contents of this document only with other employees** if you want to restrict access to the information in these documents to internal employees.</span></span> 
    
7. <span data-ttu-id="277b3-129">このリストまたはライブラリ内のドキュメントに追加の制限を適用するには、[**オプションの表示**] をクリックして、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="277b3-129">To apply additional restrictions to the documents in this list or library, click **Show Options**, and do any of the following:</span></span>
    
|<span data-ttu-id="277b3-130">**これを実行するには、次の手順に従います。**</span><span class="sxs-lookup"><span data-stu-id="277b3-130">**To do this:**</span></span>|<span data-ttu-id="277b3-131">**次の手順を実行します。**</span><span class="sxs-lookup"><span data-stu-id="277b3-131">**Do this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="277b3-132">ユーザーにこのリストまたはライブラリからのドキュメントの印刷を許可する</span><span class="sxs-lookup"><span data-stu-id="277b3-132">Allow people to print documents from this list or library</span></span>  <br/> |<span data-ttu-id="277b3-133">[**閲覧者に印刷を許可**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="277b3-133">Select the **Allow viewers to print** check box.</span></span>  <br/> |
|<span data-ttu-id="277b3-134">少なくとも、アイテムの表示権限を持つユーザーがドキュメントに対して埋め込みコードまたはマクロを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="277b3-134">Allow people with at least the View Items permission to run embedded code or macros on a document.</span></span>  <br/> |<span data-ttu-id="277b3-135">[**閲覧者に、ダウンロードしたドキュメントで機能するようにスクリーンリーダーを許可**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="277b3-135">Select the **Allow viewers to run script and screen reader to function on downloaded documents** check box.</span></span>  <br/> <span data-ttu-id="277b3-136">このオプションを選択すると、ユーザーはコードを実行してドキュメントのコンテンツを抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="277b3-136">If you select this option, users could run code to extract the contents of a document.</span></span>           |
|<span data-ttu-id="277b3-137">ユーザーが特定の間隔で資格情報を確認することを要求します。</span><span class="sxs-lookup"><span data-stu-id="277b3-137">Require that people verify their credentials at specific intervals.</span></span>  <br/> <span data-ttu-id="277b3-p107">指定した期間だけコンテンツへのアクセスを制限する場合は、このオプションを選択します。このオプションを選択すると、指定した日数が経過すると、ユーザーの発行ライセンスが有効期限切れになり、ユーザーはサーバーに戻って資格情報を確認し、新しいコピーをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="277b3-p107">Select this option if you want to restrict access to content to a specified period of time. If you select this option, people's issuance licenses to access the content will expire after the specified number of days, and people will be required to return to the server to verify their credentials and download a new copy.</span></span>  <br/> |<span data-ttu-id="277b3-140">[**ユーザーがこの間隔 (日数) を使用して資格情報を確認する必要がある**] チェックボックスをオンにして、ドキュメントを表示できる日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="277b3-140">Select the **Users must verify their credentials using this interval (days)** check box, and then specify the number of days for which you want the document to be viewable.</span></span>  <br/> |
| <span data-ttu-id="277b3-141">IRM をサポートしていないドキュメントをこのリストまたはライブラリにアップロードできないようにします。</span><span class="sxs-lookup"><span data-stu-id="277b3-141">Prevent people from uploading documents that do not support IRM to this list or library.</span></span>  <br/>  <span data-ttu-id="277b3-142">このオプションを選択すると、ユーザーは次のファイルの種類をアップロードできなくなります。</span><span class="sxs-lookup"><span data-stu-id="277b3-142">If you select this option, people will not be able to upload any of the following file types:</span></span>  <br/>  <span data-ttu-id="277b3-143">対応する IRM プロテクターがすべてのフロントエンド Web サーバーにインストールされていないファイルの種類。</span><span class="sxs-lookup"><span data-stu-id="277b3-143">File types that do not have corresponding IRM protectors installed on all of the front-end Web servers.</span></span>  <br/>  <span data-ttu-id="277b3-144">SharePoint Server 2010 が復号化できないファイルの種類。</span><span class="sxs-lookup"><span data-stu-id="277b3-144">File types that SharePoint Server 2010 cannot decrypt.</span></span>  <br/>  <span data-ttu-id="277b3-145">他のプログラムで IRM で保護されているファイルの種類</span><span class="sxs-lookup"><span data-stu-id="277b3-145">File types that are IRM protected in another program</span></span>  <br/> |<span data-ttu-id="277b3-146">[ **IRM をサポートしないドキュメントのアップロードをユーザーに許可**しない] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="277b3-146">Select the **Do not allow users to upload documents that do not support IRM** check box.</span></span>  <br/> |
|<span data-ttu-id="277b3-147">特定の日付のこのリストまたはライブラリから制限付きアクセス許可を削除します。</span><span class="sxs-lookup"><span data-stu-id="277b3-147">Remove restricted permissions from this list or library on a specific date.</span></span>  <br/> |<span data-ttu-id="277b3-148">[**ライブラリへのアクセスの制限を解除**する] チェックボックスをオンにして、目的の日付を選択します。</span><span class="sxs-lookup"><span data-stu-id="277b3-148">Select the **Stop restricting access to the library at** check box, and then select the date that you want.</span></span>  <br/> |
|<span data-ttu-id="277b3-149">ドキュメントを開くためにライセンスが付与されているプログラムの資格情報がキャッシュされる間隔を制御します。</span><span class="sxs-lookup"><span data-stu-id="277b3-149">Control the interval that credentials are cached for the program that is licensed to open the document.</span></span>  <br/> |<span data-ttu-id="277b3-150">[**グループ保護と資格情報の設定間隔**] で、[資格情報の保持期間 (日数)] を入力します。</span><span class="sxs-lookup"><span data-stu-id="277b3-150">In the **Set group protection and credentials interval**, enter theinterval for caching credentials in number of days.</span></span>  <br/> |
|<span data-ttu-id="277b3-151">グループ保護を許可して、ユーザーが同じグループのメンバーと共有できるようにします。</span><span class="sxs-lookup"><span data-stu-id="277b3-151">Allow group protection so that users can share with members of the same group.</span></span>  <br/> |<span data-ttu-id="277b3-152">[**グループ保護の許可**] を選択し、共有するグループの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="277b3-152">Select **Allow group protection**, and enter the group's name for sharing.</span></span>  <br/> |
   
8. <span data-ttu-id="277b3-153">必要なオプションを選択したら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="277b3-153">After you finish selecting the options you want, click **OK**.</span></span>
  
## <a name="what-is-information-rights-management"></a><span data-ttu-id="277b3-154">Information Rights Management とは</span><span class="sxs-lookup"><span data-stu-id="277b3-154">What is Information Rights Management?</span></span>
<span data-ttu-id="277b3-155"><a name="__toc256598175"> </a></span><span class="sxs-lookup"><span data-stu-id="277b3-155"></span></span>

<span data-ttu-id="277b3-p108">Information Rights Management (IRM) を使用すると、ユーザーがリストまたはライブラリからダウンロードされたファイルに対して実行できる操作を制限できます。IRM では、ダウンロードしたファイルが暗号化され、これらのファイルの暗号化を解除できるユーザーとプログラムのセットが制限されます。また、ファイルのコピーを印刷したり、ファイルからテキストをコピーしたりする操作を実行できないように、ファイルの読み取りが許可されているユーザーの権限を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="277b3-p108">Information Rights Management (IRM) enables you to limit the actions that users can take on files that have been downloaded from lists or libraries. IRM encrypts the downloaded files and limits the set of users and programs that are allowed to decrypt these files. IRM can also limit the rights of the users who are allowed to read files, so that they cannot take actions such as print copies of the files or copy text from them.</span></span>
  
<span data-ttu-id="277b3-p109">リストまたはライブラリで IRM を使用して、機密コンテンツの伝達を制限することができます。たとえば、今後の製品に関する情報を選択されたマーケティング担当者と共有するためにドキュメントライブラリを作成している場合は、IRM を使用して、このようなユーザーが会社の他の従業員とこのコンテンツを共有できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="277b3-p109">You can use IRM on lists or libraries to limit the dissemination of sensitive content. For example, if you are creating a document library to share information about upcoming products with selected marketing representatives, you can use IRM to prevent these individuals from sharing this content with other employees in the company.</span></span>
  
<span data-ttu-id="277b3-p110">サイトでは、個々のファイルではなく、リストまたはライブラリ全体に IRM を適用します。これにより、ドキュメントやファイルのセット全体に対して一貫したレベルの保護を実現することが容易になります。これにより、IRM により、機密情報の使用と伝達を管理する企業ポリシーを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="277b3-p110">On a site, you apply IRM to an entire list or library, rather than to individual files. This makes it easier to ensure a consistent level of protection for an entire set of documents or files. IRM can thus help your organization to enforce corporate policies that govern the use and dissemination of confidential or proprietary information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="277b3-164">information rights management に関するこのページの情報は、Microsoft sharepoint server 2013 および SharePoint Server 2016 ライセンス条項契約で「information rights management」を参照している用語よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="277b3-164">The information on this page regarding Information Rights Management supersedes any terms that reference 'Information Rights Management' in any Microsoft SharePoint Server 2013 and SharePoint Server 2016 license term agreements.</span></span> 
  
### <a name="how-irm-can-help-protect-content"></a><span data-ttu-id="277b3-165">IRM がコンテンツを保護するための方法</span><span class="sxs-lookup"><span data-stu-id="277b3-165">How IRM can help protect content</span></span>
<span data-ttu-id="277b3-166"><a name="__toc256598176"> </a></span><span class="sxs-lookup"><span data-stu-id="277b3-166"></span></span>

<span data-ttu-id="277b3-167">IRM では、制限されたコンテンツを次の方法で保護することができます。</span><span class="sxs-lookup"><span data-stu-id="277b3-167">IRM helps to protect restricted content in the following ways:</span></span>
  
- <span data-ttu-id="277b3-168">権限のない使用のためにコンテンツのコピー、変更、印刷、fax 送受信、またはコピーと貼り付けが行われないようにするために役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="277b3-168">Helps to prevent an authorized viewer from copying, modifying, printing, faxing, or copying and pasting the content for unauthorized use</span></span>
    
- <span data-ttu-id="277b3-169">Microsoft Windows の印刷画面機能を使用して、承認済みの閲覧者がコンテンツをコピーできないようにするために使用します。</span><span class="sxs-lookup"><span data-stu-id="277b3-169">Helps to prevent an authorized viewer from copying the content by using the Print Screen feature in Microsoft Windows</span></span>
    
- <span data-ttu-id="277b3-170">サーバーからダウンロードされた後に電子メールで送信された場合に、承認されていない閲覧者がコンテンツを表示できないようにするために役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="277b3-170">Helps to prevent an unauthorized viewer from viewing the content if it is sent in e-mail after it is downloaded from the server</span></span>
    
- <span data-ttu-id="277b3-171">指定した期間だけコンテンツへのアクセスを制限します。その後、ユーザーが資格情報を確認してからコンテンツを再度ダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="277b3-171">Restricts access to content to a specified period of time, after which users must confirm their credentials and download the content again</span></span>
    
- <span data-ttu-id="277b3-172">組織内のコンテンツの使用と配布を管理する企業ポリシーを適用するのに役立つ</span><span class="sxs-lookup"><span data-stu-id="277b3-172">Helps to enforce corporate policies that govern the use and dissemination of content within your organization</span></span>
    
### <a name="how-irm-cannot-help-protect-content"></a><span data-ttu-id="277b3-173">IRM でコンテンツを保護する方法</span><span class="sxs-lookup"><span data-stu-id="277b3-173">How IRM cannot help protect content</span></span>
<span data-ttu-id="277b3-174"><a name="__toc256598177"> </a></span><span class="sxs-lookup"><span data-stu-id="277b3-174"></span></span>

<span data-ttu-id="277b3-175">IRM では、制限されたコンテンツを次のように保護することはできません。</span><span class="sxs-lookup"><span data-stu-id="277b3-175">IRM cannot protect restricted content from the following:</span></span>
  
- <span data-ttu-id="277b3-176">悪意のあるプログラム (トロイの木馬、キー操作ロガー、特定の種類のスパイウェアなど) による消去、盗難、取り込み、送信</span><span class="sxs-lookup"><span data-stu-id="277b3-176">Erasure, theft, capture, or transmission by malicious programs such as Trojan horses, keystroke loggers, and certain types of spyware</span></span>
    
- <span data-ttu-id="277b3-177">コンピューターウイルスの処理による損失または破損</span><span class="sxs-lookup"><span data-stu-id="277b3-177">Loss or corruption because of the actions of computer viruses</span></span>
    
- <span data-ttu-id="277b3-178">画面に表示されるコンテンツを手動でコピーまたは再入力する</span><span class="sxs-lookup"><span data-stu-id="277b3-178">Manual copying or retyping of content from the display on a screen</span></span>
    
- <span data-ttu-id="277b3-179">画面に表示されるコンテンツのデジタルまたはフィルムの写真</span><span class="sxs-lookup"><span data-stu-id="277b3-179">Digital or film photography of content that is displayed on a screen</span></span>
    
- <span data-ttu-id="277b3-180">サードパーティ製の画面キャプチャプログラムを使用してコピーする</span><span class="sxs-lookup"><span data-stu-id="277b3-180">Copying through the use of third-party screen-capture programs</span></span>
    
- <span data-ttu-id="277b3-181">サードパーティ製の画面キャプチャプログラムまたはコピーと貼り付けの操作を使用したコンテンツメタデータ (列の値) のコピー</span><span class="sxs-lookup"><span data-stu-id="277b3-181">Copying of content metadata (column values) through the use of third-party screen-capture programs or copy-and-paste action</span></span>
    
[<span data-ttu-id="277b3-182">Information Rights Management をリストまたはライブラリに適用する</span><span class="sxs-lookup"><span data-stu-id="277b3-182">Apply Information Rights Management to a list or library</span></span>](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a><span data-ttu-id="277b3-183">リストとライブラリの IRM のしくみ</span><span class="sxs-lookup"><span data-stu-id="277b3-183">How IRM works for lists and libraries</span></span>
<span data-ttu-id="277b3-184"><a name="__toc256598178"> </a></span><span class="sxs-lookup"><span data-stu-id="277b3-184"></span></span>

<span data-ttu-id="277b3-p111">IRM 保護は、リストまたはライブラリレベルでファイルに適用されます。ライブラリで IRM が有効になっている場合、rights management はそのライブラリ内のすべてのファイルに適用されます。リストに対して IRM が有効になっている場合、rights management は、実際のリストアイテムではなく、リストアイテムに添付されているファイルにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="277b3-p111">IRM protection is applied to files at the list or library level. When IRM is enabled for a library, rights management applies to all of the files in that library. When IRM is enabled for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="277b3-p112">ユーザーが IRM 対応リストまたはライブラリにファイルをダウンロードすると、承認されたユーザーのみがファイルを表示できるように、ファイルが暗号化されます。また、各権限管理ファイルには、ファイルを表示するユーザーに制限を課す発行ライセンスが含まれています。一般的な制限としては、ファイルを読み取り専用にし、テキストのコピーを無効にして、ユーザーがローカルコピーを保存しないようにしたり、ファイルを印刷できないようにしたりすることがあります。IRM がサポートするファイルの種類を読み取ることができるクライアントプログラムは、権限が管理されたファイル内の発行ライセンスを使用して、これらの制限を適用します。これは、権限が管理されたファイルがサーバーからダウンロードされた後でも、保護を保持する方法です。</span><span class="sxs-lookup"><span data-stu-id="277b3-p112">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them. Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file. Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file. Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions. This is how a rights-managed file retains its protection even after it is downloaded from the server.</span></span>
  
<span data-ttu-id="277b3-p113">リストまたはライブラリからファイルをダウンロードするときに適用される制限の種類は、そのファイルを含むサイトに対する個々のユーザーのアクセス許可に基づいています。次の表では、サイトのアクセス許可が IRM アクセス許可とどのように対応するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="277b3-p113">The types of restrictions that are applied to a file when it is downloaded from a list or library are based on the individual user's permissions on the site that contains the file. The following table explains how the permissions on sites correspond to IRM permissions.</span></span>
  
|<span data-ttu-id="277b3-195">**アクセス許可**</span><span class="sxs-lookup"><span data-stu-id="277b3-195">**Permissions**</span></span>|<span data-ttu-id="277b3-196">**IRM アクセス許可**</span><span class="sxs-lookup"><span data-stu-id="277b3-196">**IRM Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="277b3-197">権限の管理、Web サイトの管理</span><span class="sxs-lookup"><span data-stu-id="277b3-197">Manage Permissions, Manage Web Site</span></span>  <br/> |<span data-ttu-id="277b3-198">**フルコントロール**(クライアントプログラムによって定義されています): この権限は、通常、権限が管理されたコンテンツの読み取り、編集、コピー、保存、および変更のアクセス許可をユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="277b3-198">**Full control** (as defined by the client program): This permission generally allows a user to read, edit, copy, save, and modify permissions of rights-managed content.</span></span>  <br/> |
|<span data-ttu-id="277b3-199">アイテムの編集、リストの管理、ページの追加とカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="277b3-199">Edit Items, Manage Lists, Add and Customize Pages</span></span>  <br/> |<span data-ttu-id="277b3-200">[**編集**]、[**コピー**]、[**保存**]: リストまたはライブラリの [Information Rights Management の設定] ページで、[**ユーザーにドキュメントの印刷を許可する**] チェックボックスがオンになっている場合にのみ、ファイルを印刷できます。</span><span class="sxs-lookup"><span data-stu-id="277b3-200">**Edit**, **Copy**, and **Save**: A user can print a file only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>  <br/> |
|<span data-ttu-id="277b3-201">アイテムの表示</span><span class="sxs-lookup"><span data-stu-id="277b3-201">View Items</span></span>  <br/> |<span data-ttu-id="277b3-p114">**読み取り**: ユーザーはドキュメントを読み取ることはできますが、コンテンツをコピーまたは変更することはできません。リストまたはライブラリの [Information Rights Management の設定] ページで、[ユーザー**にドキュメントの印刷を許可する**] チェックボックスがオンになっている場合にのみ、印刷を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="277b3-p114">**Read**: A user can read the document, but cannot copy or modify its content. A user can print only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.  </span></span><br/> |
|<span data-ttu-id="277b3-204">その他</span><span class="sxs-lookup"><span data-stu-id="277b3-204">Other</span></span>  <br/> |<span data-ttu-id="277b3-205">IRM アクセス許可に直接対応するその他のアクセス許可はありません。</span><span class="sxs-lookup"><span data-stu-id="277b3-205">No other permissions correspond directly to IRM permissions.</span></span>  <br/> |
   
<span data-ttu-id="277b3-p115">SharePoint Server 2013 のリストまたはライブラリで IRM を有効にする場合、すべてのフロントエンド Web サーバーにプロテクターがインストールされているリストまたはライブラリ内のファイルの種類のみを保護できます。プロテクターは、特定のファイル形式の権限が管理されたファイルの暗号化と復号化を制御するプログラムです。SharePoint には、次のファイルの種類のプロテクターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="277b3-p115">When you enable IRM for a list or library in SharePoint Server 2013, you can only protect file types in that list or library for which a protector is installed on all front-end Web servers. A protector is a program that controls the encryption and decryption of rights-managed files of a specific file format. SharePoint includes protectors for the following file types:</span></span>
  
- <span data-ttu-id="277b3-209">Microsoft Office InfoPath フォーム</span><span class="sxs-lookup"><span data-stu-id="277b3-209">Microsoft Office InfoPath forms</span></span>
    
- <span data-ttu-id="277b3-210">次の Microsoft Office プログラムの97-2003 ファイル形式: Word、Excel、および PowerPoint</span><span class="sxs-lookup"><span data-stu-id="277b3-210">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="277b3-211">office Open XML 形式の次の Microsoft Office プログラム: Word、Excel、および PowerPoint</span><span class="sxs-lookup"><span data-stu-id="277b3-211">The Office Open XML Formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="277b3-212">XML Paper Specification (XPS) 形式</span><span class="sxs-lookup"><span data-stu-id="277b3-212">The XML Paper Specification (XPS) format</span></span>
    
<span data-ttu-id="277b3-213">前述のファイル形式に加えて、IRM を使用して他のファイルの種類を保護することを組織で計画している場合は、サーバー管理者がその他のファイル形式用にプロテクターをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="277b3-213">If your organization plans to use IRM to protect any other file types in addition to those listed above, your server administrator must install protectors for these additional file formats.</span></span>
  

