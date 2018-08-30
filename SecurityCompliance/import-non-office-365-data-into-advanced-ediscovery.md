---
title: Advanced eDiscovery のために Office 365 以外のコンテンツをインポートする
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 5/25/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: 方法、Azure に O365 に格納されていないコンテンツをインポートする手順を実行する blob AeD を分析するため
ms.openlocfilehash: ab6c7ac76a159603a34719aa8edb51de3a4fabbb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532813"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a>Advanced eDiscovery のために Office 365 以外のコンテンツをインポートする

電子的証拠開示の Office 365 の詳細を分析する必要がありますすべてのドキュメントは、Office 365 で生活しています。非 Office 365 の内容とケースのリンク、Azure ストレージの blob に (PST ファイル) を除く Office 365 のライブし、高度な電子的証拠開示で解析されていないドキュメントをアップロードすること、高度な電子的証拠開示の機能をインポートします。この手順では、分析のために高度な電子的証拠開示に、Office 365 以外のドキュメントを表示する方法を示します。
  
> [!NOTE]
> 高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。 
  
> [!NOTE]
> Office 365 以外のコンテンツのため、Office 365 の高度な電子的証拠開示のデータ ・ ストレージ ・ アドオン サブスクリプションを購入できます。これは、高度な電子的証拠開示を使用して分析するのにはコンテンツだけで利用可能です。[購入または編集、およびビジネス向けの Office 365 用のアドオン](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6)で手順を実行し、Office 365 の高度な電子的証拠開示のストレージ ・ アドオンを購入します。 
  
## <a name="before-you-begin"></a>はじめに

この手順で説明したように非 Office 365 のアップロード機能を使用するがあることが必要です。
  
- コンプライアンスの高度なアドオンと E5 のサブスクリプションの Office 365 E3
    
- Office 365 以外のコンテンツがアップロードされるすべての通告は、コンプライアンスの高度なアドオンと E5 のライセンス E3 を持つ必要があります。
    
- 既存の電子的証拠開示ケース
    
- 保管担当者ごとの 1 つのフォルダーは、この形式の*alias@domainname*では、フォルダーの名前のフォルダーにアップロードするすべてのファイルが収集されます。*Alias@domainname*は、Office 365 のユーザーのエイリアスとドメインである必要があります。*Alias@domainname*のすべてのフォルダーは、ルート フォルダーに収集できます。ルート フォルダーは、 *alias@domainname*フォルダーを含めることができますのみ、必要があります圧縮しないファイルのルート フォルダー 
    
- 電子的証拠開示マネージャーまたは管理者の電子的証拠開示のいずれかのアカウント
    
- -Office 365 以外のコンテンツのフォルダー構造にアクセスできるコンピューターにインストールされている[Microsoft Azure ストレージ ・ ツール](https://aka.ms/downloadazcopy)です。 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>高度な電子的証拠開示に Office 365 以外のコンテンツをアップロードします。

1. 電子的証拠開示マネージャーまたは管理者の電子的証拠開示では、**電子的証拠開示**を Office 365 以外のデータをアップロードする場合を開きます。サポート案件を作成する場合を参照してください[電子的証拠開示の場合は、Office 365 のセキュリティを管理する&amp;コンプライアンス センター](manage-ediscovery-cases.md)
    
2. **高度な電子的証拠開示に切り替える**] をクリックします。
    
3. [**ソースの種類**には、**非 Office 365 のデータ**を選択します。
    
4. **追加のコンテナー**をクリックします。コンテナーの名前し、説明を追加します。
    
5. コンテナーの一覧から新たに追加されたコンテナーを選択し、コンテナーの詳細ペインに表示し、ウィンドウを URL をコピー
    
6. 管理者としてコマンド プロンプトを開き、インストールされている AzCopy があるフォルダーにディレクトリを変更する.
    
7. 次のようにファイルをアップロードするのには AzCopy コマンド ・ ラインを作成します。
    
    AzCopy/Source:"*ローカル マシン上のルート フォルダーへの完全パス*」/Dest:"*までコンテナーの URL が、ですか?* 」/DestSAS:」からコンテナーの url の残りの部分を *、でしょうか。最後に*/秒 
    
    たとえば、これらの値を使用します。 
    
  - ルート フォルダーの C:\Collected データ 
    
  - コンテナー url -https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&ampは sr = c&amp;si = NonOfficeData15 %7 C 0&amp;sig = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA %3 D
    
    AzCopy コマンドラインの構文は次のようになります。
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    Azcopy の詳細については構文を参照してください、 [Windows 上で AzCopy を使用してデータを転送](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)します。 
    
    > [!IMPORTANT]
    > ユーザーごとに 1 つのルート フォルダーが存在する必要があり、フォルダー名は、 *alias@domainname*の形式である必要があります。 
  
8. フォルダーが、アップロードを完了するが高度な電子的証拠開示に戻ります。アップロードしたフォルダー内のコンテンツは、高度な電子的証拠開示で処理する準備ができました。コンテナーを選択し、[プロセス] をクリックします。高度な電子的証拠開示の詳細については処理を参照してください、[プロセスのモジュールを実行し Office 365 の高度な電子的証拠の開示にデータを読み込む](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
    
    > [!IMPORTANT]
    > コンテナーは、高度な電子的証拠開示で正常に処理されて後、は、Azure で SAS ストレージに新しいコンテンツを追加することができなくなります。その他のコンテンツの収集し分析の高度な電子的証拠開示の場合に追加する、新しい**非 Office 365 のデータ**コンテナーを作成してこの手順を繰り返してください。 
  
    > [!NOTE]
    > コンテナーの*フォルダーの名前付けの問題により正常に処理されない*問題を修正し、まだなら新しいコンテナーと再接続を作成し、この資料の手順を使用してもう一度アップロードします。 
  

