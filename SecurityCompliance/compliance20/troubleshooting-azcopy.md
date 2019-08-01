---
title: Advanced eDiscovery での AzCopy のトラブルシューティング
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: eb8c84d696a05f86246a512f1867d8efc98881a0
ms.sourcegitcommit: 73dcdafb15b462223d1a670c781db260eb73c2f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "36048095"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Advanced eDiscovery での AzCopy のトラブルシューティング

高度な電子情報開示でエラーを修復するために Office ではない365データまたはドキュメントを読み込む場合、ユーザーインターフェイスは、アップロードするファイルが保存されている場所と Azure ストレージの場所を含む、Azure AzCopy コマンドを提供します。ファイルがアップロードされる場所。 ドキュメントをアップロードするには、このコマンドをコピーして、ローカルコンピューターのコマンドプロンプトで実行します。  次のスクリーンショットは、AzCopy コマンドの例を示しています。

![Office 365 以外のファイルをアップロードする](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

通常、提供されるコマンドは、実行時に機能します。 ただし、表示されるコマンドが正常に実行されない場合もあります。 考えられるいくつかの理由を次に示します。

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>サポートされているバージョンの AzCopy がローカルコンピューターにインストールされていません

現時点では、Advanced 電子情報開示で Office 以外の365データを読み込むには AzCopy v1.1 を使用する必要があります。 AzCopy v2.0 を使用していない場合、前のスクリーンショットに表示されている [**ファイルのアップロード**] ページに表示される azcopy コマンドはエラーを返します。 このバージョンをインストールするには、「 [Windows で AzCopy](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)v2.0 でデータを転送する」を参照してください。

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy がローカルコンピューターにインストールされていないか、既定の場所にインストールされていません

AzCopy がインストールされていない場合や、既定のインストール先 (つまり`%ProgramFiles(x86)%`) 以外の場所にインストールされている場合、azcopy コマンドを実行すると、次のエラーが表示されることがあります。

    The system cannot find the path specified.

AzCopy がローカルコンピューターにインストールされていない場合は、[ここ](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)からインストールできます。 必ず既定の場所にインストールしてください。

AzCopy がインストールされていても、既定の場所とは異なる場所にインストールされている場合は、コマンドをコピーしてテキストファイルに貼り付け、次に、AzCopy がインストールされている場所へのパスを変更することができます。 たとえば、Azcopy がに`%ProgramFiles%`ある場合は、コマンドの最初の部分をから`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe`に`%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`変更できます。 この変更を行った後、テキストファイルからコピーし、コマンドプロンプトで実行します。

> [!TIP]
> AzCopy が既定のインストール先以外の場所にインストールされている場合は、それをアンインストールしてから、既定の場所に再インストールすることを検討してください。 これにより、今後この問題を回避することができます。
