---
title: Office 365 から電子的証拠開示検索結果をエクスポートするときは、ダウンロード速度を上げる
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: 検索結果をダウンロードするとき、データのスループットを向上するのには Windows レジストリを構成する方法について説明し、Office 365 のセキュリティ データを検索する&amp;コンプライアンス センターと Office 365 の詳細の開示。
ms.openlocfilehash: 3f456f5ee0312d4d4d7b95f868520e6756a90fd1
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532808"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a>Office 365 から電子的証拠開示検索結果をエクスポートするときは、ダウンロード速度を上げる

Office 365 のセキュリティ コンテンツの検索結果をダウンロードするのには Office 365 の電子的証拠開示のエクスポート ツールを使用すると&amp;コンプライアンス センターまたはダウンロードのデータを Office 365 の高度な電子的証拠開示、ツールから特定の数の同時実行のエクスポートを開始します。ローカル コンピューターにデータをダウンロードする操作です。既定では、コンカレント ・ オペレーションの数が 8 倍のデータをダウンロードして使用しているコンピューターでのコアの数を設定します。たとえば、デュアル コア コンピューター (つまり、1 つのチップ上の 2 つの中央演算処理装置) がある場合は、同時実行のエクスポート操作の既定数は 16 です。増やすには、データ転送のスループットとをダウンロード処理の高速化、検索結果のダウンロードに使用するコンピューターの Windows レジストリ設定を構成することで同時操作の数を変更できます。ダウンロード処理の高速化に 24 の並行処理の設定を開始することをお勧めします。
  
低帯域幅のネットワーク上で検索結果をダウンロードすると、この設定を増やすこと、影響を及ぼすことがあります。または、(並行処理の最大数は 512 です)、高帯域幅ネットワークでの同時オペレーションを 24 個を超えるに設定できる場合があります。このレジストリ設定を構成した後は、環境内のコンカレント ・ オペレーションの最適数を検索するように変更する必要があります。
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a>データをエクスポートするときに、コンカレント ・ オペレーションの数を変更するレジストリを設定を作成します。

セキュリティからの検索結果のダウンロードを使用しているコンピューターで次の手順を実行&amp;コンプライアンス センターや高度な電子的証拠開示のデータです。
  
1. 開いている場合は、Office 365 の電子的証拠開示のエクスポート ツールを閉じます。 
    
2. .Reg のファイル名サフィックスを使用して、レジストリ ファイルのウィンドウに次のテキストを保存します。たとえば、ConcurrentOperations.reg です。 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    前に説明すると、24 の同時オペレーションを開始し、し、必要に応じてこの設定を変更することをお勧めします。
    
3. Windows エクスプ ローラーで、をクリックしてまたは前の手順で作成した .reg ファイルをダブルクリックします。
    
4. ユーザー アクセスの制御] ウィンドウで **[はい]** に変更した場合、レジストリ エディターを使用をクリックします。 
    
5. 続行するメッセージが表示されたら、[**はい**] をクリックします。
    
    レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。
    
6. 値を変更する手順 2 ~ 5 を繰り返すことができます、`DownloadConcurrency`のレジストリ設定です。 
    
    > [!IMPORTANT]
    > 作成または変更した後、`DownloadConcurrency`レジストリ設定は、必ず新しいエクスポート ジョブを作成または検索結果のデータをダウンロードする既存のエクスポート ジョブを再起動します。詳細については、[詳細について](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo)はを参照してください。 
  
## <a name="more-information"></a>詳細情報

- 最初にこの手順で作成した .reg ファイルを実行するとき、新しいレジストリ キーが作成されます。`DownloadConcurrency`のレジストリ設定を変更および編集の .reg ファイルを再実行するたびに編集します。 
    
- Office 365 の電子的証拠開示のエクスポート ツールでは、 [Azure AzCopy ユーティリティ](https://go.microsoft.com/fwlink/?linkid=849949)を使用して、セキュリティの検索データをダウンロード&amp;コンプライアンス センターまたは高度な電子的証拠開示します。構成する、`DownloadConcurrency`レジストリ設定は、 **/NC**パラメーターを使用して AzCopy ユーティリティを実行するときに似ています。などのレジストリ設定`"DownloadConcurrency=24"`のパラメーターの値を使用すると同じ効果があります`/NC:24`AzCopy ユーティリティを使用しています。 
    
- (検索結果をもう一度ダウンロードしようとしています) を再起動しますが現在進行中のエクスポート ダウンロードを停止すると、Office 365 の電子的証拠開示のエクスポート ツールは、同じダウンロードを再開しようとします。ダウンロードを開始する場合は停止し、変更、`DownloadConcurrency`レジストリ設定、ダウンロード失敗する可能性が (**ダウンロード結果のエクスポート**] をクリック) で再起動する場合。エクスポート ツールは、前にレジストリ設定を変更したためではない有効な設定を使用してダウンロードを再開しようとして ためにです。
    
    したがってを変更した後、`DownloadConcurrency`のレジストリ設定を [セキュリティ] をクリックして**エクスポートを再起動**) エクスポート ジョブを再開することを確認して&amp;コンプライアンス センターです。エクスポートされた結果をダウンロードできます。検索結果とデータのエクスポートの詳細についてを参照してください。
    
  - [Office 365 のセキュリティ コンテンツの検索結果をエクスポートする&amp;コンプライアンス センター](export-search-results.md)
    
  - [Office 365 Advanced eDiscovery で結果をエクスポートする](export-results-in-advanced-ediscovery.md)
    
