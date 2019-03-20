---
title: S/MIME 用にユーザー証明書を Office 365 に同期させる
ms.author: chrisda
author: chrisda
manager: Serdars
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: S/MIME 保護されたメッセージを送信するには、適切な証明書をセットアップする必要があります。Exchange Online 経由で暗号化メッセージを送信するために、送信者の電子メール プログラムでは受信者の公開証明書を使用してメッセージを暗号化します。この公開 X.509 証明書を Office 365 に公開する必要があります。
ms.openlocfilehash: 927f6b4c7a166ee35e11a8712cc99054b0e67dee
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692566"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="1418c-105">S/MIME 用にユーザー証明書を Office 365 に同期させる</span><span class="sxs-lookup"><span data-stu-id="1418c-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="1418c-106">すべてのユーザーが S/MIME で保護されたメッセージを Exchange Online で送信できるようにするには、適切な証明書をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1418c-106">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="1418c-107">Exchange Online を介して暗号化されたメッセージを送信する場合、送信者の電子メールアプリは受信者のパブリック証明書を使用してメッセージを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="1418c-107">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="1418c-108">この公開 X.509 証明書を Office 365 に公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1418c-108">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="1418c-109">S/MIME をサポートする証明書を同期するには</span><span class="sxs-lookup"><span data-stu-id="1418c-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="1418c-110">証明書を発行して、ローカルの Active Directory ドメイン サービスで公開することによって、S/MIME のセットアップを開始します。</span><span class="sxs-lookup"><span data-stu-id="1418c-110">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="1418c-111">Exchange Server での証明書の管理の詳細については、「 [Digital certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1418c-111">For more information about managing certificates in Exchange Server, see [Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span></span>

<span data-ttu-id="1418c-p104">証明書が公開されたら、Azure Active Directory 同期ツール を使用してオンプレミスの Exchange 環境から Office 365 にユーザー データを同期します。このプロセスの詳細については、「[DirSync: Directory 同期ツールのバージョンのリリース履歴](https://go.microsoft.com/fwlink/p/?LinkId=392587)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1418c-p104">After your certificates are published, use the Azure Active Directory Sync tool to synchronize user data from your on-premises Exchange environment to Office 365. For more information on this process, see [DirSync: Directory Sync Tool Version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span></span>

<span data-ttu-id="1418c-114">S/MIME 用に他のディレクトリデータを同期することに加えて、ツールは各ユーザーオブジェクトの**usercertificate**属性と**userSMIMECertificate**属性を同期し、データを使用してメッセージの署名と暗号化を行うことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="1418c-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="1418c-115">詳細</span><span class="sxs-lookup"><span data-stu-id="1418c-115">More Information</span></span>

[<span data-ttu-id="1418c-116">S/MIME によるメッセージの署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="1418c-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="1418c-117">Azure Active Directory 同期ツール</span><span class="sxs-lookup"><span data-stu-id="1418c-117">Azure Active Directory Sync tool</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=392587)
