---
title: S/MIME を検証するための仮想証明書コレクションをセットアップする
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: s テナント管理者は、S/MIME 証明書を検証するために使用される仮想の証明書のコレクションを構成する必要があります。
ms.openlocfilehash: 4b2d85181d95bb1f90d46412cca85c2356d98e10
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22028144"
---
# <a name="set-up-virtual-certificate-collection-to-validate-smime"></a><span data-ttu-id="7a3a1-103">S/MIME を検証するための仮想証明書コレクションをセットアップする</span><span class="sxs-lookup"><span data-stu-id="7a3a1-103">Set up virtual certificate collection to validate S/MIME</span></span>

<span data-ttu-id="7a3a1-p101">テナント管理者は、S/MIME 証明書の検証に使用する仮想証明書コレクションを構成する必要があります。この仮想証明書コレクションは、SST ファイル名拡張子を持つ証明書ストア ファイルの種類としてセットアップされます。SST ファイルには、S/MIME 証明書の検証時に使用されるすべてのルート証明書と中間証明書が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7a3a1-p101">As a tenant administrator you will need to configure a virtual certificate collection that will be used to validate S/MIME certificates. This virtual certificate collection is set up as a certificate store file type with an SST filename extension. The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>
  
## <a name="create-and-save-an-sst"></a><span data-ttu-id="7a3a1-107">SST を作成して保存する</span><span class="sxs-lookup"><span data-stu-id="7a3a1-107">Create and save an SST</span></span>
<span data-ttu-id="7a3a1-108"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="7a3a1-108"></span></span>

<span data-ttu-id="7a3a1-p102">この手順を実行するには、シェルを使用する必要があります。 オンプレミスの Exchange 組織で Exchange 管理シェル を開く方法については、「 **Open the Shell**」を参照してください。 Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3a1-p102">You can only use the Shell to perform this procedure. To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
<span data-ttu-id="7a3a1-p103">管理者は、 `Export-Certificate` コマンドレットを使用して信頼できるコンピューターから証明書をエクスポートし、その種類を SST に設定することによって、この SST ファイルを作成できます。  `Export-Certificate` コマンドレットの詳細については、「 [Export-Certificate](https://technet.microsoft.com/en-us/library/hh848628.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7a3a1-p103">As an administrator, you can create this SST file by exporting the certificates from a trusted machine using the  `Export-Certificate` cmdlet and specifying the type as SST. For more information the  `Export-Certificate` cmdlet, see the [Export-Certificate](https://technet.microsoft.com/en-us/library/hh848628.aspx) reference topic.</span></span> 
  
<span data-ttu-id="7a3a1-p104">SST ファイルが生成されたら、 `Set-Smimeconfig` コマンドレットと  _-SMIMECertificateIssuingCA_ パラメーターを使用して、そのファイルを仮想証明書ストアに保存します。例:  `Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content filename.sst -Encoding Byte)`</span><span class="sxs-lookup"><span data-stu-id="7a3a1-p104">Once the SST file is generated, use the  `Set-Smimeconfig` cmdlet to save it in the virtual certificate store by using the  _-SMIMECertificateIssuingCA_ parameter. For example:  `Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content filename.sst -Encoding Byte)`</span></span>
  
## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="7a3a1-116">証明書が有効なことを確認する</span><span class="sxs-lookup"><span data-stu-id="7a3a1-116">Ensuring a certificate is valid</span></span>
<span data-ttu-id="7a3a1-117"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="7a3a1-117"></span></span>

<span data-ttu-id="7a3a1-p105">Exchange 2013 SP1 は、まず、SST ファイルをチェックして、証明書を検証します。検証が失敗した場合は、ローカル コンピューターの証明書ストアを調査して、証明書を検証します。この動作は、Exchange 2013 SP1 で変更されたもので、以前のバージョンの Exchange とは異なります。Exchange Online では、SST のみが検証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7a3a1-p105">Exchange 2013 SP1 first checks for the SST file and validates the certificate. If the validation fails, it will look at the local machine certificate store to validate the certificate. This behavior is new for Exchange 2013 SP1 and different from prior versions of Exchange. In Exchange Online only the SST will be used for validation.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="7a3a1-122">詳細情報</span><span class="sxs-lookup"><span data-stu-id="7a3a1-122">More Information</span></span>
<span data-ttu-id="7a3a1-123"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="7a3a1-123"></span></span>

[<span data-ttu-id="7a3a1-124">S/MIME によるメッセージの署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="7a3a1-124">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
  
[<span data-ttu-id="7a3a1-125">Get SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="7a3a1-125">Get-SmimeConfig</span></span>](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
  

