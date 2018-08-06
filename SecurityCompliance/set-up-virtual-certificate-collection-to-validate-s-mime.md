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
# <a name="set-up-virtual-certificate-collection-to-validate-smime"></a>S/MIME を検証するための仮想証明書コレクションをセットアップする

テナント管理者は、S/MIME 証明書の検証に使用する仮想証明書コレクションを構成する必要があります。この仮想証明書コレクションは、SST ファイル名拡張子を持つ証明書ストア ファイルの種類としてセットアップされます。SST ファイルには、S/MIME 証明書の検証時に使用されるすべてのルート証明書と中間証明書が含まれます。
  
## <a name="create-and-save-an-sst"></a>SST を作成して保存する
<a name="sectionSection0"> </a>

この手順を実行するには、シェルを使用する必要があります。 オンプレミスの Exchange 組織で Exchange 管理シェル を開く方法については、「 **Open the Shell**」を参照してください。 Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。
  
管理者は、 `Export-Certificate` コマンドレットを使用して信頼できるコンピューターから証明書をエクスポートし、その種類を SST に設定することによって、この SST ファイルを作成できます。  `Export-Certificate` コマンドレットの詳細については、「 [Export-Certificate](https://technet.microsoft.com/en-us/library/hh848628.aspx)」を参照してください。 
  
SST ファイルが生成されたら、 `Set-Smimeconfig` コマンドレットと  _-SMIMECertificateIssuingCA_ パラメーターを使用して、そのファイルを仮想証明書ストアに保存します。例:  `Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content filename.sst -Encoding Byte)`
  
## <a name="ensuring-a-certificate-is-valid"></a>証明書が有効なことを確認する
<a name="sectionSection1"> </a>

Exchange 2013 SP1 は、まず、SST ファイルをチェックして、証明書を検証します。検証が失敗した場合は、ローカル コンピューターの証明書ストアを調査して、証明書を検証します。この動作は、Exchange 2013 SP1 で変更されたもので、以前のバージョンの Exchange とは異なります。Exchange Online では、SST のみが検証に使用されます。
  
## <a name="more-information"></a>詳細情報
<a name="sectionSection2"> </a>

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)
  
[Get SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx)
  

