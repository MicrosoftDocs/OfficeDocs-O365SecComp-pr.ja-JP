---
title: 情報権利管理 (IRM) をリストまたはライブラリに適用します。
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
description: 情報権利管理 (IRM) は、コントロールのヘルプし、リストまたはライブラリからダウンロードしたファイルを保護するために使用できます。
ms.openlocfilehash: 5a48abf13841716d4dba34311d69ca2e6a5ea422
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532079"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a><span data-ttu-id="6742e-103">情報権利管理 (IRM) をリストまたはライブラリに適用します。</span><span class="sxs-lookup"><span data-stu-id="6742e-103">Apply Information Rights Management (IRM) to a list or library</span></span>

<span data-ttu-id="6742e-104">情報権利管理 (IRM) は、コントロールのヘルプし、リストまたはライブラリからダウンロードしたファイルを保護するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="6742e-104">You can use Information Rights Management (IRM) to help control and protect files that are downloaded from lists or libraries.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="6742e-105">はじめに</span><span class="sxs-lookup"><span data-stu-id="6742e-105">Before you begin</span></span>

- <span data-ttu-id="6742e-p101">Azure の情報の保護、および設置型と同じ、Active Directory Rights Management サービス (AD RMS) から Azure 権限管理サービス (Azure RMS) は、サイトの情報権利管理をサポートします。個別または追加インストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6742e-p101">The Azure Rights Management service (Azure RMS) from Azure Information Protection, and the on-premises equivalent, Active Directory Rights Management Services (AD RMS), support Information Rights Management for sites. No separate or additional installations are required.</span></span>
    
- <span data-ttu-id="6742e-108">リストまたはライブラリに IRM を適用する前に、サイトの管理者は、最初有効する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6742e-108">Before you apply IRM to a list or library it must first be enabled by an administrator for your site.</span></span>
    
- <span data-ttu-id="6742e-109">リストまたはライブラリに IRM を適用するには、そのリストまたはライブラリに対する管理者アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="6742e-109">To apply IRM to a list or library, you must have administrator permissions for that list or library.</span></span>
    
- <span data-ttu-id="6742e-p102">SharePoint Online を使用する場合は場合、ユーザーで大規模な IRM で保護されたファイルをダウンロードするときにタイムアウトが発生可能性があります。このような場合、Office プログラムを使用して、IRM による保護を適用し、IRM を使用していない SharePoint ライブラリにサイズの大きいファイルを格納します。</span><span class="sxs-lookup"><span data-stu-id="6742e-p102">If you are using SharePoint Online, your users might experience timeouts when downloading larger IRM-protected files. If this happens, then apply IRM protection by using your Office programs, and store larger files in a SharePoint library that does not use IRM.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6742e-112">SharePoint Server 2013 を使用する場合、サーバー管理者は、組織内のユーザーが IRM を使用して保護するために必要なすべてのファイルの種類のすべてのフロント エンド Web サーバーにプロテクターをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6742e-112">If you're using SharePoint Server 2013, a server administrator must install protectors on all front-end Web servers for every file type that the people in your organization want to protect by using IRM.</span></span> 
  
## <a name="apply-irm-to-a-list-or-library"></a><span data-ttu-id="6742e-113">リストまたはライブラリに IRM を適用します。</span><span class="sxs-lookup"><span data-stu-id="6742e-113">Apply IRM to a list or library</span></span>
<span data-ttu-id="6742e-114"><a name="__toc256598179"> </a></span><span class="sxs-lookup"><span data-stu-id="6742e-114"></span></span>

