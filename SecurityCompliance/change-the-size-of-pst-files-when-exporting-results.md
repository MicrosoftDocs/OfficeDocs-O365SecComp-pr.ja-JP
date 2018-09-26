---
title: 電子的証拠開示検索結果をエクスポートするときは、PST ファイルのサイズを変更します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 変更するには、電子的証拠開示検索結果をエクスポートすると、コンピューターへのダウンロードは、PST ファイルの既定のサイズ。
ms.openlocfilehash: 1479db72117729d2e5cfa6feec1d9a0d9a60ffb5
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25037990"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>電子的証拠開示検索結果をエクスポートするときは、PST ファイルのサイズを変更します。

マイクロソフトのさまざまな電子的証拠開示ツールから、電子メールの結果、電子的証拠開示検索をエクスポートするのには Office 365 の電子的証拠開示のエクスポート ツールを使用すると、エクスポート可能な PST ファイルの既定のサイズは、10 GB です。この既定のサイズを変更する場合は、検索結果のエクスポートに使用するコンピューターの Windows レジストリを編集できます。これを行う理由の 1 つは、PST ファイルがリムーバブル メディア、このような DVD、コンパクト ディスク、または USB ドライブに収まるようにします。 
  
> [!NOTE]
>  Office 365 の電子的証拠開示のエクスポート ツールを使用して Office 365 のセキュリティでコンテンツの検索を使用する場合は、検索結果をエクスポートするのには&amp;コンプライアンス センター、Exchange online では、埋め込み先での電子的証拠開示と電子情報開示センター SharePoint Online にします。 
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>電子的証拠開示検索結果をエクスポートする場合は、PST ファイルのサイズを変更するのにはレジストリの設定を作成します。

電子的証拠開示検索結果のエクスポートを使用しているコンピューター上には、次の手順を実行します。
  
1. 開いている場合は、Office 365 の電子的証拠開示のエクスポート ツールを閉じます。 
    
2. .Reg のファイル名サフィックスを使用して、レジストリ ファイルのウィンドウに次のテキストを保存します。たとえば、PstExportSize.reg です。 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    上記の例で、`PstSizeLimitInBytes`値は 1,073, 741,824 バイトまたは約 1 GB に設定します。他のいくつかのサンプル値をここでは、`PstSizeLimitInBytes`の設定です。 
    
    |**GB 単位のサイズ (約)**|**サイズ (バイト単位)**|
    |:-----|:-----|
    |.7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. 変更、 `PstSizeLimitInBytes` 、ファイルを保存して、検索結果をエクスポートするときは、PST ファイルの最大サイズの値です。 
    
4. Windows エクスプ ローラーで、をクリックしてまたは前の手順で作成した .reg ファイルをダブルクリックします。
    
5. ユーザー アクセスの制御] ウィンドウで **[はい]** に変更した場合、レジストリ エディターを使用をクリックします。 
    
6. 続行するメッセージが表示されたら、[**はい**] をクリックします。
    
    レジストリ エディターには、設定がレジストリに正常に追加されたことを示すメッセージが表示されます。
    
7. 手順 3 ~ 6 の値を変更するを繰り返すことができます、`PstSizeLimitInBytes`のレジストリ設定です。 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>電子的証拠開示検索結果をエクスポートする場合は、PST ファイルの既定のサイズを変更することに関するよく寄せられる質問

 **理由は、既定のサイズは 10 GB ですか。**
  
10 GB の既定のサイズは、顧客からのフィードバックはに基づいてでした。10 GB は、単一の pst ファイルの破損の可能性が最小のコンテンツの最適な量のバランスです。
  
 **増加または PST ファイルの既定のサイズを小さく必要がありますか。**
  
お客様は、検索結果は、組織内の他の場所に物理的にことができます出荷をリムーバブル ・ メディアに合うようにサイズの制限値を小さく傾向があります。PST ファイル 10 GB の破損の問題があるよりも大きいために、既定サイズを大きくことはお勧めしません。
  
 **どのようなコンピューターでこれを行うにあるでしょうか。**
  
Office 365 の電子的証拠開示のエクスポート ツールを実行する任意のローカル コンピューターのレジストリ設定を変更する必要があります。
  
 **この設定を変更後する必要があります、コンピューターを再起動しますか。**
  
いいえ、コンピューターを再起動する必要はありません。Office 365 の電子的証拠開示のエクスポート ツールを実行する場合と再起動を終了する必要がありますが、この設定を変更した後ことです。
  
 **既存のレジストリ キーを編集を取得して新しいキーを作成を取得してか。**
  
最初にこの手順で作成した .reg ファイルを実行するとき、新しいレジストリ キーが作成されます。設定を変更および編集の .reg ファイルを再実行するたびに編集します。
