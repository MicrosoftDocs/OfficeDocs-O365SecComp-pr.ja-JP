---
title: 情報の障壁をトラブルシューティングする
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/24/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: この記事は、情報の障壁をトラブルシューティングするためのガイドとして使用してください。
ms.openlocfilehash: e8750358aaa7788c85f0ab656b30f5b5149d898c
ms.sourcegitcommit: 044003455eb36071806c9f008ac631d54c64dde6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2019
ms.locfileid: "35199515"
---
# <a name="troubleshooting-information-barriers-preview"></a>情報障壁のトラブルシューティング (プレビュー)

[情報障壁 (プレビュー)](information-barriers.md)は、組織が法律上の要件や業界の規制に準拠していることを維持するのに役立ちます。 たとえば、情報バリアを使用すると、特定のユーザーグループ間の通信を制限して、利息やその他の問題の競合を回避できます。 (情報の障壁を設定する方法の詳細については、「 [Define policies for information バリア (Preview)](information-barriers-policies.md)」を参照してください)。

情報の障壁が設定された後に予期しない問題が発生した場合は、それらの問題を解決するために実行できるいくつかの手順があります。 この記事をガイドとして使用します。

> [!IMPORTANT]
> この記事で説明されているタスクを実行するには、次のいずれかのような適切な役割が割り当てられている必要があります。<br/>-Microsoft 365 エンタープライズグローバル管理者<br/>-Office 365 グローバル管理者<br/>-コンプライアンス管理者<br/>-IB コンプライアンス管理 (新しい役割)<p>情報障壁の前提条件の詳細については、「[必須コンポーネント (情報バリアポリシー)](information-barriers-policies.md#prerequisites)」を参照してください。<p>[Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)するようにしてください。

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>問題: Microsoft Teams でブロックする必要があるユーザー間で通信が許可されている

この場合、情報の障壁が定義され、アクティブ化されており、適用されていますが、相互に通信できないようにする必要があるユーザーは、Microsoft Teams で何らかの方法で行うことができます。

### <a name="what-to-do"></a>行うこと

該当するユーザーが情報バリアポリシーに含まれていることを確認します。 

1. Identity パラメーターを使用して**InformationBarrierRecipientStatus**コマンドレットを使用します。

    文`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` 

    名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 

    例: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` 

    この例では、Office 365 の2つのユーザーアカウント ( *Megan*の場合は*Meガント b* 、 *Alex*の場合は*alexw* ) を参照しています。 
    
    > [!TIP]
    > 1人のユーザーに対してこのコマンドレットを使用することもできます。`Get-InformationBarrierRecipientStatus -Identity <value>`
    
2. 結果を確認します。 **InformationBarrierRecipientStatus**コマンドレットでは、属性値、適用されている情報バリアポリシーなど、ユーザーに関する情報を返します。 

    結果を確認し、次の表に示すように、次の手順を実行します。
    
    |結果  |次のステップ  |
    |---------|---------|
    |選択したユーザーのセグメントが表示されません     |次のいずれかを実行します。<br/>-Azure Active Directory でユーザープロファイルを編集して、ユーザーを既存のセグメントに割り当てます。 (「 [Office 365 PowerShell を使用してユーザーアカウントのプロパティを構成する」を](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)参照してください)。<br/>-[情報バリアに対してサポートされている属性](information-barriers-attributes.md)を使用してセグメントを定義します。 次に、[新しいポリシーを定義](information-barriers-policies.md#part-2-define-information-barrier-policies)するか、[既存のポリシーを編集](information-barriers-edit-segments-policies.md.md#edit-a-policy)してそのセグメントを含めます。  |
    |セグメントは表示されますが、これらのセグメントに情報バリアポリシーが割り当てられていません     |次のいずれかを実行します。<br/>- 対象のセグメントごとに[新しい情報バリアポリシーを定義する](information-barriers-policies.md#part-2-define-information-barrier-policies)<br/>- [既存の情報バリアポリシーを編集](information-barriers-edit-segments-policies.md.md#edit-a-policy)して正しいセグメントに割り当てる         |
    |セグメントがリストされ、それぞれが情報バリアポリシーに含まれています。     |-コマンドレット`Get-InformationBarrierPolicy`を実行して、情報バリアポリシーがアクティブであることを確認します。<br/>- `Get-InformationBarrierPoliciesApplicationStatus`コマンドレットを実行してポリシーが適用されていることを確認する<br/>-すべての`Start-InformationBarrierPoliciesApplication`アクティブ情報バリアポリシーを適用するには、コマンドレットを実行します。          |
    

## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a>問題: ユーザーが予期せず Microsoft Teams での通信をブロックされている 

この場合、ユーザーは、Microsoft Teams の他のユーザーとの間で予期しない問題を報告しています。 例:
- ユーザーが Microsoft Teams で別のユーザーを見つけることができません。
- ユーザーが Microsoft Teams で別のユーザーを選択することはできません。
- ユーザーは別のユーザーを表示できますが、Microsoft Teams 内の他のユーザーに対してメッセージを選択したり、送信したりすることはできません。
- ユーザーは別のユーザーを表示して選択できますが、Microsoft Teams でそのユーザーと通信することはできません。

### <a name="what-to-do"></a>行うこと

ユーザーが情報バリアポリシーの影響を受けているかどうかを判断します。

1. Identity パラメーターを指定して**InformationBarrierRecipientStatus**コマンドレットを使用します。 

    構文は、`Get-InformationBarrierRecipientStatus -Identity`

    名前、エイリアス、識別名 (DN)、標準 DN、電子メールアドレス、GUID など、各受信者を一意に識別する任意の id 値を使用できます。

    例: `Get-InformationBarrierRecipientStatus -Identity meganb`

    この例では、Identity パラメーターに alias (*meガント b*) を使用しています。 このコマンドレットは、ユーザーが情報バリアポリシーの影響を受けているかどうかを示す情報を返します。 (* ExoPolicyId: \<GUID> を検索します。)

    ユーザーが情報バリアポリシーに含まれていない場合は、サポートにお問い合わせください。 それ以外の場合は、次の手順に進んでください。

2. 情報バリアポリシーに含まれるセグメントを確認します。 これを行うには、 `Get-InformationBarrierPolicy` Identity パラメーターを指定したコマンドレットを使用します。 前の手順で受信したポリシー GUID (ExoPolicyId) などの詳細を identity 値として使用します。

    例: `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`

    この例では、ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*を持つ情報バリアポリシーに関する詳細情報を取得しています。
    
    コマンドレットを実行した後、結果で**AssignedSegment**、 **SegmentsAllowed**、および**SegmentsBlocked**の値を検索します。

    例: `Get-InformationBarrierPolicy`コマンドレットを実行した後、結果の一覧で次のように表示されています。

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    この場合、情報バリアポリシーが [営業] および [リサーチ] セグメントにあるユーザーに影響を与えることがわかります。 この場合、営業担当者は研究中の人々とコミュニケーションすることができません。 これが正しいように思われる場合は、情報バリアが期待どおりに機能しています。 それ以外の場合は、次の手順に進みます。

4. セグメントが正しく定義されていることを確認してください。 これを行うには、 `Get-OrganizationSegment`コマンドレットを使用して、結果の一覧を確認します。 

    特定のセグメントの詳細を表示するには`Get-OrganizationSegment` 、Identity パラメーターを指定してコマンドレットを使用します。 

    例: `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`

    この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*を持つセグメントについての情報を取得しています。

    セグメントの詳細を確認します。 必要に応じて、[セグメントを編集](information-barriers-edit-segments-policies.md.md#edit-a-segment)してから、 `Start-InformationBarrierPoliciesApplication`コマンドレットを再度使用します。

    情報バリアポリシーに問題がある場合は、サポートにお問い合わせください。
    
## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>問題: 情報バリアアプリケーションプロセスで時間がかかりすぎています

**InformationBarrierPoliciesApplication**コマンドレットを実行した後、プロセスが完了するまでに長い時間がかかります。

### <a name="what-to-do"></a>行うこと

Policy application コマンドレットを実行すると、組織内のすべてのアカウントについて、情報バリアポリシーがユーザーごとに適用 (または削除) されることに注意してください。 ユーザー数が多い場合は、処理に時間がかかります。 (一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。

1. 最新のポリシーアプリケーションの状態を確認するには、 **InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。

    文`Get-InformationBarrierPoliciesApplicationStatus`

    (*すべて*の情報バリアポリシーアプリケーションの状態を表示するには、次のコマンドレットを使用します。<br/>
    `Get-InformationBarrierPoliciesApplicationStatus -All $true`)

    これにより、ポリシーアプリケーションの完了、失敗、進行中のいずれかに関する情報が表示されます。

2. 前の手順の結果に応じて、次のいずれかの手順を実行します。
  
    |状態  |次の手順  |
    |---------|---------|
    |**未開始**     |**InformationBarrierPoliciesApplication**コマンドレットが実行されてから45分以上経過している場合は、監査ログを調べて、ポリシー定義にエラーがないかどうか、またはアプリケーションが開始されていない理由を確認してください。 |
    |**失敗**     |アプリケーションに障害が発生した場合は、監査ログを確認します。 また、セグメントとポリシーも確認してください。 複数のセグメントに割り当てられているユーザーはいますか? セグメントに複数の poliicy が割り当てられているかどうか。 必要に応じて、[セグメントを編集](information-barriers-edit-segments-policies.md.md#edit-a-segment)するか、または[ポリシーを編集](information-barriers-edit-segments-policies.md.md#edit-a-policy)してから、 **InformationBarrierPoliciesApplication**コマンドレットを再度実行します。  |
    |**処理中**     |アプリケーションがまだ進行中の場合は、完了するのに時間を確保します。 数日経過した場合は、監査ログを収集し、サポートに連絡してください。 |

## <a name="related-topics"></a>関連項目

[Microsoft Teams の情報障壁に関するポリシーを定義する (プレビュー)](information-barriers-policies.md)

[情報バリア (プレビュー)](information-barriers.md)



