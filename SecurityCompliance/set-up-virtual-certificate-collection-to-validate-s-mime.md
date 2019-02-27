---
title: S/MIME を検証するために Exchange Online で仮想証明書コレクションをセットアップする
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: 管理者は、Exchange Online で S/MIME 証明書の検証に使用する仮想証明書コレクションを作成する方法について説明します。
ms.openlocfilehash: 2aa6e529f5ca374af6fe6d80a403058a8b6e468a
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296950"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>S/MIME を検証するために Exchange Online で仮想証明書コレクションをセットアップする

管理者は、S/MIME 証明書の検証に使用する Exchange Online の仮想証明書コレクションを構成する必要があります。この仮想証明書コレクションは、SST ファイル拡張子を持つ証明書ストアとして設定されます。SST ファイルには、S/MIME 証明書の検証時に使用されるすべてのルート証明書と中間証明書が含まれています。

## <a name="create-and-save-an-sst"></a>SST を作成して保存する

この SST 証明書ストアファイルは、Windows PowerShell で**証明書のエクスポート**コマンドレットを使用して信頼できるコンピューターから証明書をエクスポートし、 _Type_の値を SST として指定することによって作成できます。手順については、「 [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)」を参照してください。

SST 証明書ストアファイルを取得したら、exchange online PowerShell で次の構文を使用して、exchange online 仮想証明書ストアに SST ファイルの内容を保存します。exchange online powershell に接続するには、「 [exchange online powershell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

この例では、SST ファイル C:\My Documents\Exported 証明書ストア SST をインポートします。

```
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

構文およびパラメーターの詳細については、「 [Set-smimeconfig](https://docs.microsoft.com/en-us/powershell/module/exchange/encryption-and-certificates/set-smimeconfig)」を参照してください。

## <a name="ensuring-a-certificate-is-valid"></a>証明書が有効なことを確認する

Exchange Online では、証明書の検証に SST のみが使用されます。

## <a name="more-information"></a>詳細情報

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)

[Get-smimeconfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
