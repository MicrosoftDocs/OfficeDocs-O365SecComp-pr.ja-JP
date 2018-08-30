---
title: Office 365 Message Encryption に関する FAQ
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/23/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: Office 365 で新しいメッセージの保護機能のしくみについて質問があるでしょうか。ここで回答を確認します。
ms.openlocfilehash: d435642d8ea98d37a58b28b55c9c1e68c746600c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22559252"
---
# <a name="office-365-message-encryption-faq"></a><span data-ttu-id="28c3d-104">Office 365 Message Encryption に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="28c3d-104">Office 365 Message Encryption FAQ</span></span>

<span data-ttu-id="28c3d-p102">Office 365 で新しいメッセージの保護機能のしくみについて質問があるでしょうか。ここで回答を確認します。またを見て[Azure の情報保護のデータの保護についてご質問がよく寄せられる](https://docs.microsoft.com/information-protection/get-started/faqs-rms)Azure の著作権管理、データ保護サービスに関する質問への回答の Azure の情報保護の。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p102">Have a question about how the new message protection capabilities in Office 365 work? Check for an answer here. Also, take a look at [Frequently asked questions about data protection in Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/faqs-rms) for answers to questions about the data protection service, Azure Rights Management, in Azure Information Protection.</span></span> 
  
## <a name="what-is-office-365-message-encryption-ome"></a><span data-ttu-id="28c3d-108">Office 365 メッセージの暗号化 (ホーム) とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-108">What is Office 365 Message Encryption (OME)?</span></span>

<span data-ttu-id="28c3d-p103">ホームでは、電子メールの暗号化と権限管理の機能を結合します。権限管理機能は、Azure の情報保護が導入されています。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p103">OME combines email encryption and rights management capabilities. Rights management capabilities are powered by Azure Information Protection.</span></span>
  
## <a name="who-can-use-ome"></a><span data-ttu-id="28c3d-111">ホームを使用していることができますか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-111">Who can use OME?</span></span>

<span data-ttu-id="28c3d-112">ホームの新機能を使用するには次の条件。</span><span class="sxs-lookup"><span data-stu-id="28c3d-112">You can use the new capabilities for OME under the following conditions:</span></span>
  
- <span data-ttu-id="28c3d-113">場合は Office 365 の Exchange Online のホームまたは IRM を設定することことはありませんが。</span><span class="sxs-lookup"><span data-stu-id="28c3d-113">If you have never set up OME or IRM for Exchange Online in Office 365.</span></span>
    
- <span data-ttu-id="28c3d-114">ホームと IRM のように設定した場合は、Azure の情報保護と Azure の権限の管理サービスを使用している場合にこの手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="28c3d-114">If you have set up OME and IRM, you can use these steps if you are using the Azure Rights Management service from Azure Information Protection.</span></span>
    
- <span data-ttu-id="28c3d-p104">使用する場合 Exchange Online では、Active Directory の権限管理サービス (AD RMS)、これらの新機能を直ちに有効にできません。代わりに、する必要があります[Azure の情報保護に AD RMS を移行](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)する最初にします。移行が終了したら、ホーム正常に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p104">If you are using Exchange Online with Active Directory Rights Management service (AD RMS), you can't enable these new capabilities right away. Instead, you need to [migrate AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) first. When you've finished the migration, you can successfully set up OME.</span></span> 
    
    <span data-ttu-id="28c3d-118">引き続き使用する場合は、オンプレミス AD RMS Exchange 情報の保護を Azure に移行するのではなく、オンラインにすることはできませんこれらの新機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="28c3d-118">If you choose to continue to use on-premises AD RMS with Exchange Online instead of migrating to Azure Information Protection, you will not be able to use these new capabilities.</span></span>
    
## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a><span data-ttu-id="28c3d-119">新しいホーム機能を使用する必要があるどのようなサブスクリプションをしますか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-119">What subscriptions do I need to use the new OME capabilities?</span></span>

<span data-ttu-id="28c3d-120">ホームの新機能を使用するには、次のプランのいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="28c3d-120">To use the new OME capabilities, you need one of the following plans:</span></span>
  
- <span data-ttu-id="28c3d-p105">Office 365 Office 365 の E3 と E5、マイクロソフト E3 と E5、Office 365 の A1、A3、A5、および Office 365 の第 3 世代との G5 の一部としてメッセージの暗号化が提供されます。お客様では、Azure 情報保護により、新しい保護機能を表示するのには追加のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p105">Office 365 Message Encryption is offered as part of Office 365 E3 and E5, Microsoft E3 and E5, Office 365 A1, A3, and A5, and Office 365 G3 and G5. Customers do not need additional licenses to receive the new protection capabilities powered by Azure Information Protection.</span></span> 
    
- <span data-ttu-id="28c3d-123">Azure 情報保護計画する場合は 1 次が新しい Office 365 のメッセージの暗号化機能を受信する計画を追加することも: Exchange オンライン計画 1、Exchange オンライン計画 2、Office 365 の F1、Office 365 の業務に関する重要事項、Office 365 のビジネス プレミアム、またはOffice 365 エンタープライズ E1。</span><span class="sxs-lookup"><span data-stu-id="28c3d-123">You can also add Azure Information Protection Plan 1 to the following plans to receive the new Office 365 Message Encryption capabilities: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Office 365 Business Essentials, Office 365 Business Premium, or Office 365 Enterprise E1.</span></span>
    
- <span data-ttu-id="28c3d-124">各ユーザーが Office 365 のメッセージの暗号化のメリットは、この機能によってカバーされるライセンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="28c3d-124">Each user benefiting from Office 365 Message Encryption needs to be licensed to be covered by the feature.</span></span>
    
- <span data-ttu-id="28c3d-125">完全なリストについては、Office 365 のメッセージの暗号化の[Exchange Online のサービスの説明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c3d-125">For the full list see the [Exchange Online service descriptions](https://technet.microsoft.com/library/exchange-online-service-description.aspx) for Office 365 Message Encryption.</span></span> 
    
## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a><span data-ttu-id="28c3d-126">使用できる Exchange Online で、Azure の情報保護の独自のキー (BYOK) を表示しますか?</span><span class="sxs-lookup"><span data-stu-id="28c3d-126">Can I use Exchange Online with bring your own key (BYOK) in Azure Information Protection?</span></span>

<span data-ttu-id="28c3d-p106">うん！ホームを設定する前に BYOK を設定する手順を完了することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p106">Yes! Microsoft recommends that you complete the steps to set up BYOK before you set up OME.</span></span>
  
<span data-ttu-id="28c3d-129">BYOK の詳細については、[計画と Azure の情報保護のテナントのキーを実装する](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c3d-129">For more information about BYOK, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).</span></span>
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a><span data-ttu-id="28c3d-130">ホームと Azure の情報保護と BYOK を変更するマイクロソフトのアプローチ令状などのサード パーティのデータ要求にでしょうか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-130">Do OME and BYOK with Azure Information Protection change Microsoft's approach to third-party data requests such as subpoenas?</span></span>

<span data-ttu-id="28c3d-p107">違います。提供し、Azure の情報の保護からの BYOK と呼ばれる独自の暗号化キーを制御するには、ホームおよびオプションは、法律の執行令状への応答には設計されていません。Azure の情報を保護するための BYOK で、ホームは、お客様のコンプライアンスを重視した設計されています。非常に真剣に、マイクロソフトでは顧客データの要求をサード ・ パーティ製です。クラウド ・ サービス ・ プロバイダーとして、私たちが顧客データのプライバシー保護のため推奨常になりました。令状を取得して、イベントには常にターゲットを変更しようサード ・ パーティ情報の取得をお客様に。(Brad Smith のブログを参照してください:[政府のスヌーピング (のぞき見) から顧客データの保護](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。受信要求の詳細な情報を定期的に公開します。サード ・ パーティ製のデータ要求の詳細については、マイクロソフトのセキュリティ センターで[政府や顧客データにアクセスするための法律執行の要求への応答](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data)を参照してください。また、漏えいのお客様で「データ」[オンライン サービス条件 (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p107">No. OME and the option to provide and control your own encryption keys, called BYOK, from Azure Information Protection were not designed to respond to law enforcement subpoenas. OME, with BYOK for Azure Information Protection, was designed for compliance-focused customers. Microsoft takes third-party requests for customer data very seriously. As a cloud service provider, we always advocate for the privacy of customer data. In the event we get a subpoena, we always attempt to redirect the third party to the customer to obtain the information. (Please read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). We periodically publish detailed information of the request we receive. For more information regarding third-party data requests, see [Responding to government and law enforcement requests to access customer data](https://www.microsoft.com/en-us/trustcenter/privacy/govt-requests-for-data) on the Microsoft Trust Center. Also, see "Disclosure of Customer Data" in the [Online Services Terms (OST)](https://www.microsoft.com/en-us/Licensing/product-licensing/products.aspx).</span></span>
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a><span data-ttu-id="28c3d-141">従来の Office 365 メッセージの暗号化 (ホーム) および情報権利管理 (IRM) 機能にこの機能が関連するはどのようにでしょうか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-141">How is this feature related to legacy Office 365 Message Encryption (OME) and Information Rights Management (IRM) features?</span></span>

<span data-ttu-id="28c3d-p108">Office 365 のメッセージの暗号化のための新しい機能は、既存の IRM と従来のホーム ソリューションの発展させたものです。次の表は、詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p108">The new capabilities for Office 365 Message Encryption are an evolution of the existing IRM and legacy OME solutions. The following table provides more details.</span></span>
  
<span data-ttu-id="28c3d-144">**従来のホーム、IRM では、ホームの新機能の比較**</span><span class="sxs-lookup"><span data-stu-id="28c3d-144">**Comparison of legacy OME, IRM, and new OME capabilities**</span></span>

|<span data-ttu-id="28c3d-145">**機能**</span><span class="sxs-lookup"><span data-stu-id="28c3d-145">**Capability**</span></span>|<span data-ttu-id="28c3d-146">**ホームの以前のバージョン**</span><span class="sxs-lookup"><span data-stu-id="28c3d-146">**Previous versions of OME**</span></span>|<span data-ttu-id="28c3d-147">**IRM**</span><span class="sxs-lookup"><span data-stu-id="28c3d-147">**IRM**</span></span>|<span data-ttu-id="28c3d-148">**ホームの新機能**</span><span class="sxs-lookup"><span data-stu-id="28c3d-148">**New OME capabilities**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="28c3d-149">**暗号化された電子メールを送信します。**</span><span class="sxs-lookup"><span data-stu-id="28c3d-149">**Sending an encrypted email**</span></span>|<span data-ttu-id="28c3d-150">Exchange メール フロー ルールによってのみ</span><span class="sxs-lookup"><span data-stu-id="28c3d-150">Only through Exchange mail flow rules</span></span>|<span data-ttu-id="28c3d-151">エンドユーザーが Outlook の PC、Mac 用の Outlook または Outlook は web 上から行うまたは Exchange からのメール フロー ルール</span><span class="sxs-lookup"><span data-stu-id="28c3d-151">End-user initiated from Outlook for PC, Outlook for Mac, or Outlook on the web; or through Exchange mail flow rules</span></span>|<span data-ttu-id="28c3d-152">エンドユーザーが Outlook の PC、Mac 用の Outlook または Outlook は web 上から行うまたはメール フロー ルールを使用</span><span class="sxs-lookup"><span data-stu-id="28c3d-152">End-user initiated from Outlook for PC, Outlook for Mac, or Outlook on the web; or through mail flow rules</span></span>|
|<span data-ttu-id="28c3d-153">**アクセス権管理**</span><span class="sxs-lookup"><span data-stu-id="28c3d-153">**Rights management**</span></span>|-|<span data-ttu-id="28c3d-154">転送不可のオプションとカスタム テンプレートの操作を行います</span><span class="sxs-lookup"><span data-stu-id="28c3d-154">Do Not Forward option and custom templates</span></span>|<span data-ttu-id="28c3d-155">転送不可のオプション、暗号化のみのオプション、既定値、およびカスタム テンプレートの操作を行います</span><span class="sxs-lookup"><span data-stu-id="28c3d-155">Do Not Forward option, encrypt-only option, default and custom templates</span></span>|
|<span data-ttu-id="28c3d-156">**受信者の種類をサポート**</span><span class="sxs-lookup"><span data-stu-id="28c3d-156">**Supported recipient type**</span></span>|<span data-ttu-id="28c3d-157">外部受信者のみ</span><span class="sxs-lookup"><span data-stu-id="28c3d-157">External recipients only</span></span>|<span data-ttu-id="28c3d-158">内部の受信者のみ</span><span class="sxs-lookup"><span data-stu-id="28c3d-158">Internal recipients only</span></span>|<span data-ttu-id="28c3d-159">内部および外部の受信者</span><span class="sxs-lookup"><span data-stu-id="28c3d-159">Internal and external recipients</span></span>|
|<span data-ttu-id="28c3d-160">**受信者の経験**</span><span class="sxs-lookup"><span data-stu-id="28c3d-160">**Experience for recipient**</span></span>|<span data-ttu-id="28c3d-161">外部の受信者は、ダウンロードし、ブラウザーで開かれているにモバイル アプリケーションをダウンロード、html 形式のメッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="28c3d-161">External recipients received an HTML message that they downloaded and opened in a browser or downloaded mobile app.</span></span>|<span data-ttu-id="28c3d-162">のみ、内部の受信者は、PC の Outlook、Outlook for Mac、および web 上の Outlook で暗号化された電子メールを受け取りました。</span><span class="sxs-lookup"><span data-stu-id="28c3d-162">Internal recipients only received encrypted email in Outlook for PC, Outlook for Mac, and Outlook on the web.</span></span>|<span data-ttu-id="28c3d-p109">、IOS 用または web ポータルでは、同じ Office 365 組織または任意の Office 365 にするかどうかにかかわらず、内部および外部の受信者が PC の Outlook、Outlook for Mac、web 上で Outlook、Android では、Outlook と Outlook で電子メールを受信します。組織です。ホーム ポータルには、個別のダウンロードは不要です。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p109">Internal and external recipients receive email in Outlook for PC, Outlook for Mac, Outlook on the web, Outlook for Android, and Outlook for iOS, or through a web portal, regardless of whether or not they are in the same Office 365 organization or in any Office 365 organization. The OME portal requires no separate download.</span></span>|
|<span data-ttu-id="28c3d-165">**独自のキーのサポートを提供します。**</span><span class="sxs-lookup"><span data-stu-id="28c3d-165">**Bring Your Own Key support**</span></span>|<span data-ttu-id="28c3d-166">使用不可</span><span class="sxs-lookup"><span data-stu-id="28c3d-166">Not available</span></span>|<span data-ttu-id="28c3d-167">使用不可</span><span class="sxs-lookup"><span data-stu-id="28c3d-167">Not available</span></span>| <span data-ttu-id="28c3d-168">BYOK のサポート</span><span class="sxs-lookup"><span data-stu-id="28c3d-168">BYOK supported</span></span>|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a><span data-ttu-id="28c3d-169">自分の所属組織のホームの新機能を有効する方法</span><span class="sxs-lookup"><span data-stu-id="28c3d-169">How do I enable the new OME capabilities for my organization?</span></span>

<span data-ttu-id="28c3d-170">[新しい Office 365 のメッセージの暗号化機能の設定](set-up-new-message-encryption-capabilities.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28c3d-170">See [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a><span data-ttu-id="28c3d-171">ホームの以前のバージョンは推奨されていませんか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-171">Will the previous version of OME be deprecated?</span></span>

<span data-ttu-id="28c3d-p110">ホームの以前のバージョンを使用することができますが、この時点でない推奨されません。ただし、強くお勧め、新規あるいは強化されたホーム ソリューションを使用する組織です。ホームを配置していないお客様は、ホームの以前のバージョンの新しい展開を設定できません。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p110">You can still use the previous version of OME, it will not be deprecated at this time. However, we highly encourage organizations to use the new and improved OME solution. Customers that have not already deployed OME cannot set up a new deployment of the previous version of OME.</span></span>
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a><span data-ttu-id="28c3d-175">組織が Active Directory の権限の管理を使用して、この機能を使用できますか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-175">My organization uses Active Directory Rights Management, can I use this functionality?</span></span>

<span data-ttu-id="28c3d-p111">違います。使用する場合 Exchange Online では、Active Directory の権限管理サービス (AD RMS)、これらの新機能を直ちに有効にできません。代わりに、する必要があります[Azure の情報保護に AD RMS を移行](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)する最初にします。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p111">No. If you are using Exchange Online with Active Directory Rights Management service (AD RMS), you can't enable these new capabilities right away. Instead, you need to [migrate AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) first.</span></span> 
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a><span data-ttu-id="28c3d-p112">自組織は、Exchange ハイブリッド展開をします。この機能を使用することができますか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p112">My organization has an Exchange Hybrid deployment. Can I use this feature?</span></span>

<span data-ttu-id="28c3d-p113">オンプレミス ユーザーがオンラインの Exchange のメール フロー ルールを使用して、暗号化されたメールを送信できます。これを行うには、Exchange のオンラインを介して電子メールをルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p113">On-premises users can send encrypted mail using Exchange Online mail flow rules. In order to do this, you need to route email through Exchange Online.</span></span>
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a><span data-ttu-id="28c3d-p114">ホームの暗号化されたメッセージを作成するために使用する必要があるどのような電子メール クライアントをしますか。保護されたメッセージを送信するためにどのようなアプリケーションがサポートされてでしょうか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p114">What email client do I need to use in order to create an OME encrypted message? What applications are supported for sending protected messages?</span></span>

<span data-ttu-id="28c3d-185">Outlook の 2016年と PC と Mac 用の Outlook 2013 および web 上の Outlook からは、保護されたメッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="28c3d-185">You can create protected messages from Outlook 2016, and Outlook 2013 for PC and Mac, and from Outlook on the web.</span></span>
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a><span data-ttu-id="28c3d-186">読み取りおよび保護された電子メールに返信するのには、どのような電子メール クライアントがサポートされているでしょうか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-186">What email clients are supported to read and reply to protected emails?</span></span>

<span data-ttu-id="28c3d-p115">Office 365 ユーザーの場合は、Outlook の PC と Mac (2013 および 2016)、web 上の Outlook および Outlook モバイル (Android と iOS) からの応答を読み書きできます。組織で許可される場合にも、iOS のネイティブのメール クライアントを使用できます。以外の Office 365 ユーザーの場合は、読み取りし、web ブラウザーを通じて web 上で暗号化されたメッセージに返信できます。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p115">You can read and respond from Outlook for PC and Mac (2013 and 2016), Outlook on the web, and Outlook mobile (Android and iOS) if you are an Office 365 user. You can also use the iOS native mail client if your organization allows it. If you are a non-Office 365 user, you can read and reply to encrypted messages on the web through your web browser.</span></span>
  
## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a><span data-ttu-id="28c3d-p116">保護された電子メールの添付ファイルとしては、どのようなファイルの種類がサポートされているでしょうか。添付ファイルは保護された電子メールに関連付けられている保護ポリシーを継承しますか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p116">What file types are supported as attachments in protected emails? Do attachments inherit the protection policies associated with protected emails?</span></span>

<span data-ttu-id="28c3d-192">上でのみ、ファイルの形式で述べた[ここで](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)保護ポリシーが適用されますが、保護されたメールの場合は、あらゆる種類のファイルを添付できます。</span><span class="sxs-lookup"><span data-stu-id="28c3d-192">You can attach any file type to a protected mail, however protection policies are applied only on the file formats mentioned [here](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types).</span></span> 
  
<span data-ttu-id="28c3d-p117">Word、Excel、または PowerPoint ファイルなど、ファイル形式がサポートされている場合、ファイルは常に保護、受信者が添付ファイルのダウンロードが完了した後でも。たとえば、添付ファイルは転送不可で保護されていると、元の受信者がダウンロードされ、新しい受信者に添付ファイルを転送、新しい受信者されません保護されたファイルを開くことができません。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p117">If a file format is supported, such as a Word, Excel, or PowerPoint file, the file is always protected, even after the attachment has been downloaded by the recipient. For example, if an attachment is protected by Do Not Forward, and the original recipient downloads and forwards the attachment to a new recipient, the new recipient will not be able to open the protected file.</span></span>
  
## <a name="are-pdf-file-attachments-supported"></a><span data-ttu-id="28c3d-195">PDF ファイルの添付ファイルはサポートされますか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-195">Are PDF file attachments supported?</span></span>

<span data-ttu-id="28c3d-p118">保護されたメッセージには、PDF ファイルを添付する場合、メッセージ自体は保護されているが、追加の保護は適用されません、PDF ファイルを受信者が受信した後。つまりに限って使用するように名前を付けて保存、転送、コピー、および PDF ファイルを印刷します。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p118">If you attach a PDF file to a protected message, the message itself will be protected, but no additional protection will be applied to the PDF file after the recipient has received it. This means that the recipient can Save As, Forward, Copy, and Print the PDF file.</span></span>
  
## <a name="are-onedrive-for-business-attachments-supported"></a><span data-ttu-id="28c3d-198">OneDrive をビジネスの添付ファイルがサポートされているのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-198">Are OneDrive for Business attachments supported?</span></span>

<span data-ttu-id="28c3d-p119">まだです。ビジネスの添付ファイルの OneDrive はサポートされていませんし、エンド ・ ユーザーは、ビジネスの添付ファイルのためのクラウド OneDrive を含むメールを暗号化できません。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p119">Not yet. OneDrive for Business attachments are not supported and end-users can't encrypt a mail that contains a cloud OneDrive for Business attachment.</span></span>
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a><span data-ttu-id="28c3d-201">できますに自動的にメッセージの暗号化のポリシーを設定することによってでしょうか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-201">Can I automatically encrypt messages by setting up policies?</span></span>

<span data-ttu-id="28c3d-p120">うん。使用してメール フロー ルール Exchange オンライン特定の条件に基づいてメッセージを自動的に暗号化します。受信者に基づくポリシーを作成することができますたとえば、ID、受信者のドメイン、またはメッセージの件名、本文の内容にします。参照してください[Office 365 で電子メール メッセージを暗号化するためにメール フローの規則を定義します](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p120">Yes. Use mail flow rules in Exchange Online to automatically encrypt a message based on certain conditions. For example, you can create policies that are based on recipient ID, recipient domain, or on the content in the body or subject of the message. See [Define mail flow rules to encrypt email messages in Office 365.](define-mail-flow-rules-to-encrypt-email.md)</span></span>
  
## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a><span data-ttu-id="28c3d-206">自動的に暗号化メッセージでデータ損失防止 (DLP)、セキュリティ ・ ポリシーを設定することによって&amp;コンプライアンス センターでしょうか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-206">Can I automatically encrypt messages by setting up policies in Data Loss Prevention (DLP) through the Security &amp; Compliance Center?</span></span>

<span data-ttu-id="28c3d-p121">現在のみ設定できますメール フロー ルールを Exchange オンライン。暗号化は現在サポートされていません、セキュリティによる DLP の&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p121">Currently you can only set up mail flow rules in Exchange Online. Encryption is currently not supported in DLP through the Security &amp; Compliance Center.</span></span>
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a><span data-ttu-id="28c3d-209">暗号化されたメッセージを自分の会社ブランド設定をカスタマイズできますか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-209">Can I customize encrypted messages with my company branding?</span></span>

<span data-ttu-id="28c3d-p122">うん！電子メール メッセージおよびホーム ポータルをカスタマイズする方法の詳細についてを参照してください暗号化されたメッセージに、組織のブランドを追加します。参照してください[、暗号化されたメッセージを組織のブランドを追加します](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p122">Yes! For information on customizing email messages and the OME portal, see Add your organization's brand to your encrypted messages. See [Add your organization's brand to your encrypted messages.](add-your-organization-brand-to-encrypted-messages.md)</span></span>
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a><span data-ttu-id="28c3d-213">レポート作成機能や暗号化された電子メールの情報はありますか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-213">Are there any reporting capabilities or insights for encrypted emails?</span></span>

<span data-ttu-id="28c3d-214">ではなくこの時間が準備中です。</span><span class="sxs-lookup"><span data-stu-id="28c3d-214">Not at this time but coming soon.</span></span>
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a><span data-ttu-id="28c3d-215">電子的証拠開示などのコンプライアンス機能とメッセージの暗号化を使用できますか。</span><span class="sxs-lookup"><span data-stu-id="28c3d-215">Can I use message encryption with compliance features such as eDiscovery?</span></span>

<span data-ttu-id="28c3d-p123">うん。すべての暗号化された電子メール メッセージは、Office 365 のコンプライアンス機能により検出可能です。</span><span class="sxs-lookup"><span data-stu-id="28c3d-p123">Yes. All encrypted email messages are discoverable by Office 365 compliance features.</span></span>
  

