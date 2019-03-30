---
title: Office 365 の高度な電子情報開示のケースとテナントの設定を定義する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 383809de-7f5e-4a1d-9098-c525f67b7a9a
description: 'Office 365 Advanced eDiscovery のケースレベルで定義できるラベル、クロスモジュール、およびテナントの設定について説明します。  '
ms.openlocfilehash: 2e95984651bf4da86bd64cfc3730fae75391410d
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000840"
---
# <a name="define-case-and-tenant-settings-in-office-365-advanced-ediscovery"></a>Office 365 の高度な電子情報開示のケースとテナントの設定を定義する

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
このトピックでは、高度な電子情報開示ケースとテナントの設定について説明します。
  
## <a name="case-settings"></a>ケースの設定

このセクションでは、ケースレベルで定義できる設定について説明します。
  
> [!NOTE]
> 詳細な電子情報開示で現在ケースが選択されていない場合は、[**ケースの設定**] タブが非アクティブになります。 
  
### <a name="cross-module"></a>交差モジュール

次のクロスモジュール設定は、高度な電子情報開示モジュールに適用される case オプションです。
  
- ログイン後の既定のページ: Advanced eDiscovery の開始時に既定のページが表示されるように設定します。
    
- [ファイルの表示名]: ファイルタイトル/パスまたは電子メールの件名の高度な電子情報開示表示名の代わりに、上級電子情報開示全体に表示されるファイル識別子。
    
1. **cogwheel**アイコンをクリックして、**設定とユーティリティ**を開きます。 [**設定] と\> [ユーティリティケースの設定**] タブ\>の**2 次元のモジュール**を開きます。 
    
2. ログインオプションの [**既定のページ**から] を選択します。 
    
  - **前回のログインの最後のページ**
    
  - **ケースページ**
    
3. [**保存**] をクリックします。
    
## <a name="tenant-settings"></a>テナントの設定

詳細な電子情報開示テナントの設定については、このセクションで説明します。
  
### <a name="user-administration"></a>ユーザー管理

ユーザー管理オプションの詳細については、「[ユーザーとケースをセットアップ](set-up-users-and-cases-in-advanced-ediscovery.md)する」を参照してください。
  
### <a name="event-log"></a>イベントログ

イベントログは、高度な電子情報開示操作中に、高度な電子情報開示処理に関するメタデータを提供します。 たとえば、メインの高度な電子情報開示プロセス (インポート、分析、関連性、エクスポート) の開始時刻、および終了時刻と状態を含みます。 このログは、データ処理アクティビティを追跡およびトラブルシューティングするため、およびエラーと警告に対処するために使用できます。
  
1. **cogwheel**アイコンをクリックして、**設定とユーティリティ**を開きます。 
    
2. [**設定とユーティリティ\>のテナント設定**] タブで、[**イベントログ**] を選択します。 イベントログのデータが表示されます。
    
  - ケースごとにログ出力をフィルター処理するには、ケースリスト**** からケースを選択します。 
    
  - 列ごとにログを並べ替えるには、列見出しをクリックします。 
    
  - 列の順序を変更するには、列見出しをクリックしてドラッグします。
    
  - ログページ間を移動するに**\>** は**\<** 、[] と [アイコン] をクリックします。 
    
### <a name="system-information"></a>システム情報

高度な電子情報開示のバージョンシステム情報とアクティブなタスクが [テナントの設定] タブに表示されます。
  
1. **cogwheel**アイコンをクリックして、**設定とユーティリティ**を開きます。 
    
2. [**設定とユーティリティ\>のテナント設定**] タブで、[**システム情報**] を選択します。 バージョン情報が表示されます。
    
テナント情報の下にある [**更新**] アイコンをクリックすると、表示を更新できます。 
  
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[ユーティリティを使用する](use-advanced-ediscovery-utilities.md)

