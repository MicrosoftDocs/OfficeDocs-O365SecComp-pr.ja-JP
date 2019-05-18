---
title: Office 365 で問題を定義してユーザーを割り当てる高度な電子情報開示
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 48d37ee7-05bd-4cb8-9723-a8959ad23fbe
description: Office 365 Advanced eDiscovery でユーザーを割り当てたり、電子情報開示ケースの問題を削除したりするなど、案件を追加または編集する方法について説明します。
ms.openlocfilehash: a7dad3cce54a3162cedf3c14e521f5e8fe966acf
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34150689"
---
# <a name="define-issues-and-assign-users-in-office-365-advanced-ediscovery"></a>Office 365 で問題を定義してユーザーを割り当てる高度な電子情報開示

> [!NOTE]
> Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。 
  
詳細な電子情報開示では、1つまたは複数の問題をケース内に定義できます。 問題の定義により、さらにトピックの分類を行うことができます。 新しいケースに接続する場合は、1つの既定の問題が提供されます。 既定の問題名を編集して、ユーザーを懸案事項に割り当てることができます。 
  
## <a name="adding-or-editing-an-issue-and-assigning-users"></a>懸案事項の追加または編集とユーザーの割り当て

1. [**関連性\>の関連性の設定**] タブ\>で、[**問題**] を選択します。
    
    ![関連性の設定の問題](media/dfd8f9ef-b167-4ed9-980e-00ae98a97169.png)
  
2. 問題を追加するには、* * + * * アイコンをクリックします。 [**懸案事項の追加**] ダイアログが表示されます。 
    
    ![[関連性の設定] の追加問題](media/c8e94982-139a-472a-b85d-282f2d742046.png)
  
    問題を編集するには、[**編集**] アイコンをクリックします。 
    
3. [**発行名**] で、ケースにわかりやすく、重要な名前を入力します。 
    
4. [**説明**] に、問題に関する情報を入力します。
    
5. [**同時トレーニングを有効**にする] チェックボックスをオンにして、このオプションを有効にします。 この設定により、複数の校閲者が同時に同じ問題に対処できます (個別のサンプル)。 
    
6. [**発行するユーザーの割り当て**] の [**すべてのユーザー** ] の一覧で、懸案事項に割り当てるユーザーを選択し、右側にある矢印をクリックして、**選択した**ユーザーの一覧にユーザーを追加します。 必要に応じて繰り返します。 上記のウィンドウでは、"Admin" が選択されたユーザーとして表示されます。 
    
    > [!NOTE]
    > 問題へのユーザー割り当ては、関連性トレーニングサイクルの前後で変更できます。 
  
7. [**選択したユーザー**] で、選択したユーザーの名前の横にあるドロップダウンリストから、次のいずれかのサンプリングモードを選択します。 
    
  - **On**: ファイルを表示し、タグを付けることができます。 既定の設定です。
    
  - **Idle**: ファイルは表示できます。タグ付けは省略可能です。
    
  - **Off**: ファイルを表示またはタグ付けすることができません。
    
8. 懸案事項の追加が完了したら、[ **OK]** をクリックします。
    
## <a name="deleting-issues"></a>問題の削除

問題が定義された直後に削除される (つまり、データベースから削除される) 場合があり、その問題に対して実際の作業が行われていないことがあります。 
  
1. [**関連性\>の関連性の設定**] タブで、[**問題**] を選択します。
    
2. データベースから削除する問題を選択し、[**削除**] をクリックします。
    
3. 確認メッセージが表示されます。 [ **はい**] をクリックして確定します。 
    
4. **[OK]** をクリックします。
    
## <a name="see-also"></a>関連項目

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[インポートしたファイルを追加するためのロードの設定](set-up-loads-to-add-imported-files.md)
  
[強調表示されたキーワードと詳細オプションの定義](define-highlighted-keywords-and-advanced-options.md)