![情報権利の管理の設定](media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. <span data-ttu-id="6742e-116">IRM を構成するリストまたはライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="6742e-116">Go to the list or library for which you want to configure IRM.</span></span>
    
2. <span data-ttu-id="6742e-p103">リボンで、[**ライブラリ**] タブをクリックし、**ライブラリの設定**] をクリックします。(**リスト**] タブをクリックして、ボックスの一覧で作業している場合と、[**リストの設定**] をクリックして)。</span><span class="sxs-lookup"><span data-stu-id="6742e-p103">On the ribbon, click the **Library** tab, and then click **Library Settings**. (If you are working in a list, click the **List** tab, and then click **List Settings**).</span></span>
    
    ![リボン上の SharePoint ライブラリの設定ボタン](media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. <span data-ttu-id="6742e-p104">[**権限と管理**、**情報権利の管理**] をクリックします。情報権利管理のリンクが表示されない場合は、サイトの IRM が有効にできない可能性があります。サイトに対して IRM を有効にするかどうかをサーバー管理者に問い合わせてください。情報権利管理のリンクは、画像ライブラリには表示されません。</span><span class="sxs-lookup"><span data-stu-id="6742e-p104">Under **Permissions and Management**, click **Information Rights Management**. If the Information Rights Management link does not appear, IRM might not be enabled for your site. Contact your server administrator to see if it is possible to enable IRM for your site. The Information Rights Management link does not appear for picture libraries.</span></span>
    
4. <span data-ttu-id="6742e-124">[ **Information Rights Management 設定**] ページでは、このリストまたはライブラリからダウンロードされるドキュメントにアクセス許可の制限を適用するには、**ダウンロード時にこのライブラリのドキュメントに対するアクセス許可を制限する**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="6742e-124">On the **Information Rights Management Settings** page, select the **Restrict permission to documents in this library on download** check box to apply restricted permission to documents that are downloaded from this list or library.</span></span> 
    
5. <span data-ttu-id="6742e-p105">**作成アクセス許可ポリシーのタイトル**] ボックスでは、このポリシーを他のポリシーから区別するために後で使用できるポリシーのわかりやすい名前を入力します。などを入力できます**社外秘**] ボックスの一覧または機密扱いの社内文書を格納するライブラリにアクセス許可の制限を適用する場合。</span><span class="sxs-lookup"><span data-stu-id="6742e-p105">In the **Create a permission policy title** box, type a descriptive name for the policy that you can use later to differentiate this policy from other policies. For example, you can type **Company Confidential** if you are applying restricted permission to a list or library that will contain company documents that are confidential.</span></span> 
    
6. <span data-ttu-id="6742e-p106">**追加のアクセス許可ポリシーの説明**] ボックスでは、このリストまたはこのリストまたはライブラリ内のドキュメントを処理する方法を説明するライブラリを使用するユーザーに表示される説明を入力します。など入力できます**社員には、このドキュメントの内容を説明**社内の従業員にこれらのドキュメント内の情報へのアクセスを制限する場合。</span><span class="sxs-lookup"><span data-stu-id="6742e-p106">In the **Add a permission policy description** box, type a description that will appear to people who use this list or library that explains how they should handle the documents in this list or library. For example, you can type **Discuss the contents of this document only with other employees** if you want to restrict access to the information in these documents to internal employees.</span></span> 
    
7. <span data-ttu-id="6742e-129">このリストまたはライブラリ内のドキュメントに追加の制限を適用するに**オプションを表示**] をクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6742e-129">To apply additional restrictions to the documents in this list or library, click **Show Options**, and do any of the following:</span></span>
    
