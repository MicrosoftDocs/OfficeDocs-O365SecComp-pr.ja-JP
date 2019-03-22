---
title: Advanced eDiscovery での azcopy のトラブルシューティング (プレビュー)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 9711bee4ec9a61510b47568df37dfd3135e1e00c
ms.sourcegitcommit: cf9d9b545a7c153d314aa9c08c7fb16fcd785b3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "30742509"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery-preview"></a>Advanced eDiscovery での azcopy のトラブルシューティング (プレビュー)

高度な電子情報開示 (プレビュー) でエラーを修復するために Office 以外の365データまたはドキュメントを読み込む場合、ユーザーインターフェイスは、アップロードするファイルが保存されている場所と azure にパラメーターを含む azure azcopy コマンドを提供します。ファイルがアップロードされる保存場所。 ドキュメントをアップロードするには、このコマンドをコピーして、ローカルコンピューターのコマンドプロンプトで実行します。  次のスクリーンショットは、azcopy コマンドの例を示しています。

![Office 365 以外のファイルをアップロードする](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

ほとんどの場合、提供されているコマンドは、実行時に機能します。 ただし、表示されるコマンドが正常に実行されない場合もあります。 考えられるいくつかの理由を次に示します。

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>azcopy がローカルコンピューターにインストールされていないか、既定の場所にインストールされていません

azcopy がインストールされていない場合や、既定のインストール先 (つまり`%ProgramFiles(x86)%`) 以外の場所にインストールされている場合、azcopy コマンドを実行すると、次のエラーが表示されることがあります。

    The system cannot find the path specified.

azcopy がローカルコンピューターにインストールされていない場合は、ここからインストールできます (既定の場所にインストールする[https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)必要があります)。


azcopy がインストールされていても、既定の場所とは別の場所にインストールされている場合は、コマンドをコピーしてテキストファイルに貼り付け、次に、azcopy が実際にインストールされている場所へのパスを変更することができます。 たとえば、azcopy がに`%ProgramFiles%`ある場合は、コマンドの最初の部分をから`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe`に`%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`変更できます。 この変更を行った後、テキストファイルからコピーし、コマンドプロンプトで実行します。

> [!TIP]
> azcopy が既定のインストール先以外の場所にインストールされている場合は、それをアンインストールしてから、既定の場所に再インストールすることを検討してください。 これにより、今後この問題を回避することができます。