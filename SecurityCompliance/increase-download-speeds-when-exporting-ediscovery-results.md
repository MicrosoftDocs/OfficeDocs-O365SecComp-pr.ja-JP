---
title: Office 365 から電子情報開示検索の結果をエクスポートするときにダウンロード速度を上げる
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: Office 365 のセキュリティ & コンプライアンスセンターおよび Advanced eDiscovery から検索結果をダウンロードし、データを検索するときに、データのスループットを向上させるように Windows レジストリを構成する方法について説明します。
ms.openlocfilehash: 10eff929d6b668d5e2bc22d8ee7f223da4943326
ms.sourcegitcommit: f0e3c9de0b545081a4d264f74559b941f6c71410
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "31958627"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a>Office 365 から電子情報開示検索の結果をエクスポートするときにダウンロード速度を上げる

office 365 eDiscovery エクスポートツールを使用して、Security & コンプライアンスセンターでコンテンツ検索の結果をダウンロードするか、office 365 Advanced eDiscovery からのデータをダウンロードすると、ツールによって、ダウンロードするための一定数の同時エクスポート操作が開始されます。ローカルコンピューターにデータを作成します。 既定では、同時操作の数は、データのダウンロードに使用しているコンピューターのコア数の8倍に設定されます。 たとえば、デュアルコアコンピューター (1 つのチップ上に2台の中央処理装置があることを意味します) では、既定の同時エクスポート操作数は16です。 データ転送のスループットとダウンロード処理の速度を向上させるために、検索結果のダウンロードに使用するコンピューターで Windows レジストリ設定を構成することによって、同時操作の数を増やすことができます。 ダウンロードプロセスを高速化するには、24回の同時操作の設定から始めることをお勧めします。
  
低帯域幅ネットワーク経由で検索結果をダウンロードする場合は、この設定値を大きくすると、悪影響を及ぼす可能性があります。 または、高帯域幅ネットワーク (同時操作の最大数は 48) で、24を超える同時操作の設定値を増やすことができる場合もあります。 このレジストリ設定を構成した後で、環境に最適な同時操作数を見つけるために、この設定を変更する必要がある場合があります。
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a>レジストリ設定を作成してデータをエクスポートするときの同時操作数を変更する

セキュリティ & コンプライアンスセンターまたは Advanced eDiscovery からのデータからの検索結果をダウンロードするために使用するコンピューターで、次の手順を実行します。
  
1. Office 365 eDiscovery エクスポートツールが開いている場合は、これを閉じます。 
    
2. ファイル名サフィックス .reg を使用して、次のテキストをウィンドウのレジストリファイルに保存します。たとえば、ConcurrentOperations のようにします。 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    前述のとおり、24回の同時操作から始めて、必要に応じてこの設定を変更することをお勧めします。
    
3. エクスプローラーで、前の手順で作成した .reg ファイルをクリックまたはダブルクリックします。
    
4. [ユーザーアクセス制御] ウィンドウで、[**はい**] をクリックしてレジストリエディターに変更を許可します。 
    
5. 続行するように求めるメッセージが表示されたら、[**はい**] をクリックします。
    
    レジストリエディターに、設定が正常にレジストリに追加されたことを示すメッセージが表示されます。
    
6. 手順 2-5 を繰り返して、 `DownloadConcurrency`レジストリの設定の値を変更できます。 
    
    > [!IMPORTANT]
    > `DownloadConcurrency`レジストリ設定を作成または変更した後は、必ず新しいエクスポートジョブを作成するか、またはダウンロードする検索結果またはデータに対して既存のエクスポートジョブを再起動します。 詳細については、「[詳細情報](#more-information)」を参照してください。 
  
## <a name="more-information"></a>詳細情報

- この手順で作成した .reg ファイルを初めて実行するときに、新しいレジストリキーが作成されます。 その後`DownloadConcurrency` 、.reg の編集ファイルを変更して再実行するたびに、レジストリ設定が編集されます。 
    
- Office 365 eDiscovery エクスポートツールは、 [Azure azcopy ユーティリティ](https://go.microsoft.com/fwlink/?linkid=849949)を使用して、Security & コンプライアンスセンターまたは Advanced eDiscovery から検索データをダウンロードします。 レジストリ設定`DownloadConcurrency`の構成は、azcopy ユーティリティを実行するときに、 **/NC**パラメーターを使用するのと似ています。 そのため、の`"DownloadConcurrency=24"`レジストリ設定は、azcopy ユーティリティ`/NC:24`でパラメーター値を使用するのと同じ効果があります。 
    
- 現在進行中のエクスポートのダウンロードを停止してから再起動すると (検索結果を再度ダウンロードしようとした場合)、Office 365 eDiscovery エクスポートツールは同じダウンロードを再開します。 そのため、ダウンロードを開始し、停止した後、 `DownloadConcurrency`レジストリ設定を変更すると、再起動するとダウンロードが失敗することがあります ([エクスポートされた結果の**ダウンロード**] をクリックします)。 これは、エクスポートツールがレジストリ設定を変更したために有効でない設定を使用して、以前のダウンロードを再開しようとしたためです。
    
    そのため、 `DownloadConcurrency`レジストリ設定を変更した後、Security & コンプライアンスセンターで、必ずエクスポートジョブを再起動します ([**再起動**] をクリックします)。 その後、エクスポートされた結果をダウンロードできます。 検索結果とデータのエクスポートの詳細については、以下を参照してください。
    
  - [コンテンツ検索の結果をエクスポートする](export-search-results.md)
    
  - [Office の結果をエクスポートする 365 Advanced eDiscovery](export-results-in-advanced-ediscovery.md)
    
