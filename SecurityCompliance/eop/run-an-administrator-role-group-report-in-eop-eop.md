---
title: 'EOP で管理者役割グループ レポートを実行する '
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: 管理者が管理者の役割グループに対してメンバーを追加または削除すると、Microsoft Exchange Online Protection (EOP) によって各発生がログに記録されます。
ms.openlocfilehash: 752def771d95fcfbb3f7cbe0bc86a33b3967716d
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256185"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>EOP で管理者役割グループ レポートを実行する 

 管理者が管理者役割グループに対してメンバーを追加または削除すると、操作のたびに Microsoft Exchange Online Protection (EOP) がその情報をログに記録します。Exchange 管理センターで管理者役割グループ レポートを実行すると、検索結果としてエントリが表示されます。エントリには、影響を受ける役割グループ、誰がいつ役割グループのメンバーシップを変更したか、およびどのメンバーシップが更新されたかが含まれます。このレポートを使用して、組織内のユーザーに割り当てられた管理アクセス許可に対する変更を監視します。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- 予想所要時間:2 分
    
- 「この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「レポート」セクション。 
    
- このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。
    
> [!TIP]
> 問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>EAC を使用して管理者役割グループ レポートを実行する

管理者役割グループ レポートを実行して、特定の期間に組織の管理役割グループに加えられた変更を確認します。
  
1. EAC で、 **[コンプライアンス管理]** \> **[監査]** に移動し、 **[管理者の役割グループ レポートの実行]** を選択します。
    
2. **[開始日]** と **[終了日]** を選択します。既定では、管理者役割グループに対する過去 2 週間の変更のレポート検索が実行されます。
    
3. 特定の役割グループに対する変更を表示するには、 **[役割グループの選択]** をクリックします。後続のダイアログ ボックスで役割グループ (複数可) を選択し、 **[OK]** をクリックします。また、変更された役割グループをすべて検索するために、フィールドを空のままにしておくこともできます。
    
4. **[検索]** をクリックします。
    
指定した条件を使用して変更を検索した場合は、結果が結果ウィンドウに表示されます。検索結果内で役割グループをクリックすると、変更内容が詳細ウィンドウに表示されます。
  
## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

管理者の役割グループ レポートが正常に実行されると、日付の範囲内に変更された役割グループが検索結果ウィンドウに表示されます。検索結果がない場合、指定された日付の範囲内に役割グループの変更はなかったことを意味します。検索結果があるはずであれば、日付の範囲を変更してレポートを再度実行します。
  
## <a name="monitor-changes-to-role-group-membership"></a>役割グループのメンバーシップに対する変更の監視

役割グループのメンバーが追加または削除されると、詳細ウィンドウに表示される検索結果に、役割グループのメンバーシップが更新されたことが示され、現在のメンバーが一覧表示されます。検索結果には、どのユーザーが追加または削除されたかは明示されません。
  
ユーザーが追加または削除されたかどうかを判断するには、レポート内の 2 つの異なるエントリを比較する必要があります。たとえば、 **HelpDesk** 役割グループの次のログ エントリを見てみましょう。 
  
 **1/27/2013 4:43 PM**
  
 **管理者**
  
 **Updated members: Administrator;annb,florencef;pilarp**
  
 **2/06/2013 10:09 AM**
  
 **管理者**
  
 **Updated members: Administrator;annb;florencef;pilarp;tonip**
  
 **2/19/2013 2:12 PM**
  
 **管理者**
  
 **Updated members: Administrator;annb;florencef;tonip**
  
この例では、管理者ユーザー アカウントによって次の変更が加えられています。
  
- 2013 年 2 月 6 日に、ユーザー tonip が追加されました。
    
- 2013 年 2 月 19 日に、ユーザー pilarp が削除されました。
    

