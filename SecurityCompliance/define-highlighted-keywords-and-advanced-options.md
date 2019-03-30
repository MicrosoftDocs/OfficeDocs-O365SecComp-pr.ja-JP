---
title: Office 365 の高度な電子情報開示で強調表示されたキーワードと詳細オプションを定義する
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
ms.assetid: 03cc4387-2c7d-4058-8a44-0deefb58f011
description: 'ユーザー定義のキーワードを関連性に追加して、Office 365 の高度な電子情報開示でのタグ付けとコストパラメータを指定する際に関連ファイルを特定する方法について説明します。  '
ms.openlocfilehash: aec9efac91cc3fb48068fca9b6b7313f829f4fe2
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999340"
---
# <a name="define-highlighted-keywords-and-advanced-options-in-office-365-advanced-ediscovery"></a>Office 365 の高度な電子情報開示で強調表示されたキーワードと詳細オプションを定義する

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
詳細な電子情報開示では、ユーザー定義のキーワードを関連性に追加して、タグ付けの際に関連ファイルを識別するのに役立てることができます。 キーワードは、**関連性\>タグ**の指定した色で表示されます。 
  
以下に示すように、キーワードリストを追加したり、キーワードリストに割り当てられている色や関連する問題を追加したりできます。 ヒントには、キーワードの説明 (存在する場合) が、二重下線で示されます。
  
> [!IMPORTANT]
> 関連性のタグ付け時にドキュメント内の関連性の強調表示とキーワードヒット結果の表示は、日本語、中国語、韓国語の2バイト文字セットでは機能しません。 
  
## <a name="adding-highlighted-keywords"></a>強調表示されたキーワードの追加

1. [**関連性\>の関連性の設定**] タブで、[**強調表示**されたキーワード] を選択します。
    
2. アイコンを**+** クリックしてキーワードを追加します。 [**新しいキーワードの追加**] ダイアログが表示されます。 
    
3. [**キーワード**] にキーワードリストを入力します。キーワードはコンマで区切ります。 
    
4. [**色**] ボックスの一覧で色を選択し、[入力したキーワード] ボックスの一覧を強調表示にします。 
    
5. **[問題の選択**] リストで、[キーワード] リストを [すべての問題] に適用するか、選択した案件に適用するかを選択します。 
    
6. [**説明**] に、キーワードリスト (省略可能) を入力します。
    
    ![新しいキーワードの追加](media/1683a71f-0875-48fc-b4ef-01f3b0e8e8e9.png)
  
7. 完了したら、[ **OK]** をクリックします。 作成したリストがキーワードリストテーブルに追加され、編集または削除できるようになります。 
    
    ![関連性の設定のキーワードの一覧](media/a05d5ec0-8bde-470d-97e2-456b169281d6.png)
  
ユーザー定義のキーワードが、[関連性\> ] タグの指定した色で表示されます。 
  
## <a name="specifying-relevance-setup-advanced-settings"></a>関連性セットアップの詳細設定の指定

これらの設定は、関連性のあるトラックと判断グラフに影響します。
  
1. [**関連性\>の関連性の設定**] タブで、[**詳細設定**] を選択します。
    
2. [**コストパラメーター** ] ダイアログで、次のように選択します。 
    
1. 1**時間あたりのコストレビュー ($)** の一覧で、[金額] を選択するか、既定値をそのまま使用します。 
    
2. [**時間で確認されたファイルの数**] ボックスの一覧で、金額を選択するか、既定値をそのまま使用します。 
    
    ![関連性の設定のコストのパラメーター](media/bab7b5b7-6297-4e7c-b0a6-ba5aa8b21787.png)
  
3. [**保存**] をクリックします。 選択した設定が保存されます。
    
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[問題の定義とユーザーの割り当て](define-issues-and-assign-users.md)
  
[インポートしたファイルを追加するためのロードの設定](set-up-loads-to-add-imported-files.md)

