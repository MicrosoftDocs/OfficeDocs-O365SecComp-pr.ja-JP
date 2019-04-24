---
title: Office 365 の ATP の安全なリンクを使用して、リライトしないカスタムの url リストを設定する
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
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection:
- M365-security-compliance
description: ATP の安全なリンクポリシーを設定するときに、組織内の一部のユーザーがリストに含まれているサイトにアクセスできるようにするために、url の書き換え不可のリストを含めることができます。
ms.openlocfilehash: 006dab44054f9cb707bb13d158588ab6606fab5c
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264456"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>Office 365 の ATP の安全なリンクを使用して、リライトしないカスタムの url リストを設定する

> [!IMPORTANT]
> この記事は、企業のお客様を対象としています。自宅ユーザーで Outlook の安全なリンクに関する詳細情報をご覧になる場合は、「[Office 365 サブスクライバー用の Outlook.com の高度なセキュリティ](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

[office 365 Advanced Threat Protection](office-365-atp.md) (ATP) を使用すると、組織に[カスタムのブロック](set-up-a-custom-blocked-urls-list-wtih-atp.md)された url を設定できます。これにより、ユーザーが電子メールメッセージや特定の Office ドキュメント内の web アドレス (url) をクリックしたときに、それらの url にアクセスできなくなります。 組織では、組織内の特定のグループに対してカスタムの "書き換え不可" リストを作成することもできます。 [書き換えない] リストを使用すると、一部のユーザーは、 [Office 365 で ATP の安全なリンク](atp-safe-links.md)によってブロックされている url にアクセスすることができます。 
  
この記事では、ATP の安全なリンクスキャンから除外する url の一覧を指定する方法と、注意すべき重要な点について説明します。

## <a name="set-up-a-do-not-rewrite-list"></a>「書き換えない」リストを設定する

ATP の安全なリンク保護では、組織のブロックされた url のリストや例外の「書き換えない」リストを含むいくつかのリストを使用します。 必要なアクセス許可を持っている場合は、カスタムの "書き換えない" リストを設定できます。 この操作は、組織内の特定の受信者に適用する安全なリンクポリシーを追加または編集するときに行います。 

ATP ポリシーを編集 (または定義) するには、次の表に示す役割の 1 つが割り当てられている必要があります。

|役割  |参照先/割り当て方法  |
|---------|---------|
|Office 365 グローバル管理者 |Office 365 の購入へのサインアップをする場合、既定ではグローバル管理者になります。詳細については、「[Office 365 の管理者の役割について](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)」を参照してください。         |
|セキュリティ管理者 |Azure Active Directory 管理センター ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 組織の管理 |Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照してください) |

> [!TIP]
> 役割とアクセス許可の詳細については、「[Office 365 セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a>ユーザー設定の「リライトしない」 url リストを表示または編集するには
  
1. [https://protection.office.com](https://protection.office.com) に移動し、職場または学校のアカウントでサインインします。 
    
2. 左側のナビゲーションで、[**脅威管理** \> **ポリシー** \> **セーフリンク**] の下にあります。
    
3. [**特定の受信者に適用するポリシー** ] セクションで、[**新規**作成] (新しいボタンは**+** プラス記号 () に似ています) を選択して、新しいポリシーを作成します。 (または、既存のポリシーを編集することもできます)。<br/>![[新規] を選択して、特定の電子メール受信者の安全なリンクポリシーを追加します。](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. ポリシーの名前と説明を指定します。
    
5. [**次の url を書き換えない**] セクションで、[**有効な url を入力**してください] ボックスを選択し、url を入力して、プラス記号 (+) を選択します。 
    
6. [**適用先**] セクションで、[**受信者が次のメンバー**である] を選択し、ポリシーに含めるグループを選択します。 [**追加**] を選択し、[ **OK]** を選択します。
    
7. 画面の右下隅で URL の追加が完了したら、**[保存]** を選択します。
    
> [!NOTE]
> 組織の禁止された url のカスタムリストを必ず確認してください。 「 [ATP Safe Links を使用してカスタムのブロックされた url リストをセットアップする](set-up-a-custom-blocked-urls-list-wtih-atp.md)」を参照してください。 
  
## <a name="important-points-to-keep-in-mind"></a>留意すべき重要な点

- [書き換えない] ボックスの一覧で指定したすべての url は、指定した受信者の ATP の安全なリンクスキャンから除外されます。
 
- ATP の安全なリンクポリシーの "書き込み不可" リストを指定する場合は、最大3つのワイルドカードのアスタリスク\*() を含めることができます。 のよう\*に、ワイルドカード () は`contoso.com`、または`http://` `https://`のように、明示的にプレフィックスまたはサブドメインを含まないエントリに対して想定されます。 これは、「書き換えない」 `contoso.com`リスト`*contoso.com*`のようなエントリを意味します。

- 「書き換えない」リスト内に既に url のリストがある場合は、そのリストを確認し、必要に応じてワイルドカードを追加してください。 たとえば、既存のリストにそのよう`http://contoso.com/a`なエントリがあり、ポリシーにそのような`http://contoso.com/a/b`サブパスを含める場合は、エントリにワイルドカードを追加`http://contoso.com/a*`して、次のようにします。
    
- 「書き換えない」の一覧で指定した url にスラッシュ (/) を含めないでください。 たとえば、「リライトしない`contoso.com/` 」の一覧で入力するのではなく`contoso.com`、を入力します。
    
次の表に、入力できる内容と、それらのエントリの影響についての例を示します。
    
|**エントリの例**|**機能**|
|:-----|:-----|
|`*contoso.com*`  <br/> |特定の受信者が`http://www.contoso.com`、 `https://www.contoso.com` `https://maps.contoso.com`、、またはなどのドメイン、サブドメイン、およびパスにアクセスできるようにします。`http://www.contoso.com/a`  <br/> |
|`http://contoso.com/a`  <br/> |特定の受信者が、次`http://contoso.com/a`のようなサブパスではなく、サイトにアクセスできるようにします。`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |特定の受信者が、次`http://contoso.com/a`のようなサブパスでサイトにアクセスできるようにします。`http://contoso.com/a/b`  <br/> |
   
 