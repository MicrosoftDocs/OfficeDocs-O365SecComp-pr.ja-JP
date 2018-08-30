---
title: S/MIME 用にユーザー証明書を Office 365 に同期させる
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
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: S/MIME 保護されたメッセージを送信するには、適切な証明書をセットアップする必要があります。Exchange Online 経由で暗号化メッセージを送信するために、送信者の電子メール プログラムでは受信者の公開証明書を使用してメッセージを暗号化します。この公開 X.509 証明書を Office 365 に公開する必要があります。
ms.openlocfilehash: 452b538b4515bdbcd5fcbdedad17f0450c04207a
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002385"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="fddc8-105">S/MIME 用にユーザー証明書を Office 365 に同期させる</span><span class="sxs-lookup"><span data-stu-id="fddc8-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="fddc8-p102">S/MIME 保護されたメッセージを送信するには、適切な証明書をセットアップする必要があります。Exchange Online 経由で暗号化メッセージを送信するために、送信者の電子メール プログラムでは受信者の公開証明書を使用してメッセージを暗号化します。この公開 X.509 証明書を Office 365 に公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fddc8-p102">Before anyone can send S/MIME-protected messages, the appropriate certificates must be set up. In order to send encrypted messages through Exchange Online, the sender's email program uses the public certificate of the recipient to encrypt the message. This public X.509 certificate has to be published to Office 365.</span></span>
  
## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="fddc8-109">S/MIME をサポートする証明書を同期するには</span><span class="sxs-lookup"><span data-stu-id="fddc8-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="fddc8-p103">証明書を発行して、ローカルの Active Directory ドメイン サービスで公開することによって、S/MIME のセットアップを開始します。Exchange 2013 での証明書の管理方法については、「[Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fddc8-p103">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service. For more information about managing certificates in Exchange 2013, see [Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span></span>
  
<span data-ttu-id="fddc8-p104">証明書が公開されたら、Azure Active Directory 同期ツール を使用してオンプレミスの Exchange 環境から Office 365 にユーザー データを同期します。このプロセスの詳細については、「[DirSync: Directory 同期ツールのバージョンのリリース履歴](https://go.microsoft.com/fwlink/p/?LinkId=392587)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fddc8-p104">After your certificates are published, use the Azure Active Directory Sync tool to synchronize user data from your on-premises Exchange environment to Office 365. For more information on this process, see [DirSync: Directory Sync Tool Version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span></span>
  
<span data-ttu-id="fddc8-114">S/MIME のために他のディレクトリ データを同期することに加えて、このツールは、各ユーザー オブジェクトの  `userCertificate` 属性と  `userSMIMECertificate` 属性を同期して、そのデータをメッセージの署名と暗号化に使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fddc8-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  `userCertificate` and  `userSMIMECertificate` attributes for each user object so the data can be used to sign and encrypt messages.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="fddc8-115">詳細</span><span class="sxs-lookup"><span data-stu-id="fddc8-115">More Information</span></span>

[<span data-ttu-id="fddc8-116">S/MIME によるメッセージの署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="fddc8-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
  
[<span data-ttu-id="fddc8-117">Azure Active Directory 同期ツール</span><span class="sxs-lookup"><span data-stu-id="fddc8-117">Azure Active Directory Sync tool</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=392587)
  

