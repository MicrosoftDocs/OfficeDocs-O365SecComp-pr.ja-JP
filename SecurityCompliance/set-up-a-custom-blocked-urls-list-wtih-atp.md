---
title: Office 365 の ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定します。
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: Office 365 の高度な脅威保護を使用して、組織のブロックされた Url の一覧を設定する方法の詳細については、この資料を参照してください。ブロックされた Url は、電子メール メッセージと、ATP の安全なリンク ポリシーに基づき、Office ドキュメントに適用されます。
ms.openlocfilehash: cd17fe61b7ecd5becd0918323952f304a73a4ce0
ms.sourcegitcommit: 2cf7f5bb282c971d33e00f65d9982a3f14aec74e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2018
ms.locfileid: "26706211"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>Office 365 の ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定します。

[Office 365 の高度な脅威保護](office-365-atp.md)(ATP)、組織はブロックされている web サイト アドレス (Url) のユーザー設定リストを持つことができます。URL がブロックされると、ブロックされた URL へのリンクをクリックするユーザーが次の図のような[警告ページ](atp-safe-links-warning-pages.md)に実行されます。 
  
![このサイトがブロックされています。](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
組織の Office 365 のセキュリティ チームがブロックされている Url のリストが定義されているし、Office 365 の ATP の安全なリンク ポリシーの対象となる組織内の全員がそのリストが適用されます。 
  
[Office 365 の安全なリンクを ATP](atp-safe-links.md)の組織のカスタム ブロックされた Url の一覧を設定する方法の詳細については、この資料を参照してください。
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>表示またはブロックされた Url のカスタム リストを編集します。

[Office 365 の ATP の安全なリンク](atp-safe-links.md)では、組織のカスタム ブロックされた Url の一覧を含む、いくつかのリストを使用します。必要な権限があれば、組織のユーザー設定リストを設定できます。組織の安全なリンクの既定のポリシーを編集することによってこれを行います。
  
1. [https://security.microsoft.com](https://security.microsoft.com)と、職場、学校のアカウントでサインインします。 
    
2. **脅威の管理**の下で、左側のナビゲーションで [**ポリシー** ] を選択します\>**安全なリンク**です。
    
3. **組織全体に適用されるポリシー** ] セクションで **[既定**] を選択しの**編集**([編集] ボタンのような鉛筆) します。<br/>![安全なリンクの保護のため、既定のポリシーを編集するのにはの編集] をクリックします。](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>これでは、ブロックされた Url の一覧を表示します。最初にあることに注意して、すべての Url を一覧表示する必要はありません。<br/>![Url のブロック リストは、組織全体に適用される安全なリンク ポリシー、既定では。](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. **有効な URL を入力**] ボックスを選択し、URL を入力し、プラス記号 (+) を選択し。留意する点を以下に示します。 
    
  - ドメイン専用の URL を指定することができます (のような`contoso.com`または`tailspintoys.com`)。クリック ノイズをブロックするこのドメインが含まれる任意の URL にします。
    
  - スラッシュが含まれていない ( **/**)、URL の末尾にします。入力するのではなく、たとえば、 `http://www.contoso.com/`、入力`http://www.contoso.com`。
    
  - 最大 3 つのワイルドカードのアスタリスクを含めることができます (\*) あたりの URL です。入力することができ、どのような効果のこれらのエントリの例をいくつかが次の表の一覧です。
    
|**エントリの例**|**何します。**|
|:-----|:-----|
|`contoso.com`または`*contoso.com*`  <br/> |ドメイン、サブドメイン、およびパスを次のようにブロック`https://www.contoso.com`、`http://sub.contoso.com`と`http://contoso.com/abc`  <br/> |
|`http://contoso.com/a`  <br/> |サイトをブロックする`http://contoso.com/a`いない追加のサブパスのような`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |サイトをブロックする`http://contoso.com/a`などの他のサブパスを含めると`http://contoso.com/a/b`  <br/> |
   
5. 画面の右下隅で、Url の追加が完了したら、**保存**を選択します。
    
## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>組織で特定のユーザーに対して例外を定義する方法

特定のグループが他のユーザーがブロックされている Url を表示できるようにする場合は、特定の受信者に適用される分析ツールの安全なリンクのポリシーを指定できます。[ATP の安全なリンクを使用してカスタム」を書き換えない"Url リストを設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を参照してください。
  

