---
title: レビュー セットに Office 365 以外のデータを読み込む
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
ms.openlocfilehash: 60775002d5ebec83aacbec350a044b9d6ffeb461
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834963"
---
# <a name="load-non-office-365-data-into-a-review-set"></a>レビュー セットに Office 365 以外のデータを読み込む

Office 365 の高度な電子情報開示で分析する必要があるすべてのドキュメントが Office 365 に存在するわけではありません。 Advanced eDiscovery の Office 365 以外のコンテンツインポート機能を使用すると、Office 365 に存在しないドキュメントをレビューセットにアップロードして、高度な電子情報開示で分析することができます。 この手順では、非 Office 365 ドキュメントを分析のために上級電子情報開示に移行する方法を示します。

>[!Note]
>高度な電子情報開示では、組織の高度なコンプライアンスアドオンまたは E5 サブスクリプションに Office 365 E3 が必要です。 その計画がなく、高度な電子情報開示を試行する必要がある場合は、Office 365 Enterprise E5 の試用版にサインアップすることができます。

## <a name="before-you-begin"></a>始める前に

この記事の説明に従って Office 365 以外のアップロード機能を使用するには、次の条件を持っている必要があります。

- Office 365 または Microsoft 365 E5 サブスクリプション、または Advanced コンプライアンスアドオンサブスクリプションを使用した E3 サブスクリプション。

- Office 以外の365コンテンツをアップロードするすべての保管担当者には、高度なコンプライアンスアドオンライセンスを備えた E3 ライセンスが必要です。または、E5 ライセンスが必要です。

- 既存の高度な電子情報開示ケース。

- 関連付けられている Office 以外の365データをアップロードする前に、保管担当者をケースに追加する必要があります。

- アップロードされるすべてのファイルは、特定の保管担当者に関連付けられているフォルダーに格納されている必要があります。 これらのフォルダーの名前には、*エイリアス @ domainname*のような名前を付ける必要があります。 *エイリアス @ domainname*は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。 すべての*エイリアス @ domainname*フォルダーをルートフォルダーに収集できます。 ルートフォルダーには、*別名 @ domainname* folders のみを含めることができます。ルートフォルダーでは、圧縮されていないファイルを使用できません。

   たとえば、アップロードする Office 365 以外のデータのフォルダー構造は、次のようになります。

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   この例では、abraham.mcmahon@contoso.com、jewell.gordon@contoso.com、および staci.gonzalez@contoso.com は、保管担当者の SMTP アドレスです。

   ![Office 以外の365データアップロードフォルダーの構造](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- 電子情報開示マネージャーまたは電子情報開示管理者のどちらかのアカウント

- Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされた Microsoft Azure Storage Tools。

- AzCopy をインストールします。これは、ここから行うことができます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Office 以外の365コンテンツを上級電子情報開示にアップロードする

1. 電子情報開示マネージャーまたは電子情報開示管理者として、Advanced eDiscovery を開き、Office 以外の365データのアップロード先となるケースを開きます。  [**閲覧設定**] タブをクリックし、Office ではない365データを読み込むレビューセットを選択します。  レビューセットをまだ作成していない場合は、ここで作成できます。  最後に、[**レビューセットの管理**] をクリックし、[Office 以外の365データタイルでの**アップロードの表示**] をクリックします。

2. [**ファイルのアップロード**] ボタンをクリックして、Office 365 以外のデータインポートウィザードを起動します。

   ![ファイルをアップロードする](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. ウィザードの最初の手順では、ファイルをアップロードするために、セキュリティで保護された Azure blob を準備するだけです。  準備が完了したら、[**次へ: ファイルのアップロード**] ボタンをクリックします。

   ![Office 以外の365インポート-準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. [**ファイルのアップロード**] ステップで、**ファイルの場所へのパス**を指定します。この場合、インポートする予定の非 Office 365 データが配置されます。  正しい場所を設定することにより、AzCopy コマンドが正しく更新されます。

   > [!NOTE]
   > AzCopy をまだインストールしていない場合は、ここから実行できます。https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. [**クリップボードにコピー** ] リンクをクリックして、定義済みのコマンドをコピーします。 Windows コマンドプロンプトを起動し、コマンドを貼り付けて、enter キーを押します。  ファイルは、次の手順のために secure Azure blob ストレージにアップロードされます。

   ![Office 以外の365インポート-ファイルのアップロード](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   ![Office 以外の365インポート-AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > 指定した AzCopy コマンドが失敗した場合は、 [「Advanced eDiscovery での AzCopy のトラブルシューティング」](troubleshooting-azcopy.md)を参照してください。

6. 最後に、Security & コンプライアンスに戻って、[**次へ: ファイルの処理**] ボタンをクリックします。  これにより、アップロードしたファイルの処理、テキストの抽出、およびインデックス作成が開始されます。  処理の進行状況を追跡するには、[**ジョブ**] タブを使用します。 完了すると、新しいファイルがレビューセットで利用できるようになります。  処理が完了したら、ウィザードを閉じることができます。

   ![Office 以外の365インポート処理ファイル](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

