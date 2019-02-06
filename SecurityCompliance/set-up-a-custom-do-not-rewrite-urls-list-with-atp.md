---
title: Office 365 の ATP の安全なリンクを使用してユーザー設定の再書き込みしない操作を行います Url のリストを設定します
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/05/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
description: ATP の安全なリンク ・ ポリシーを設定するときは、do not 書き換えを含めることができます ' 人、組織内のリストに含まれるサイトへのアクセスを有効にする Url の一覧です。
ms.openlocfilehash: f97abdb0f4e20ed968b4f71761a60cda79658d18
ms.sourcegitcommit: a64af0ebd0b03e4a5e60a33e9108c44c7d74f356
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2019
ms.locfileid: "29741070"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a>Office 365 の ATP の安全なリンクを使用してユーザー設定の再書き込みしない操作を行います Url のリストを設定します

[Office 365 の高度な脅威保護](office-365-atp.md)(ATP)、組織が[ブロックされているユーザー設定の Url](set-up-a-custom-blocked-urls-list-wtih-atp.md)では、web 上をクリックしたときのアドレス (Url) を電子メール メッセージまたは特定の Office ドキュメントで、これらの Url へのアクセスを禁止することです。組織は、組織の特定のグループ」を書き換えない」独自のリストもあります。」を書き換えない」の一覧は、人によってはそれ以外の場合、 [Office 365 の ATP の安全なリンク](atp-safe-links.md)によってブロックされている Url にアクセスを使用できます。 
  
この資料では、ATP の安全なリンクをスキャンして、いくつかの重要な点に注意してくださいから除外されている Url の一覧を指定する方法について説明します。

## <a name="set-up-a-do-not-rewrite-list"></a>「書き換えない」リストを設定します。

ATP の安全なリンクの保護は、組織のブロックされた Url] ボックスの一覧「を書き換えない」の例外の一覧など、いくつかのリストを使用します。必要な権限があれば、「を書き換えない」のユーザー設定リストを設定できます。追加または組織内の特定の受信者に適用される安全なリンク ポリシーを編集する場合に実行します。 

ATP のポリシーを編集 (または定義) を割り当てる必要があります、次の表に記載されている役割のいずれか。

|役割  |場所と方法が割り当てられています。  |
|---------|---------|
|Office 365 のグローバル管理者 |Office 365 を購入するのに署名した人は、既定でグローバル管理者です。( [Office 365 の管理者の役割](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)の詳細についてを参照してください)。         |
|Office 365 のセキュリティ管理者 |管理者センター ([https://aka.ms/admincenter](https://aka.ms/admincenter))|
|Exchange オンライン組織の管理 |Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>または <br>  PowerShell コマンドレット (を参照してください[Exchange オンライン PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
  
1. [https://protection.office.com](https://protection.office.com)と、職場、学校のアカウントでサインインします。 
    
2. **脅威の管理**の下、左側のナビゲーションで\>**ポリシー** \> **安全なリンク**です。
    
3. **特定の受信者に適用されるポリシー** ] セクションで [**新規**] をクリックして ([新規] ボタンのようなプラス記号 ( **+**)) 新しいポリシーを作成します。(または、することができます既存ポリシーを編集します。)<br/>![特定の電子メールの受信者の安全なリンク ポリシーを追加するのには新規を選択します。](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
4. ポリシーの説明と名前を指定します。
    
5. **次の Url の書き換えを行う**セクションでの**有効な URL を入力**] ボックスを選択し、URL を入力し、プラス記号 (+) を選択し。 
    
6. [**適用先**] セクションでは、**受信者のメンバーである**を選択し、ポリシーに追加するグループを選択し、します。**追加**を選択し、[ **ok]** をクリックします。
    
7. 画面の右下隅で、Url の追加が完了したら、**保存**を選択します。
    
> [!NOTE]
> ブロックされた Url の組織のユーザー設定] ボックスの一覧を確認してください。[ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定する](set-up-a-custom-blocked-urls-list-wtih-atp.md)を参照してください。 
  
## <a name="important-points-to-keep-in-mind"></a>重要な点に注意してください。

- 「書き換えない」リストで指定したすべての Url は、ATP 安全なリンクを指定する受信者スキャンから除外されます。
 
- ATP の安全なリンク ・ ポリシー」を書き換えない」の一覧を指定する場合は、最大 3 つのワイルドカードのアスタリスクを含めることができます (\*)。ワイルドカード (\*) と見なされますエントリを次のように`contoso.com`、明示的に変数名は、プレフィックスまたはサブドメインでは、このような`http://`または`https://`。つまり、エントリを次のように`contoso.com`のような`*contoso.com*`「を書き換えない」リストにします。

- 「を書き換えない」リストにある Url の一覧が場合に、その一覧を確認し、適切なワイルドカードを追加することを確認してください。などの場合は、既存のリストのエントリなどの`http://contoso.com/a`と同様のサブパスを含めると`http://contoso.com/a/b`で、ポリシーを追加ワイルドカード エントリに次のように`http://contoso.com/a*`。
    
- 「を書き換えない」リストで指定した Url ではスラッシュ (/) を含めないでください。たとえば、入力するのではなく`contoso.com/`「を書き換えない」リストで、次のように入力します。 `contoso.com`。
    
以下の表リストの例を入力することができ、どのような効果のこれらのエントリがあります。
    
|**エントリの例**|**何します。**|
|:-----|:-----|
|`*contoso.com*`  <br/> |特定の受信者を参照してください、ドメイン、サブドメインでは、パス、次のように`http://www.contoso.com`、 `https://www.contoso.com`、 `https://maps.contoso.com`、または`http://www.contoso.com/a`  <br/> |
|`http://contoso.com/a`  <br/> |ようなサイトにアクセスするのには特定の受信者では、 `http://contoso.com/a`、サブパスではないようですが、`http://contoso.com/a/b`  <br/> |
|`http://contoso.com/a*`  <br/> |ようなサイトにアクセスするのには特定の受信者では、`http://contoso.com/a`のサブパスを含めると`http://contoso.com/a/b`  <br/> |
   
 