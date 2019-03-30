---
title: 高度な電子情報開示分析のために Office 365 以外のコンテンツをインポートする
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: O365 に格納されていないコンテンツを Azure blob にインポートして、aed で分析できるようにする手順
ms.openlocfilehash: 7b7694754b26951aa02930fd101631ba9060bc17
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31001170"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a>高度な電子情報開示分析のために Office 365 以外のコンテンツをインポートする

office 365 の高度な電子情報開示で分析する必要があるすべてのドキュメントが office 365 に存在するわけではありません。 advanced 電子情報開示の office 365 以外のコンテンツインポート機能を使用すると、office 365 に存在しないドキュメント (PST ファイルを除く) を、ケースにリンクされた Azure ストレージ blob にアップロードし、アドバンスト ediscovery で分析することができます。 この手順では、非 Office 365 ドキュメントを分析のために上級電子情報開示に移行する方法を示します。
  
> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
> [!NOTE]
> office 365 Advanced eDiscovery data storage アドオンサブスクリプションは、office 以外の365コンテンツに対して購入できます。 これは、Advanced eDiscovery で分析するコンテンツにのみ使用できます。 「 [office 365 for business の購入または編集とアドオン](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6)」の手順に従って、office 365 Advanced eDiscovery storage アドオンを購入します。 
  
## <a name="before-you-begin"></a>はじめに

この手順の説明に従って Office 365 以外のアップロード機能を使用するには、次の条件を持っている必要があります。
  
- 高度なコンプライアンスアドオンまたは E5 サブスクリプションを使用した Office 365 E3
    
- Office 以外の365コンテンツをアップロードするすべての保管担当者には、高度なコンプライアンスアドオンまたは E5 ライセンスを含む E3 が必要です。
    
- 既存の電子情報開示ケース
    
- 収集されたすべてのファイルは、保管担当者ごとにフォルダーが1つ存在し、フォルダーの名前が*エイリアス @ domainname*の形式になっているフォルダーにアップロードされます。 *エイリアス @ domainname*は、ユーザーの Office 365 エイリアスおよびドメインである必要があります。 すべての*エイリアス @ domainname*フォルダーをルートフォルダーに収集できます。 ルートフォルダーに含めることができるのは、 *@ domainname* folders のエイリアスのみです。ルートフォルダーには圧縮されていないファイルは存在しない必要があります。 
    
- 電子情報開示マネージャーまたは電子情報開示管理者のどちらかのアカウント
    
- Office 365 以外のコンテンツフォルダー構造にアクセスできるコンピューターにインストールされた[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) 。 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Office 以外の365コンテンツを上級電子情報開示にアップロードする

1. 電子情報開示マネージャーまたは電子情報開示管理者として、**電子情報開示**を開いて、Office 以外の365データがアップロードされるケースを開きます。 ケースを作成する必要がある場合は、「 [Office 365 セキュリティ&amp; /コンプライアンスセンターで電子情報開示ケースを管理](manage-ediscovery-cases.md)する」を参照してください。
    
2. [**高度な電子情報開示に切り替え] を**クリックします。
    
3. [**ソースの種類**] で **、[Office 以外の365データ**] を選択します。
    
4. [**コンテナーの追加**] をクリックします。 コンテナーの名前を指定し、説明を追加します。
    
5. [コンテナー] ボックスの一覧から新しく追加したコンテナーを選択し、[コンテナー詳細] ウィンドウに表示される URL をコピーして、ウィンドウを閉じます。
    
6. 管理者としてコマンドプロンプトを開き、azcopy がインストールされているフォルダーにディレクトリを変更します。
    
7. azcopy コマンドラインを作成して、次のようにファイルをアップロードします。
    
    azcopy/source: "*ローカルコンピューター上のルートフォルダーへの完全なパス*"/Dest: "*コンテナー URL があるかどうか*。  "/destsas:"*コンテナー url の残りの部分を end* "/S. 
    
    たとえば、次のような値を使用します。 
    
  - ルートフォルダー-c/一度収集したデータ 
    
  - コンテナーの url https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp-; sr =&amp;c si = NonOfficeData15%&amp;7C0 sig = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3d
    
    azcopy コマンドライン構文は次のようになります。
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    azcopy 構文の詳細については、「 [Windows での azcopy を使用してデータを転送する](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)」を参照してください。 
    
    > [!IMPORTANT]
    > ユーザーごとに1つのルートフォルダーが存在し、フォルダー名が*エイリアス @ domainname*形式になっている必要があります。 
  
8. フォルダーのアップロードが完了したら、[Advanced eDiscovery] に切り替えます。 アップロードしたフォルダーの内容は、高度な電子情報開示で処理する準備ができました。 コンテナーを選択し、[プロセス] ボタンをクリックします。 高度な電子情報開示処理の詳細については、「 [Process モジュールを実行し、Office 365 でデータを読み込む](run-the-process-module-and-load-data-in-advanced-ediscovery.md)」を参照してください。 advanced ediscovery
    
    > [!IMPORTANT]
    > 上級電子情報開示でコンテナーが正常に処理されると、Azure の SAS ストレージに新しいコンテンツを追加できなくなります。 追加のコンテンツを収集し、高度な電子情報開示分析のケースに追加する場合は、 **Office 365 以外**の新しいデータコンテナーを作成し、この手順を繰り返す必要があります。 
  
    > [!NOTE]
    > *フォルダーの名前付けの問題によってコンテナーが正常に処理されず*に問題が修正された場合は、この記事の手順を使用して、新しいコンテナーと再接続を作成し、再度アップロードする必要があります。 
  

