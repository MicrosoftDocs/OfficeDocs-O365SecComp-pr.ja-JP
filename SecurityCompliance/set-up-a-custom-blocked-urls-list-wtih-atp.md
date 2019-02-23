---
title: Office 365 ATP Safe Links を使用して、カスタムのブロックされた url リストを設定する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection を使用して、組織でブロックされている url の一覧を設定する方法について説明します。受信拒否された url は、ATP の安全なリンクポリシーに従って、電子メールメッセージおよび Office ドキュメントに適用されます。
ms.openlocfilehash: ad9c613221b94e61022b11541ee068e35e47cc70
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213027"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a>Office 365 ATP Safe Links を使用して、カスタムのブロックされた url リストを設定する

> [!IMPORTANT]
> この記事は、ビジネスのお客様を対象としています。Outlook の安全なリンクに関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) を使用すると、ブロックされる web サイトアドレス (url) のカスタムリストを組織に割り当てることができます。url がブロックされると、ブロックされた url へのリンクをクリックしたユーザーは、次のような[警告ページ](atp-safe-links-warning-pages.md)にジャンプします。 
  
![このサイトはブロックされています](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
禁止された url の一覧は、組織の office 365 セキュリティチームによって定義されており、そのリストは、office 365 ATP Safe Links ポリシーでカバーされている組織内のすべてのユーザーに適用されます。 
  
この記事では、 [Office 365 で ATP の安全なリンク](atp-safe-links.md)のために組織のカスタムのブロックされた url リストを設定する方法について説明します。
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a>禁止された url のカスタムリストを表示または編集する

[Office 365 の ATP の安全なリンク](atp-safe-links.md)では、組織のカスタムブロックされた url リストを含むいくつかのリストが使用されます。必要なアクセス許可がある場合は、組織のカスタムリストを設定できます。これを行うには、組織の既定の安全なリンクポリシーを編集します。

ATP ポリシーを編集 (または定義) するには、次の表に示すいずれかの役割を割り当てられている必要があります。 

|役割  |場所/割り当て方法  |
|---------|---------|
|Office 365 グローバル管理者 |Office 365 の購入にサインアップするユーザーは、既定ではグローバル管理者です。(詳細については、「 [Office 365 管理者の役割につい](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)て」を参照してください)。         |
|セキュリティ管理者 |Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織の管理 |Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  powershell コマンドレット (「 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照) |

> [!TIP]
> 役割とアクセス許可の詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a>ブロックするカスタム url リストを表示または編集するには
  
1. に[https://protection.office.com](https://protection.office.com)移動して、職場または学校のアカウントでサインインします。 
    
2. 左側のナビゲーションで、[**脅威の管理**] の下にある [**ポリシー** \> **セーフリンク**] を選択します。
    
3. [**組織全体に適用されるポリシー** ] セクションで、[**既定**] を選択し、[**編集**] を選択します (このボタンは鉛筆に似ています)。<br/>![[編集] をクリックして、安全なリンクの保護のための既定のポリシーを編集します。](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)<br/>これにより、ブロックされた url の一覧を表示できます。最初に、url がここに表示されていない場合があります。<br/>![既定の安全なリンクポリシーのブロックされた url の一覧](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. [**有効な url を入力**してください] ボックスを選択し、url を入力し**+** て、プラス記号 () を選択します。 

5. url の追加が終了したら、画面の右下隅にある [**保存**] を選択します。
    
## <a name="a-few-things-to-keep-in-mind"></a>留意すべきこと

リストに url を追加する際には、次の点に注意してください。 

- URL の末尾にスラッシュ ( **/**) を含めないでください。たとえば、 `http://www.contoso.com/`と入力する代わりに、 `http://www.contoso.com`を入力します。
    
- ドメインのみの URL (または`contoso.com` `tailspintoys.com`など) を指定できます。これにより、そのドメインを含む任意の URL のクリックがブロックされます。

- 完全なドメインをブロックせず`toys.contoso.com*`にサブドメイン (like) を指定`contoso.com`することができます (like)。これにより、サブドメインを含む url がクリックによってブロックされますが、完全なドメインを含む url へのクリックはブロックされません。  
    
- URL ごとに最大3つのワイルドカード\*のアスタリスク () を含めることができます。次の表に、入力できる内容とそのエントリの影響について、いくつかの例を示します。
    
|**エントリの例**|**機能**|
|:-----|:-----|
|`contoso.com`や`*contoso.com*`  <br/> |ドメイン、サブドメイン、およびパス (、、など`https://www.contoso.com`) `http://sub.contoso.com`をブロックします。`http://contoso.com/abc`  <br/> |
|`http://contoso.com/a`  <br/> |サイト`http://contoso.com/a`をブロックしますが、次のような追加のサブパスはありません。`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |サイト`http://contoso.com/a`とその他のサブパスをブロックします。`http://contoso.com/a/b`  <br/> |
|`http://toys.contoso.com*`  <br/> |サブドメイン (この場合は "玩具") をブロックしますが、他のドメインの`http://contoso.com` url `http://home.contoso.com`(またはなど) へのクリックを許可します。  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a>組織内の特定のユーザーに対して例外を定義する方法

特定のグループが他のユーザーに対してブロックされている可能性がある url を表示できるようにする場合は、特定の受信者に適用される ATP の安全なリンクポリシーを指定できます。「 [ATP Safe Links を使用して、ユーザー設定の "書き込み不可" url リストを設定する](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)」を参照してください。
  