|<span data-ttu-id="6742e-130">**これを実行するには、次の操作を実行します。**</span><span class="sxs-lookup"><span data-stu-id="6742e-130">**To do this:**</span></span>|<span data-ttu-id="6742e-131">**この操作を行います。**</span><span class="sxs-lookup"><span data-stu-id="6742e-131">**Do this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6742e-132">このリストまたはライブラリからドキュメントを印刷できるように</span><span class="sxs-lookup"><span data-stu-id="6742e-132">Allow people to print documents from this list or library</span></span>  <br/> |<span data-ttu-id="6742e-133">**印刷するビューアーを許可する**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="6742e-133">Select the **Allow viewers to print** check box.</span></span>  <br/> |
|<span data-ttu-id="6742e-134">許可するには、少なくともドキュメントで埋め込みコードやマクロを実行するアイテムの表示権限を持つユーザーです。</span><span class="sxs-lookup"><span data-stu-id="6742e-134">Allow people with at least the View Items permission to run embedded code or macros on a document.</span></span>  <br/> |<span data-ttu-id="6742e-135">**ビューアーをダウンロード済みのドキュメントの関数をスクリプトとスクリーンのリーダーを実行する**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="6742e-135">Select the **Allow viewers to run script and screen reader to function on downloaded documents** check box.</span></span>  <br/> <span data-ttu-id="6742e-136">このオプションを選択した場合、ユーザーはドキュメントの内容を抽出するコードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="6742e-136">If you select this option, users could run code to extract the contents of a document.</span></span>           |
|<span data-ttu-id="6742e-137">ユーザーが特定の間隔で資格情報を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6742e-137">Require that people verify their credentials at specific intervals.</span></span>  <br/> <span data-ttu-id="6742e-p107">一定の時間にコンテンツへのアクセスを制限する場合は、このオプションを選択します。このオプションを選択した場合、コンテンツにアクセスするユーザーの発行ライセンス期限切れになる日、およびユーザーの指定した数は、サーバーが資格情報を確認し、新しいコピーをダウンロードするに戻るには必要があります。</span><span class="sxs-lookup"><span data-stu-id="6742e-p107">Select this option if you want to restrict access to content to a specified period of time. If you select this option, people's issuance licenses to access the content will expire after the specified number of days, and people will be required to return to the server to verify their credentials and download a new copy.</span></span>  <br/> |<span data-ttu-id="6742e-140">選択して、**のユーザーがこの間隔を使用して資格情報を確認する必要があります (日)** チェック ボックスをオンし、ドキュメントを表示日数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6742e-140">Select the **Users must verify their credentials using this interval (days)** check box, and then specify the number of days for which you want the document to be viewable.</span></span>  <br/> |
| <span data-ttu-id="6742e-141">このリストまたはライブラリに IRM をサポートしていないドキュメントをアップロードできないようにするには。</span><span class="sxs-lookup"><span data-stu-id="6742e-141">Prevent people from uploading documents that do not support IRM to this list or library.</span></span>  <br/>  <span data-ttu-id="6742e-142">このオプションを選択すると、ユーザーは、次のファイルの種類のいずれかをアップロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6742e-142">If you select this option, people will not be able to upload any of the following file types:</span></span>  <br/>  <span data-ttu-id="6742e-143">対応する IRM プロテクターがすべてのフロント エンド Web サーバーにインストールされていないファイルの種類です。</span><span class="sxs-lookup"><span data-stu-id="6742e-143">File types that do not have corresponding IRM protectors installed on all of the front-end Web servers.</span></span>  <br/>  <span data-ttu-id="6742e-144">SharePoint Server 2010 の復号化できないファイルの種類です。</span><span class="sxs-lookup"><span data-stu-id="6742e-144">File types that SharePoint Server 2010 cannot decrypt.</span></span>  <br/>  <span data-ttu-id="6742e-145">別のプログラムで IRM 保護されているファイルの種類</span><span class="sxs-lookup"><span data-stu-id="6742e-145">File types that are IRM protected in another program</span></span>  <br/> |<span data-ttu-id="6742e-146">**IRM をサポートしていないドキュメントのアップロードを許可しない**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="6742e-146">Select the **Do not allow users to upload documents that do not support IRM** check box.</span></span>  <br/> |
|<span data-ttu-id="6742e-147">このリストまたはライブラリから特定の日付に制限されたアクセス許可を削除します。</span><span class="sxs-lookup"><span data-stu-id="6742e-147">Remove restricted permissions from this list or library on a specific date.</span></span>  <br/> |<span data-ttu-id="6742e-148">**ライブラリへのアクセスを制限することを停止**する] チェック ボックスをオンを選択し、使用する日付を選択します。</span><span class="sxs-lookup"><span data-stu-id="6742e-148">Select the **Stop restricting access to the library at** check box, and then select the date that you want.</span></span>  <br/> |
|<span data-ttu-id="6742e-149">文書を開くためのライセンスがプログラムの資格情報がキャッシュされる間隔を制御します。</span><span class="sxs-lookup"><span data-stu-id="6742e-149">Control the interval that credentials are cached for the program that is licensed to open the document.</span></span>  <br/> |<span data-ttu-id="6742e-150">**グループの保護および資格情報の間隔を設定**するには、日数で資格情報をキャッシュするため待ち時間を入力します。</span><span class="sxs-lookup"><span data-stu-id="6742e-150">In the **Set group protection and credentials interval**, enter theinterval for caching credentials in number of days.</span></span>  <br/> |
|<span data-ttu-id="6742e-151">グループの保護を許可するユーザーが同じグループのメンバーと共有できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6742e-151">Allow group protection so that users can share with members of the same group.</span></span>  <br/> |<span data-ttu-id="6742e-152">**グループの保護を許可する**を選択し、共有するためのグループの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6742e-152">Select **Allow group protection**, and enter the group's name for sharing.</span></span>  <br/> |
   
