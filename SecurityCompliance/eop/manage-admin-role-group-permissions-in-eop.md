---
title: EOP で管理役割グループのアクセス許可を管理する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: 管理者は、exchange Online Protection の Exchange 管理センター (EAC) でアクセス許可を割り当てる、または削除する方法を学習できます。
ms.openlocfilehash: 7bd1a6959dd03a118608dfe45faa253fd56539d4
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676727"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a>EOP で管理役割グループのアクセス許可を管理する
  
Microsoft Exchange Online Protection (EOP) では、Exchange 管理センター (EAC) を使用して、特定の管理タスクを実行するアクセス許可を割り当てるために、ユーザーを役割グループのメンバーにすることができます。また、EAC を使用して、ユーザーを役割グループから削除することもできます。
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- 予想所要時間 : 5 ～ 10 分

- Exchange 管理センターを開くには、「exchange [Online Protection の exchange 管理センター](../exchange-admin-center-in-exchange-online-protection-eop.md)」を参照してください。

- この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](feature-permissions-in-eop.md)」の「ユーザー、連絡先、および役割グループ」。

- このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。

> [!TIP]
> 問題がある場合は、 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)フォーラムでヘルプを要求します。
  
## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a>EAC を使用してメンバーを管理役割グループに割り当てる

1. EAC で、[**アクセス許可** \> **管理者の役割**] に移動し、ユーザーを追加する役割グループをクリックしてから、[ **** ![編集] 編集](../media/ITPro-EAC-EditIcon.gif)アイコンをクリックします。

2. [メンバー] で**** ![、[追加](../media/ITPro-EAC-AddIcon.gif)] アイコンをクリックします。 [メンバーの選択] ウィンドウが表示されます。

3. 追加するユーザーを検索するか、または一覧からユーザーを選択します。

4. 追加するユーザーを選択したら、 **[追加]**、 **[OK]** の順にクリックします。[メンバーの選択] ウィンドウが閉じます。

5. ユーザーが **[メンバー]** ウィンドウに追加された状態になります。 **[保存]** をクリックします。

   > [!NOTE]
   > 役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。 
  
## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a>EAC を使用して管理役割グループからメンバーを削除する

1. EAC で、[**アクセス許可** \> **管理者の役割**] に移動し、ユーザーを削除する役割グループをクリックしてから、[ **** ![編集アイコン](../media/ITPro-EAC-EditIcon.gif)の編集] をクリックします。

2. [メンバー] で削除するユーザーを選択し、[削除] [ **** ![削除] アイコン](../media/ITPro-EAC-RemoveIcon.gif)をクリックします。

3. **[保存]** をクリックして役割グループに対する変更内容を保存し、 **[管理役割]** ページに戻ります。ユーザーが管理者役割グループから正常に削除されているかは、選択した役割グループの詳細ウィンドウの [メンバー] に、該当するメンバーが表示されていないことで確認します。

   > [!NOTE]
   > 役割グループに対してメンバーを追加または削除した後、ユーザーは自身の管理者権限の変更を確認するためにサインアウトしてから、再度サインインしなければならない場合があります。
  
## <a name="for-more-information"></a>詳細情報

[EOP の機能アクセス許可](feature-permissions-in-eop.md)
