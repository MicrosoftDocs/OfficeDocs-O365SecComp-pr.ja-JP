---
title: 情報の障壁をトラブルシューティングする
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
description: この記事は、情報の障壁をトラブルシューティングするためのガイドとして使用してください。
ms.openlocfilehash: b88f97cd872d4ea3b95bfac049f47cd71dfb2cb2
ms.sourcegitcommit: c603a07d24c4c764bdcf13f9354b3b4b7a76f656
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2019
ms.locfileid: "35131351"
---
# <a name="troubleshooting-information-barriers-preview"></a>情報障壁のトラブルシューティング (プレビュー)

[情報障壁 (プレビュー)](information-barriers.md)は、組織が法律上の要件や業界の規制に準拠していることを維持するのに役立ちます。 たとえば、情報バリアを使用すると、特定のユーザーグループ間の通信を制限して、利息やその他の問題の競合を回避できます。 (情報の障壁を設定する方法の詳細については、「 [Define policies for information バリア (Preview)](information-barriers-policies.md)」を参照してください)。

情報の障壁が設定された後に予期しない問題が発生した場合は、それらの問題を解決するために実行できるいくつかの手順があります。 この記事をガイドとして使用します。


## <a name="before-you-begin"></a>開始する前に

この記事で説明されているタスクを実行するには、次のいずれかのような適切な役割が割り当てられている必要があります。
- Microsoft 365 エンタープライズグローバル管理者
- Office 365 グローバル管理者
- コンプライアンス管理者
- IB コンプライアンス管理 (新しい役割)

情報障壁の前提条件の詳細については、「[必須コンポーネント (情報バリアポリシー)](information-barriers-policies.md#prerequisites)」を参照してください。

[Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)するようにしてください。

## <a name="issue-communications-are-still-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>問題: Microsoft Teams でブロックする必要があるユーザー間でも、コミュニケーションが可能

この場合、情報バリアは定義、アクティブ、および適用されますが、相互に通信できないようにする必要があるユーザーは、Microsoft Teams でも利用できます。

### <a name="what-to-do"></a>行うこと

該当するユーザーが情報バリアポリシーに含まれていることを確認します。 Identity パラメーターを使用して**InformationBarrierRecipientStatus**コマンドレットを使用します。

文`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` 

名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。 

例: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` 

この例では、Office 365 の2つのユーザーアカウント ( *Megan*の場合は*Meガント b* 、 *Alex*の場合は*alexw* ) を参照しています。 

(1 人のユーザーに対してこのコマンドレットを`Get-InformationBarrierRecipientStatus -Identity <value>`使用することもできます)。このコマンドレットは、属性値、適用されている情報バリアポリシーなど、ユーザーに関する情報を返します。


|結果  |次のステップ  |
|---------|---------|
|選択したユーザーのセグメントが表示されません     |次のいずれかを実行します。<br/>-Azure Active Directory でユーザープロファイルを編集して、ユーザーを既存のセグメントに割り当てる<br/>-[情報の障壁に対してサポートされている属性](information-barriers-attributes.md)を使用してセグメントを定義する         |
|セグメントは表示されますが、これらのセグメントに情報バリアポリシーが割り当てられていません     |次のいずれかを実行します。<br/>- 対象のセグメントごとに[情報バリアポリシーを定義する](information-barriers-policies.md#part-2-define-information-barrier-policies)<br/>- [情報バリアポリシーを編集](information-barriers-policies.md#edit-a-policy)して、適切なセグメントに割り当てる         |
|セグメントがリストされ、それぞれが情報バリアポリシーに含まれています。     |-コマンドレット`Get-InformationBarrierPolicy`を実行して、情報バリアポリシーがアクティブであることを確認します。<br/>- `Get-InformationBarrierPoliciesApplicationStatus`コマンドレットを実行してポリシーが適用されていることを確認する<br/>-すべての`Start-InformationBarrierPoliciesApplication`アクティブ情報バリアポリシーを適用するには、コマンドレットを実行します。          |


## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a>問題: ユーザーが予期せず Microsoft Teams での通信をブロックされている 

この場合、ユーザーは Microsoft Teams での予期しない問題を報告しています。 例:
- ユーザーが Microsoft Teams 内の他のユーザーとの間で検索や通信を行うことができません。
- ユーザーが Microsoft Teams で別のユーザーを表示または選択できません。
- ユーザーは別のユーザーを表示できますが、Microsoft Teams 内の他のユーザーに対してメッセージを選択したり、送信したりすることはできません。

### <a name="what-to-do"></a>行うこと

1. ユーザーが情報バリアポリシーの影響を受けているかどうかを判断します。 これを行うには、Identity パラメーターを指定して**InformationBarrierRecipientStatus**コマンドレットを使用します。 

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

    セグメントの詳細を確認します。 必要に応じて、[セグメントを編集](information-barriers-policies.md#edit-a-segment)してから、 `Start-InformationBarrierPoliciesApplication`コマンドレットを再度使用します。

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
    |**失敗**     |アプリケーションに障害が発生した場合は、監査ログを確認します。 また、セグメントとポリシーも確認してください。 複数のセグメントに割り当てられているユーザーはいますか? セグメントに複数の poliicy が割り当てられているかどうか。 必要に応じて、[セグメントを編集](information-barriers-policies.md#edit-a-segment)するか、または[ポリシーを編集](information-barriers-policies.md#edit-a-policy)してから、 **InformationBarrierPoliciesApplication**コマンドレットを再度実行します。  |
    |**処理中**     |アプリケーションがまだ進行中の場合は、完了するのに時間を確保します。 数日経過した場合は、監査ログを収集し、サポートに連絡してください。 |

## <a name="related-topics"></a>関連項目

[Microsoft Teams の情報障壁に関するポリシーを定義する (プレビュー)](information-barriers-policies.md)

[情報バリア (プレビュー)](information-barriers.md)



