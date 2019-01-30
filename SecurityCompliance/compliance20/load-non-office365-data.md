---
title: ワーキング セットにない-Office 365 のデータを読み込む
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 427b4c8c9dfffe351827a6869ae26a5356d646d8
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608030"
---
# <a name="load-non-office-365-data-into-a-working-set"></a>ワーキング セットにない-Office 365 のデータを読み込む

電子的証拠開示の Office 365 の詳細を分析する必要がありますすべてのドキュメントは、Office 365 で生活しています。非 Office 365 のコンテンツを持つだ Office 365 のワーキング セットには、高度な電子的証拠開示を分析するためのドキュメントをアップロードするときに高度な電子的証拠開示の機能をインポートします。この手順では、分析のために高度な電子的証拠開示に、Office 365 以外のドキュメントを表示する方法を示します。

>[!Note]
>Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、Office 365 Enterprise E5 の試用版にサインアップしてください。

## <a name="before-you-begin"></a>はじめに
この手順で説明したように非 Office 365 のアップロード機能を使用するがあることが必要です。
* コンプライアンスの高度なアドオンと E5 のサブスクリプションの Office 365 E3
* Office 365 以外のコンテンツがアップロードされるすべての通告は、コンプライアンスの高度なアドオンと E5 のライセンス E3 を持つ必要があります。
* 既存の電子的証拠開示ケース
* 保管担当者ごとの 1 つのフォルダーは、この形式の*alias@domainname*では、フォルダーの名前のフォルダーにアップロードするすべてのファイルが収集されます。*Alias@domainname*は、Office 365 のユーザーのエイリアスとドメインである必要があります。*Alias@domainname*のすべてのフォルダーは、ルート フォルダーに収集できます。ルート フォルダーは、 *alias@domainname*フォルダーを含めることができますのみ、必要があります圧縮しないファイルのルート フォルダー
* 電子的証拠開示マネージャーか、電子的証拠開示管理者 Microsoft Azure ストレージ ツールを Office 365 以外のコンテンツ フォルダーの構造体へのアクセスを持つコンピューターにインストールされているアカウントです。
* インストールの AzCopy、ここから実行することができます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>高度な電子的証拠開示に Office 365 以外のコンテンツをアップロードします。
1. 電子的証拠開示マネージャーまたは管理者の電子的証拠開示では、高度な電子的証拠開示は、[Office 365 以外のデータをアップロードする場合に開きます。 **ワーキング セット**] タブをクリックし、ワーキング セットにない Office 365 のデータをロードするを選択します。 ワーキング セットをまだ作成していない場合これを行うようになりました。 最後に、[**管理の動作を設定**し、非 Office 365 のデータ セクションに**ビューのアップロード**] をクリックします。

2. 非 Office 365 のデータのインポート ウィザードを起動するのには [**ファイルをアップロード**] ボタンをクリックします。

![ファイルをアップロードします。](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. ウィザードの最初のステップは、単にアップロードするファイルのセキュリティで保護された Azure blob を準備します。 準備が compelted をクリックして、**次: ファイルをアップロード**ボタン。

![非 Office 365 のインポート - の準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. **ファイルのアップロード**の手順で、**ファイルの場所へのパス**を指定してこれをインポートするように計画する非 Office 365 のデータが格納されています。 コマンドが正常に更新 AzCopy を確実に正しい場所を設定します。

> [!NOTE]
> AzCopy をまだインストールしていない場合は、ここから行うこのできます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. 定義済みのコマンドをコピーするには、**クリップボードにコピー** ] リンクをクリックします。Windows コマンド プロンプトを起動し、コマンドを貼り付け、enter キーを押します。 ファイルは、次の手順のセキュリティで保護された Azure blob ストレージにアップロードされます。

![Office 365 以外のインポート ・ ファイルをアップロード](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![非 Office 365 のインポート - AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. 最後に、セキュリティ & 準拠状態に戻すしをクリックして、**次: ファイルを処理する**ボタン。 テキストの抽出を処理して、アップロードされたファイルのインデックス作成が開始されます。 ここまたは **[ジョブ**] タブでの処理の進行状況を追跡することができます。 完了後、新しいファイルがワーキング セットで使用されます。 処理が完了した後、ウィザードを閉じることができます。

![Office 365 以外のインポート ・ ファイルの処理](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

