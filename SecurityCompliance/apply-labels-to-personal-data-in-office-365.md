---
title: Office 365 の個人データにラベルを適用する
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Office のラベルを GDPR 保護計画の一部として使用する方法について説明します。
ms.openlocfilehash: 518e5352861242bfbf9220f876edcb4b616493df
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598253"
---
# <a name="apply-labels-to-personal-data-in-office-365"></a>Office 365 の個人データにラベルを適用する

 GDPR 保護計画の一環として、分類ラベルを使用している場合は、このトピックを使用します。 

Office 365 で個人用データを保護するためにラベルを使用している場合は、[保持ラベル](labels.md)を使用することをお勧めします。 保持ラベルを使用すると、次のことができます。
- アドバンスト データ ガバナンスを使用して、機密情報の種類やその他の基準に基づいてラベルを自動的に適用できます。
- データ損失防止機能を備えた保持ラベルを使用して、保護を適用できます。 
- 電子情報開示とコンテンツの検索でラベルを使用できます。 

現在、Cloud App Security は保持ラベルをサポートしていません。ただし、Office 365 の機密情報を Cloud App Security と併用して、別の SaaS アプリにある個人データを監視することはできます。

[機密ラベル](sensitivity-labels.md)は現在、オンプレミスのファイル、その他のクラウド サービスのファイル、プロバイダーにラベルを適用する場合に推奨されています。 また、営業秘密ファイルなどのデータ保護用の Azure Information Protection 暗号化を必要とする Office 365 のファイルにも推奨されます。

現時点では、GDPR の対象となるデータを含む Office 365 のファイルに対して Azure Information Protection を使用して暗号化を適用することは、推奨されていません。 現在、Office 365 サービスでは AIP で暗号化されたファイルへの読み取りはできません。 そのため、サービスでこれらのファイル内の機密データを検索することはできません。

保持ラベルは Exchange Online のメールに適用できます。これらのラベルは Office 365 のデータ損失防止と連動することができます。 

![Office 365 のラベルと Azure Information Protection のラベル](Media/Apply-labels-to-personal-data-in-Office-365-image1.png)


この図について:

-   SharePoint Online および OneDrive for Business では、個人データや厳しく規制された営業秘密ファイルに保持ラベルを使用します。
-   Office 365 の機密情報の種類を Office 365 内と Cloud App Security で使用して、別の SaaS アプリにある個人データを監視できます。
-   厳しく規制された営業秘密ファイル、Exchange Online 電子メール、他の SaaS サービスのファイル、オンプレミスのデータセンターのファイル、他のクラウド プロバイダーのファイルには、機密ラベルを使用します。


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a>情報を保護するために Microsoft 365 全体で保持ラベルと機密情報の種類を使用する

次の図は、ラベル ポリシー、データ損失防止ポリシー、Cloud App Security ポリシーで保持ラベルと機密情報の種類を使用する方法を示しています。

![Office のラベルと機密情報の種類](Media/Apply-labels-to-personal-data-in-Office-365-image2.png)

次の表では、図での例と同じものを見やすいように記載しています。

<table>
<thead>
<tr class="header">
<th align="left"><strong>分類の要素</strong></th>
<th align="left"><strong>ラベル ポリシー — 2 つの例</strong></th>
<th align="left"><strong>データ損失防止ポリシー — 2 つの例</strong></th>
<th align="left"><strong>すべての SaaS アプリの Cloud App Security ポリシー — 1 つの例</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">保持ラベル。 例: 個人、公開、顧客のデータ、人事データ、社外秘、非常に機密性の高い社外秘</td>
<td align="left"><p>このラベルを自動で . . .</p>
<p>顧客データ</p>
<p>. . . これらの機密情報の種類に一致する文書に適用します . . .</p>
<p>&lt;機密情報の種類の例の一覧&gt;</p></td>
<td align="left"><p>この保護を . . .</p>
<p>&lt;保護の定義&gt;</p>
<p>. . . このラベルを持つドキュメントに適用します . . .</p>
<p>顧客データ</p></td>
<td align="left"><p>承認された SaaS アプリのこれらの属性を持つファイルが . . .</p>
<p>1 つまたは複数の属性を選択します: 定義済みの PII 属性、Office 365 の機密情報の種類、機密ラベル (AIP)、カスタム式</p>
<p>。 。 。 組織外で共有された際に警告します</p><p>注: 現在、保持ラベルは Cloud App Security ではサポートされていません。</td>
</tr>
<tr class="even">
<td align="left">機密情報の種類。例: ベルギーの国民番号、クレジット カード番号、クロアチアの身分証明書番号、フィンランドの国民 ID</td>
<td align="left"><p>これらのラベルを発行して、ユーザーが . . .</p>
<p>&lt;ラベルの選択&gt;</p>
<p>. . . これらの場所に手動で適用するようにします . . .</p>
<p>&lt;すべての場所、あるいは特定の場所を選択&gt;</p></td>
<td align="left"><p>この保護を . . .</p>
<p>&lt;保護の定義&gt;</p>
<p>. . . これらの機密情報の種類に一致する文書に適用します&gt;</p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a>自動適用ラベル ポリシーの優先順位付け

