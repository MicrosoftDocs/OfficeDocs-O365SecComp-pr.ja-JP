---
title: Office 365 の ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定します。
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection: M365-security-compliance
description: Office 365 の高度な脅威保護を使用して、組織のブロックされた Url の一覧を設定する方法について説明します。ブロックされた Url は、電子メール メッセージと、ATP の安全なリンク ポリシーに基づき、Office ドキュメントに適用されます。
ms.openlocfilehash: 261d85ce72de3a19ed4c2327d56fe1f32107781b
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995318"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>Office 365 の ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定します。

> [!IMPORTANT]
> この資料は、ビジネスのお客様向けです。ホーム ユーザーが Outlook での安全なリンクに関する情報を検索する場合は、 [Outlook.com の高度なセキュリティ](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)を参照してください。

[Office 365 の高度な脅威保護](office-365-atp.md)(ATP)、組織はブロックされている web サイト アドレス (Url) のユーザー設定リストを持つことができます。URL がブロックされると、ブロックされた URL へのリンクをクリックするユーザーが次の図のような[警告ページ](atp-safe-links-warning-pages.md)に実行されます。 
  
![このサイトがブロックされています。](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
組織の Office 365 のセキュリティ チームがブロックされている Url のリストが定義されているし、Office 365 の ATP の安全なリンク ポリシーの対象となる組織内の全員がそのリストが適用されます。 
  
[Office 365 の安全なリンクを ATP](atp-safe-links.md)の組織のカスタム ブロックされた Url の一覧を設定する方法の詳細については、この資料を参照してください。
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>表示またはブロックされた Url のカスタム リストを編集します。

[Office 365 の ATP の安全なリンク](atp-safe-links.md)では、組織のカスタム ブロックされた Url の一覧を含む、いくつかのリストを使用します。必要な権限があれば、組織のユーザー設定リストを設定できます。組織の安全なリンクの既定のポリシーを編集することによってこれを行います。

ATP のポリシーを編集 (または定義) を割り当てる必要があります、次の表に記載されている役割のいずれか。 

|役割  |場所と方法が割り当てられています。  |
|---------|---------|
|Office 365 のグローバル管理者 |Office 365 を購入するのに署名した人は、既定でグローバル管理者です。( [Office 365 の管理者の役割](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)の詳細についてを参照してください)。         |
|セキュリティ管理者 |Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange オンライン組織の管理 |Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  PowerShell コマンドレット (を参照してください[Exchange オンライン PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |

> [!TIP]
> ロールとアクセス許可の詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>表示またはブロックされた Url のユーザー設定リストを編集するには
  
1. [https://protection.office.com](https://protection.office.com)と、職場、学校のアカウントでサインインします。 
    
2. **脅威の管理**の下で、左側のナビゲーションで [**ポリシー** ] を選択します\>**安全なリンク**です。
    
3. **組織全体に適用されるポリシー** ] セクションで **[既定**] を選択しの**編集**([編集] ボタンのような鉛筆) します。<br/>![安全なリンクの保護のため、既定のポリシーを編集するのにはの編集] をクリックします。](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>これにより、ブロックされた Url の一覧を表示することができます。最初は、ここで記載されているすべての Url をいない可能性があります。<br/>![安全なリンクの既定のポリシーの Url] ボックスの一覧のブロック](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. **有効な URL を入力**] ボックスを選択、URL を入力し、プラス記号を選択し、(**+**)。 

5. 画面の右下隅で、Url の追加が完了したら、**保存**を選択します。
    
## <a name="a-few-things-to-keep-in-mind"></a>点に留意してください。

リストに Url を追加するときに、次の点に注意してください。 

- スラッシュが含まれていない ( **/**)、URL の末尾にします。入力するのではなく、たとえば、 `http://www.contoso.com/`、入力`http://www.contoso.com`。
    
- ドメイン専用の URL を指定することができます (のような`contoso.com`または`tailspintoys.com`)。クリック ノイズをブロックするこのドメインが含まれる任意の URL にします。

- サブドメインを指定することができます (のような`toys.contoso.com*`)、完全なドメインをブロックすることがなく (と同様に`contoso.com`)。このブロックは、サブドメインを含む任意の URL をクリックすると、クリック ノイズをブロックしない、完全なドメインを含む URL にします。  
    
- 最大 3 つのワイルドカードのアスタリスクを含めることができます (\*) あたりの URL です。入力することができ、どのような効果のこれらのエントリの例をいくつかが次の表の一覧です。
    
|**エントリの例**|**何します。**|
|:-----|:-----|
|`contoso.com`または`*contoso.com*`  <br/> |ドメイン、サブドメイン、およびパスを次のようにブロック`https://www.contoso.com`、`http://sub.contoso.com`と`http://contoso.com/abc`  <br/> |
|`http://contoso.com/a`  <br/> |サイトをブロックする`http://contoso.com/a`いない追加のサブパスのような`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |サイトをブロックする`http://contoso.com/a`などの他のサブパスを含めると`http://contoso.com/a/b`  <br/> |
|`http://toys.contoso.com*`  <br/> |サブドメイン (この場合の「おもちゃ」)、ブロックは他のドメインの Url をクリックを許可する (のような`http://contoso.com`または`http://home.contoso.com`)。  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>組織で特定のユーザーに対して例外を定義する方法

特定のグループが他のユーザーがブロックされている Url を表示できるようにする場合は、特定の受信者に適用される分析ツールの安全なリンクのポリシーを指定できます。[ATP の安全なリンクを使用してカスタム」を書き換えない"Url リストを設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を参照してください。
  

