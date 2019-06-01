---
title: 情報の障壁をトラブルシューティングする
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: この記事は、情報の障壁をトラブルシューティングするためのガイドとして使用してください。
ms.openlocfilehash: b37585469ec8bb299b7976f8a330f4c6b29e3f95
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668317"
---
# <a name="troubleshooting-information-barriers-preview"></a>情報障壁のトラブルシューティング (プレビュー)

情報バリアは、組織が法的な要件や業界の規制に準拠していることを支援します。 たとえば、情報バリアを使用すると、特定のユーザーグループ間の通信を制限して、利息やその他の問題の競合を回避できます。 詳細については、「[情報の障壁 (プレビュー)](information-barriers.md)」を参照してください。

この記事では、情報の障壁に関する質問に回答したり、発生する可能性のある問題を解決したりするために使用できるガイダンスを提供します。  

## <a name="before-you-begin"></a>開始する前に

この記事で説明されているタスクを実行するには、次のいずれかのような適切な役割が割り当てられている必要があります。
- Microsoft 365 エンタープライズグローバル管理者
- Office 365 グローバル管理者
- コンプライアンス管理者
- IB コンプライアンス管理 (新しい役割)

役割とアクセス許可の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

情報障壁の前提条件の詳細については、「[必須コンポーネント (情報バリアポリシー)](information-barriers-policies.md#prerequisites)」を参照してください。

また、 [Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)するようにしてください。

## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a>問題: ユーザーが予期せず Microsoft Teams での通信をブロックされている 

この場合、ユーザーは Microsoft Teams での予期しない問題を報告しています。 例:
- ユーザーが Microsoft Teams 内の他のユーザーとの間で検索や通信を行うことができません。
- ユーザーが Microsoft Teams で別のユーザーを表示または選択できません。
- ユーザーは、Microsoft Teams の他のユーザーにメッセージを表示することはできますが、メッセージを送信することはできません。

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

1. Policy application コマンドレットを実行すると、組織内のすべてのアカウントについて、情報バリアポリシーがユーザーごとに適用 (または削除) されることに注意してください。 ユーザー数が多い場合は、処理に時間がかかります。 (一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。 

2. 状態を確認するには、 **InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。

    文`Get-InformationBarrierPoliciesApplicationStatus`

    すべての情報バリアポリシーアプリケーションの状態を表示するには、を使用します。`Get-InformationBarrierPoliciesApplicationStatus -All $true`

    これにより、ポリシーアプリケーションの完了、失敗、進行中のいずれかに関する情報が表示されます。

3. 手順2の結果に応じて、次のいずれかの手順を実行します。

    - アプリケーションが開始されておらず、 **InformationBarrierPoliciesApplication**コマンドレットが実行されてから45分以上経過している場合は、監査ログを確認してポリシー定義にエラーがないかどうか、またはその他の理由でアプリケーションが開始されていません。

    - アプリケーションに障害が発生した場合は、セグメントとポリシーを確認してください。 必要に応じて、[セグメントを編集](information-barriers-policies.md#edit-a-segment)するか、または[ポリシーを編集](information-barriers-policies.md#edit-a-policy)してから、 **InformationBarrierPoliciesApplication**コマンドレットを再度実行します。

    - アプリケーションがまだ進行中の場合は、完了するのに時間を確保します。 数日かかる場合は、サポートにお問い合わせください。

## <a name="related-topics"></a>関連項目

[Microsoft Teams の情報障壁に関するポリシーを定義する (プレビュー)](information-barriers-policies.md)

[情報バリア (プレビュー)](information-barriers.md)