8. <span data-ttu-id="6742e-153">目的のオプションを選択したら、[ **OK**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6742e-153">After you finish selecting the options you want, click **OK**.</span></span>
  
## <a name="what-is-information-rights-management"></a><span data-ttu-id="6742e-154">情報権利の管理とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="6742e-154">What is Information Rights Management?</span></span>
<span data-ttu-id="6742e-155"><a name="__toc256598175"> </a></span><span class="sxs-lookup"><span data-stu-id="6742e-155"></span></span>

<span data-ttu-id="6742e-p108">情報権利管理 (IRM) を使用すると、リストまたはライブラリからダウンロードしたファイルに対してユーザーが実行できるアクションを制限できます。IRM では、ダウンロードしたファイルを暗号化して、ユーザーとこれらのファイルを復号化が許可されているプログラムのセットを制限します。IRM からテキストをコピーしたり、ファイルのコピーを印刷操作を実行できないように、ファイルの読み取りを許可されているユーザーの権限を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="6742e-p108">Information Rights Management (IRM) enables you to limit the actions that users can take on files that have been downloaded from lists or libraries. IRM encrypts the downloaded files and limits the set of users and programs that are allowed to decrypt these files. IRM can also limit the rights of the users who are allowed to read files, so that they cannot take actions such as print copies of the files or copy text from them.</span></span>
  
<span data-ttu-id="6742e-p109">リストまたはライブラリに対して IRM を使用して、機密性の高いコンテンツの配布を制限することができます。たとえば、特定のマーケティング担当者と今後の製品についての情報を共有するドキュメント ライブラリを作成する場合は、IRM を使用してこれらの担当者が会社の他の従業員にこのコンテンツを共有するを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="6742e-p109">You can use IRM on lists or libraries to limit the dissemination of sensitive content. For example, if you are creating a document library to share information about upcoming products with selected marketing representatives, you can use IRM to prevent these individuals from sharing this content with other employees in the company.</span></span>
  
<span data-ttu-id="6742e-p110">サイトでは、個々 のファイルではなく、リスト全体またはライブラリに IRM を適用します。やすく一貫性のあるドキュメントやファイルのセット全体の保護のレベルを確実にします。IRM のため、組織の使用と機密情報または専有情報の伝達に関する企業ポリシーを適用するに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6742e-p110">On a site, you apply IRM to an entire list or library, rather than to individual files. This makes it easier to ensure a consistent level of protection for an entire set of documents or files. IRM can thus help your organization to enforce corporate policies that govern the use and dissemination of confidential or proprietary information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6742e-164">情報権利の管理に関しては、このページ上の情報には、Microsoft SharePoint Server 2013 と SharePoint サーバーの 2016年ライセンス条件の契約での ' 情報権利管理」を参照しているすべての条件がより優先されます。</span><span class="sxs-lookup"><span data-stu-id="6742e-164">The information on this page regarding Information Rights Management supersedes any terms that reference 'Information Rights Management' in any Microsoft SharePoint Server 2013 and SharePoint Server 2016 license term agreements.</span></span> 
  
### <a name="how-irm-can-help-protect-content"></a><span data-ttu-id="6742e-165">IRM で行えるコンテンツ保護</span><span class="sxs-lookup"><span data-stu-id="6742e-165">How IRM can help protect content</span></span>
<span data-ttu-id="6742e-166"><a name="__toc256598176"> </a></span><span class="sxs-lookup"><span data-stu-id="6742e-166"></span></span>

<span data-ttu-id="6742e-167">IRM は、次の方法で制限されているコンテンツを保護するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6742e-167">IRM helps to protect restricted content in the following ways:</span></span>
  
- <span data-ttu-id="6742e-168">正当な閲覧者のコピー、変更、印刷、fax またはコピーおよび不正使用のコンテンツを貼り付けるを防ぐのに役立ちます</span><span class="sxs-lookup"><span data-stu-id="6742e-168">Helps to prevent an authorized viewer from copying, modifying, printing, faxing, or copying and pasting the content for unauthorized use</span></span>
    
- <span data-ttu-id="6742e-169">正当な閲覧者が Microsoft Windows の画面印刷機能を使用してコンテンツをコピーすることを防止するのに役立ちます</span><span class="sxs-lookup"><span data-stu-id="6742e-169">Helps to prevent an authorized viewer from copying the content by using the Print Screen feature in Microsoft Windows</span></span>
    
- <span data-ttu-id="6742e-170">不正な閲覧者がサーバーからダウンロードされた後に電子メールで送信された場合は、コンテンツを表示することを防止するのに役立ちます</span><span class="sxs-lookup"><span data-stu-id="6742e-170">Helps to prevent an unauthorized viewer from viewing the content if it is sent in e-mail after it is downloaded from the server</span></span>
    
- <span data-ttu-id="6742e-171">一定の時間、ユーザーする必要があります資格情報を確認し、コンテンツを再度ダウンロードするコンテンツへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="6742e-171">Restricts access to content to a specified period of time, after which users must confirm their credentials and download the content again</span></span>
    
- <span data-ttu-id="6742e-172">使用と、組織内のコンテンツの配布を管理する企業ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="6742e-172">Helps to enforce corporate policies that govern the use and dissemination of content within your organization</span></span>
    
### <a name="how-irm-cannot-help-protect-content"></a><span data-ttu-id="6742e-173">方法 IRM がコンテンツの保護を支援することはできません。</span><span class="sxs-lookup"><span data-stu-id="6742e-173">How IRM cannot help protect content</span></span>
<span data-ttu-id="6742e-174"><a name="__toc256598177"> </a></span><span class="sxs-lookup"><span data-stu-id="6742e-174"></span></span>

<span data-ttu-id="6742e-175">IRM では、次の制限されたコンテンツを保護することはできません。</span><span class="sxs-lookup"><span data-stu-id="6742e-175">IRM cannot protect restricted content from the following:</span></span>
  
- <span data-ttu-id="6742e-176">消去、盗難、取得、またはトロイの木馬、キー ロガー、スパイウェアなどの悪意のあるプログラムで送信</span><span class="sxs-lookup"><span data-stu-id="6742e-176">Erasure, theft, capture, or transmission by malicious programs such as Trojan horses, keystroke loggers, and certain types of spyware</span></span>
    
- <span data-ttu-id="6742e-177">コンピューター ウイルスによる紛失や破損</span><span class="sxs-lookup"><span data-stu-id="6742e-177">Loss or corruption because of the actions of computer viruses</span></span>
    
- <span data-ttu-id="6742e-178">手動コピーまたは画面に表示されたコンテンツからの再入力</span><span class="sxs-lookup"><span data-stu-id="6742e-178">Manual copying or retyping of content from the display on a screen</span></span>
    
- <span data-ttu-id="6742e-179">デジタルまたはフィルムによる撮影、画面に表示されているコンテンツの</span><span class="sxs-lookup"><span data-stu-id="6742e-179">Digital or film photography of content that is displayed on a screen</span></span>
    
- <span data-ttu-id="6742e-180">サード ・ パーティ製の画面取り込みプログラムを使ったコピー</span><span class="sxs-lookup"><span data-stu-id="6742e-180">Copying through the use of third-party screen-capture programs</span></span>
    
- <span data-ttu-id="6742e-181">サード ・ パーティ製の画面取り込みプログラムまたはコピー アンド ペースト操作を使用してコンテンツ メタデータ (列値) のコピー</span><span class="sxs-lookup"><span data-stu-id="6742e-181">Copying of content metadata (column values) through the use of third-party screen-capture programs or copy-and-paste action</span></span>
    
[<span data-ttu-id="6742e-182">Information Rights Management をリストまたはライブラリに適用する</span><span class="sxs-lookup"><span data-stu-id="6742e-182">Apply Information Rights Management to a list or library</span></span>](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a><span data-ttu-id="6742e-183">リストおよびライブラリに対する IRM のしくみ</span><span class="sxs-lookup"><span data-stu-id="6742e-183">How IRM works for lists and libraries</span></span>
<span data-ttu-id="6742e-184"><a name="__toc256598178"> </a></span><span class="sxs-lookup"><span data-stu-id="6742e-184"></span></span>

<span data-ttu-id="6742e-p111">IRM による保護はリストまたはライブラリ レベルでファイルに適用されます。ライブラリに対して IRM を有効に、権限の管理は、そのライブラリ内のファイルのすべてに適用されます。リストに対して IRM を有効に、実際のリスト アイテムではなくリスト アイテムに関連付けられているファイルにのみアクセス権管理が適用されます。</span><span class="sxs-lookup"><span data-stu-id="6742e-p111">IRM protection is applied to files at the list or library level. When IRM is enabled for a library, rights management applies to all of the files in that library. When IRM is enabled for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="6742e-p112">ユーザーは、IRM が有効なリストやライブラリ内のファイルをダウンロードするとき、ファイルが暗号化されるため、承認されたユーザーのみが表示ことができます。各権限が管理されたファイルには、ファイルを表示できるユーザーの制限を課する発行ライセンスも含まれています。典型的な制限、ファイルを読み取り専用にする、ローカル コピーを保存し、ファイルの印刷を禁止するから人を防止する、テキストのコピーを無効にします。IRM 対応のファイル タイプを読み取ることができるクライアント プログラムは、権限が管理されたファイル内でこれらの制限を適用するのに発行ライセンスを使用します。これは、権限が管理されたファイルが、保護を保持するサーバーからダウンロードされた後にも方法です。</span><span class="sxs-lookup"><span data-stu-id="6742e-p112">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them. Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file. Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file. Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions. This is how a rights-managed file retains its protection even after it is downloaded from the server.</span></span>
  
<span data-ttu-id="6742e-p113">リストまたはライブラリからダウンロードされるときにファイルに適用される制限の種類は、ファイルを含むサイト上の個々 のユーザーのアクセス許可に基づいています。次の表は、IRM のアクセス許可をサイトのアクセス許可の対応について説明します。</span><span class="sxs-lookup"><span data-stu-id="6742e-p113">The types of restrictions that are applied to a file when it is downloaded from a list or library are based on the individual user's permissions on the site that contains the file. The following table explains how the permissions on sites correspond to IRM permissions.</span></span>
  
|<span data-ttu-id="6742e-195">**アクセス許可**</span><span class="sxs-lookup"><span data-stu-id="6742e-195">**Permissions**</span></span>|<span data-ttu-id="6742e-196">**IRM アクセス許可**</span><span class="sxs-lookup"><span data-stu-id="6742e-196">**IRM Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6742e-197">アクセス許可を管理、Web サイトの管理</span><span class="sxs-lookup"><span data-stu-id="6742e-197">Manage Permissions, Manage Web Site</span></span>  <br/> |<span data-ttu-id="6742e-198">**フル コントロール**(定義されているクライアント プログラムによって): 通常は、読み取り、編集、コピー、保存、および権限管理コンテンツのアクセス許可を変更します。</span><span class="sxs-lookup"><span data-stu-id="6742e-198">**Full control** (as defined by the client program): This permission generally allows a user to read, edit, copy, save, and modify permissions of rights-managed content.</span></span>  <br/> |
|<span data-ttu-id="6742e-199">アイテムの編集、リストの管理を追加し、ページをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="6742e-199">Edit Items, Manage Lists, Add and Customize Pages</span></span>  <br/> |<span data-ttu-id="6742e-200">**編集**、**コピー**、および**保存**: ユーザーは、リストまたはライブラリの [Information Rights Management 設定] ページで、**ユーザーがドキュメントを印刷できるようにする**] チェック ボックスが選択されている場合にのみ、ファイルを印刷できます。</span><span class="sxs-lookup"><span data-stu-id="6742e-200">**Edit**, **Copy**, and **Save**: A user can print a file only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>  <br/> |
|<span data-ttu-id="6742e-201">アイテムの表示</span><span class="sxs-lookup"><span data-stu-id="6742e-201">View Items</span></span>  <br/> |<span data-ttu-id="6742e-p114">**読み取り**: ユーザーからドキュメントを読み取ることができますがコピーことはできません、またはその内容を変更します。ユーザーは、リストまたはライブラリの [Information Rights Management 設定] ページで、**ユーザーがドキュメントを印刷できるようにする**] チェック ボックスが選択されている場合にのみ印刷できます。</span><span class="sxs-lookup"><span data-stu-id="6742e-p114">**Read**: A user can read the document, but cannot copy or modify its content. A user can print only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.  </span></span><br/> |
|<span data-ttu-id="6742e-204">その他</span><span class="sxs-lookup"><span data-stu-id="6742e-204">Other</span></span>  <br/> |<span data-ttu-id="6742e-205">IRM アクセス権を直接他のアクセス許可が対応してないです。</span><span class="sxs-lookup"><span data-stu-id="6742e-205">No other permissions correspond directly to IRM permissions.</span></span>  <br/> |
   
