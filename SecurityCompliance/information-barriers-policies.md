---
title: 情報バリアポリシーの定義
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Microsoft Teams の情報障壁に関するポリシーを定義する方法について説明します。
ms.openlocfilehash: 4f63d79f59741f74d2ac8167a8cd86717c6f9ec4
ms.sourcegitcommit: c603a07d24c4c764bdcf13f9354b3b4b7a76f656
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2019
ms.locfileid: "35131381"
---
# <a name="define-policies-for-information-barriers-preview"></a>情報バリアのポリシーを定義する (プレビュー)

## <a name="overview"></a>概要

情報の障壁を使用すると、特定のユーザーセグメントが相互に通信するのを防ぐように設計されたポリシーを定義したり、特定のセグメントのみが特定のセグメントと通信できるようにすることができます。 情報バリアポリシーは、組織が関連する業界標準および規制に準拠し、潜在的な競合を回避するのに役立ちます。 詳細については、「[情報の障壁 (プレビュー)](information-barriers.md)」を参照してください。 

この記事では、情報バリアポリシーを計画、定義、実装、および管理する方法について説明します。 いくつかの手順が関係しており、作業フローはいくつかの部分に分かれています。 情報バリアポリシーの定義 (または編集) を開始する前に、必ず[前提条件](#prerequisites)とプロセス全体に目を通してください。

> [!TIP]
> この記事には、情報バリアポリシーを計画して定義するのに役立つ、[シナリオの例](#example-contosos-departments-segments-and-policies)とダウンロード可能な[Excel ブック](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)が含まれています。

## <a name="concepts-of-information-barrier-policies"></a>情報バリアポリシーの概念

情報バリアポリシーの基礎概念を理解しておくと役に立ちます。

- **ユーザーアカウントの属性**は、Azure Active Directory (または Exchange Online) で定義されます。 これらの属性には、部署、役職、場所、チーム名、その他のジョブプロファイルの詳細を含めることができます。 

- **セグメント**とは、Office 365 セキュリティ & コンプライアンスセンターで、選択した**ユーザーアカウント属性**を使用して定義された一連のユーザーのことです。 ([サポートされている属性の一覧](information-barriers-attributes.md)を参照してください)。 

- **情報バリアポリシー**では、通信制限または制限を決定します。 情報バリアポリシーを定義するときは、次の2種類のポリシーから選択します。
    - "Block" ポリシーは、あるセグメントが別のセグメントと通信できないようにします。
    - [許可] ポリシーでは、1つのセグメントが特定の他のセグメントのみと通信できるようにします。

- **ポリシーアプリケーション**は、すべての情報バリアポリシーが定義された後に実行され、組織に適用する準備が整っています。

## <a name="the-work-flow-at-a-glance"></a>作業フローの概要

|フェーズ    |関係するもの  |
|---------|---------|
|[前提条件が満たされていることを確認する](#prerequisites)     |-[必要なライセンスとアクセス許可](information-barriers.md#required-licenses-and-permissions)を持っていることを確認する<br/>-ディレクトリにユーザーをセグメント化するためのデータが含まれていることを確認する<br/>-Microsoft Teams のスコープ付きディレクトリ検索を有効にする<br/>-監査ログが有効になっていることを確認します。<br/>-PowerShell の使用 (例は提供されています)<br/>-Microsoft Teams に対する管理者の同意を提供する (手順は含まれています)          |
|[パート 1: 組織内のユーザーのセグメント化](#part-1-segment-users)     |-必要なポリシーを決定する<br/>-定義するセグメントの一覧を作成する<br/>-使用する属性を識別する<br/>-ポリシーフィルターの観点からセグメントを定義する        |
|[パート 2: 情報バリアポリシーを定義する](#part-2-define-information-barrier-policies)     |-ポリシーを定義します (まだ適用しない)<br/>-2 つの種類 (ブロックまたは許可) から選択します。 |
|[パート 3: 情報バリアポリシーを適用する](#part-3-apply-information-barrier-policies)     |-ポリシーをアクティブな状態に設定します。<br/>-ポリシーアプリケーションを実行する<br/>-ポリシーの状態を表示する         |
|(必要な場合)[セグメントまたはポリシーを編集する](#edit-a-segment-or-a-policy)     |-セグメントを編集する<br/>-ポリシーを編集または削除する<br/>-ポリシーアプリケーションを実行する<br/>-ポリシーの状態を表示する         |
|(必要な場合)[トラブルシューティング](information-barriers-troubleshooting.md)|-期待どおりに動作しない場合に処理を実行する|

## <a name="prerequisites"></a>前提条件

[必要なライセンスとアクセス許可](information-barriers.md#required-licenses-and-permissions)に加えて、次の要件が満たされていることを確認してください。 
     
- **ディレクトリデータ**。 組織の構造がディレクトリデータに反映されていることを確認します。 これを行うには、Azure Active Directory (または Exchange Online) に、グループメンバーシップ、部署名などのユーザーアカウント属性が正しく設定されていることを確認してください。 詳細については、以下のリソースを参照してください。
  - [情報バリアポリシーの属性 (プレビュー)](information-barriers-attributes.md)
  - [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Office 365 PowerShell でユーザー アカウント プロパティを構成する](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

- **スコープ付きディレクトリ検索**。 組織の最初の情報バリアポリシーを定義する前に、 [Microsoft Teams でスコープ付きディレクトリ検索を有効](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)にする必要があります。 情報バリアポリシーを設定または定義する前に、スコープ付きディレクトリ検索を有効にした後、少なくとも24時間待機します。

- **監査ログ**。 ポリシーアプリケーションの状態を参照するには、監査ログを有効にする必要があります。 セグメントまたはポリシーの定義を開始する前に、この手順を実行することをお勧めします。 詳細については、「 [Office 365 監査ログ検索をオンまたはオフに](turn-audit-log-search-on-or-off.md)する」を参照してください。

- **PowerShell**。 現時点で、情報バリアポリシーは、PowerShell コマンドレットを使用して Office 365 セキュリティ & コンプライアンスセンターで定義および管理されます。 この記事ではいくつかの例が示されていますが、PowerShell のコマンドレットとパラメーターについて理解しておく必要があります。 [Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)します。

- **Microsoft Teams の情報障壁に対する管理者の同意**。 ポリシーが適切に設定されている場合、情報バリアはチャットセッションからユーザーを削除することはできません。 これにより、組織はポリシーと規制に準拠したままになります。 次の手順を使用して、Microsoft Teams で情報バリアポリシーが期待どおりに動作するようにします。 

   1. 次の PowerShell コマンドレットを実行します。

      ```
      Login-AzureRmAccount 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureRmADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzureRmADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. メッセージが表示されたら、Office 365 の職場または学校アカウントを使用してサインインします。

   3. [**要求されたアクセス許可**] ダイアログボックスで情報を確認し、[**同意**する] を選択します。

すべての前提条件が満たされたら、次のセクションに進みます。

> [!TIP]
> プランの準備に役立てるため、この記事にはシナリオの例が含まれています。 [「Contoso 社の部門、セグメント、ポリシー」を参照してください](#example-contosos-departments-segments-and-policies)。<p>また、セグメントとポリシーを計画して定義したり、PowerShell コマンドレットを作成したりするのに役立つダウンロード可能な Excel ブックが用意されています。 [ブックを取得](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)します。 

## <a name="part-1-segment-users"></a>パート 1: セグメントユーザー

このフェーズでは、必要な情報バリアポリシーを決定し、定義するセグメントの一覧を作成して、セグメントを定義します。

### <a name="determine-what-policies-are-needed"></a>必要なポリシーを決定する

法的および業界の規制を考慮しています。組織内で情報の障壁ポリシーを必要とするグループは誰ですか。 リストを作成します。 他のグループとの通信を禁止する必要があるグループはありますか。 1つまたは2つの他のグループとのみ通信できるようにする必要があるグループはありますか。 次の2つのグループのいずれかに属している必要があるポリシーについて考えます。
- "Block" ポリシーは、あるグループが別のグループと通信できないようにします。
- [許可] ポリシーにより、グループは特定の他の特定のグループのみと通信できるようになります。

最初にグループとポリシーの一覧を作成したら、次の手順を実行して、必要なセグメントを特定します。 

### <a name="identify-segments"></a>セグメントを識別する

ポリシーの初期リストに加えて、組織のセグメントの一覧を作成します。 情報バリアポリシーに含まれるユーザーは、セグメントに属する必要があり、ユーザーは2つ以上のセグメントに属することはできません。 各セグメントには、1つの情報バリアポリシーのみを適用できます。 

セグメントを定義するために使用する組織のディレクトリデータの属性を決定します。 *Department*、 *MemberOf*、またはサポートされている属性のいずれかを使用できます。 ユーザー用に選択した属性の値があることを確認してください。 [情報バリア (プレビュー) でサポートされている属性の一覧を参照してください](information-barriers-attributes.md)。

> [!IMPORTANT]
> **次のセクションに進む前に、セグメントを定義するために使用できる属性の値がディレクトリデータにあることを確認して**ください。 ディレクトリデータに使用する属性の値が含まれていない場合は、情報の障壁を処理する前に、その情報を含めるようにユーザーアカウントを更新する必要があります。 これに関するヘルプを表示するには、次のリソースを参照してください。<br/>- [Office 365 PowerShell を使用してユーザーアカウントのプロパティを構成する](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)<br/>- [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>PowerShell を使用してセグメントを定義する

セグメントを定義しても、ユーザーに影響はありません。情報バリアポリシーが定義され、適用される段階を設定するだけです。

組織セグメントを定義するには、使用する[属性](information-barriers-attributes.md)に対応する**usergroupfilter**パラメーターを指定して、**新しい-組織**セグメントコマンドレットを使用します。

文`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`

例: `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`

この例では、hr と** いう名前のセグメント** が、 *Department*属性の値を使用して定義されています。 コマンドレットの "-eq" 部分は、"equals" を参照しています。

定義するセグメントごとに、このプロセスを繰り返します。

各コマンドレットを実行すると、新しいセグメントに関する詳細情報の一覧が表示されます。 詳細には、セグメントの種類、作成者または最終更新日時などが含まれます。 

> [!IMPORTANT]
> **セグメントが重ならないようにして**ください。 情報バリアによって影響を受ける各ユーザーは、1つ (1 つの) セグメントに属している必要があります。 ユーザーは、2つ以上のセグメントに属することはできません。 (この記事の「 [Example: Contoso の定義済みセグメント](#contosos-defined-segments)」を参照してください)。

セグメントを定義した後、「情報バリアポリシーを定義する」に進みます。

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>セグメント定義での "等しい" と "not equals" の使用

上記の最初の例では、"Department が HR に等しい" というセグメントを定義しています。 そのセグメントには "equals" パラメーターが含まれています。 また、次の例に示すように、セグメントを定義するには、"not equals" パラメーターを使用します。

文`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -ne 'attributevalue'"`

例: `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"`

この例では、Sales ではないすべてのユーザーを含む NotSales というセグメントを定義しました。 コマンドレットの "-ne" 部分は "not equals" を参照しています。

また、"equals" パラメーターと "not equals" パラメーターの両方を使用してセグメントを定義することもできます。

例: `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" and "Position -ne 'Temporary'"`

この例では、ローカルに配置されていて、その位置が*一時的*としてリストされていないユーザーを含む、 *localfte*というセグメントを定義しました。

## <a name="part-2-define-information-barrier-policies"></a>パート 2: 情報バリアポリシーを定義する

特定のセグメント間の通信を禁止する必要があるか、または特定のセグメントへの通信を制限する必要があるかを決定します。 組織が法律上および業界の要件を満たしていることを確認するために、最小限のポリシーを使用することが理想的です。

定義するユーザーセグメントと情報バリアポリシーの一覧を使用して、シナリオを選択し、手順を実行します。 

- [シナリオ 1: セグメント間の通信をブロックする](#scenario-1-block-communications-between-segments)
- [シナリオ 2: セグメントが他の1つのセグメントとのみ通信できるようにする](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **ポリシーを定義するときは、1つのセグメントに複数のポリシーを割り当てない**ようにしてください。 たとえば、 *sales*というセグメントに対して1つのポリシーを定義する場合は、 *sales*に対して追加のポリシーを定義しないでください。<p>また、情報バリアポリシーを定義するときには、これらのポリシーを適用する準備ができるまで、非アクティブ状態に設定してください。 ポリシーを定義 (または編集) すると、それらのポリシーがアクティブな状態に設定された後、ユーザーに影響を与えることはありません。

(この記事の「 [Example: Contoso の情報バリアポリシー](#contosos-information-barrier-policies) 」を参照してください)。

### <a name="scenario-1-block-communications-between-segments"></a>シナリオ 1: セグメント間の通信をブロックする

セグメントが相互に通信するのをブロックする場合は、2つのポリシーを定義します。 各ポリシーは、一一の通信のみをブロックします。

たとえば、セグメント A とセグメント B 間の通信をブロックするとします。この場合は、セグメント A からセグメント B と通信することを妨げる1つのポリシーを定義してから、セグメント B とセグメント A との通信を禁止する2番目のポリシーを定義します。

1. 最初のブロックポリシーを定義するには、 **InformationBarrierPolicy**コマンドレットを**SegmentsBlocked**パラメーターと共に使用します。 

    文`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"`

    例: `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`

    この例では、 *sales*というセグメントの*sales Research*というポリシーを定義しました。 このポリシーを有効にして適用すると、 *Sales*のユーザーは*Research*というセグメントにあるユーザーと通信できなくなります。

2. 2番目のブロックセグメントを定義するには、 **InformationBarrierPolicy**コマンドレットを**SegmentsBlocked**パラメーターと共に再度使用します。この場合は、セグメントを反転された状態にします。

    例: `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`

    この例では、リサーチという名前のポリシーを定義して、*研究**部門*との通信によるコミュニケーションを防止しています。 **
 
2. 次のいずれかの手順を実行します。

   - (必要な場合)[セグメントが1つの他のセグメントとのみ通信できるようにするポリシーを定義する](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (すべてのポリシーが定義された後)[情報バリアポリシーの適用](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>シナリオ 2: セグメントが他の1つのセグメントとのみ通信できるようにする

1. 1つのセグメントが他の1つのセグメントとのみ通信できるようにするには、 **InformationBarrierPolicy**コマンドレットを**SegmentsAllowed**パラメーターと共に使用します。 

    文`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name"`

    例: `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`

    この例では、*製造*と呼ばれるセグメントに対して、*工場*という名前のポリシーを定義しています。 このポリシーを有効にして適用すると、*製造*者は*HR*というセグメントにあるユーザーとのみ通信できるようになります。 (この場合、*製造*は*人事*の一部ではないユーザーと通信できません)。

    **必要に応じて、次の例に示すように、このコマンドレットで複数のセグメントを指定できます。**

    文`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name"`

    **例 2: セグメントが他の2つのセグメントとのみ通信できるようにするポリシーを定義する**    

    `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing" -State Inactive`

    この例では、*リサーチ*セグメントが*HR*と*製造*のみと通信できるようにするポリシーを定義しました。

    特定のセグメントのみが特定の特定のセグメントと通信できるようにするために定義するポリシーごとに、この手順を繰り返します。

2. 次のいずれかの手順を実行します。

   - (必要な場合)[セグメント間の通信をブロックするポリシーを定義する](#scenario-1-block-communications-between-segments) 
   - (すべてのポリシーが定義された後)[情報バリアポリシーの適用](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>パート 3: 情報バリアポリシーを適用する

情報バリアポリシーは、アクティブな状態に設定してからポリシーを適用するまで有効になりません。

1. **InformationBarrierPolicy**コマンドレットを使用して、定義されているポリシーの一覧を表示します。 各ポリシーの状態と id (GUID) をメモします。

    文`Get-InformationBarrierPolicy`

2. ポリシーをアクティブな状態に設定するには、 **Identity**パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用し、 **State**パラメーターを**active**に設定します。 

    文`Set-InformationBarrierPolicy -Identity GUID -State Active`

    例: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`
    
    この例では、GUID が*43c37853-ea10-4b90-a23d-ab8c93772471*の情報バリアポリシーをアクティブな状態に設定しています。

    各ポリシーに該当する場合は、この手順を繰り返します。

3. 情報バリアポリシーのアクティブ状態の設定が終了したら、Office 365 セキュリティ & コンプライアンスセンターで**InformationBarrierPoliciesApplication**コマンドレットを使用します。

    文`Start-InformationBarrierPoliciesApplication`

    約30時間後に、組織のポリシーがユーザーごとに適用されます。 組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。 (一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>ユーザーアカウント、セグメント、ポリシー、またはポリシーアプリケーションの状態を表示する

PowerShell を使用すると、次の表に示すように、ユーザーアカウント、セグメント、ポリシー、およびポリシーアプリケーションの状態を表示できます。

|これを表示するには  |説明  |
|---------|---------|
|ユーザー アカウント     |Identity パラメーターを使用して**InformationBarrierRecipientStatus**コマンドレットを使用します。 <p>文`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 <p>例: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>この例では、Office 365 の2つのユーザーアカウント ( *Megan*の場合は*Meガント b* 、 *Alex*の場合は*alexw* ) を参照しています。 <p>(1 人のユーザーに対してこのコマンドレットを`Get-InformationBarrierRecipientStatus -Identity <value>`使用することもできます。) <p>このコマンドレットは、属性値、適用されている情報バリアポリシーなど、ユーザーに関する情報を返します。|
|多角形     |コマンドレット**** を使用します。<p>文`Get-OrganizationSegment` <p>これにより、組織に定義されているすべてのセグメントの一覧が表示されます。         |
|情報バリアポリシー     |**InformationBarrierPolicy**コマンドレットを使用します。 <p> 文`Get-InformationBarrierPolicy` <p>これにより、定義された情報バリアポリシーの一覧とその状態が表示されます。       |
|最新情報バリアポリシーアプリケーション     | **InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。 <p>文`Get-InformationBarrierPoliciesApplicationStatus`<p>    これにより、ポリシーの適用が完了したか、失敗したか、または進行中であるかに関する情報が表示されます。       |
|すべての情報バリアポリシーアプリケーション|使え`Get-InformationBarrierPoliciesApplicationStatus -All $true`<p>これにより、ポリシーの適用が完了したか、失敗したか、または進行中であるかに関する情報が表示されます。|

## <a name="stop-a-policy-application"></a>ポリシーアプリケーションを停止する

情報バリアポリシーの適用を開始した後で、これらのポリシーの適用を停止するには、次の手順を使用します。 プロセスが開始されるまで約30-35 分かかることに注意してください。

1. 最新の情報バリアポリシーアプリケーションの状態を表示するには、 **InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。

    文`Get-InformationBarrierPoliciesApplicationStatus`

    アプリケーションの GUID をメモします。

2. Identity パラメーターを指定して**InformationBarrierPoliciesApplication**コマンドレットを使用します。

    文`Stop-InformationBarrierPoliciesApplication -Identity GUID`

    例: `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`

    この例では、情報バリアポリシーの適用を停止しています。

## <a name="edit-a-segment-or-a-policy"></a>セグメントまたはポリシーを編集する

### <a name="edit-a-segment"></a>セグメントを編集する

1. 既存のすべてのセグメントを表示するには、コマンドレットの**取得**を使用します。
    
    文`Get-OrganizationSegment`

    セグメントの種類、UserGroupFilter 値、作成者または最終更新日時、GUID など、セグメントと詳細の一覧が表示されます。

    > [!TIP]
    > 後で参照するために、セグメントのリストを印刷または保存します。 たとえば、セグメントを編集する場合は、その名前を知っているか、値を識別する必要があります (これは Identity パラメーターと共に使用されます)。

2. セグメントを編集するには、 **Identity**パラメーターと関連する詳細情報を使用して、**グループ**化コマンドレットを使用します。 

    文`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`

    例: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`

    この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*を持つセグメントに対して、部署名を "hrdept" に更新しました。

組織のセグメントの編集が終了したら、「情報バリアポリシーの[定義](#part-2-define-information-barrier-policies)または[編集](#edit-a-policy)」に進むことができます。

### <a name="edit-a-policy"></a>ポリシーを編集する

1. 現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。

    文`Get-InformationBarrierPolicy`

    結果の一覧で、変更するポリシーを特定します。 ポリシーの GUID と名前をメモします。

2. **InformationBarrierPolicy**コマンドレットを**Identity**パラメーターと共に使用して、必要な変更を指定します。

    例: ポリシーが定義されていて、*リサーチ*セグメントが*販売*および*マーケティング*セグメントとの通信をブロックするとします。 このポリシーは、このコマンドレットを使用して定義されています。`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`
    
    *研究*セグメント内のユーザーが*HR*セグメント内のユーザーとのみ通信できるように変更するとします。 この変更を行うには、次のコマンドレットを使用します。`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    この例では、"SegmentsBlocked" を "SegmentsAllowed" に変更し、 *HR*セグメントを指定しました。

3. ポリシーの編集が終了したら、変更内容を適用してください。 ([情報バリアポリシーの適用](#part-3-apply-information-barrier-policies)を参照してください)。

### <a name="remove-a-policy"></a>ポリシーを削除する

1. 現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。

    文`Get-InformationBarrierPolicy`

    結果の一覧で、削除するポリシーを特定します。 ポリシーの GUID と名前をメモします。 ポリシーが非アクティブの状態に設定されていることを確認します。

2. Identity パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用します。

    文`Remove-InformationBarrierPolicy -Identity GUID`

    例: GUID が*43c37853-ea10-4b90-a23d-ab8c93772471*のポリシーを削除するとします。 これを行うには、次のコマンドレットを使用します。
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    メッセージが表示されたら、変更を確認します。

3. 削除するポリシーごとに、手順1-2 を繰り返します。

4. ポリシーの削除が終了したら、変更内容を適用します。 これを行うには、 **InformationBarrierPoliciesApplication**コマンドレットを使用します。

    文`Start-InformationBarrierPoliciesApplication`

    組織の変更がユーザーごとに適用されます。 組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。

### <a name="set-a-policy-to-inactive-status"></a>ポリシーを非アクティブな状態に設定する

1. 現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。

    文`Get-InformationBarrierPolicy`

    結果の一覧で、変更する (または削除する) ポリシーを特定します。 ポリシーの GUID と名前をメモします。

2. ポリシーの状態を非アクティブに設定するには、Identity パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用し、State パラメーターを inactive に設定します。

    文`Set-InformationBarrierPolicy -Identity GUID -State Inactive`

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    この例では、GUID *43c37853-ea10-4b90-a23d-ab8c9377247*を非アクティブな状態に設定する情報バリアポリシーを設定します。

3. 変更を適用するには、 **InformationBarrierPoliciesApplication**コマンドレットを使用します。

    文`Start-InformationBarrierPoliciesApplication`

    組織の変更がユーザーごとに適用されます。 組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。 (一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。

この時点で、1つまたは複数の情報バリアポリシーが非アクティブ状態に設定されます。 ここから、次のいずれかの操作を実行できます。
- そのまま保持する (非アクティブな状態に設定されたポリシーはユーザーに影響しません)
- [ポリシーを編集する](#edit-a-policy) 
- [ポリシーを削除する](#remove-a-policy)

## <a name="example-contosos-departments-segments-and-policies"></a>例: Contoso 社の部署、セグメント、ポリシー

組織がセグメントとポリシーを定義する方法を確認するには、次の例を参照してください。

### <a name="contosos-departments-and-plan"></a>Contoso 社の部門と計画

Contoso には、人事、営業、マーケティング、研究、製造の5つの部門があります。 業界の規制に準拠するために、一部の部署のユーザーは、次の表に示すように、他の部署とは通信することは想定されていません。

|化  |会話可能  |会話できません  |
|---------|---------|---------|
|HR     |すべてのユーザー         |(制限なし)         |
|営業     |人事、マーケティング、製造         |リサーチ         |
|マーケティング     |すべてのユーザー         |(制限なし)         |
|リサーチ     |人事、マーケティング、製造        |営業     |
|製造 |人事、マーケティング |人事またはマーケティング以外のすべてのユーザー |

この点を考慮して、Contoso 社の計画には3つの情報バリアポリシーが含まれています。

1. セールスが研究との通信を禁止するように設計されたポリシー (および研究からのセールスとの通信を禁止する別のポリシー)
2. 製造に HR および Marketing のみと通信できるように設計されたポリシー 

人事またはマーケティングのポリシーを定義する必要はありません。

### <a name="contosos-defined-segments"></a>Contoso 社が定義したセグメント

Contoso 社は、次のように、Azure Active Directory の Department 属性を使用してセグメントを定義します。

|部署  |セグメント定義  |
|---------|---------|
|HR     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|営業     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|マーケティング     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|リサーチ     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|製造     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

セグメントが定義されていると、Contoso はポリシーの定義に進みます。 

### <a name="contosos-information-barrier-policies"></a>Contoso 社の情報バリアポリシー

Contoso 社では、次の表に示す3つのポリシーを定義しています。

|ポリシー  |ポリシー定義  |
|---------|---------|
|ポリシー 1: Sales がリサーチと通信できないようにする     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> この例では、情報バリアポリシーを*Sales Research*と呼びます。 このポリシーがアクティブで適用されている場合は、営業部門のユーザーが Research セグメントのユーザーと通信できないようにするのに役立ちます。 これは一ウェイのポリシーです。研究からセールスへのコミュニケーションが妨げられることはありません。 そのためには、ポリシー2が必要です。      |
|ポリシー 2: リサーチがセールスと通信できないようにする     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> この例では、情報バリアポリシーを*Research Sales*と呼びます。 このポリシーがアクティブで適用されている場合は、リサーチセグメントにあるユーザーが営業セグメント内のユーザーと通信できないようにするのに役立ちます。       |
|ポリシー 3: 製造に HR と Marketing のみが通信できるようにする     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing" -State Inactive` <p>この例では、情報バリアポリシーを*製造-HRMarketing*と呼びます。 このポリシーがアクティブで適用されている場合、製造は人事およびマーケティングとのみ通信できます。 人事およびマーケティングは、他のセグメントとの通信に制限されていないことに注意してください。 |

セグメントとポリシーが定義されているので、Contoso は**InformationBarrierPoliciesApplication**コマンドレットを実行してポリシーを適用します。 

この処理が完了すると、Contoso は法律および業界の要件に準拠します。

## <a name="related-articles"></a>関連記事

[情報障壁の概要を理解する](information-barriers.md)

[Microsoft Teams の情報障壁の詳細を知る](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[情報バリアポリシーの属性 (プレビュー)](information-barriers-attributes.md)

[情報障壁のトラブルシューティング (プレビュー)](information-barriers-troubleshooting.md)
