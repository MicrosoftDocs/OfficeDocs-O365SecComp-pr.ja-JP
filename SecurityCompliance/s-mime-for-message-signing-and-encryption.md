---
title: S/MIME によるメッセージの署名と暗号化
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 秒/MIME を使用すると、電子メールの暗号化し、デジタル署名を有効にできます。電子メール メッセージに S/MIME を使用すると、受信トレイに表示される送信者を開始する正確なメッセージを特定するのには、そのメッセージを受信する人に役立ちます。
ms.openlocfilehash: 26c50fb6e4d1b07b7dba26948ae46e7f36eeaec5
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002770"
---
# <a name="smime-for-message-signing-and-encryption"></a><span data-ttu-id="86087-104">S/MIME によるメッセージの署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="86087-104">S/MIME for message signing and encryption</span></span>

<span data-ttu-id="86087-p102">S/MIME (Secure Multipurpose とインターネット メールの拡張機能) は、広く受け入れられているメソッド、またはより正確には、プロトコル、デジタル署名され、暗号化されたメッセージです。秒/MIME を使用すると、電子メールの暗号化し、デジタル署名を有効にできます。電子メール メッセージに S/MIME を使用すると、受信トレイに表示される送信者を開始する正確なメッセージを特定するのには、そのメッセージを受信する人に役立ちます。なることを確認するメッセージを受信するユーザーと、特定の送信者から送信元を装って誰かからではなく、メッセージが付属しています。これを行うには、秒/MIME は、認証、メッセージの整合性、および否認 (デジタル署名を使用して) 元の暗号化セキュリティ サービスを提供します。高めることにつながりますプライバシーとデータ セキュリティ (暗号化を使用して) の電子メッセージングです。履歴と S/MIME の電子メールのコンテキストでのアーキテクチャに関する詳細については、[理解すると、S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86087-p102">S/MIME (Secure/Multipurpose Internet Mail Extensions) is a widely accepted method, or more precisely a protocol, for sending digitally signed and encrypted messages. S/MIME allows you to encrypt emails and digitally sign them. When you use S/MIME with an email message, it helps the people who receive that message to be certain that what they see in their inbox is the exact message that started with the sender. It will also help people who receive messages to be certain that the message came from the specific sender and not from someone pretending to be the sender. To do this, S/MIME provides for cryptographic security services such as authentication, message integrity, and non-repudiation of origin (using digital signatures). It also helps enhance privacy and data security (using encryption) for electronic messaging. For a more complete background about the history and architecture of S/MIME in the context of email, see [Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948).</span></span> 
  
<span data-ttu-id="86087-p103">管理者は、Exchange 2013 の SP1 または Exchange Online、Office 365 の一部のいずれかのメールボックスがある場合、組織の MIME ベースのセキュリティを有効にできます。秒/MIME を設定するのには Exchange 管理シェルとは、ここにリンクされているトピックのガイダンスを使用します。署名と暗号化の目的で発行された証明書と、オンプレミスの Active Directory に公開するデータ サポート対象のバージョンの Outlook または Exchange 2013 SP1 または Exchange Online では、いずれかで、ActiveSync で S/MIME を使用するには、組織内のユーザーが必要ドメイン サービス (AD DS)。AD DS は、物理的な場所を制御することで、リモート ・ サイトまたはインターネット上のどこかにクラウド ベースのサービスではなく、コンピューター上になければなりません。AD DS の詳細については、 [Active Directory ドメイン サービス](https://go.microsoft.com/fwlink/?LinkID=394064)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86087-p103">As an administrator, you can enable S/MIME-based security for your organization if you have mailboxes in either Exchange 2013 SP1 or Exchange Online, a part of Office 365. Use the guidance in the topics linked here along with the Exchange Management Shell to set up S/MIME. To use S/MIME in supported versions of Outlook or ActiveSync, with either Exchange 2013 SP1 or Exchange Online, the users in your organization must have certificates issued for signing and encryption purposes and data published to your on-premises Active Directory Domain Service (AD DS). Your AD DS must be located on computers at a physical location that you control and not at a remote facility or cloud-based service somewhere on the internet. For more information about AD DS, see [Active Directory Domain Services](https://go.microsoft.com/fwlink/?LinkID=394064).</span></span>
  
## <a name="supported-scenarios-and-technical-considerations"></a><span data-ttu-id="86087-117">サポートされるシナリオと技術的な考慮事項</span><span class="sxs-lookup"><span data-stu-id="86087-117">Supported scenarios and technical considerations</span></span>
<span data-ttu-id="86087-118"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="86087-118"></span></span>

<span data-ttu-id="86087-119">組織は、Exchange 2013 SP1 または Exchange Online を使用する場合は、次の端点のいずれかで動作する、秒/MIME を設定できます。</span><span class="sxs-lookup"><span data-stu-id="86087-119">If your organization uses either Exchange 2013 SP1 or Exchange Online, you can set up S/MIME to work with any of the following end points:</span></span> 
  
- <span data-ttu-id="86087-120">Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="86087-120">Outlook 2010</span></span>
    
- <span data-ttu-id="86087-121">Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="86087-121">Outlook 2013</span></span>
    
- <span data-ttu-id="86087-122">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="86087-122">Outlook Web App</span></span>
    
- <span data-ttu-id="86087-123">Exchange ActiveSync (EAS)</span><span class="sxs-lookup"><span data-stu-id="86087-123">Exchange ActiveSync (EAS)</span></span>
    
<span data-ttu-id="86087-p104">これらの各エンドポイントに S/MIME をセットアップする手順は、どのエンドポイントを選択するかにより、若干異なってきます。一般的には、次の作業をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="86087-p104">The steps that you follow to set up S/MIME with each of these end points is slightly different depending on which you choose. Generally, you will need to accomplish the following:</span></span>
  
- <span data-ttu-id="86087-p105">Windows ベースの証明機関をインストールし、S/MIME 証明書を発行する公開キー基盤を設定します。サード パーティの証明書プロバイダーによって発行された証明書もサポートされています。詳細については、 [Active Directory 証明書サービスの概要](https://technet.microsoft.com/library/hh831740.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86087-p105">Install a Windows-based Certification Authority and set up a public key infrastructure to issue S/MIME certificates. Certificates issued by third-party certificate providers are also supported. For details, see [Active Directory Certificate Services Overview](https://technet.microsoft.com/library/hh831740.aspx).</span></span>
    
- <span data-ttu-id="86087-129">UserSMIMECertificate および/または UserCertificate 属性の社内 AD DS アカウントでユーザー証明書を発行します。</span><span class="sxs-lookup"><span data-stu-id="86087-129">Publish the user certificate in an on-premises AD DS account in the UserSMIMECertificate and/or UserCertificate attributes.</span></span>
    
- <span data-ttu-id="86087-p106">Exchange Online 組織では、Azure Active Directory への AD DS からユーザー証明書をディレクトリ同期の適切なバージョンを使用して同期します。これらの証明書が Exchange のオンライン ディレクトリに同期 Azure Active Directory から取得し、し、受信者にメッセージを暗号化するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="86087-p106">For Exchange Online organizations, synchronize the user certificates from AD DS to Azure Active Directory by using an appropriate version of DirSync. These certificates will then get synchronized from Azure Active Directory to Exchange Online directory and will be used when encrypting a message to a recipient.</span></span>
    
- <span data-ttu-id="86087-p107">S/MIME を検証するためには、仮想の証明書のコレクションを設定します。この情報は、電子メールの署名を検証する際に OWA により使用され、そのメールが信頼される証明書により署名されたことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="86087-p107">Set up a virtual certificate collection in order to validate S/MIME. This information is used by OWA when validating the signature of an email and ensuring that it was signed by a trusted certificate.</span></span>
    
- <span data-ttu-id="86087-134">S/MIME を使用する Outlook エンド ポイントまたは EA エンド ポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="86087-134">Set up the Outlook or EAS end point to use S/MIME.</span></span> 
    
## <a name="setup-smime-with-outlook-web-app"></a><span data-ttu-id="86087-135">Outlook Web App で S/MIME を設定する</span><span class="sxs-lookup"><span data-stu-id="86087-135">Setup S/MIME with Outlook Web App</span></span>
<span data-ttu-id="86087-136"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="86087-136"></span></span>

<span data-ttu-id="86087-137">Exchange 2013 SP1 または Exchange Online では、Outlook Web App の S/MIME を設定するには、次のキーの手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="86087-137">Setting up S/MIME for Exchange 2013 SP1 or Exchange Online with Outlook Web App involves the following key steps:</span></span>
  
1. [<span data-ttu-id="86087-138">Outlook Web App 用 S/MIME 設定値の構成</span><span class="sxs-lookup"><span data-stu-id="86087-138">Configure S/MIME settings for Outlook Web App</span></span>](configure-s-mime-settings-for-outlook-web-app.md)
    
2. [<span data-ttu-id="86087-139">S/MIME を検証するための仮想証明書コレクションをセットアップする</span><span class="sxs-lookup"><span data-stu-id="86087-139">Set up virtual certificate collection to validate S/MIME</span></span>](set-up-virtual-certificate-collection-to-validate-s-mime.md)
    
3. <span data-ttu-id="86087-140">[秒/MIME の Office 365 にユーザー証明書を同期](sync-user-certificates-to-office-365-for-s-mime.md)この手順は、Exchange Online にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="86087-140">[Sync user certificates to Office 365 for S/MIME](sync-user-certificates-to-office-365-for-s-mime.md) This step applies to Exchange Online only.</span></span> 
    
## <a name="related-message-encryption-technologies"></a><span data-ttu-id="86087-141">関連するメッセージ暗号化テクノロジ</span><span class="sxs-lookup"><span data-stu-id="86087-141">Related message encryption technologies</span></span>
<span data-ttu-id="86087-142"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="86087-142"></span></span>

<span data-ttu-id="86087-p108">メッセージのセキュリティがさらに重要になると、管理者は、原則とセキュリティで保護されたメッセージングの概念を理解しておく必要があります。増大するさまざまな保護に関連するテクノロジ、S-MIME など使用可能になったため、この理解は特に重要です。S/MIME および電子メールのコンテキストでのしくみについて理解を深めるには、[理解すると、S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)を参照してください。さまざまな暗号化テクノロジは、残りの部分と、転送中のメッセージの保護を提供する共同作業です。秒/MIME では、次のテクノロジを同時に操作できますが、それらに依存しません。</span><span class="sxs-lookup"><span data-stu-id="86087-p108">As message security becomes more important, administrators need to understand the principles and concepts of secure messaging. This understanding is especially important because of the growing variety of protection-related technologies, such as S/MIME, that have become available. To understand more about S/MIME and how it works in context of email, see [Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948). A variety of encryption technologies work together to provide protection for messages at rest and in-transit. S/MIME can work simultaneously with the following technologies but is not dependent on them:</span></span>
  
> <span data-ttu-id="86087-148">**トランスポート層セキュリティ (TLS)** は、盗聴防止に役立てるために電子メール サーバー間のトンネルまたはルートを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="86087-148">**Transport Layer Security (TLS)** encrypts the tunnel or the route between email servers in order to help prevent snooping and eavesdropping.</span></span> 
    
> <span data-ttu-id="86087-149">**Secure Sockets Layer (SSL)** は、電子メール クライアントと Office 365 サーバーとの間の接続を暗号化します。</span><span class="sxs-lookup"><span data-stu-id="86087-149">**Secure Sockets Layer (SSL)** encrypts the connection between email clients and Office 365 servers.</span></span> 
    
> <span data-ttu-id="86087-150">**BitLocker**は、不正なアクセスを取得誰かがある場合、読み取ることができないように、データ ・ センターのハード ドライブ上のデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="86087-150">**BitLocker** encrypts the data on a hard drive in a datacenter so that if someone gets unauthorized access, they can't read it.</span></span> 
    
### <a name="smime-compared-with-office-365-message-encryption"></a><span data-ttu-id="86087-151">S/MIME と Office 365 のメッセージ暗号化との比較</span><span class="sxs-lookup"><span data-stu-id="86087-151">S/MIME compared with Office 365 Message Encryption</span></span>

<span data-ttu-id="86087-p109">秒/MIME では、企業間および企業消費者の状況で使用される証明書と公開のインフラストラクチャが必要です。ユーザーは、S/MIME で暗号化キーを制御し、各メッセージの送信に使用するかどうかを選択できます。Outlook などの電子メール プログラムでは、デジタル署名と署名の検証を実行する信頼されたルート証明機関の場所を検索します。Office 365 メッセージの暗号化は、管理者、および各ユーザーではなく、組織内または組織の外部ユーザーに送信されたメールを暗号化するために、構成可能なポリシー ・ ベースの暗号化サービスです。Azure 権利管理 (RM) の構築および公開キー基盤に依存しないオンライン サービスすることをお勧めします。Office 365 のメッセージの暗号化では、組織のブランドとのメールをカスタマイズする機能などの追加機能も提供します。Office 365 のメッセージの暗号化の詳細については、 [Office 365 のメッセージの暗号化](https://go.microsoft.com/fwlink/?LinkID=392525)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86087-p109">S/MIME requires a certificate and publishing infrastructure that is often used in business-to-business and business-to-consumer situations. The user controls the cryptographic keys in S/MIME and can choose whether to use them for each message they send. Email programs such as Outlook search a trusted root certificate authority location to perform digital signing and verification of the signature. Office 365 Message Encryption is a policy-based encryption service that can be configured by an administrator, and not an individual user, to encrypt mail sent to anyone inside or outside of the organization. It's an online service that's built on Azure Rights Management (RMS) and does not rely on a public key infrastructure. Office 365 Message Encryption also provides additional capabilities, such as the capability to customize the mail with organization's brand. For more information about Office 365 Message Encryption, see [Office 365 Message Encryption](https://go.microsoft.com/fwlink/?LinkID=392525).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="86087-159">詳細情報</span><span class="sxs-lookup"><span data-stu-id="86087-159">More information</span></span>
<span data-ttu-id="86087-160"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="86087-160"></span></span>

[<span data-ttu-id="86087-161">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="86087-161">Outlook Web App</span></span>](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)
  
[<span data-ttu-id="86087-162">セキュリティで保護されたメール (2000)</span><span class="sxs-lookup"><span data-stu-id="86087-162">Secure Mail (2000)</span></span>](https://technet.microsoft.com/en-us/library/cc962043.aspx)
  

