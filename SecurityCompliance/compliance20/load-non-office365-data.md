---
title: レビュー セットに Office 365 以外のデータを読み込む
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 高度な電子情報開示ケースのレビューセットに Office 365 以外のデータをインポートします。
ms.openlocfilehash: d7609c774e7c8a42e24b22a87fbed271a12a97f5
ms.sourcegitcommit: 73dcdafb15b462223d1a670c781db260eb73c2f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "36048109"
---
# <a name="load-non-office-365-data-into-a-review-set"></a>レビュー セットに Office 365 以外のデータを読み込む

上級電子情報開示で分析する必要があるすべてのドキュメントが Office 365 にあるわけではありません。 Advanced eDiscovery で Office 365 以外のデータインポート機能を使用すると、Office 365 にないドキュメントをレビューセットにアップロードできます。 この記事では、非 Office 365 ドキュメントを分析のために上級電子情報開示に移行する方法について説明します。

>[!Note]
>高度な電子情報開示では、組織の Microsoft 365 または Office 365 E5 サブスクリプション、および Advanced コンプライアンスアドオンサブスクリプションを備えた E3 サブスクリプションが必要です。 その計画がなく、高度な電子情報開示を試行する必要がある場合は、Office 365 Enterprise E5 の試用版にサインアップすることができます。

## <a name="before-you-begin"></a>始める前に

この記事に記載されている「Office 以外の365をアップロードする」機能を使用するには、次のものが必要です。

- Office に対応していない365コンテンツに関連付ける必要があるすべての保管担当者には、E5 ライセンスが割り当てられているか、または Advanced コンプライアンスアドオンライセンスを備えた E3 ライセンスが必要です。

- 既存の高度な電子情報開示ケース。

- Office 以外の365データをアップロードして関連付けるには、保管担当者をケースに追加する必要があります。

- Office 以外の365データは、Advanced eDiscovery でサポートされているファイルの種類である必要があります。 詳細については、「 [Advanced eDiscovery でサポートされるファイルの種類](supported-filetypes-ediscovery20.md)」を参照してください。

- レビューセットにアップロードされたすべてのファイルは、フォルダーに配置されている必要があります。各フォルダーは特定の保管担当者に関連付けられています。 これらのフォルダーの名前には、*エイリアス @ domainname*のような名前を付ける必要があります。 エイリアス @ domainname は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。 ルートフォルダー内のすべてのエイリアス @ domainname フォルダーを収集できます。 ルートフォルダーには、別名 @ domainname folders のみを含めることができます。 ルートフォルダー内のルースファイルはサポートされていません。

   アップロードする Office 365 以外のデータのフォルダー構造は、次の例のようになります。

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   この例では、abraham.mcmahon@contoso.com、jewell.gordon@contoso.com、および staci.gonzalez@contoso.com は、保管担当者の SMTP アドレスです。

   ![Office 以外の365データアップロードフォルダーの構造](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- 電子情報開示マネージャーの役割グループに割り当てられているアカウント (および電子情報開示管理者として追加されたもの)。

- Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされている AzCopy v2.0 ツール。 AzCopy をインストールするには、「 [Windows で AzCopy](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)v2.0 を使用してデータを転送する」を参照してください。 AzCopy は、既定の場所である **% ProgramFiles (x86)% \ Microsoft SDKs\Azure\AzCopy**にインストールしてください。 AzCopy v1.1 を使用する必要があります。 その他のバージョンの AzCopy は、高度な電子情報開示で Office 以外の365データを読み込む場合には機能しない可能性があります。


## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Office 以外の365コンテンツを上級電子情報開示にアップロードする

1. 電子情報開示マネージャーまたは電子情報開示管理者として、Advanced eDiscovery を開き、Office 以外の365データのアップロード先となるケースを開きます。  

2. [**チェックセット**] をクリックし、[Office 以外の365データをアップロードするレビューセット] を選択します。  レビューセットを持っていない場合は、作成できます。 
 
3. レビューセットで、[**レビューセットの管理**] をクリックし、[ **Office 以外の365データ**タイルの [**アップロードの表示**] をクリックします。

4. [**ファイルのアップロード**] をクリックして、Office 365 以外のデータインポートウィザードを起動します。

   ![ファイルをアップロードする](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   ウィザードの最初の手順では、にファイルをアップロードするための、セキュリティ保護された Microsoft 提供の Azure ストレージの場所を準備します。  準備が完了すると、 **[次へ: ファイルのアップロード**] ボタンがアクティブになります。

   ![Office 以外の365のインポート: 準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. [**次へ: ファイルのアップロード**] をクリックします。

6. [**ファイルのアップロード**] ページで、次の操作を行います。

   ![Office 以外の365インポート: ファイルのアップロード](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. [**ファイルの場所のパス**] ボックスで、アップロードする Office 365 以外のデータを格納したルートフォルダーの場所を確認するか、または入力します。 たとえば、[**開始する前に] セクション**に表示されるサンプルファイルの場所については、「 **%USERPROFILE\Downloads\nonO365**」と入力します。 正しい場所を指定すると、パスの下のボックスに表示される AzCopy コマンドが適切に更新されるようになります。

   b. [**クリップボードにコピー** ] をクリックして、ボックスに表示されているコマンドをコピーします。

7. Windows コマンドプロンプトを起動し、前の手順でコピーしたコマンドを貼り付け、 **enter**キーを押して、azcopy コマンドを開始します。  コマンドを開始すると、Office 以外の365ファイルは、手順4で準備した Azure ストレージの場所にアップロードされます。

   ![Office 以外の365インポート: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > 前述したように、[**ファイルのアップロード**] ページで提供されているコマンドを正常に使用するには、azcopy v1.1 を使用する必要があります。 指定した AzCopy コマンドが失敗した場合は、「 [Advanced eDiscovery での AzCopy のトラブルシューティング](troubleshooting-azcopy.md)」を参照してください。

8. セキュリティ & コンプライアンスセンターに戻り、[**次へ:** ウィザードでファイルを処理します] をクリックします。  これにより、Azure ストレージの場所にアップロードされた非 Office 365 ファイルの処理、テキスト抽出、およびインデックス作成が開始されます。  

9. Office ではない365ファイルの処理の進行状況を追跡するには、[**処理ファイル**] ページまたは [**ジョブ**] タブで、[ **office 以外の365データをレビューセットに追加する**] というジョブを表示します。  ジョブが完了すると、新しいファイルがレビューセットで利用できるようになります。

   ![Office 以外の365インポート: 処理ファイル](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. 処理が終了したら、ウィザードを閉じることができます。