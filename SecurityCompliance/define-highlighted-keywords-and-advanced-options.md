---
title: Office 365 Advanced eDiscovery で強調表示されたキーワードと高度なオプションを定義する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 03cc4387-2c7d-4058-8a44-0deefb58f011
description: 'コスト パラメーターを指定して Office 365 の高度な電子的証拠の開示にタグ付けしているときに関連するファイルを識別するために関連するユーザー定義のキーワードを追加する方法について説明します。  '
ms.openlocfilehash: c7e16fc18ba724d5b778b42e3782e04df10c50ec
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531983"
---
# <a name="define-highlighted-keywords-and-advanced-options-in-office-365-advanced-ediscovery"></a>Office 365 Advanced eDiscovery で強調表示されたキーワードと高度なオプションを定義する

> [!NOTE]
> 高度な電子的証拠開示では、組織のコンプライアンスを高度なアドオンや、E5 のサブスクリプションの Office 365 E3 が必要です。その計画して高度な電子的証拠開示を実行する、 [Office 365 エンタープライズ E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)することができます。 
  
高度な電子的証拠開示は、タグ付けしているときに関連するファイルを識別するために関連するユーザー定義のキーワードを追加します。キーワードで指定した色で表示されます**関連\>タグ**。 
  
後述のように、キーワード リストを追加することができますと、キーワードのリストと関連する問題に色が割り当てられています。ツールヒントに表示されますキーワードの説明では、いずれかが存在する場合は、二重下線で示されるようにします。
  
> [!IMPORTANT]
> ヒット結果のヒットの関連性の強調表示とキーワードを表示する関連性の中にドキュメント内でタグ付けが行われない日本語、中国語、韓国語の 2 バイト文字セットです。 
  
## <a name="adding-highlighted-keywords"></a>強調表示されているキーワードを追加します。

1. **の関連性\>関連性の高いセットアップ**] タブで、 **[強調表示のキーワード**を選択します。
    
2. クリックして、**+** のキーワードを追加するアイコン。**新しいキーワードを追加**] ダイアログが表示されます。 
    
3. **キーワード**キーワードをコンマで区切ります、キーワードのリストを入力します。 
    
4. [**色**] 一覧で、入力したキーワードのリストを強調表示する色を選択します。 
    
5. **問題の選択**] ボックスの一覧で選択した懸案事項をすべての問題」に、[キーワード] ボックスの一覧を適用するかどうかを選択します。 
    
6. **説明**キーワードのリスト (省略可能) を入力します。
    
    ![新しいキーワードの追加](media/1683a71f-0875-48fc-b4ef-01f3b0e8e8e9.png)
  
7. 設定が終わったら **[ok]** をクリックします。作成するリストがテーブルに追加のキーワード] ボックスの一覧とことができます編集または削除します。 
    
    ![関連性の設定のキーワードの一覧](media/a05d5ec0-8bde-470d-97e2-456b169281d6.png)
  
関連性で、指定した色に、ユーザー定義のキーワードが表示されます\>タグです。 
  
## <a name="specifying-relevance-setup-advanced-settings"></a>詳細設定の関連性設定を指定します。

これらの設定は、関連性のトラックおよび決定のグラフを反映します。
  
1. **の関連性\>関連性の高いセットアップ**] タブで、**詳細設定**を選択します。
    
2. **コスト パラメーター**ダイアログ ボックスで、次の選択を行います。 
    
1. **コスト ($) を 1 時間あたりの確認**] ボックスの一覧でドルで、金額を選択して、デフォルトを受け入れます。 
    
2. **時間を確認するファイルの数**] ボックスの一覧で金額を選択して、デフォルトを受け入れます。 
    
    ![関連性の設定のコストのパラメーター](media/bab7b5b7-6297-4e7c-b0a6-ba5aa8b21787.png)
  
3. [**保存**] をクリックします。選択した設定が保存されます。
    
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[問題を定義し、ユーザーの割り当て](define-issues-and-assign-users.md)
  
[インポートしたファイルを追加するのには、荷重を設定](set-up-loads-to-add-imported-files.md)

