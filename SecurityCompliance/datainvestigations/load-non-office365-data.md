---
title: Office 以外の365データを証拠に読み込む
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: f5478d89d71db22e710b5d5fcab397ae8d6aee56
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030327"
---
# <a name="load-non-office-365-data-into-evidence"></a>Office 以外の365データを証拠に読み込む

office 365 の高度な電子情報開示で分析する必要があるすべてのドキュメントが office 365 に存在するわけではありません。 advanced ediscovery の office 365 以外のコンテンツインポート機能を使用すると、office 365 に存在しないドキュメントを作業セットにアップロードして、advanced ediscovery で分析することができます。 この手順では、非 Office 365 ドキュメントを分析のために上級電子情報開示に移行する方法を示します。

>[!Note]
>高度な電子情報開示では、組織の高度なコンプライアンスアドオンまたは E5 サブスクリプションに Office 365 E3 が必要です。 その計画がなく、高度な電子情報開示を試行する必要がある場合は、Office 365 Enterprise E5 の試用版にサインアップすることができます。

## <a name="before-you-begin"></a>はじめに
この手順の説明に従って Office 365 以外のアップロード機能を使用するには、次の条件を持っている必要があります。

- 高度なコンプライアンスアドオンまたは E5 サブスクリプションを備えた Office 365 E3。

- Office 以外の365コンテンツをアップロードするすべての保管担当者には、高度なコンプライアンスアドオンまたは E5 ライセンスを含む E3 が必要です。

- 既存の電子情報開示ケース。

- 収集されたすべてのファイルは、保管担当者ごとにフォルダーが1つ存在し、フォルダーの名前が*エイリアス @ domainname*の形式になっているフォルダーにアップロードされます。 *エイリアス @ domainname*は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。 すべての*エイリアス @ domainname*フォルダーをルートフォルダーに収集できます。 ルートフォルダーに含めることができるのは、 *@ domainname* folders のエイリアスのみです。ルートフォルダーには圧縮されていないファイルは存在しない必要があります。

- Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされている、電子情報開示マネージャーまたは電子情報開示管理者の Microsoft Azure Storage Tools のどちらかのアカウント。

- azcopy をインストールします。これは、ここから行うことができます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Office 以外の365コンテンツを上級電子情報開示にアップロードする

1. 電子情報開示マネージャーまたは電子情報開示管理者として、Advanced ediscovery を開き、Office 以外の365データのアップロード先となるケースを開きます。  [**作業設定**] タブをクリックし、Office 以外の365データを読み込む作業セットを選択します。  作業セットをまだ作成していない場合は、ここで作成できます。  最後に、[動作**設定の管理**] をクリックし、[Office ではない365データ] セクションの [**アップロードを表示**する] をクリックします。

2. [**ファイルのアップロード**] ボタンをクリックして、Office 365 以外のデータインポートウィザードを起動します。

![ファイルをアップロードする](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. ウィザードの最初の手順では、ファイルをアップロードするために、セキュリティで保護された Azure blob を準備するだけです。  準備が整ったら、[**次へ: ファイルのアップロード**] ボタンをクリックします。

![Office 以外の365インポート-準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. [**ファイルのアップロード**] ステップで、**ファイルの場所へのパス**を指定します。この場合、インポートする予定の非 Office 365 データが配置されます。  正しい場所を設定することにより、azcopy コマンドが正しく更新されます。

> [!NOTE]
> azcopy をまだインストールしていない場合は、ここから実行できます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. [**クリップボードにコピー** ] リンクをクリックして、定義済みのコマンドをコピーします。 windows コマンドプロンプトを起動し、コマンドを貼り付けて、enter キーを押します。  ファイルは、次の手順のために secure Azure blob ストレージにアップロードされます。

![Office 以外の365インポート-ファイルのアップロード](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Office 以外の365インポート-azcopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. 最後に、Security & コンプライアンスに戻って、[**次へ: ファイルの処理**] ボタンをクリックします。  これにより、アップロードしたファイルの処理、テキストの抽出、およびインデックス作成が開始されます。  処理の進行状況を追跡するには、[**ジョブ**] タブを使用します。 完了すると、新しいファイルがワーキングセットで利用できるようになります。  処理が完了したら、ウィザードを閉じることができます。

![Office 以外の365インポート処理ファイル](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

