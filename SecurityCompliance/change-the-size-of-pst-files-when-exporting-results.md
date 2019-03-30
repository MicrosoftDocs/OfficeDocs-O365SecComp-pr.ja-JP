---
title: 電子情報開示検索結果をエクスポートするときに PST ファイルのサイズを変更する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 電子情報開示検索結果をエクスポートするときに、コンピューターにダウンロードされる PST ファイルの既定のサイズを変更できます。
ms.openlocfilehash: 98b543b6e34cb9cb075a765671def91742aee6c1
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999720"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>電子情報開示検索結果をエクスポートするときに PST ファイルのサイズを変更する

Office 365 ediscovery エクスポートツールを使用して、さまざまな Microsoft ediscovery ツールから電子情報開示検索の結果をエクスポートする場合、エクスポート可能な PST ファイルの既定のサイズは 10 GB です。 この既定のサイズを変更する場合は、検索結果のエクスポートに使用するコンピューターで Windows レジストリを編集できます。 これを行う理由の1つは、PST ファイルが DVD、コンパクトディスク、または USB ドライブなどのリムーバブルメディアに格納できるようにするためです。 
  
> [!NOTE]
>  Office 365 eDiscovery エクスポートツールは、セキュリティ/コンプライアンスセンター、Exchange online のインプレース電子情報開示、および SharePoint online の電子情報開示センターでコンテンツ検索ツールを使用して検索結果をエクスポートするために使用されます。
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>電子情報開示検索結果をエクスポートするときに PST ファイルのサイズを変更するためのレジストリ設定を作成する

電子情報開示検索の結果をエクスポートするために使用するコンピューターで、次の手順を実行します。
  
1. Office 365 eDiscovery エクスポートツールが開いている場合は、これを閉じます。 
    
2. ファイル名サフィックス .reg を使用して、次のテキストをウィンドウのレジストリファイルに保存します。たとえば、PstExportSize のようにします。 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    上記の例では、 `PstSizeLimitInBytes`値は1073741824バイトまたは約 1 GB に設定されます。 この`PstSizeLimitInBytes`設定の他のサンプル値を次に示します。 
    
    |**サイズ (GB) (約)**|**バイト単位のサイズ**|
    |:-----|:-----|
    |7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. 検索結果`PstSizeLimitInBytes`をエクスポートするときに、必要な PST ファイルの最大サイズに値を変更して、ファイルを保存します。 
    
4. エクスプローラーで、前の手順で作成した .reg ファイルをクリックまたはダブルクリックします。
    
5. [ユーザーアクセス制御] ウィンドウで、[**はい**] をクリックしてレジストリエディターに変更を許可します。 
    
6. 続行するように求めるメッセージが表示されたら、[**はい**] をクリックします。
    
    レジストリエディターに、設定が正常にレジストリに追加されたことを示すメッセージが表示されます。
    
7. 手順 3-6 を繰り返して、 `PstSizeLimitInBytes`レジストリの設定の値を変更できます。 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>電子情報開示検索結果をエクスポートするときの PST ファイルの既定のサイズ変更に関してよく寄せられる質問

 **既定のサイズが 10 GB ののはなぜですか。**
  
既定のサイズは 10 GB で、お客様のフィードバックに基づいています。10 GB は、1つの PST に含まれるコンテンツの最適な量と、ファイルの破損が最小限になる確率とのバランスが優れています。
  
 **PST ファイルの既定のサイズを増減する必要がありますか。**
  
お客様は、組織内の他の場所を物理的に出荷できるリムーバブルメディアに検索結果が格納されるように、サイズ制限を小さくする傾向があります。 10 GB を超える PST ファイルで破損の問題が発生する可能性があるため、既定のサイズを大きくしないことをお勧めします。
  
 **この操作を実行する必要があるコンピューター**
  
Office 365 eDiscovery エクスポートツールを実行するローカルコンピューターのレジストリ設定を変更する必要があります。
  
 **この設定を変更した後、コンピューターを再起動する必要がありますか。**
  
いいえ、コンピューターを再起動する必要はありません。 ただし、Office 365 eDiscovery エクスポートツールを実行している場合は、この設定を変更した後に、このツールを閉じて再起動する必要があります。
  
 **既存のレジストリキーを編集するか、新しいキーを作成しますか?**
  
この手順で作成した .reg ファイルを初めて実行するときに、新しいレジストリキーが作成されます。 その後、.reg の編集ファイルを変更して再実行するたびに、この設定が編集されます。