GDPR の対象となる個人データについては、環境に合わせて設定した機密情報の種類を使用してラベルを自動適用することをお勧めします。自動適用ラベル ポリシーは、意図した動作が確実に行われるように、適切に設計され、テストされていることが重要です。

自動適用ポリシーが作成される順序と、ユーザーもこれらのラベルを適用するかどうかによって結果が異なってきます。したがって、ポリシーの作成とラベルの適用を慎重に計画する必要があります。重要なポイントを次に示します。

### <a name="one-label-at-a-time"></a>一度に 1 つのラベルを適用する

ドキュメントに割り当てることができるラベルの数は 1 つのみです。

### <a name="older-auto-apply-policies-win"></a>優先されるのは古いポリシー

自動適用ラベルを割り当てるルールが複数あり、コンテンツが複数のルールの条件を満たす場合は、最も古いルールのラベルが割り当てられます。このため、ラベル ポリシーを構成する前に注意深く計画することが重要です。組織がラベル ポリシーの優先順位を変更する必要がある場合は、ラベル ポリシーを削除して再度作成する必要があります。

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a>自動適用ラベルよりもユーザーが手動で適用したラベルが優先される

ユーザーが手動で適用したラベルは、自動適用ラベルよりも優先されます。自動適用ポリシーでは、ユーザーがすでに適用しているラベルを置き換えることはできませんが、ユーザーは、自動適用されたラベルを置き換えることができます。

### <a name="auto-assigned-labels-can-be-updated"></a>自動的に割り当てられたラベルは更新可能

自動的に割り当てられたラベルは、新しいラベル ポリシーにより、または既存のポリシーを更新することによって最新の状態にすることができます。

ラベルを実装する際に重要な点:

-   自動適用ポリシーが作成される順序の優先順位付けを行います。

-   ユーザーが手動でラベルを適用する前に、ラベルが自動適用されるまで十分な時間の余裕があります。条件に一致するすべてのコンテンツにラベルが適用されるまでに最大 7 日間かかることがあります。

### <a name="example-priority-for-creating-the-auto-apply-policies"></a>自動適用ポリシー作成の優先順位の例

<table>
<thead>
<tr class="header">
<th align="left"><strong>ラベル</strong></th>
<th align="left"><strong>自動適用ポリシーの作成順序の優先順位</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">人事 — 従業員データ</td>
<td align="left">1</td>
</tr>
<tr class="even">
<td align="left">顧客データ</td>
<td align="left">2</td>
</tr>
<tr class="odd">
<td align="left">非常に機密性の高い社外秘</td>
<td align="left">3</td>
</tr>
<tr class="even">
<td align="left">人事 — 給与データ</td>
<td align="left">4</td>
</tr>
<tr class="odd">
<td align="left">社外秘</td>
<td align="left">5</td>
</tr>
<tr class="even">
<td align="left">公開</td>
<td align="left">6</td>
</tr>
<tr class="odd">
<td align="left">個人</td>
<td align="left">自動適用ポリシーなし</td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a>ラベルおよび自動適用ラベル ポリシーの作成

セキュリティ センターまたはコンプライアンス センターで、ラベルおよびポリシーを作成します。

<table>
<thead>
<tr class="header">
<th align="left"><strong>手順</strong></th>
<th align="left"><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>コンプライアンス チームのメンバーにアクセス許可を与えます。</p></td>
<td align="left"><p>ラベルを作成するコンプライアンス チームのメンバーには、セキュリティ センターやコンプライアンス センターを使用するためのアクセス許可が必要です。セキュリティ センターまたはコンプライアンス センターの [アクセス許可] に移動し、コンプライアンス管理者グループのメンバーを変更します。</p>
<p>「<a href="https://support.office.com/en-ie/article/Give-users-access-to-the-Office-365-Security-Compliance-Center-2cfce2c8-20c5-47f9-afc4-24b059c1bd76">ユーザーにセキュリティ センターやコンプライアンス センターへのアクセス権を付与する</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>保持ラベルを作成します。</p></td>
<td align="left">セキュリティ センターまたはコンプライアンス センターの [分類] に移動し、[保持ラベル] を選択して、使用している環境のラベルを作成します。</td>
</tr>
<tr class="odd">
<td align="left"><p>ラベルの自動適用ポリシーを作成します。</p></td>
<td align="left">セキュリティ センターまたはコンプライアンスセンターの [分類] に移動し、[ラベル ポリシー] を選択し、自動適用ラベルのポリシーを作成します。これらのポリシーは、優先順位に従って作成してください。</td>
</tr>
</tbody>
</table>

次の図は、顧客データ ラベル用の自動適用ラベルを作成する方法を示しています。

![顧客データのラベルの作成と適用](Media/Apply-labels-to-personal-data-in-Office-365-image3.png)

この図について:

-   “顧客データ” ラベルが作成されます。

-   GDPR の必要な機密情報の種類 (ベルギーの国民番号、クレジット カード番号、クロアチアの身分証明書番号、フィンランドの国民 ID) が記載されています。

-   自動適用ポリシーを作成すると、ポリシーに追加する機密情報の種類のいずれかを含むファイルに、“顧客データ” ラベルが割り当てられます。
