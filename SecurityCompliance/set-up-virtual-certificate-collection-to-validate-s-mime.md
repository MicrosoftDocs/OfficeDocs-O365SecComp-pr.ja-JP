---
title: S/MIME を検証するために Exchange Online で仮想証明書コレクションをセットアップする
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: 管理者は、Exchange Online で S/MIME 証明書の検証に使用する仮想証明書コレクションを作成する方法について説明します。
ms.openlocfilehash: 15998bce1971952286d8dd4401a92f1e9e47c25d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260725"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="2bf98-103">S/MIME を検証するために Exchange Online で仮想証明書コレクションをセットアップする</span><span class="sxs-lookup"><span data-stu-id="2bf98-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

<span data-ttu-id="2bf98-104">管理者は、S/MIME 証明書の検証に使用する Exchange Online の仮想証明書コレクションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bf98-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="2bf98-105">この仮想証明書コレクションは、SST ファイル拡張子を持つ証明書ストアとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="2bf98-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="2bf98-106">SST ファイルには、S/MIME 証明書の検証時に使用されるすべてのルート証明書と中間証明書が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2bf98-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="2bf98-107">SST を作成して保存する</span><span class="sxs-lookup"><span data-stu-id="2bf98-107">Create and save an SST</span></span>

<span data-ttu-id="2bf98-108">この SST 証明書ストアファイルは、Windows PowerShell で**証明書のエクスポート**コマンドレットを使用して信頼できるコンピューターから証明書をエクスポートし、 _Type_の値を SST として指定することによって作成できます。</span><span class="sxs-lookup"><span data-stu-id="2bf98-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="2bf98-109">手順については、「 [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bf98-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="2bf98-110">SST 証明書ストアファイルを取得したら、exchange online PowerShell で次の構文を使用して、exchange online 仮想証明書ストアに SST ファイルの内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="2bf98-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="2bf98-111">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bf98-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="2bf98-112">この例では、SST ファイル C:\My Documents\Exported 証明書ストア SST をインポートします。</span><span class="sxs-lookup"><span data-stu-id="2bf98-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="2bf98-113">構文およびパラメーターの詳細については、「 [Set-smimeconfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2bf98-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="2bf98-114">証明書が有効なことを確認する</span><span class="sxs-lookup"><span data-stu-id="2bf98-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="2bf98-115">Exchange Online では、証明書の検証に SST のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2bf98-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="2bf98-116">詳細</span><span class="sxs-lookup"><span data-stu-id="2bf98-116">More Information</span></span>

[<span data-ttu-id="2bf98-117">S/MIME によるメッセージの署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="2bf98-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="2bf98-118">Get-smimeconfig</span><span class="sxs-lookup"><span data-stu-id="2bf98-118">Get-SmimeConfig</span></span>](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
