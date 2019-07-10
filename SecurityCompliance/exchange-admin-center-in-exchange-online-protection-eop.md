---
title: 'Exchange Online Protection の Exchange 管理センター '
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Exchange 管理センター (EAC) は、Microsoft Exchange Online Protection (EOP) 向けの Web ベース管理コンソールです。
ms.openlocfilehash: 9d32e6bfc9137a04d92c3916894e2070313607a8
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599513"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a>Exchange Online Protection の Exchange 管理センター 

Exchange 管理センター (EAC) は、Microsoft Exchange Online Protection (EOP) 向けの Web ベース管理コンソールです。 
  
このトピックの Exchange 2013 バージョンについては、「[Exchange admin center in Exchange 2013](http://technet.microsoft.com/library/a9aea11a-6ba3-4f4a-a76e-79072e7cfc7d.aspx)」を参照してください。
  
このトピックの Exchange Online バージョンについては、「[Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。
  
## <a name="accessing-the-eac"></a>EACへのアクセスについて

ほとんどの場合、EOP のお客様は、Microsoft 365 管理センターを通じて EAC にアクセスします。 EOP へのリンクは、 **[自分]** タイルの横にある **[管理]** タイルのドロップ ダウン メニューから選択できます。 **[管理]** タイルをクリックし、ドロップ ダウン メニューから **[Exchange Online Protection]** を選択すると、EAC にアクセスできます。 
  
You can also access the EAC sign in page directly via the following URL: https://admin.protection.outlook.com/ecp/\<companydomain\>. For example, https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com. After specifying your user credentials you will be taken directly into the EAC.
  
## <a name="common-user-interface-elements-in-the-eac"></a>EAC で共通のユーザー インターフェイス要素

ここでは、EAC のユーザー インターフェイス要素について説明します。
  
![EOP-AdminCenter](media/EOP-AdminCenter.png)
  
### <a name="feature-pane"></a>機能ウィンドウ

EAC で実行する多くのタスクで、これがナビゲーションの第 1 階層になります。[機能] ウィンドウは、機能領域ごとに整理されています。
  
1. **受信者** 社内ユーザーおよび社外の連絡先を確認します。 
    
2. **アクセス許可** 管理者の役割を管理します。 
    
3. **コンプライアンス マネジメント** 監査ログや、管理者役割グループ レポートなどの各種レポートを確認します。 
    
4. **保護** 組織のマルウェア対策保護やスパム対策保護、および検疫のメッセージを管理します。 
    
5. **メール フロー** ルール、承認済みドメイン、コネクタ、およびメッセージ トレースの実行方法を管理します。 
    
### <a name="tabs"></a>タブ

タブは、ナビゲーションの第 2 階層になります。各機能領域にはさまざまなタブがあり、それぞれのタブは各機能を表しています。
  
### <a name="toolbar"></a>ツールバー

ほとんどのタブは、クリックするとツールバーが表示されます。ツールバーには、特定のアクションを実行する複数のアイコンがあります。次の表は、各アイコンとそのアクションを示しています。
  
|**アイコン**|**名前**|**Action**|
|:-----|:-----|:-----|
|![[追加] アイコン](media/ITPro-EAC-AddIcon.gif)           <br/> |追加、新規  <br/> |このアイコンを使用して、新しいオブジェクトを作成します。これらの一部のアイコンには下方向キーが関連付けられており、これをクリックして、作成可能な追加のオブジェクトを表示できます。  <br/> |
|![編集アイコン](media/ITPro-EAC-EditIcon.gif)           <br/> |編集  <br/> |このアイコンを使用してオブジェクトを編集します。  <br/> |
|![[削除] アイコン](media/ITPro-EAC-DeleteIcon.gif)           <br/> |削除  <br/> |このアイコンを使用してオブジェクトを削除します。一部の削除アイコンには下方向キーがあり、これをクリックして追加オプションを表示できます。  <br/> |
|![[検索] アイコン](media/ITPro-EAC-.gif)           <br/> |検索  <br/> |このアイコンを使用して、検索するオブジェクトの検索文字列を入力できる検索ボックスを開きます。  <br/> |
|![[最新の情報に更新] アイコン](media/ITPro-EAC-RefreshIcon.gif)           <br/> |最新の情報に更新  <br/> |このアイコンを使用してリスト ビューを更新します。  <br/> |
|![[その他のオプション] アイコン](media/ITPro-EAC-MoreOptionsIcon.gif)           <br/> |その他のオプション  <br/> |このアイコンを使用して、そのタブのオブジェクトに対して実行できる他のアクションを表示します。たとえば、 **受信者 \> ユーザー**のアイコンをクリックすると、 **詳細検索**のオプションが表示されます。  <br/> |
|![上矢印アイコン](media/ITPro-EAC-UpArrowIcon.gif)![下矢印アイコン](media/ITPro-EAC-DownArrowIcon.gif)           <br/> |上方向キーと下方向キー  <br/> |これらのアイコンを使用して、オブジェクトの優先度を上下に移動します。  <br/> |
|![[削除] アイコン](media/ITPro-EAC-RemoveIcon.gif)           <br/> |削除  <br/> |このアイコンを使用して、一覧からオブジェクトを削除します。  <br/> |
   
### <a name="list-view"></a>リスト ビュー

タブを選択すると、通常、リスト ビューが表示されます。EAC リスト ビューの表示可能限度は、ほぼ 10,000 オブジェクトです。さらに、ページングが含まれているため、結果をページングできます。
  
### <a name="details-pane"></a>詳細ウィンドウ

リスト ビューからオブジェクトを選択すると、そのオブジェクトに関する情報が詳細ウィンドウに表示されます。場合によっては、[詳細] ウィンドウに管理タスクが含まれていることがあります。
  
### <a name="me-tile-and-help"></a>[自分] タイルとヘルプ

**[自分]** タイルでは、EAC からのサインアウトおよび他のユーザーとしてサインインが行えます。 **[ヘルプ]**![ヘルプ アイコン](media/ITPro-EAC-HelpIcon.gif) ドロップ ダウン メニューから次のアクションを行えます。 
  
1. **ヘルプ**![ヘルプ アイコン](media/ITPro-EAC-HelpIcon.gif) をクリックして、オンライン ヘルプ コンテンツを表示します。 
    
2. **ヘルプ バブルを無効にする** ヘルプ バブルは、オブジェクトを作成または編集する際に、フィールドのコンテキスト ヘルプを表示します。ヘルプ バブルをオフにしたり、無効になっている場合はオンにすることができます。 
    
3. **著作権** このリンクをクリックして、Exchange Online Protection に関する著作権の情報を確認します。 
    
4. **プライバシー** ここをクリックして、Exchange Online Protection に関するプライバシー ポリシーを確認します。 
    
## <a name="supported-browsers"></a>サポートされているブラウザー

EAC を最大限に活用できるように、常に最新のブラウザー、Office クライアント、アプリを使用することをお勧めします。また、ソフトウェア更新プログラムも、利用可能になり次第インストールすることをお勧めします。サービスでサポートされるブラウザー要件とシステム要件の詳細については、「[Office 365 のシステム要件](https://go.microsoft.com/fwlink/p/?LinkID=402699)」を参照してください。 
  
## <a name="supported-languages-in-eop"></a>EOP でサポートされている言語

Exchange Online Protection でサポートされ、利用可能な言語は、以下のとおりです。
  
- アムハラ語
    
- アラビア語
    
- バスク語 (バスク)
    
- バングラ語 (インド)
    
- ブルガリア語
    
- カタルニア語
    
- 簡体字中国語
    
- 繁体字中国語
    
- クロアチア語
    
- チェコ語
    
- デンマーク語
    
- オランダ語
    
- オランダ語
    
- 英語
    
- エストニア語
    
- フィリピン語 (フィリピン)
    
- フィンランド語
    
- フランス語
    
- ガリシア語
    
- ドイツ語
    
- ギリシャ語
    
- グジャラート語
    
- ヘブライ語
    
- ヒンディー語
    
- ハンガリー語
    
- アイスランド語
    
- インドネシア語
    
- イタリア語
    
- 日本語
    
- カンナダ語
    
- カザフ語
    
- スワヒリ語
    
- 韓国語
    
- ラトビア語
    
- リトアニア語
    
- マレー語 (ブルネイ・ダルサラーム国)
    
- マレー語 (マレーシア)
    
- マラヤーラム語
    
- マラーティー語
    
- ノルウェー語 (ブークモール)
    
- ノルウェー語 (ニーノシュク)
    
- オリヤー語
    
- ペルシャ語
    
- ポーランド語
    
- ポルトガル語 (ブラジル)
    
- ポルトガル語 (ポルトガル)
    
- ルーマニア語
    
- ロシア語
    
- セルビア語 (キリル、セルビア)
    
- セルビア語 (ラテン)
    
- スロバキア語
    
- スロベニア語
    
- スペイン語
    
- スウェーデン語
    
- タミール語
    
- テルグ語
    
- タイ語
    
- トルコ語
    
- ウクライナ語
    
- ウルドゥ語
    
- ベトナム語
    
- ウェールズ語
    