<span data-ttu-id="6742e-p115">リストまたはライブラリでは、SharePoint Server 2013 の IRM を有効にすると、そのリストまたはライブラリのすべてのフロント エンド Web サーバー上のプロテクターがインストールされているファイルの種類のみ保護できます。プロテクターとは、暗号化と復号化の特定のファイル形式のファイルの権限管理を制御するプログラムです。SharePoint には、次のファイルの種類の保護機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6742e-p115">When you enable IRM for a list or library in SharePoint Server 2013, you can only protect file types in that list or library for which a protector is installed on all front-end Web servers. A protector is a program that controls the encryption and decryption of rights-managed files of a specific file format. SharePoint includes protectors for the following file types:</span></span>
  
- <span data-ttu-id="6742e-209">Microsoft Office InfoPath フォーム</span><span class="sxs-lookup"><span data-stu-id="6742e-209">Microsoft Office InfoPath forms</span></span>
    
- <span data-ttu-id="6742e-210">次の Microsoft Office プログラムの 97-2003 ファイル形式: Word、Excel、および PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6742e-210">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="6742e-211">Office オープン XML ファイル形式を次の Microsoft Office プログラム: Word、Excel、および PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6742e-211">The Office Open XML Formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="6742e-212">XML 用紙仕様 (XPS) 形式</span><span class="sxs-lookup"><span data-stu-id="6742e-212">The XML Paper Specification (XPS) format</span></span>
    
<span data-ttu-id="6742e-213">組織で IRM を使用して、上記以外のファイルの種類を保護する計画をサーバー管理者はこれらの追加のファイル形式のプロテクターをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6742e-213">If your organization plans to use IRM to protect any other file types in addition to those listed above, your server administrator must install protectors for these additional file formats.</span></span>
  

